# Adding an AWS Glue crawler

A company stores daily records of the financial performance of investment portfolios in .csv format in an Amazon S3 bucket. A data engineer uses AWS Glue crawlers to crawl the S3 data.
The data engineer must make the S3 data accessible daily in the AWS Glue Data Catalog.

**Which solution will meet these requirements?**

**Response:**

1. Create an IAM role that includes the AWSGlueServiceRole policy.
2. Associate the role with the crawler.
3. Specify the S3 bucket path of the source data as the crawler's data store.
4. Create a daily schedule to run the crawler.
5. Specify a database name for the output.


Source: https://docs.aws.amazon.com/glue/latest/dg/tutorial-add-crawler.html
