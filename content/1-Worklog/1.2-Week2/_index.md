---
title: "Week 2 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---



### Week 2 Objectives:

* Learn and practice deploying virtual servers with Amazon EC2.
* Grant application permissions running on EC2 using IAM Roles.
* Manage hybrid DNS with Amazon Route 53 and practice the Networking Workshop.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Watch FCJ Bootcamp EC2 tutorial videos <br> - Study EC2 theory: Instance types, AMI, key pairs, EBS volumes <br> - Practice: <br>&emsp; + Launch EC2 instance (Amazon Linux 2) <br>&emsp; + Configure Security Group to open port 22 (SSH) and 80 (HTTP) <br>&emsp; + Connect to EC2 via SSH from local machine <br>&emsp; + Install Apache Web Server and verify in browser | 27/04/2026 | 27/04/2026 | <https://000004.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - Watch FCJ Bootcamp IAM Roles for EC2 videos <br> - Study the difference between IAM User and IAM Role <br> - Practice: <br>&emsp; + Create IAM Role with AmazonS3ReadOnlyAccess <br>&emsp; + Attach Role to EC2 instance <br>&emsp; + Verify S3 access from EC2 using AWS CLI <br>&emsp; + Compare behavior before and after attaching the Role | 28/04/2026 | 28/04/2026 | <https://000048.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | - Watch FCJ Bootcamp Route 53 & Hybrid DNS videos <br> - Study Amazon Route 53: Hosted Zone, Record types (A, CNAME, Alias) <br> - Practice: <br>&emsp; + Create Public Hosted Zone <br>&emsp; + Create A Record pointing to EC2 instance <br>&emsp; + Configure Routing Policies (Simple, Weighted) | 29/04/2026 | 29/04/2026 | <https://000010.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | - **Practice Networking on AWS Workshop:** <br>&emsp; + Configure VPC Peering between 2 VPCs <br>&emsp; + Set up Transit Gateway to connect multiple VPCs <br>&emsp; + Test connectivity between VPCs after configuration | 30/04/2026 | 02/05/2026 | <https://000092.awsstudygroup.com> |
| 7   | - Review and consolidate Week 2 knowledge | 03/05/2026 | 03/05/2026 |                                           |


### Week 2 Achievements:

* Successfully deployed EC2 instance, connected via SSH, and installed a Web Server.
* Configured IAM Role attached to EC2 to securely grant S3 access.
* Understood and practiced Route 53: created Hosted Zone and configured DNS Records.
* Completed VPC Peering and Transit Gateway in the Networking Workshop.

