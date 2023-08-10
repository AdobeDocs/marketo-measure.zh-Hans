---
unique-page-id: 18874722
description: 测试的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 测试最佳实践
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---

# 测试最佳实践 {#best-practices-for-testing}

您应该测试所有不同类型的表单，以确保 [!DNL Marketo Measure] JavaScript工作正常。

## 推荐的测试过程 {#recommended-test-process}

1. 使用无痕浏览器或在每次表单提交测试之间清除Cookie _和_ 每次使用不同的电子邮件地址。

   >[!TIP]
   >
   >最佳实践是使用包含指示该测试的内容以及时间的假电子邮件。 例如： `testing830am@test.com`.

1. 在搜索引擎上开始搜索(例如， `google.com`)，或直接导航到表单。

1. 使用唯一的电子邮件地址在您的网站上提交表单。

1. 记录提交表单时所在页面的URL以及使用的电子邮件地址。

1. 找到在您的CRM（潜在客户或联系人）中为该表单提交创建的记录，并验证是否正确创建了接触点。

>[!NOTE]
>
>您可以使用 [!DNL Marketo Measure] 库存报表，例如销售线索具有 [!DNL Marketo Measure] 接触点或查看销售线索/联系人页面布局（如果您选择使用更新页面布局） [!DNL Marketo Measure] 详细信息。 这可能需要一些时间来处理数据。
