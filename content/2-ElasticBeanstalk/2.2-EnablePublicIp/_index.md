---
title : "Enable auto-assign public IPv4 address"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

#### Enable auto-assign public IPv4 address

1. Go to **VPC**, select **Subnets**, choose subnet ```fcj-aws-subnet-public1-*```.

![0001](/images/2-ElasticBeanstalk/2.2-EnablePublicIp/0001.svg)

2. Click **Actions** then click **Edit subnet settings**.

![0002](/images/2-ElasticBeanstalk/2.2-EnablePublicIp/0002.svg)

3. Check **Enable auto-assign public IPv4 address**, then click **Save**.

![0003](/images/2-ElasticBeanstalk/2.2-EnablePublicIp/0003.svg)

4. Repeat those steps with subnet ```fcj-aws-subnet-public2-*```.