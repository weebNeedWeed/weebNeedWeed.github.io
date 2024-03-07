---
title : "Create EC2 Instance Profile"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

#### Create a new EC2 Instance Profile

1. Find ```IAM```, select **IAM**.

![0001](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0001.svg)

2. Select **Roles** then click **Create role**.

![0002](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0002.svg)

3. Select **AWS Service** for **Trusted entity type**.

![0003](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0003.svg)

4. Scroll down and select **EC2**, then click **Next**.

![0004](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0004.svg)

5. Find and select ```AWSElasticBeanstalkWebTier``` policy.

![0005](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0005.svg)

6. Click **Next**.

![0006](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0006.svg)

7. Enter ```fcj-aws-ec2-instance-profile``` for **Role name**.

![0007](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0007.svg)

8. Click **Create role**.

![0008](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0008.svg)