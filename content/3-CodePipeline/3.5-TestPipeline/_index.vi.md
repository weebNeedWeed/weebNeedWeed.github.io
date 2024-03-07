---
title : "Kiểm thử Pipeline"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 3.5 </b> "
---

#### Kiểm thử Pipeline

1. Quay về giao diện Pipeline khi nãy ta vừa tạo, kiểm tra xem các **Stage** đã chạy thành công hay chưa.

![0001](/images/3-CodePipeline/3.5-TestPipeline/0001.svg)

2. Truy cập vào Elastic Beanstalk, kiểm tra các **Event** diễn ra khi Elastic Beanstalk vận hành để cập nhật phiên bản ứng dụng.

![0002](/images/3-CodePipeline/3.5-TestPipeline/0002.svg)

3. Truy cập vào DNS xem kết quả.

![0003](/images/3-CodePipeline/3.5-TestPipeline/0003.svg)

{{% notice tip %}}
Giờ bạn hãy thử tạo một commit mới với nội dung là sửa response của endpoint ***/*** (Ví dụ sửa *"Hello world"* > *"Hello world 123"*) để quan sát cách Pipeline hoạt động nhé.
{{% /notice %}}
