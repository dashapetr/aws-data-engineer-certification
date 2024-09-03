# Error: A job is reprocessing data when job bookmarks are enabled

A data engineer needs to debug an AWS Glue job that reads from Amazon S3 and writes to Amazon Redshift. The data engineer enabled the bookmark feature for the AWS Glue job.
The data engineer has set the maximum concurrency for the AWS Glue job to 1.

The AWS Glue job is successfully writing the output to Amazon Redshift. However, the Amazon S3 files that were loaded during previous runs of the AWS Glue job are being reprocessed by subsequent runs.

**What is the likely reason the AWS Glue job is reprocessing the files?**

**Response:**

The AWS Glue job does not have a required commit statement.

### Documentation quote:
```
Missing Job Object
Ensure that your job run script ends with the following commit:

job.commit()

When you include this object, AWS Glue records the timestamp and path of the job run.
If you run the job again with the same path, AWS Glue processes only the new files.

If you don't include this object and job bookmarks are enabled,
the job reprocesses the already processed files along with the new files
and creates redundancy in the job's target data store.
```

Source: https://docs.aws.amazon.com/glue/latest/dg/glue-troubleshooting-errors.html#error-job-bookmarks-reprocess-data
