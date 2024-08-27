# Monitoring events for the Amazon Redshift Data API in Amazon EventBridge

A company loads transaction data for each day into Amazon Redshift tables at the end of each day. The company wants to have the ability to track which tables have been loaded and which tables still need to be loaded.
A data engineer wants to store the load statuses of Redshift tables in an Amazon DynamoDB table. The data engineer creates an AWS Lambda function to publish the details of the load statuses to DynamoDB.


**How should the data engineer invoke the Lambda function to write load statuses to the DynamoDB table?**

**Response:**

1. Use the Amazon Redshift Data API to publish an event to Amazon EventBridge.
2. Configure an EventBridge rule to invoke the Lambda function.


Documentation quote: 
```
You can monitor Data API events in EventBridge,
which delivers a stream of real-time data from your own applications,
software-as-a-service (SaaS) applications, and AWS services.

EventBridge routes that data to targets such as AWS Lambda and Amazon SNS.
```


Source: https://docs.aws.amazon.com/redshift/latest/mgmt/data-api-monitoring-events.html
