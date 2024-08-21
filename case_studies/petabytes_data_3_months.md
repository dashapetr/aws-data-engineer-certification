# Moving petabytes of data in 3 months

AnyCompany Streaming Media (ASM) company needs to migrate over 3 PB of data to Amazon S3. ASM wants to decrease infrastructure costs for their large data set while providing a better streaming service to their customers. The project timetable is set for 3 months because existing data center and licensing contracts will expire by then.

## Business goal and objectives

#### What business goal or objective is driving the data migration plan?
Hosting petabytes of streaming content is expensive, and we at ASM want to reduce those costs. Reducing infrastructure and eliminating hardware and software licensing costs will help achieve this objective. Also, we want to provide a better quality streaming service to wherever our customers are at any time. Having our streaming catalogue in a data center limits our options.

#### Are you prioritizing migration speed or cost?
Speed. We need to move as quickly as we can.

#### Is this a one-time migration or a recurring data transfer?
This project calls for a one-time migration.

#### What is your cutover window to start and complete the migration?
As soon as the entire data set is available in AWS.

#### What events or milestones are driving your migration schedule?
Software licensing and data center contracts expire within four months. Extending current contracts is an expensive option we want to avoid.

## On-premises discovery

#### What are the details of the data to migrate?

ASM has over 3 PB of media archives in a data center. All of the media are video files that average around 21 GB for each file. The archives hold approximately 175,000 files. The files themselves in the archives don't change. We transcode the files and deliver the content to our customers. All the files are stored on volumes backed by storage area network (SAN) devices. The SAN devices serve out block volumes to our transcoding servers. We don't use any kind of local object storage.  

#### How is the data accessed?
The data is accessed through block volumes that are presented by SAN devices. The transcoding software accesses the files as if they were local drives attached to the server.

#### What are your site requirements for each service?
Not applicable.

#### What type of internet connectivity and available bandwidth do you have?
We have 5 Gbps internet connection for the data center that we use to push our content to our partner's content delivery network. Our bandwidth usage averages about 60 percent each day. We initially thought about setting up AWS Direct Connect, but we aren't sure if that's an option. We worry that setting up AWS Direct Connect and performing the migration may go beyond our project timeline.

#### Do you have a Virtual Machine infrastructure available to deploy a virtual appliance for your data migration?
Yes, we do run a virtual infrastructure in our data center and have additional capacity.

#### When does the data need to be available after the data is transferred?
As quickly as possible.

#### Have you identified the personnel who will be in charge of the network and storage components for the migration?
Yes, we have both storage and transcoding staff available for this migration project. We also have staff in the data center that can help with the migration.

## AWS destination

#### What is the AWS storage destination for your data?
Our destination is Amazon S3. We would like to use the Intelligent-Tiering option, as we believe it will give us the flexibility of being able to manage our media.

#### Where is the destination? (For example, what is the target Region)
Our data center is located in southern Germany. We intend to use the eu-central-1 Region as that Region fits our purpose for this project.



## Which AWS service would you recommend AnyCompany Streaming Media use for their large-scale data migration?

- [ ] AWS DataSync
- [ ] Amazon S3 File Gateway
- [ ] AWS Snowball Edge
- [ ] Both AWS DataSync and AWS Snowball Edge


Correct answer: 

- [ ] AWS DataSync
- [ ] Amazon S3 File Gateway
- [x] AWS Snowball Edge
- [ ] Both AWS DataSync and AWS Snowball Edge

## Solution:

Multiple Snowball Edge devices are the best choice for ASM. The devices don't need internet access, and ASM stated they have available staffing in the data center to connect the devices.


Based on information from the framework, several Snowball Edge Storage Optimized devices is the best approach to meet the three-month timeline. AWS DataSync could have been another option if there was available bandwidth. However, ASM stated that there are constraints on bandwidth availability. With AWS recommendations in place, ASM set up an infrastructure where four Snowball devices read from on-premises storage simultaneously. One engineer was present at the data center to manage the setup of the devices while other team members worked remotely to manage the logistics and file transfers. 

At any given time, 12 AWS Snowball Edge devices were in use, whether copying data on-site at the data center, uploading content to Amazon S3, or in transit. 


Source: https://explore.skillbuilder.aws/learn/course/15545/play/76124/planning-large-scale-data-migrations-to-aws
