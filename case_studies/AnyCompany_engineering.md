# Meet AnyCompany Engineering

AnyCompany Engineering (ACE) is a software company that specializes in developing 3D design, engineering, and entertainment software. ACE maintains a large, on-premises storage array that hosts Oracle and SQL server database backups. Due to compliance requirements, the retention policy for the backups is several years. ACE doesn't want to upgrade the aging storage infrastructure to handle its current 700 TB and growing data set. They prefer to move to a managed, scalable, and reliable solution, specifically Amazon S3.

## Migration

ACE wants to migrate its 700 TB of database backups. ACE anticipates additional data transfers after the initial 700 TB migration, so prefers a robust solution to handle additional transfer tasks. ACE qualifies as a large-scale migration effort and requires a plan to move its data to Amazon S3.

## Business goal and objectives

#### What business goal or objective is driving the data migration plan?
ACE IT evaluated multiple options to ease the maintenance and management of the current storage system. One option was to upgrade the existing infrastructure to a newer version but that would still have an infrastructure to build and maintain. Instead, we prefer Amazon S3 because of cost, high durability, and availability. Also, we plan to use the lifecycle management capabilities for long-term archival storage.

#### Are you prioritizing migration speed or cost?
Cost. We need to meet compliance requirements with our database backups, which means long-term storage. We want to realize the financial benefit of the Amazon S3 Glacier storage classes.

#### Is this a one-time migration or a recurring data transfer?
This project calls for an initial migration of 700 TB, then subsequent migration of database backups.

#### What is your cutover window to start and complete the migration?
We haven't determined an exact time yet. The planning is still in an early stage.

#### What events or milestones are driving your migration schedule?
When we started exploring options, we had a storage capacity issue, as the data set then was 2.4 PB. However, as we conducted our analysis of the data, we tweaked our retention policy. The change in the policy allowed us to shrink the data set to 700 TB. Even still, we intend to move forward with this effort to migrate away from our current storage infrastructure.

## On-premise discovery

#### What are the details of the data to migration?

ACE has 700 TB and growing of Oracle RMAN and SQL Server database backups located in one data center. The data spans multiple racks and arrays. Data integrity is key, so we need to validate each file in this migration.  

#### How is the data accessed?
Backups occur regularly as defined by the backup policy to our NAS systems. We use the NFS file sharing protocol.

#### What are your site requirements for each service?
Not applicable.

#### Do you have a Virtual Machine infrastructure available to deploy a virtual appliance for your data migration?
Yes, we do run a virtual infrastructure in our data center and have additional capacity.

#### Have you identified the personnel who will be in charge of the network and storage components for the migration?
Yes, we have both storage and IT staff available for this migration project. We also have staff in the data center that can help with the migration. The storage and IT staff have some familiarity with AWS migration and storage services. They plan to run a pilot, and manage the technical tasks of the migration plan. They are prepared to write and test scripts for this migration project.

## AWS destination

#### What is the AWS destination for your data?
Our destination is Amazon S3.

#### Where is the AWS destination? (For example, what is the target Region?)
Our data center is located in the western United States. We intend to use the us-west-2 (Oregon) Region, as that Region fits our purpose for this project.

## Additional details

#### What type of internet connectivity and available bandwidth do you have?
We have a 2 Gbps internet connection for the data center. We don't ever reach bandwidth saturation. However, this project is a priority for us, so we could allocate 70 percent of the connection's bandwidth.  We do have production workloads that require internet connectivity, so we can't use the full 2 Gbps connection during business hours. 

#### When does the data need to be available after the data is transferred?
There is no rush for when the data becomes available to use, because the data is primarily backup data. We are interested in available options and how much time it would take with each one.

## With these additional details, what AWS service is a good fit for the ACE migration and subsequent transfer of data?

- [ ] AWS DataSync
- [ ] Amazon S3 File Gateway
- [ ] AWS Snowball Edge
- [ ] AWS Transfer Family

## Solution

- [x] AWS DataSync
- [ ] Amazon S3 File Gateway
- [ ] AWS Snowball Edge
- [ ] AWS Transfer Family

ACE migrated 700 TB of data to Amazon S3 using AWS DataSync. After several rounds of testing and configuring DataSync tasks to the project specifications, the total migration time was 2.5 months. The transfer task was fast, steady, and used 1.4 Gbps of bandwidth during the low peak usage hours at night. It yielded a data transfer rate of about 500 Gibibytes an hour.

ACE could have used about 10 AWS Snowball Edge devices for this migration, but the Snowball based migration plan included many more steps than using AWS DataSync. For example, the Snowball based plan called for creating and managing scripts to transfer data to the Snowball Edge devices and handling each Snowball Edge device in the data center. The AWS DataSync plan was straightforward and required less time to complete than the AWS Snowball Edge option.

Source: https://explore.skillbuilder.aws/learn/course/15545/play/76124/planning-large-scale-data-migrations-to-aws
