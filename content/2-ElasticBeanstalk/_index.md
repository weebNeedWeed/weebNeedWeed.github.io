---
title : "Create Elastic Beanstalk Environment"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

#### Fundamentals of Elastic Beanstalk

1. **Application**: Application is a logical collection of components like Environments, Versions and Environment Configurations.
2. **Version**: Each Application has many versions. For example, Application with version A uses Mysql and with Version B it uses PostgreSQL.
3. **Environment Tier**: When we create new Environment, we can choose 1 of 2 tiers:
   - Web server: For Application that serves on HTTP/HTTPS.
   - Worker: For application that pulls tasks of SQS Queue to process.
4. **Environment Configuration**: The settings of the Application.

In this section, we will create a High Availability Environment with AWS provided sample code.

![Only eb architecture](/images/2-ElasticBeanstalk/0001.svg)

#### Content 

1. [Create a VPC](2.1-createvpc/)
2. [Enable auto-assign public IPv4 address](2.2-enablepublicip/)
3. [Create EC2 Keypair](2.3-createkeypair/)
4. [Create EC2 Instance Profile](2.4-instanceprofile/)
5. [Deploy the Environment](2.5-createenv/)
6. [Test the Environment](2.6-testenv/)

