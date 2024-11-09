# Why is the AWS Glue crawler running for a long time?

**Steps to approach:**

## 1. Do you need a crawler?

Unless you need to create a table in the AWS Glue Data Catalog and use the table in an extract, transform, and load (ETL) job or a downstream service, such as Amazon Athena, you don't need to run a crawler. 
For ETL jobs, you can use [from_options](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-crawler-pyspark-extensions-dynamic-frame-reader.html#aws-glue-api-crawler-pyspark-extensions-dynamic-frame-reader-from_options) to read the data directly from the data store and use the transformations on the DynamicFrame. When you do this, you don't need a crawler in your ETL pipeline.

## 2. Review if you add a lot of files or folders to your data store between crawler runs

During the first crawler run, the crawler reads the first megabyte of each file to infer the schema. During subsequent crawler runs, the crawler lists files in the target, including files that were crawled during the first run, and reads the first megabyte of new files. 
The crawler doesn't read files that were read in the previous crawler run. This means that subsequent crawler runs are often faster. This is due to the [incremental crawl feature](https://docs.aws.amazon.com/glue/latest/dg/incremental-crawls.html), if activated. 
With this option, crawler only reads new data in subsequent crawl runs. However, when you add a lot of files or folders to your data store between crawler runs, the run time increases each time.

## 3. Are your files compressed?

Compressed files take longer to crawl. That's because the crawler must download the file and decompress it before reading the first megabyte or listing the file.

## 4. Use an exclude pattern

An exclude pattern tells the crawler to skip certain files or paths. 
Exclude patterns reduce the number of files that the crawler must list, making the crawler run faster. 
For example, use an exclude pattern to exclude meta files and files that have already been crawled. For more information, including examples of exclude patterns, see [Include and exclude patterns](https://docs.aws.amazon.com/glue/latest/dg/define-crawler.html#crawler-data-stores-exclude).

## 5. Use the sample size feature

The AWS Glue crawler supports the [sample size feature](https://docs.aws.amazon.com/glue/latest/dg/define-crawler.html). With this feature, you can specify the number of files in each leaf folder to be crawled when crawling sample files in a dataset. 
When this feature is turned on, the crawler randomly selects some files in each leaf folder to crawl instead of crawling all the files in the dataset. If you have previous knowledge about your data formats and know that schemas in your folders do not change, then use the sampling crawler. Turning on this feature significantly reduces the crawler run time.

## 6. Run multiple crawlers

Instead of running one crawler on the entire data store, consider running multiple crawlers. 
Running multiple crawlers for a short amount of time is better than running one crawler for a long time. For example, assume that you are partitioning your data by year, and that each partition contains a large amount of data. If you run a different crawler on each partition (each year), the crawlers complete faster.

## 7. Combine smaller files to create larger ones

It takes more time to crawl a large number of small files than a small number of large files. That's because the crawler must list each file and must read the first megabyte of each new file.

Source: https://repost.aws/knowledge-center/long-running-glue-crawler
