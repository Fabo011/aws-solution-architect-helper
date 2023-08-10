# AWS Database Differences

## Aurora
Relational Database.
### Pro
- Aurora comes with Postgres and MySQL compatibility.
- Fully managed serverless database.
- Automated failover, failover priority. Less than 30 seconds failover.
- Automated AutoScaling.
- Master + up to 15 read replicas. 
- Automated encrypted backups which are stored in a S3.
- Multi-Master is possible, but only within availability zones, not regional.
- Aurora Global up to 16 READ replicas in each region.
- Aurora Machine Learning, ML using SageMaker

## Contra
- Costs 20% more than RDS databases.
- Multiple master replication only within a region, multiple region write data not possible.

## Use Cases
- High performance, scaleable, high available, managed relational database, compatable with Postgres and MySQL.
- WebApps, fast read and write.
- CMS platforms.
- Microservice architecture.


## DynamoDB
NoSQL database.<br>
DynamoDB is the only one global database in AWS which offers global tables.

### Pro
- Automatically replicate READ/Write data across multiple AWS regions.
- Fully managed, high availabilty serverless database.
- Low latency access due to regional replicas.
- Each regional replica is asynchronously updated. Maintain consistency.
- TTL, time to live functionality. Meaning, automatically delete items after expiry timestamp.
- Steaming processing, react in real time.
- Able to trigger Lambda functions.
- Fully automated on-demand backup, restore, and point-in-time recovery for data protection and archiving.
- DynamoDB DAX for read cache, low latency.
- Export, import to S3.
- AutoScaling
- Integrated IAM for security.

### Use Cases:
- Serverless architectures.
- Millions of requests per seconds.
- Multi regional architecture.  

## DocumentDB
NoSQL Database.<br>
Aurora is an AWS implementation of Postgres/MySQL and DocumentDB is the same for MongoDB.

### Pro
- AutoScaling.
- MongoDB compatibility.
- Replication accross three AZ.
- Fully managed, high availabilty serverless database.
- Continuous backups into an S3, automated snapshots.

### Contra 
- Multi reagion READ/Write replications not possible.

### Use Cases
- Million requests per second. 

## RSD
Relational databases.<br>
Managed Postgres, MySQL, Oracle, SQL Server, MariaDB databases.

### Pro
- AutoScaling capability.
- Multi AZ read replicas.
- Automated backups.
- Manual DB snapshots possible.
- RDS Custom to customize the underlying EC2 Instance only for Oracle & SQL Server.

### Contra
- Multi reagion READ/Write replications not possible.

## S3
The core service of AWS, a key/value store for objects.

### S3 Types
- S3 Standard: General-purpose storage for various data types like static websites, videos, pictures, and more.
- S3 Standard-IA (Infrequent Access): Cost-effective storage for infrequently accessed data, suitable for backups and disaster recovery.
- S3 One Zone-IA (Infrequent Access): Cost-effective infrequent access storage with data stored in a single availability zone for reduced redundancy.
- S3 Glacier (Instant Retrieval): Low-cost archival storage with quick retrieval times for data that may be needed more frequently.
- S3 Glacier Deep Archive: Extremely low-cost archival storage with longer retrieval times, suitable for data that is accessed very infrequently. Also called cold data.
- S3 Intelligent-Tiering: Automatically moves objects between frequent and infrequent access tiers based on changing usage patterns, optimizing costs.

### Pro
- Different tiers for data backups.
- Cheap data store of any kind of data.
- Able to trigger Lambda functions.
- Accessable by Lambda.
- Versioning of data in S3 possible.
- Ability to create different path, for example /photos, /private, /secure and grant specific or differnet policies to each path.
- Lifecycle rules: Manage things on S3 for example move data from S3 Standard to S3 Glacier or delete data which are older than 7 years. 
- Sync between S3 buckets in differnet regions possible via CLI.
- Batch operations: Encrypt un-encrypt objects etc.
- Event Notifications: Send events via EventBridge to over 18 AWS services like SNS, SQS, Lambda.
- S3 is accessable via roles, can also have policies and you can create an secret link to grant access via this links to other AWS users.
- Requester pays model. You can configure that the requester pay the network costs.

### Use Cases
- Deploy static websites, also possible to deploy React, Vuejs websites which have access to an API server.
- Use S3 as a backup database.
- Personal use to store pictures, videos or private backups.
- AWS using S3 for backup for other services like EBS snapshot, Aurora backups, DynamoDB backups, EFS backups etc.

## ElastiCache
ElastiCache is a database in RAM for high performance read.<br>
Redis- and Memcached-compatible service.

### Pro
- For frequently accessed data.
- Session management, store user session data.
- Attachable to multiple microservices.
- Speeds up database and application performance while caching database data etc.
- Compatible with RDS and Aurora.
- Redis for scaling, durability, automated backups to S3. You can also make a backup to the SSD.
- Memcached for multi-node partitioning, multi-threaded architecture.

### Contra
- No backup method for Memcached, but you can use Redis, just keep in mind.

### Use Cases
- In memory caching.
- Speeds up database and application performance.
- Data Analytics.

## Neptune
Graph database.

### Pro
- Fully managed.
- 3 AZ up to 15 read replicas.
- Fully managed.

### Use Cases
- Social Media apps.
- Knowledge graphs.
- Recommendation engines like e-commerce, streaming-provider.

## Keyspaces Apache Cassandra
NoSQL database. <br>
AWS Keyspaces.

### Pro
- Fully managed.
- AutoScaling.
- 3 AZ.
- Encrypted backups.

### Use Cases
- IoT devices info.
- Time series data

## QLDB



## Timestream

