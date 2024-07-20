---
unique-page-id: 18874722
description: 测试的最佳实践 —  [!DNL Marketo Measure]
title: 测试最佳实践
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# 测试最佳实践 {#best-practices-for-testing}

您应该测试所有类型的表单，以确保[!DNL Marketo Measure] JavaScript正常工作。

## 推荐的测试过程 {#recommended-test-process}

1. 使用无痕浏览器或清除每个表单提交测试&#x200B;_和_&#x200B;之间的Cookie，每次使用不同的电子邮件地址。

   >[!TIP]
   >
   >最佳实践是使用包含指示该测试的内容以及时间的假电子邮件。 例如： `testing830am@test.com`。

1. 在搜索引擎（例如，`google.com`）上开始搜索，或直接导航到表单。

1. 使用唯一的电子邮件地址在您的网站上提交表单。

1. 记录提交表单时所在页面的URL以及使用的电子邮件地址。

1. 找到在您的CRM（潜在客户或联系人）中为该表单提交创建的记录，并验证是否正确创建了接触点。

>[!NOTE]
>
>您可以使用[!DNL Marketo Measure]库存报告，例如具有[!DNL Marketo Measure]接触点的潜在客户，或者如果您选择使用[!DNL Marketo Measure]详细信息更新您的页面布局，则可以查看潜在客户/联系人页面布局。 这可能需要一些时间来处理数据。
