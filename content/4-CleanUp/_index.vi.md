---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
#### Dọn dẹp tài nguyên

1. Xoá Pipeline
   - Truy cập vào trang quản trị **CodePipeline**.
   - Chọn Pipeline bạn vừa tạo.
   - Chọn **Delete pipeline**.

2. Xoá CodeBuild Project.
   - Truy cập vào trang quản trị **CodeBuild**.
   - Chọn Project bạn đã tạo.
   - Chọn **Actions** > **Delete**.

3. Xoá kết nối Github
   - Chọn **Settings** > **Connections**.
   - Chọn Connection bạn vừa tạo.
   - Chọn **Delete**.

4. Xoá Elastic Beanstalk Application
   - Truy cập vào **Elastic Beanstalk**.
   - Chọn **Applications** sau đó chọn Application bạn vừa tạo.
   - Chọn **Actions** > **Delete application**.

5. Xoá S3 Bucket
   - Truy cập vào **S3**
   - Truy cập vào Bucket **elasticbeanstalk-**
   - Chọn tab **Permissions**, cuộn xuống phần **Bucket Policy**, chọn **Delete**.
   - **Empty** và **Delete** Bucket **elasticbeanstalk-**.
   - **Empty** và **Delete** Bucket chứa Artifact ta đã tạo dành cho CodePipeline.

6. Xoá IAM Role
   - Truy cập vào **IAM**.
   - Chọn **Roles**.
   - Xoá các role ta đã tạo.

7. Xoá Keypair
   - Truy cập vào **EC2**.
   - Chọn **Key Pairs**.
   - Xoá Keypair ta đã tạo.

8. Xoá NAT Gateway
   - Truy cập vào **VPC**.
   - Chọn **NAT Gateways**.
   - Xoá NAT Gateway ta đã tạo.

9. Xoá Elastic IP
   - Chọn **Elastic IPs** trong **VPC**.
   - Chọn IP AWS tạo cho ta trước đó.
   - Chọn **Actions** > **Release Elastic IP**.

10. Xoá VPC
    - Truy cập vào **VPC**.
    - Chọn VPC ta đã tạo trước đó.
    - Xoá VPC.