# Read data from Kinesis Data Streams using Amazon Redshift

A technology company currently uses Amazon Kinesis Data Streams to collect log data in real time. The company wants to use Amazon Redshift for downstream real-time queries and to enrich the log data.

**Which solution will ingest data into Amazon Redshift with the LEAST operational overhead?**

**Response:**

Use Amazon Redshift streaming ingestion from Kinesis Data Streams and to present data as a materialized view

### Documentation quote:
```
Amazon Redshift supports streaming ingestion from Amazon Kinesis Data Streams.

The Amazon Redshift streaming ingestion feature provides low-latency, high-speed ingestion of streaming data
from Amazon Kinesis Data Streams into an Amazon Redshift materialized view. 
```

Source: https://docs.aws.amazon.com/streams/latest/dev/using-other-services-redshift.html
