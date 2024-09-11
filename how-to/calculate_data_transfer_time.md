Suppose you want to take the least amount of time for your data migration with minimal disruption to your existing environment and workflow. AWS uses a data transfer formula to determine the length of time for an online transfer of any given amount of data.

```
(Terabytes * 8 bits per Byte)/(CIRCUIT gigabits per second * NETWORK_UTILIZATION
percent * 3600 seconds per hour * AVAILABLE_HOURS) = Number of Days 
```

If you have a 1 Gbps internet connection and 100 TB of data to migrate to AWS, the minimum time to complete an online transfer at about 80 percent network use is approximately 12 days.

```
(100,000,000,000,000 Bytes * 8 bits per byte) /(1,000,000,000 bps * 80 percent 
* 3600 seconds per hour * 24 hours per day) = 11.57 days 
```

This calculation assumes a full 24 hours for each day for the data migration to AWS. The 80 percent of network usage is an approximation to determine a theoretical number of days. You can modify the formula to your exact parameters. With the results you calculate, you can compare the theoretical amount of days to your project's timeline to determine whether an online or offline data transfer is right for you.

The following is a table that provides some guidance to determine if an online or offline data transfer will take the least amount of time.

### Large data migration – Time to transfer online

|       | 1 Gbps   | 2 Gbps  | 5 Gbps   | 10 Gbps  |
|-------|----------|---------|----------|----------|
|100 TB | 12 days  | 6 days  | 3 days   | 30 hours |
|500 TB | 58 days  |29 days  | 12 days  | 6 days   |
|5 PB   | 2 years  | 1 year  | 116 days | 58 days  |
|10 PB  | 3 years  |2 years  | 232 days | 116 days |


Comparatively, using a Snowball Edge device for an offline transfer takes about **25–30 days end-to-end for the majority of use cases**. For your large-scale data migration, you will want more than one device at a time at your data center.  

Source: https://explore.skillbuilder.aws/learn/course/15545/play/76124/planning-large-scale-data-migrations-to-aws  
