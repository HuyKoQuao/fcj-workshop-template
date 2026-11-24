---
title: "Week 7 Worklog"
date: 2026-11-02
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Understand how to operate relational databases on AWS using Amazon RDS and Amazon Aurora.
* Distinguish between RDS Multi-AZ and Read Replicas.
* Grasp the fundamentals of Amazon DynamoDB (NoSQL) and practice RDS Failover.

### Tasks Carried Out This Week:

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| Mon | - Learn about **Amazon RDS**: <br>&emsp; + Supported engines (MySQL, PostgreSQL) and DB Subnet Groups <br>&emsp; + Automated Backups, Snapshots, and Point-in-Time Recovery | 02/11/2026 | 02/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Tue | - Learn about database scaling architectures: <br>&emsp; + Compare **RDS Multi-AZ** (HA standby) and **Read Replicas** (read scaling) <br>&emsp; + Overview of **Amazon Aurora** architecture | 03/11/2026 | 03/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Wed | - Learn about **Amazon DynamoDB** & **ElastiCache**: <br>&emsp; + Table, Item, Partition Key, Sort Key concepts, and On-Demand mode <br>&emsp; + Overview of ElastiCache (Redis/Memcached) | 04/11/2026 | 04/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Thu | - **Amazon RDS Practice:** <br>&emsp; + Create a DB Subnet Group and launch an RDS MySQL Multi-AZ instance in a Private Subnet <br>&emsp; + Configure Security Group rules to allow port 3306 only from the EC2 app server | 05/11/2026 | 05/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Fri | - **Connection & Failover Practice:** <br>&emsp; + Connect the application from EC2 to RDS and create test tables/data <br>&emsp; + Trigger "Reboot with Failover" on RDS to observe automatic failover to the standby instance | 06/11/2026 | 06/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |

### Week 7 Achievements:

* Deployed an isolated RDS MySQL Multi-AZ database inside a Private Subnet and successfully connected to it from EC2.
* Directly verified the automatic failover mechanism of RDS when the primary instance experiences an outage.
* Understood DynamoDB's key-value/document storage structure for use in serverless architectures.
