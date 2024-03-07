---
title : "Create a new S3 Bucket"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

#### Create a new S3 Bucket

1. Find and select **S3**.

![0001](/images/3-CodePipeline/3.1-CreateBucket/0001.svg)

2. Select **Buckets**, then select **Create bucket**.

![0002](/images/3-CodePipeline/3.1-CreateBucket/0002.svg)

3. Select **AWS Region** as the region which you are using.
* In the **Bucket name** section, enter a valid name.

![0003](/images/3-CodePipeline/3.1-CreateBucket/0003.svg)

4. Select **Create bucket**.

![0004](/images/3-CodePipeline/3.1-CreateBucket/0004.svg)

5. Click the bucket you have created.

![0005](/images/3-CodePipeline/3.1-CreateBucket/0005.svg)

6. Select the **Permissions** tab.

![0006](/images/3-CodePipeline/3.1-CreateBucket/0006.svg)

7. In the **Block public access** section, select **Edit**.

![0007](/images/3-CodePipeline/3.1-CreateBucket/0007.svg)

8. Uncheck all then select **Save change**.

![0008](/images/3-CodePipeline/3.1-CreateBucket/0008.svg)

9. Select **Edit bucket policy**.

![0009](/images/3-CodePipeline/3.1-CreateBucket/0009.svg)

10. Enter the **Policy** as below:

![0010](/images/3-CodePipeline/3.1-CreateBucket/0010.svg)


```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Statement1",
            "Effect": "Allow",
            "Principal": {
                "AWS": "*"
            },
            "Action": [
                "s3:List*",
                "s3:Get*",
                "s3:Put*"
            ],
            "Resource": [
                "arn:aws:s3:::fcj-aws-eb-lab",
                "arn:aws:s3:::fcj-aws-eb-lab/*"
            ]
        }
    ]
}
```

* In the **`Principal`** block, we allow all AWS Services to perform all actions stated with **`List`**, **`Get`** and **`Put`** on the S3 bucket and objects inside it.

11. Click **Save change**.

![0011](/images/3-CodePipeline/3.1-CreateBucket/0011.svg)
