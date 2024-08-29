# Choose data distribution styles

A company uses an Amazon Redshift provisioned cluster as its database. The Redshift cluster has five reserved ra3.4xlarge nodes and uses key distribution.
A data engineer notices that one of the nodes frequently has a CPU load over 90%. SQL Queries that run on the node are queued. The other four nodes usually have a CPU load under 15% during daily operations.
The data engineer wants to maintain the current number of compute nodes. The data engineer also wants to balance the load more evenly across all five compute nodes.

**Which solution will meet these requirements?**

**Response:**

Change the distribution key to the table column that has the largest dimension.

### Documentation quote:
```
KEY distribution

The rows are distributed according to the values in one column.
The leader node places matching values on the same node slice.
If you distribute a pair of tables on the joining keys,
the leader node collocates the rows on the slices according to the values in the joining columns.
This way, matching values from the common columns are physically stored together.
```

Source: https://docs.aws.amazon.com/redshift/latest/dg/c_choosing_dist_sort.html
