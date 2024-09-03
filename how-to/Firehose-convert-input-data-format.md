# Convert input data format in Amazon Data Firehose

A company plans to use Amazon Kinesis Data Firehose to store data in Amazon S3. The source data consists of 2 MB .csv files. The company must convert the .csv files to JSON format. The company must store the files in Apache Parquet format.

**Which solution will meet these requirements with the LEAST development effort?**

**Response:**

1. Use Kinesis Data Firehose to invoke an AWS Lambda function that transforms the .csv files to JSON.
2. Use Kinesis Data Firehose to store the files in Parquet format.


### Documentation quote:
```
Amazon Data Firehose can convert the format of your input data from JSON to Apache Parquet or Apache ORC before storing the data in Amazon S3.
Parquet and ORC are columnar data formats that save space and enable faster queries compared to row-oriented formats like JSON.

If you want to convert an input format other than JSON, such as comma-separated values (CSV) or structured text, you can use AWS Lambda to transform it to JSON first.
```

Source: https://docs.aws.amazon.com/firehose/latest/dev/record-format-conversion.html
