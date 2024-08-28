# Detect and process sensitive data

A data engineer must use AWS services to ingest a dataset into an Amazon S3 data lake. The data engineer profiles the dataset and discovers that the dataset contains personally identifiable information (PII). The data engineer must implement a solution to profile the dataset and obfuscate the PII.

**Which solution will meet this requirement with the LEAST operational effort?**

**Response:**

1. Use the Detect PII transform in AWS Glue Studio to identify the PII.
2. Obfuscate the PII.
3. Use an AWS Step Functions state machine to orchestrate a data pipeline to ingest the data into the S3 data lake.


Source: https://docs.aws.amazon.com/glue/latest/dg/detect-PII.html
