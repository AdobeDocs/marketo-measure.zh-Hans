---
unique-page-id: 18874722
description: 测试最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 测试最佳实践
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---

# 测试最佳实践 {#best-practices-for-testing}

您应该测试所有不同类型的表单，以确保 [!DNL Marketo Measure] JavaScript运行正常。

## 推荐的测试流程 {#recommended-test-process}

1. 在每次表单提交测试中，使用隐身浏览器或清除Cookie _和_ 每次使用不同的电子邮件地址。

   >[!TIP]
   >
   >最佳做法是使用一封假电子邮件，其中包含一些指示它是测试的内容，以及一天中的某个时间。 例如： `testing830am@test.com`.

1. 在搜索引擎中开始搜索(例如， `google.com`)，或直接导航到表单。

1. 使用唯一的电子邮件地址在您的网站上提交表单。

1. 记录您在上提交表单的页面的URL和使用的电子邮件地址。

1. 找到在CRM（潜在客户或联系人）中为表单提交创建的记录，并验证是否已正确创建接触点。

>[!NOTE]
>
>您可以使用 [!DNL Marketo Measure] 库存报表，如具有 [!DNL Marketo Measure] 如果您选择更新页面布局，则可以查看潜在客户/联系人页面布局 [!DNL Marketo Measure] 详细信息。 处理数据可能需要一些时间。
