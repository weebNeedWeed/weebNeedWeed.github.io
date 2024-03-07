---
title : "Triển khai Environment"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 2.5 </b> "
---

#### Tạo Application

1. Tìm ```Elastic Beanstalk``` trên thanh tìm kiếm và chọn **Elastic Beanstalk**.

![0001](/images/2-ElasticBeanstalk/2.5-CreateEnv/0001.svg)

2. Chọn **Applications** sau đó chọn **Create application**.

![0002](/images/2-ElasticBeanstalk/2.5-CreateEnv/0002.svg)

3. Nhập **Application name** là ```fcj-aws-application```. Chọn **Create**.

![0003](/images/2-ElasticBeanstalk/2.5-CreateEnv/0003.svg)

#### Tạo Environment

1. Truy cập vào trang quản trị của Application **fcj-aws-application** vừa tạo, chọn **Create new application**.

![0004](/images/2-ElasticBeanstalk/2.5-CreateEnv/0004.svg)

2. Ở phần **Environment tier**, ta chọn **Web server environment**.

![0005](/images/2-ElasticBeanstalk/2.5-CreateEnv/0005.svg)

3. Nhập ```fcj-aws-application-prod-env``` cho **Environment name** và **Domain** nhằm mục đích đánh dấu đây là Environment dành cho Production(prod).

![0006](/images/2-ElasticBeanstalk/2.5-CreateEnv/0006.svg)

4. Chọn **Check availability**, nếu thông báo **...is available** hiện lên thì tên bạn đặt là hợp lệ, nếu không bạn có thể đổi tên khác.

![0007](/images/2-ElasticBeanstalk/2.5-CreateEnv/0007.svg)

5. Ở phần **Platform** ta chọn **Platform type** là **Managed platform** và chọn **.NET Core on Linux**.

![0008](/images/2-ElasticBeanstalk/2.5-CreateEnv/0008.svg)

6. Chọn **Sample application** cho **Application code** để sử dụng sample app AWS cung cấp sẵn.
* Ở phần **Presets**, chọn **High availability** để xây dựng Environment có độ sẵn sàng cao.
* Chọn **Next**.

![0009](/images/2-ElasticBeanstalk/2.5-CreateEnv/0009.svg)

7. Chọn **Create and use new service role** để AWS tự động tạo một service role mới.
* Chọn **aws-keypair** và **fcj-aws-ec2-instance-profile** đã tạo trong bước trước.
* Chọn **Next**.

![0010](/images/2-ElasticBeanstalk/2.5-CreateEnv/0010.svg)

9. Chọn **fcj-aws-vpc**.

![0011](/images/2-ElasticBeanstalk/2.5-CreateEnv/0011.svg)

10. Chọn **2 Private Subnet** cho **Instance Subnets**.

![0012](/images/2-ElasticBeanstalk/2.5-CreateEnv/0012.svg)

11. Cuộn xuống và chọn **Next**.

![0013](/images/2-ElasticBeanstalk/2.5-CreateEnv/0013.svg)

12. Chọn **Monitoring interval** là **1 minute**, cứ mỗi 1 phút thì sẽ cập nhật số liệu 1 lần.
* Phần **EC2 security groups** ta có thể bỏ trống vì Elastic Beanstalk sẽ tự động tạo mới một security group và gán cho EC2 Instance.

![0014](/images/2-ElasticBeanstalk/2.5-CreateEnv/0014.svg)

13. Chọn **Load balanced** cho **Environment type** và chọn số lượng instance tối thiểu/tối đa, ta có thể để mặc định tối thiểu là 1 và tối đa là 4.

![0015](/images/2-ElasticBeanstalk/2.5-CreateEnv/0015.svg)

14. **Instance types**, chọn **t2.micro**.

![0016](/images/2-ElasticBeanstalk/2.5-CreateEnv/0016.svg)

{{% notice tip %}}
Ở phần **Scaling triggers** ta có thể giữ các giá trị mặc định. AWS Elastic Beanstalk sẽ tự động tăng giảm số lượng instance khi lưu lượng mạng đi của mỗi instance lớn hơn 6MB và bé hơn 2MB.
![Scaling trigger](/images/2-ElasticBeanstalk/2.5-CreateEnv/scaling_trigger.svg)
{{% /notice %}}

15. Ở phần **Load balancer subnets**, chọn **2 Public Subnet**.

{{% notice tip %}}
Ở bước này mặc định AWS sẽ chọn sẵn **2 Private Subnet**, nếu ta để mặc định thì Load balancer sẽ không thể nhận traffic.
{{% /notice %}}

![0017](/images/2-ElasticBeanstalk/2.5-CreateEnv/0017.svg)

16. Chọn **Application load balancer** và **Dedicated** cho **Load balancer type**.

![0018](/images/2-ElasticBeanstalk/2.5-CreateEnv/0018.svg)

17. Chọn **Next**.

![0019](/images/2-ElasticBeanstalk/2.5-CreateEnv/0019.svg)

18. Ta chọn **Enhanced** cho **Health reporting system**.

![0020](/images/2-ElasticBeanstalk/2.5-CreateEnv/0020.svg)

19. Chọn **Activated** cho **Log streaming** để ta có thể xem log trên CloudWatch.

![0021](/images/2-ElasticBeanstalk/2.5-CreateEnv/0021.svg)

20. Ta có thể nhập email để Elastic Beanstalk thông báo các sự kiện quan trọng khi Environment vận hành.

![0022](/images/2-ElasticBeanstalk/2.5-CreateEnv/0022.svg)

21.  **Deployment policy** chọn **Rolling** và giữ các giá trị khác mặc định.

* Deployment policy bao gồm các lựa chọn sau:

  * **All at once**: Đồng thời triển khai phiên bản application mới trên toàn bộ EC2 Instance, User sẽ không thể truy cập vào website trong một khoảng thời gian ngắn.
  * **Rolling**: Triển khai theo từng batch. Ví dụ: ta có 10 instance và batch size là 2 thì ta sẽ có mỗi lượt 2 instance sẽ được triển khai.
  * **Rolling with additional batch**: Như **Rolling** nhưng ở giai đoạn khởi tạo sẽ tự động khởi tạo thêm một số lượng instance nhằm đảm bảo hệ thống đạt được hiệu suất như trước khi triển khai phiên bản mới.
  * **Immutable**: Triển khai trên một nhóm các instance hoàn toàn khác với các instance đang vận hành sau đó sẽ thay từ từ các instance mới vào các instance cũ.
  * **Traffic splitting**: Triển khai trên một nhóm các instance hoàn toàn khác với các instance đang vận hành, đồng thời chuyển hướng một lượng traffic từ các instance cũ sang các instance mới.

![0023](/images/2-ElasticBeanstalk/2.5-CreateEnv/0023.svg)

22. Chọn **Activated** cho **Instance log streaming**.
* Chọn **Next**.

![0024](/images/2-ElasticBeanstalk/2.5-CreateEnv/0024.svg)

23. Review lại cấu hình sau đó chọn **Submit**.

![0025](/images/2-ElasticBeanstalk/2.5-CreateEnv/0025.svg)

24. Chờ khoảng 10 phút để Environment khởi tạo thành công.

![0026](/images/2-ElasticBeanstalk/2.5-CreateEnv/0026.svg)
