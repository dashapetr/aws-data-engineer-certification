# Streaming ingestion to a materialized view

A healthcare company uses Amazon Kinesis Data Streams to stream real-time health data from wearable devices, hospital equipment, and patient records.
A data engineer needs to find a solution to process the streaming data. The data engineer needs to store the data in an Amazon Redshift Serverless warehouse. The solution must support near real-time analytics of the streaming data and the previous day's data.

**Which solution will meet these requirements with the LEAST operational overhead?**

**Response:**

Use the streaming ingestion feature of Amazon Redshift.

### Documentation quote:
```
Streaming ingestion provides low-latency, high-speed data ingestion from Amazon Kinesis Data Streams
or Amazon Managed Streaming for Apache Kafka
to an Amazon Redshift provisioned or Amazon Redshift Serverless database.

The data lands in a Redshift materialized view that's configured for the purpose.
This results in fast access to external data.

Streaming ingestion lowers data-access time and reduces storage cost.

You can configure it for your Amazon Redshift cluster or for your Amazon Redshift Serverless workgroup,
using a small collection of SQL commands.
After it's set up, each materialized-view refresh can ingest hundreds of megabytes of data per second.
```

Source: https://docs.aws.amazon.com/redshift/latest/dg/materialized-view-streaming-ingestion.html
