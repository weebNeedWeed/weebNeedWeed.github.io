---
title : "Tạo VPC"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

#### Tạo mới một VPC

{{% notice info %}}
Trước khi bắt đầu lab, bạn nên chọn một Region của AWS để triển khai các dịch vụ. Các tài nguyên trong lab này sẽ được tạo trong Region **Singapore (ap-southeast-1)**.
{{% /notice %}}

1. Đăng nhập vào bảng điều khiển, tìm **VPC**, chọn **VPC**.

![0002](/images/2-ElasticBeanstalk/2.1-CreateVPC/0002.svg)

2. Ở mục **Resource to create**, chọn **VPC and more**
* Chọn **Auto-generate** và nhập ``fcj-aws`` cho mục **Name tag auto-generation**.

![0003](/images/2-ElasticBeanstalk/2.1-CreateVPC/0003.svg)

3. Nhập ``10.10.0.0/16`` cho mục **IPv4 CIDR Block**.

![0004](/images/2-ElasticBeanstalk/2.1-CreateVPC/0004.svg)

4. Chọn 2 **AZ**, 2 **Public Subnet** và 2 **Private Subnet**.

![0005](/images/2-ElasticBeanstalk/2.1-CreateVPC/0005.svg)

5. Ở mục **NAT Gateways**, chọn **In 1 AZ**.
* Chọn **None** cho **VPC Endpoints**.

![0006](/images/2-ElasticBeanstalk/2.1-CreateVPC/0006.svg)

6. Chọn **Create VPC**.

![0007](/images/2-ElasticBeanstalk/2.1-CreateVPC/0007.svg)

7. Sau khi VPC được khởi tạo thành công, chọn **View VPC** để xem VPC.

![0008](/images/2-ElasticBeanstalk/2.1-CreateVPC/0008.svg)