---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

#### AWS CodeBuild

**CodeBuild** is an AWS service that helps with the continuous integration flow. CodeBuild compiles, run unit-tests to ensure the source being ready for deployment to other services. With CodeBuild, we don't have to worry about the operation, management and scaling of build servers.

CodeBuild nowadays supports many languages like C#, Java, Javascript, etc. CodeBuild also has prepared build tools like Maven and Gradle or some popular platforms like Docker and Android.

#### AWS CodeDeploy

**CodeDeploy** automates deployment to AWS Services like EC2, Lambda, Fargate or even on-premises environments with 2 primary deployment types: **In-place deployment** and **Blue/green deployment**.

#### AWS CodePipeline

**CodePipeline** is an continuous delivery service that can be used to model, virtualize and automate application deployment steps. When using with CodeBuild, we will have a fully-automated model of build-test-release workflow.

#### AWS Elastic Beanstalk

**Elastic Beanstalk** is a PaaS(Platform as a service) service facilitating the deployment and management of our applications. When the developers initializes a new **Environment**, Elastic Beanstalk will create other resources like **EC2**, **Elastic Load Balancer**, **Auto Scaling Group**, etc... to make our applications high availability without developer worrying about the management issues.

Some **benefits** of **Elastic Beanstalk**:

1. Deploy and manage applications without worrying about infrastructure, load balancing, scaling, etc.
2. **Multiple environments**: Elastic Beanstalk supports deployment to many environments, so we could have our applications to live on certain environments like Production, Development, Staging, etc.
3. Support various languages and platforms.
4. Cost optimization.

![Architecture](/images/1-Introduction/0001.svg)

With the above architecture model, we have the workflow as follows:

1. When developers commit their changes and push them to the remote repository, CodePipeline will fetch those changes and upload to S3 Bucket as **Source Artifacts**. This step is called **Source State**.
2. In **Build Stage**, CodeBuild uses Build Artifacts uploaded to S3 Bucket to compile and run tests. After that, CodeBuild will upload **Build Artifacts** to S3 Bucket.
3. Finally, in **Deploy Stage**, Build Artifact is uploaded to **Elastic Beanstalk Environment**. Beanstalk will automatically update the application.
4. Users can access to the application through AWS Route53 DNS.