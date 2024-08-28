# Improving Amazon Redshift Spectrum query performance

A company is building an analytics solution. The solution uses Amazon S3 for data lake storage and Amazon Redshift for a data warehouse. The company wants to use Amazon Redshift Spectrum to query the data that is in Amazon S3.

**Which actions will provide the FASTEST queries?**

**Response:**

1. Use a columnar storage file format.
2. Partition the data based on the most common query predicates.

## Documentation quote:
```
Use Apache Parquet formatted data files.
Parquet stores data in a columnar format, so Redshift Spectrum can eliminate unneeded columns from the scan.
When data is in text-file format, Redshift Spectrum needs to scan the entire file.

Use multiple files to optimize for parallel processing.
Keep your file sizes larger than 64 MB.
Avoid data size skew by keeping files about the same size.

Use partitions to limit the data that is scanned.
Partition your data based on your most common query predicates, then prune partitions by filtering on partition columns. 
```

Source: https://docs.aws.amazon.com/redshift/latest/dg/c-spectrum-external-performance.html
