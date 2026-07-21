---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---



### Week 4 Objectives:

* Learn and practice automatic system scaling with EC2 Auto Scaling and Elastic Load Balancer.
* Configure global content delivery with Amazon CloudFront.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Watch FCJ Bootcamp Auto Scaling & ELB tutorial videos <br> - Study EC2 Auto Scaling: Launch Template, Scaling Policies (Target Tracking, Step Scaling) <br> - Study Elastic Load Balancer: ALB vs NLB, Target Group, Health Check | 11/05/2026 | 11/05/2026 | <https://000006.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - **Practice Auto Scaling:** <br>&emsp; + Create Launch Template with AMI and Security Group <br>&emsp; + Create Auto Scaling Group with Min=1, Max=3, Desired=1 <br>&emsp; + Configure Target Tracking Policy based on CPU Utilization (70%) <br>&emsp; + Attach Application Load Balancer to Auto Scaling Group <br>&emsp; + Simulate high load to verify auto-scaling behavior | 12/05/2026 | 12/05/2026 | <https://000006.awsstudygroup.com> |
| 4   | - Watch FCJ Bootcamp CloudFront tutorial videos <br> - Study Amazon CloudFront: Distribution, Origin, Cache Behavior, TTL, Invalidation <br> - Study CloudFront integration with S3 and WAF | 13/05/2026 | 13/05/2026 | <https://000094.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | - **Practice CloudFront:** <br>&emsp; + Create CloudFront Distribution with S3 Bucket as Origin <br>&emsp; + Configure Origin Access Control (OAC) to secure S3 <br>&emsp; + Enable HTTPS and configure SSL Certificate <br>&emsp; + Create Cache Invalidation to refresh content <br>&emsp; + Compare access speed via CloudFront vs direct S3 | 14/05/2026 | 15/05/2026 | <https://000094.awsstudygroup.com> |
| 6   | - Review and consolidate Week 4 knowledge | 16/05/2026 | 16/05/2026 |                                           |


### Week 4 Achievements:

* Deployed Auto Scaling Group with ALB; system scales automatically under high load.
* Configured CloudFront Distribution connected to S3, delivering content globally with HTTPS.
* Understood Cache and Invalidation mechanisms in CloudFront.
* Compared performance before and after using CloudFront.

