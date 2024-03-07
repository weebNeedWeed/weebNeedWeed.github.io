---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

#### AWS CodeBuild

**CodeBuild** là một dịch vụ trên AWS hỗ trợ quá trình tích hợp liên tục các thay đổi trong mã nguồn. CodeBuild biên dịch, chạy các unit test để đảm bảo chất lượng mã nguồn cho việc triển khai lên khác dịch vụ khác. Với CodeBuild, ta sẽ không cần lo lắng về việc vận hành, quản lý và mở rộng máy chủ chuyên dụng cho việc build.

CodeBuild hiện nay hỗ trợ khá nhiều ngôn ngữ như C#, Java, JavaScript, các build tool như Maven, Gradle và các nền tảng như Docker, Android được xây dựng sẵn. 

#### AWS CodeDeploy

**CodeDeploy** tự động hoá việc triển khai ứng dụng lên các dịch vụ như EC2, Lambda, Fargate và môi trường on-premises với 2 kiểu triển khai chính là **In-place deployment** và **Blue/green deployment**.

#### AWS CodePipeline

**CodePipeline** là một dịch vụ hỗ trợ chuyên giao liên tục được sử dụng để mô hình hoá, trực quan hoá và tự động hoá các bước để triển khai ứng dụng. Khi kết hợp với CodeBuild, ta sẽ có được mô hình tự động hoá hoàn toàn các bước **build-test-release**.

#### AWS Elastic Beanstalk

**Elastic Beanstalk** là một dịch vụ PaaS(Platform as a service) trên AWS giúp ta dễ dàng hơn trong việc triển khai và quản lý các ứng dụng.
Khi developer tạo mới một **Environment**, Elastic Beanstalk sẽ tự động khởi tạo các tài nguyên khác như **EC2**, **Elastic Load Balancer**, **Auto Scaling Group**,... để giúp ứng dụng có độ sẵn sàng cao(High Availability) mà không cần developer bận tâm về các vấn đề quản lý tài nguyên chi tiết.

Các lợi ích khi sử dụng Elastic Beanstalk: 

1. Triển khai và quản lý ứng dụng một cách tiện lợi mà không cần lo lắng về các vấn đề như hạ tầng, cân bằng tải, mở rộng hệ thống,...
2. **Đa môi trường**: Elastic Beanstalk hỗ trợ triển khai nhiều môi trường, do đó ta có thể triển khai ứng dụng lên các môi trường riêng biệt như Development, Production,...
3. Hỗ trợ nhiều ngôn ngữ, nền tảng cùng với đó là khả năng tuỳ chỉnh, mở rộng cao.
4. **Tiết kiệm chi phí**: Bạn chỉ phải chi trả cho những dịch vụ **Elastic Beanstalk** đã tạo như EC2 hay Elastic Load Balancer.

Trong lab này ta sẽ cùng nhau thực hành triển khai các dịch vụ trên với mô hình kiến trúc dưới đây:

![Architecture](/images/1-Introduction/0001.svg)

Với mô hình kiến trúc trên, ta có workflow như sau:

1. Khi Developer commit các thay đổi và push lên remote repository trên github, CodePipeline sẽ watch remote repository và pull source code về sau đó upload vào S3 Bucket. Bước này được gọi là **Source Stage** và source code ở bước này được gọi là **Source Artifact**.
2. Ở **Build Stage** CodeBuild sẽ lấy source code đã được upload và tiến hành build với các cấu hình ta định nghĩa trong file **buildspec.yml**. Sau khi build thành công CodeBuild sẽ upload **Build Artifact** vào S3 Bucket. 
3. Sau cùng, ở **Deploy Stage**, Build Artifact sẽ được upload vào **Elastic Beanstalk Environment**. Elastic Beanstalk sẽ tự động cập nhật phiên bản ứng dụng trong EC2 Instance và thay đổi các cấu hình bên trong Environment.
4. Ở phía người dùng, sau khi hệ thống được triển khai thành công, có thể truy cập vào website thông qua DNS được Route53 cung cấp.