---
title : "Deploy the Environment"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 2.5 </b> "
---

#### Create a new Application

1. Find ```Elastic Beanstalk``` and select **Elastic Beanstalk**.

![0001](/images/2-ElasticBeanstalk/2.5-CreateEnv/0001.svg)

2. Select **Applications** and then click **Create application**.

![0002](/images/2-ElasticBeanstalk/2.5-CreateEnv/0002.svg)

3. Enter ```fcj-aws-application``` for **Application name**. Click **Create**.

![0003](/images/2-ElasticBeanstalk/2.5-CreateEnv/0003.svg)

#### Create a new Environment

1. Go to the console of our **fcj-aws-application** application and click **Create new application**.

![0004](/images/2-ElasticBeanstalk/2.5-CreateEnv/0004.svg)

2. In **Environment tier**, Select **Web server environment**.

![0005](/images/2-ElasticBeanstalk/2.5-CreateEnv/0005.svg)

3. Type ```fcj-aws-application-prod-env``` for both **Environment name** and **Domain**.

![0006](/images/2-ElasticBeanstalk/2.5-CreateEnv/0006.svg)

4. Click **Check availability** to check if your name is valid.

![0007](/images/2-ElasticBeanstalk/2.5-CreateEnv/0007.svg)

5. In **Platform**, select **Managed platform** for **Platform type** and then choose **.NET Core on Linux**.

![0008](/images/2-ElasticBeanstalk/2.5-CreateEnv/0008.svg)

6. Select **Sample application** for **Application code** to utilize AWS providing source code.
* In **Presets** section, select **High availability** for building high availability environment.
* Click **Next**.

![0009](/images/2-ElasticBeanstalk/2.5-CreateEnv/0009.svg)

7. Select **Create and use new service role** to generate new service role automatically.
* Select **aws-keypair** and **fcj-aws-ec2-instance-profile** created in the previous steps.
* Click **Next**.

![0010](/images/2-ElasticBeanstalk/2.5-CreateEnv/0010.svg)

9. Select **fcj-aws-vpc**.

![0011](/images/2-ElasticBeanstalk/2.5-CreateEnv/0011.svg)

10. Select **2 Private Subnet** for **Instance Subnets**.

![0012](/images/2-ElasticBeanstalk/2.5-CreateEnv/0012.svg)

11. Scroll down then select **Next**.

![0013](/images/2-ElasticBeanstalk/2.5-CreateEnv/0013.svg)

12. Select **1 minute** for **Monitoring interval**, that means EC2 instance will send metrics for each minute.
* When initialization, Elastic Beanstalk creates a new Security Group for EC2 Instance, so we can skip **EC2 security groups** section.

![0014](/images/2-ElasticBeanstalk/2.5-CreateEnv/0014.svg)

13. Select **Load balanced** for **Environment type** then type the number of minimum instances and maximum instances.

![0015](/images/2-ElasticBeanstalk/2.5-CreateEnv/0015.svg)

14. **Instance types**, select **t2.micro**.

![0016](/images/2-ElasticBeanstalk/2.5-CreateEnv/0016.svg)

15. In the **Load balancer subnets** section, select **2 Public Subnet**.

{{% notice tip %}}
AWS by default selects 2 Private Subnet, so if we leave it as its default values, the load balancer can't receive traffic.
{{% /notice %}}

![0017](/images/2-ElasticBeanstalk/2.5-CreateEnv/0017.svg)

16. Select **Application load balancer** and **Dedicated** for **Load balancer type**.

![0018](/images/2-ElasticBeanstalk/2.5-CreateEnv/0018.svg)

17. Select **Next**.

![0019](/images/2-ElasticBeanstalk/2.5-CreateEnv/0019.svg)

18. Select **Enhanced** for **Health reporting system**.

![0020](/images/2-ElasticBeanstalk/2.5-CreateEnv/0020.svg)

19. Select **Activated** for **Log streaming** so we can view logs using CloudWatch.

![0021](/images/2-ElasticBeanstalk/2.5-CreateEnv/0021.svg)

20. Enter your email to receive significant messages from Elastic Beanstalk Environment.

![0022](/images/2-ElasticBeanstalk/2.5-CreateEnv/0022.svg)

21.  **Deployment policy** select **Rolling** and leave others as their default values.

* Deployment policy types:

  * **All at once**: Deploy the new version to all instances simultaneously. All instances in your environment are out of service for a short time while the deployment occurs.
  * **Rolling**:  Deploy the new version in batches. Each batch is taken out of service during the deployment phase, reducing your environment's capacity by the number of instances in a batch.
  * **Rolling with additional batch**: Deploy the new version in batches, but first launch a new batch of instances to ensure full capacity during the deployment process.
  * **Immutable**: Deploy the new version to a fresh group of instances by performing an immutable update.
  * **Traffic splitting**: Deploy the new version to a fresh group of instances and temporarily split incoming client traffic between the existing application version and the new one.

![0023](/images/2-ElasticBeanstalk/2.5-CreateEnv/0023.svg)

22. Select **Activated** for **Instance log streaming**.
* Select **Next**.

![0024](/images/2-ElasticBeanstalk/2.5-CreateEnv/0024.svg)

23. Review your choices and select **Submit**.

![0025](/images/2-ElasticBeanstalk/2.5-CreateEnv/0025.svg)

24. Wait for about 10 minutes for the environment to be created.

![0026](/images/2-ElasticBeanstalk/2.5-CreateEnv/0026.svg)
