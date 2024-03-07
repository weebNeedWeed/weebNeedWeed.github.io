---
title : "Deploy CodePipeline"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

#### Deploy CodePipeline

In this section, we will together add a CI/CD workflow for our .NET 6 application pushed to [this repository](https://github.com/weebNeedWeed/sample-code-for-eb-codepipeline). This application has only one endpoint as "**/**" return the text **Hello world**.

![Demo](/images/3-CodePipeline/showcase.svg)

{{% notice note %}}
To carry out the content in this section, you should clone **[this repository](https://github.com/weebNeedWeed/sample-code-for-eb-codepipeline)** and push it to your own repository.
{{% /notice %}}

![Architecture](/images/1-Introduction/0001.svg)

#### Content

1. [Create a new S3 Bucket](3.1-CreateBucket/)
2. [Connect AWS to Github](3.2-ConnectToGithub/)
3. [Create a new Pipeline](3.3-CreatePipeline/)
4. [Add Policy for Service Role](3.4-AddRolePolicy/)
5. [Test the Pipeline](3.5-TestPipeline/)