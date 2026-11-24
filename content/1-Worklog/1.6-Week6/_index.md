---
title: "Week 6 Worklog"
date: 2026-10-26
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Master the core features of Amazon S3 (Storage Classes, Versioning, Lifecycle, Bucket Policy).
* Distinguish when to use S3, EBS, and EFS.
* Practice connecting on-premises storage to S3 via AWS Storage Gateway.

### Tasks Carried Out This Week:

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| Mon | - Learn about **Amazon S3**: <br>&emsp; + Buckets, Objects, Versioning, and encryption (SSE-S3, SSE-KMS) <br>&emsp; + Storage Classes (Standard, IA, Intelligent-Tiering, Glacier) and Lifecycle Rules | 26/10/2026 | 26/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Tue | - Learn about S3 Security & **Amazon EFS**: <br>&emsp; + Bucket Policies, Block Public Access, and Presigned URLs <br>&emsp; + Compare S3, EBS, and EFS (sharing files across multiple EC2 instances simultaneously) | 27/10/2026 | 27/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Wed | - Learn about **AWS Storage Gateway**: <br>&emsp; + Distinguish between File Gateway, Volume Gateway, and Tape Gateway <br>&emsp; + How file synchronization works from on-premises servers to S3 | 28/10/2026 | 28/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Thu | - **Amazon S3 Practice:** <br>&emsp; + Create a bucket, enable Versioning, and configure a Lifecycle Rule to transition files to Glacier <br>&emsp; + Test static website hosting on S3 and generate a Presigned URL | 29/10/2026 | 29/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Fri | - **Storage Gateway Practice:** <br>&emsp; + Set up a File Gateway and create an SMB/NFS File Share connected to an S3 bucket <br>&emsp; + Mount the network drive on a client machine, copy files, and verify synchronization on S3 | 30/10/2026 | 30/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |

### Week 6 Achievements:

* Learned how to configure S3 securely, manage file versions, and automate storage class transitions to reduce costs.
* Completed the AWS Storage Gateway lab connecting file shares from a client to S3.
* Clearly distinguished the pros and cons of S3, EBS, and EFS for different data types.
