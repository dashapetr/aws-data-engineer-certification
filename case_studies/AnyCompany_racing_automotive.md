# Meet AnyCompany Racing Automotive

AnyCompany Racing Automotive (ACRA) is a global racing organization that hosts races in multiple geographical locations. ACRA needs to replicate its 400 TB video archive to an offsite location. However, this video content must remain accessible locally and with low latency. ACRA doesn't want to invest in another data center for its offsite requirement. ACRA will need to replicate additional video content over time.

## Migration

ACRA wants to replicate its 400 TB video archive to AWS. ACRA qualifies as a large-scale migration effort and requires a plan to move its data to Amazon S3.

## Business goal and objectives

#### What business goal or objective is driving the data migration plan?
Managing another data center for our offsite requirements is cost-prohibitive. Co-location options don't meet our goal for the same reason—cost. We have two goals at play. We need to replicate this data offsite for backup and recovery purposes. Additionally, our end users depend on low latency access to the data, so the content will need to be accessible in our data center. We have plans to create data lakes for our other data sets, but currently, our focus is on our video content.

#### Are you prioritizing migration speed or cost?
Cost. We need to only spend as much as we consume with our data.

#### Is this a one-time migration or a recurring data transfer?
This project calls for an initial replication of 400 TB, then subsequent replication as new content is created.

#### What events or milestones are driving your migration schedule?
Hardware contracts are ending soon. We'd like to ensure that we have enough time to thoroughly test our backup and disaster recovery plans before that time.

## On-premise discovery

#### What are the details of the data to migrate?
ACRA has 400 TBs and growing of video footage located in one data center. There are approximately 80,000 files. The amount of data grows by about 4 TB each day. Data integrity is key, so we need to validate each file in this migration. Although the data is raw video footage, our end users will need to be able to quickly retrieve it whenever needed.

#### How is the data accessed?
End users access the data on a network-attached storage (NAS) device. The NAS shares out the content using the NFS sharing protocol.

#### What are your site requirements for each service?
We need to maintain local access to the data.

#### What type of internet connectivity and available bandwidth do you have?
We have a 1 Gbps internet connection for the data center. We sometimes reach bandwidth saturation. However, this project is a priority for us, so the amount of bandwidth is flexible. Additionally, we have an AWS Direct Connect connection to the eu-west-2 Region.

#### Do you have a Virtual Machine infrastructure available to deploy a virtual appliance for your data migration?
Yes, we do run a virtual infrastructure in our data center and have additional capacity.

#### When does the data need to be available after the data is transferred?
As quickly as possible.

#### Have you identified the personnel who will be in charge of the network and storage components for the migration?
Yes, we have both storage and IT staff available for this migration project. We also have staff in the data center that can help with the migration. The storage and IT staff have some familiarity with AWS migration and storage services. They plan to run a pilot, and manage the technical tasks of the migration plan.

## AWS destination

#### What is the AWS destination for your data?
Our destination is Amazon S3.

#### Where is the AWS destination? (For example, what is the target Region?)
Our data centers are located in the United Kingdom. We intend to use the eu-west-2 (London) Region, as that Region fits our purpose for this project.

## Additional details

#### What is your cutover window to start and complete the migration?
We intend for the migration to happen over a 3-month period. After all the data is in AWS, we will retire our current backup infrastructure. We'd like to have the data migrated into AWS by the end of 3 months, then have another 3 months to run recoverability tests.

## With this additional detail, what AWS services are a good fit for the ACRA migration and local data access? (Choose TWO responses.)

- [ ] AWS DataSync
- [ ] Amazon S3 File Gateway
- [ ] AWS Snowball Edge
- [ ] AWS Transfer Family

## Solution

- [x] AWS DataSync
- [x] Amazon S3 File Gateway
- [ ] AWS Snowball Edge
- [ ] AWS Transfer Family

ACRA replicates up to 4 TB for each day to Amazon S3 using AWS DataSync. The racing organization uses AWS Storage Gateway to provide standard file access to data in Amazon S3 with a local cache for low latency access.

Source: https://explore.skillbuilder.aws/learn/course/15545/play/76124/planning-large-scale-data-migrations-to-aws
