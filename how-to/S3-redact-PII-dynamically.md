# Using Amazon S3 object Lambda access points for personally identifiable information (PII)

A company has multiple applications that use datasets that are stored in an Amazon S3 bucket. The company has an ecommerce application that generates a dataset that contains personally identifiable information (PII). The company has an internal analytics application that does not require access to the PII.
To comply with regulations, the company must not share PII unnecessarily. A data engineer needs to implement a solution that with redact PII dynamically, based on the needs of each application that accesses the dataset.

**Which solution will meet the requirements with the LEAST operational overhead?**

**Response:**

1.  Create an S3 Object Lambda endpoint.
2.  Use the S3 Object Lambda endpoint to read data from the S3 bucket.
3.  Implement redaction logic within an S3 Object Lambda function to dynamically redact PII based on the needs of each application that accesses the data.

### Documentation quote:
```
Use Amazon S3 Object Lambda Access Points for personally identifiable information (PII)
to configure how documents are retrieved from your Amazon S3 bucket.

You can control access to documents that contain PII and redact PII from documents.
```

Source: https://docs.aws.amazon.com/comprehend/latest/dg/using-access-points.html
