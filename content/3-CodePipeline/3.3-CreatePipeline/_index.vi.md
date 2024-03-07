---
title : "Tạo Pipeline"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

#### Tạo Pipeline với CodePipeline

1. Tìm và chọn **CodePipeline** trên thanh tìm kiếm.

![0001](/images/3-CodePipeline/3.3-CreatePipeline/0001.svg)

2. Chọn **Pipelines** > **Create pipeline**.

![0002](/images/3-CodePipeline/3.3-CreatePipeline/0002.svg)

3. Với **Pipeline name**, nhập ```fcj-aws-pipeline```.
* **Pipeline type** chọn **V2**.
* **Execution mode** chọn **Superseded**.

![0003](/images/3-CodePipeline/3.3-CreatePipeline/0003.svg)

4. **Service role** chọn **New service role**, nhập **Role name** và chọn **Allow AWS CodePipeline to create a service role so it can be used with this new pipeline**.

![0004](/images/3-CodePipeline/3.3-CreatePipeline/0004.svg)

5. Trong **Advanced settings**, chọn **Custom location** sau đó chọn **Bucket** mà ta chuẩn bị trước đó.

![0005](/images/3-CodePipeline/3.3-CreatePipeline/0005.svg)

6. Đối với **Source provider** ta chọn **Github(Version 2)**. 

![0006](/images/3-CodePipeline/3.3-CreatePipeline/0006.svg)

7. Ta chọn **Connection** đã tạo trước đó. Đồng thời chọn Repository trên Github.

![0007](/images/3-CodePipeline/3.3-CreatePipeline/0007.svg)

8. Chọn nhánh **master** và **Output artifact format** là **CodePipeline default**.

![0008](/images/3-CodePipeline/3.3-CreatePipeline/0008.svg)

9. Chọn **Trigger** là **No filter**, chọn **Next**.

![0009](/images/3-CodePipeline/3.3-CreatePipeline/0009.svg)

10. Chọn **Build provider** là **AWS CodeBuild**, tiếp theo chọn **Create project**.

![0010](/images/3-CodePipeline/3.3-CreatePipeline/0010.svg)

11. **Project name** nhập ```fcj-aws-proj```.

![0011](/images/3-CodePipeline/3.3-CreatePipeline/0011.svg)

12. Chọn **New service role** sau đó nhập **Role name**.

![0012](/images/3-CodePipeline/3.3-CreatePipeline/0012.svg)

13. Chọn **Use a buildspec file**.

![0013](/images/3-CodePipeline/3.3-CreatePipeline/0013.svg)

14. Chọn **Cloud watch logs**, nhập **Group name** và **Stream name prefix**. Chọn **Continue to CodePipeline**.

![0014](/images/3-CodePipeline/3.3-CreatePipeline/0014.svg)

15. Chọn **Build type** là **Single build**. Chọn **Next**.

![0015](/images/3-CodePipeline/3.3-CreatePipeline/0015.svg)

16. Chọn **Deploy provider** là **AWS Elastic Beanstalk**. Chọn **Application name** và **Environment name** ta đã tạo trước đó.

![0016](/images/3-CodePipeline/3.3-CreatePipeline/0016.svg)

17. Xem lại cấu hình và chọn **Create pipeline**.

![0017](/images/3-CodePipeline/3.3-CreatePipeline/0017.svg)

{{% notice warning %}}
Dù ta đã tạo thành công Pipeline nhưng Pipeline của ta vẫn chưa thể chạy được. Đó là vì **Service role** CodePipeline tự động tạo **không có quyền** truy cập đến **Elastic Beanstalk** nên ta sẽ phải [cấp quyền cho Service role](/3-codepipeline/3.4-addrolepolicy).
{{% /notice %}}