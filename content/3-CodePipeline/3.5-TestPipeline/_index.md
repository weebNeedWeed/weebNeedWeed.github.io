---
title : "Test the Pipeline"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 3.5 </b> "
---

#### Test the Pipeline

1. Go back to the Pipeline interface, check if all **Stages** has successfully run.

![0001](/images/3-CodePipeline/3.5-TestPipeline/0001.svg)

2. Go to Elastic Beanstalk, view **Event** happening when Elastic Beanstalk operating to upgrade the Application to new version.

![0002](/images/3-CodePipeline/3.5-TestPipeline/0002.svg)

3. Click the DNS and view result.

![0003](/images/3-CodePipeline/3.5-TestPipeline/0003.svg)

{{% notice tip %}}
Now you could try adding new commit to Github like changing the endpoint ***/***'s response(*"Hello world"* > *"Hello world 123"*) to see how Pipeline work.
{{% /notice %}}
