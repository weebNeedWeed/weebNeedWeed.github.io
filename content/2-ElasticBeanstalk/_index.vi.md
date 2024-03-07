---
title : "Triển khai Elastic Beanstalk Environment"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

#### Các khái niệm cơ bản trong Elastic Beanstalk

1. **Application**: Một Application là một tập hợp luận lý các thành phần bao gôm các Environment, các Version và Environment Configuration.
2. **Version**: mỗi Application có nhiều Version, ví dụ: ta có một Application có Version *v1* sử dụng MySQL, Version *v2* sử dụng PostgreSQL.
3. **Environment Tier**: Khi khởi tạo một Environment, ta sẽ được chọn 1 trong 2 tier: 
   - Web server: Dành cho các Application thông thường, lắng nghe các HTTP Request và trả về kết quả.
   - Worker: Dành cho các Application chuyên lắng nghe và xử lý các AWS Simple Queue Service message.
4. **Environment Configuration**: Các tham số cài đặt của một Environment.

Trong phần này, ta sẽ cùng tìm hiểu và triển khai một High Availability Environment đơn giản với sample code được AWS cung cấp sẵn.

![Only eb architecture](/images/2-ElasticBeanstalk/0001.svg)

#### Nội dung

1. [Tạo VPC](2.1-createvpc/)
2. [Bật Public IP cho Public Subnet](2.2-enablepublicip/)
3. [Tạo EC2 Keypair](2.3-createkeypair/)
4. [Tạo EC2 Instance Profile](2.4-instanceprofile/)
5. [Triển khai Environment](2.5-createenv/)
6. [Kiểm tra Environment](2.6-testenv/)

