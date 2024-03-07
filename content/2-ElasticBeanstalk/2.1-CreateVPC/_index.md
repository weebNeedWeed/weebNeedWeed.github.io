---
title : "Create a VPC"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

#### Create a new VPC

{{% notice info %}}
Before starting ,you need to choose one region deploy AWS services, all resources in this lab is created in region **Singapore (ap-southeast-1)**.
{{% /notice %}}

1. Search and select ```VPC``.

![0002](/images/2-ElasticBeanstalk/2.1-CreateVPC/0002.svg)

2. In **Resource to create** section, select **VPC and more**
* Select **Auto-generate** and type ``fcj-aws`` for **Name tag auto-generation**.

![0003](/images/2-ElasticBeanstalk/2.1-CreateVPC/0003.svg)

3. Enter ``10.10.0.0/16`` for **IPv4 CIDR Block**.

![0004](/images/2-ElasticBeanstalk/2.1-CreateVPC/0004.svg)

4. Select 2 **AZ**, 2 **Public Subnet** and 2 **Private Subnet**.

![0005](/images/2-ElasticBeanstalk/2.1-CreateVPC/0005.svg)

5. In **NAT Gateways**, select **In 1 AZ**.
* Select **None** for **VPC Endpoints**.

![0006](/images/2-ElasticBeanstalk/2.1-CreateVPC/0006.svg)

6. Click **Create VPC**.

![0007](/images/2-ElasticBeanstalk/2.1-CreateVPC/0007.svg)

7. Click **View VPC** to view your VPC after creation.

![0008](/images/2-ElasticBeanstalk/2.1-CreateVPC/0008.svg)