---
title: "Week 3 Worklog"
date: 2026-10-05
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Understand inter-VPC networking models on AWS: Bastion Host, VPC Peering, and Transit Gateway.
* Gain an overview of hybrid network connectivity (Site-to-Site VPN, Direct Connect).
* Complete the multi-VPC routing lab using Transit Gateway.

### Tasks Carried Out This Week:

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| Mon | - Learn about the Bastion Host model for accessing servers in a Private Subnet <br> - Learn about **VPC Peering** and its non-transitive limitation | 05/10/2026 | 05/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Tue | - Learn about **AWS Transit Gateway** (Hub-and-Spoke model) <br> - Read an overview of Site-to-Site VPN and AWS Direct Connect | 06/10/2026 | 06/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Wed | - **Practice:** <br>&emsp; + Set up a Bastion Host in a Public Subnet to SSH into an EC2 instance in a Private Subnet <br>&emsp; + Establish VPC Peering between 2 VPCs with different CIDR blocks and update Route Tables | 07/10/2026 | 07/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Thu | - **Transit Gateway Practice:** <br>&emsp; + Create a Transit Gateway and attach 3 VPCs to it <br>&emsp; + Configure the Transit Gateway Route Table to enable communication between VPCs | 08/10/2026 | 08/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Fri | - Test ping connectivity between EC2 instances across different VPCs via Transit Gateway <br> - Clean up all Transit Gateway Attachments and EC2 instances from the lab | 09/10/2026 | 09/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |

### Week 3 Achievements:

* Learned how to use a Bastion Host and configure VPC Peering to connect two internal networks.
* Completed the AWS Transit Gateway lab and understood how to manage centralized routing across multiple VPCs.
* Grasped the fundamental concepts of VPN connectivity from an on-premises environment to AWS.
