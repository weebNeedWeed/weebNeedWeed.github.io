---
title : "Kiểm tra Environment"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 2.6 </b> "
---

#### Kiểm tra Environment

1. Sau khi Environment được khởi tạo thành công sẽ có **Health** là **Ok**.

* Ta có thể click vào DNS của application để xem kết quả.

![0001](/images/2-ElasticBeanstalk/2.6-TestEnv/0001.svg)

![0002](/images/2-ElasticBeanstalk/2.6-TestEnv/0002.svg)

2. Chọn tab **Events** để xem các tài nguyên đã và đang khởi tạo.


![0003](/images/2-ElasticBeanstalk/2.6-TestEnv/0003.svg)

3. Chọn tab **Health** để kiểm tra trạng thái của các Instance.

![0004](/images/2-ElasticBeanstalk/2.6-TestEnv/0004.svg)

4. Tiếp đó chọn **Logs** và chọn **Request logs** > **Full** để fetch các log file của EC2 Instance nhằm mục đích troubleshoot lỗi nếu gặp phải.

![0005](/images/2-ElasticBeanstalk/2.6-TestEnv/0005.svg)

![0006](/images/2-ElasticBeanstalk/2.6-TestEnv/0006.svg)