---
title : "Tạo S3 Bucket"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

#### Tạo mới một Bucket 

1. Tìm và truy cập **S3** trên thanh tìm kiếm.

![0001](/images/3-CodePipeline/3.1-CreateBucket/0001.svg)

2. Chọn **Buckets**, tiếp đó chọn **Create bucket**.

![0002](/images/3-CodePipeline/3.1-CreateBucket/0002.svg)

3. Chọn **AWS Region** là Region bạn đang thực hiện lab.
* Ở phần **Bucket name**, nhập một tên hợp lệ.

![0003](/images/3-CodePipeline/3.1-CreateBucket/0003.svg)

4. Chọn **Create bucket**.

![0004](/images/3-CodePipeline/3.1-CreateBucket/0004.svg)

5. Click vào Bucket bạn vừa tạo.

![0005](/images/3-CodePipeline/3.1-CreateBucket/0005.svg)

6. Chọn tab **Permissions**.

![0006](/images/3-CodePipeline/3.1-CreateBucket/0006.svg)

7. Ở phần **Block public access** chọn **Edit**.

![0007](/images/3-CodePipeline/3.1-CreateBucket/0007.svg)

8. Bỏ chọn tất cả các Checkbox.

* Chọn **Save change**.

![0008](/images/3-CodePipeline/3.1-CreateBucket/0008.svg)

9. Chọn **Edit bucket policy**.

![0009](/images/3-CodePipeline/3.1-CreateBucket/0009.svg)

10.   Nhập **Policy** sau:

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

* Ở phần **`Principal`**, ta cho phép toàn bộ Service trong AWS được thực hiện các Action bên dưới đối với Bucket với **`"AWS": "*"`**.
* Cho phép thực hiện các Action bắt đầu với **`List`**, **`Get`** và **`Put`** đối với Bucket vừa tạo **`arn:aws:s3:::fcj-aws-eb-lab`** và các Object bên trong nó **`arn:aws:s3:::fcj-aws-eb-lab/*`**.

11. Chọn **Save change**.

![0011](/images/3-CodePipeline/3.1-CreateBucket/0011.svg)
