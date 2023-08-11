# Storages in AWS

AWS means under the word "storage" to have EBS-Elastic Block Storage, EFS-Elastic File Storage, Instance Storage which you can attach to your EC2 Instances or containers. Keep in mind, logically under almost every managed serverless service in AWS lives a EC2 Instance.

---
<br>

## EBS Elastic Block Storage
A network drive you can attach to your instances.
It is like a USB-Stick to you instance.

### Pro
- Persist data even after termination of EC2 Instance.
- Host operating system on EBS to easily start multiple EC2 Instances with the same configuration and data.
- Free tier of 30GB SSD.
- Snapshot archive possible.
- Recycle bin possible to create to prevent accidental deletions.
- Data encryption is possible with minimal latency.
- Multi attach in one AZ.
- Cheap.
- Different volumes types like SSD General Purpose, SSD high performance, HDD frequently accessed, HDD less frequently accessed, but keep in mind that HDD is much slower than SSD

### Contra
- Multi attach in one AZ possible.
- Locked to one AZ.
- No scalability.

### Use Cases
- Store instance data on it to replicate it easily to other instances.
- Ability to store/run operating system.

---
<br>

## EFS Elastic File System

### Pro
- AutoScale.
- Fully managed serverless file system.
- Accessible by multiple instances per default.
- Encryption at rest using KMS. KMS = Key Management Service.
- Works in multiple AZ.
- Different modes, General Purpose, Throughput mode.

### Contra
- Only compatible with Linux - no Windows.
- Not designed to store operating system on it.

### Use Cases
- When you need a file system across multiple AZ.
- Can be attached from multiple instances.
- CMS - Wordpress etc.

---
<br>

## EC2 Instance Storage

### Pro
- Better IOPS performance.
- High performance.

### Contra
- Data loss if hardware crashes or stopped.

### Use Cases
- Good for buffer, caching, temporary content.

---
<br>

## Solution Architect Summary 😍

- <b>EBS: </b>Use EBS when you need reliable, block-level storage for individual EC2 instances, including hosting the operating system, applications, and databases.

- <b>EFS: </b>Use EFS when you require shared and scalable file storage that can be concurrently accessed by multiple EC2 instances, such as for web hosting, content management, and development environments.

- <b>Instance Storage: </b>Use instance store when you need temporary, high-performance storage that is closely tied to the lifecycle of an EC2 instance and does not require data persistence beyond instance termination.


