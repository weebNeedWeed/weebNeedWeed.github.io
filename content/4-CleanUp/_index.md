---
title : "Clean up resources"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
#### Clean up resources

1. Delete Pipeline
   - Go to **CodePipeline**.
   - Select Pipeline we have created.
   - Select **Delete pipeline**.

2. Delete CodeBuild Project.
   - Go to **CodeBuild**.
   - Select Project we have created.
   - Select **Actions** > **Delete**.

3. Delete Github Connection
   - Select **Settings** > **Connections**.
   - Select Connection we have created.
   - Select **Delete**.

4. Delete Elastic Beanstalk Application
   - Go to **Elastic Beanstalk**.
   - Select **Applications** then select Application we have created.
   - Select **Actions** > **Delete application**.

5. Delete S3 Bucket
   - Go to **S3**
   - Select **elasticbeanstalk-** bucket.
   - Select **Permissions** tab, Scroll down to **Bucket Policy**, select **Delete**.
   - **Empty** and **Delete** **elasticbeanstalk-** bucket.
   - **Empty** and **Delete** Bucket created to store Artifacts.

6. Delete IAM Role
   - Go to **IAM**.
   - Select **Roles**.
   - Select Role we have created.

7. Delete Keypair
   - Go to **EC2**.
   - Select **Key Pairs**.
   - Delete Keypair we have created.

8. Delete NAT Gateway
   - Go to **VPC**.
   - Select **NAT Gateways**.
   - Delete NAT Gateway we have created.

9. Release Elastic IP
   - Select **Elastic IPs** in **VPC**.
   - Select IP we used for the lab.
   - Select **Actions** > **Release Elastic IP**.

10. Delete VPC
    - Go to **VPC**.
    - Select VPC we have created.
    - Delete VPC.