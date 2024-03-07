---
title : "Create a new Pipeline"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

#### Create a new Pipeline with CodePipeline

1. Find and select **CodePipeline**.

![0001](/images/3-CodePipeline/3.3-CreatePipeline/0001.svg)

2. Select **Pipelines** > **Create pipeline**.

![0002](/images/3-CodePipeline/3.3-CreatePipeline/0002.svg)

3. For **Pipeline name**, enter ```fcj-aws-pipeline```.
* **Pipeline type** select **V2**.
* **Execution mode** select **Superseded**.

![0003](/images/3-CodePipeline/3.3-CreatePipeline/0003.svg)

4. For **Service role** select **New service role**, enter **Role name** then check **Allow AWS CodePipeline to create a service role so it can be used with this new pipeline**.

![0004](/images/3-CodePipeline/3.3-CreatePipeline/0004.svg)

5. In **Advanced settings**, select **Custom location** then select **Bucket** we have prepared.

![0005](/images/3-CodePipeline/3.3-CreatePipeline/0005.svg)

6. For **Source provider** select **Github(Version 2)**. 

![0006](/images/3-CodePipeline/3.3-CreatePipeline/0006.svg)

7. Select **Connection** we have created then choose the repository to deploy.

![0007](/images/3-CodePipeline/3.3-CreatePipeline/0007.svg)

8. Select the **master** branch and select **Output artifact format** as **CodePipeline default**.

![0008](/images/3-CodePipeline/3.3-CreatePipeline/0008.svg)

9. Select **Trigger** as **No filter**, then click **Next**.

![0009](/images/3-CodePipeline/3.3-CreatePipeline/0009.svg)

10. Select **Build provider** as **AWS CodeBuild**, then click **Create project**.

![0010](/images/3-CodePipeline/3.3-CreatePipeline/0010.svg)

11. **Project name** enter ```fcj-aws-proj```.

![0011](/images/3-CodePipeline/3.3-CreatePipeline/0011.svg)

12. Select **New service role** then enter **Role name**.

![0012](/images/3-CodePipeline/3.3-CreatePipeline/0012.svg)

13. Select **Use a buildspec file**.

![0013](/images/3-CodePipeline/3.3-CreatePipeline/0013.svg)

14. Check **Cloud watch logs** checkbox, enter **Group name** and **Stream name prefix**. Click **Continue to CodePipeline**.

![0014](/images/3-CodePipeline/3.3-CreatePipeline/0014.svg)

15. Select **Build type** as **Single build**. Select **Next**.

![0015](/images/3-CodePipeline/3.3-CreatePipeline/0015.svg)

16. Select **Deploy provider** as **AWS Elastic Beanstalk**. Select **Application name** and **Environment name** created in the previous steps.

![0016](/images/3-CodePipeline/3.3-CreatePipeline/0016.svg)

17. Review your choices and click **Create pipeline**.

![0017](/images/3-CodePipeline/3.3-CreatePipeline/0017.svg)

{{% notice warning %}}
Although we have successfully created a new Pipeline, our Pipeline still can't run. That because the **CodePipeline Service Role** doesn't have permissions to perform actions on the **Elastic Beanstalk** environment. So that we have to [add policy to the Service Role](/3-codepipeline/3.4-addrolepolicy) to make it work.
{{% /notice %}}