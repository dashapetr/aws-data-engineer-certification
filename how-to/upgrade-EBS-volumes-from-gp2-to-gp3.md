# Migrate your Amazon EBS volumes from gp2 to gp3

A company is planning to upgrade its Amazon Elastic Block Store (Amazon EBS) General Purpose SSD storage from gp2 to gp3. The company wants to prevent any interruptions in its Amazon EC2 instances that will cause data loss during the migration to the upgraded storage.

**Which solution will meet these requirements with the LEAST operational overhead?**

**Response:**

1. Change the volume type of the existing gp2 volumes to gp3.
2. Enter new values for volume size, IOPS, and throughput.

### AWS Blog post quote:
```
1. Open the Amazon EC2 console.
2. Choose Volumes, select the volume to modify, and then choose Actions, Modify Volume.
3. The Modify Volume window displays the volume ID and the volume’s current configuration, including type, size, IOPS, and throughput.
Set new configuration values as follows:

 - To modify the type, choose gp3 for Volume Type.
 - To modify the size, enter a new value for Size.
 - To modify the IOPS, enter a new value for IOPS.
 - To modify the throughput, if the volume type is gp3, enter a new value for Throughput.
 - After you have finished changing the volume settings, choose Modify. When prompted for confirmation, choose Yes.
```

Source: https://aws.amazon.com/blogs/storage/migrate-your-amazon-ebs-volumes-from-gp2-to-gp3-and-save-up-to-20-on-costs/
