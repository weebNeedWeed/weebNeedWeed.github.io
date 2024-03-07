---
title : "Bật Public IP cho Public Subnet"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

#### Bật Public IP cho Public Subnet

1. Truy cập bảng điều khiển của **VPC**, chọn **Subnets**, chọn subnet ```fcj-aws-subnet-public1-*```.

![0001](/images/2-ElasticBeanstalk/2.2-EnableIP/0001.svg)

2. Chọn **Actions** sau đó chọn **Edit subnet settings**.

![0002](/images/2-ElasticBeanstalk/2.2-EnableIP/0002.svg)

3. Chọn **Enable auto-assign public IPv4 address**, sau đó chọn **Save**.

![0003](/images/2-ElasticBeanstalk/2.2-EnableIP/0003.svg)

4. Lặp lại các bước trên với subnet ```fcj-aws-subnet-public2-*```.
