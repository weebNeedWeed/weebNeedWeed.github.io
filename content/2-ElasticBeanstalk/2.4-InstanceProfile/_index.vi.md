---
title : "Tạo EC2 Instance Profile"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

#### Tạo EC2 Instance Profile

1. Tìm ```IAM```, chọn **IAM**.

![0001](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0001.svg)

2. Chọn **Roles** sau đó chọn **Create role**.

![0002](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0002.svg)

3. Chọn **AWS Service** ở phần **Trusted entity type**.

![0003](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0003.svg)

4. Cuộn xuống và chọn **EC2**, sau đó click **Next**.

![0004](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0004.svg)

5. Tìm và chọn policy ```AWSElasticBeanstalkWebTier```.

![0005](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0005.svg)

6. Chọn **Next**.

![0006](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0006.svg)

7. Nhập **Role name** là ```fcj-aws-ec2-instance-profile```.

![0007](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0007.svg)

8. Chọn **Create role**.

![0008](/images/2-ElasticBeanstalk/2.4-InstanceProfile/0008.svg)