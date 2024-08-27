# Configuring concurrency scaling queues

A company uses an Amazon Redshift cluster that runs on RA3 nodes. The company wants to scale read and write capacity to meet demand. A data engineer needs to identify a solution that will turn on concurrency scaling.

**Which solution will meet this requirement?**

--------------------------------

**Response:**

Turn on concurrency scaling at the workload management (WLM) queue level in the Redshift cluster.

--------------------------------
Documentation quote:
```
You route queries to concurrency scaling clusters
by enabling concurrency scaling in a workload manager (WLM) queue.

To turn on concurrency scaling for a queue, set the Concurrency Scaling mode value to auto.
```
-------------------------------
Source: https://docs.aws.amazon.com/redshift/latest/dg/concurrency-scaling-queues.html
