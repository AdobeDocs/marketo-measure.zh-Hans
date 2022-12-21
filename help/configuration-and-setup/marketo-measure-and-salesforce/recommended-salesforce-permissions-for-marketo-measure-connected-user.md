---
unique-page-id: 18874696
description: 建议 [!DNL Salesforce] 的权限 [!DNL Marketo Measure] 连接的用户 —  [!DNL Marketo Measure]  — 产品文档
title: 建议 [!DNL Salesforce] 的权限 [!DNL Marketo Measure] 连接的用户
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# 建议 [!DNL Salesforce] 的权限 [!DNL Marketo Measure] 连接的用户 {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] 通过连接的 [!DNL Salesforce] 用户 [!DNL Marketo Measure] 应用程序。

要将接触点数据推送到 [!DNL Salesforce] 实例中，连接的用户必须具有 [!DNL Marketo Measure] 自定义对象（即买方接触点和买方归因接触点）以及标准 [!DNL Salesforce] 对象，如潜在客户和联系人(请参阅 [[!DNL Marketo Measure] 在Salesforce中](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] 管理员用户许可证可以用作连接的用户，因为默认情况下，他们通常具有必要的数据权限。 但是，您的团队可能希望使用集成用户或专用 [!DNL Salesforce] 用户跟踪 [!DNL Marketo Measure] 在您的实例中。

我们建议您使用以下权限来确保 [!DNL Marketo Measure] 数据准确流动：

* [!DNL Marketo Measure] 专用用户的管理员权限集

受管权限集使SFDC管理员能够从中创建、读取、写入、删除记录 [!DNL Marketo Measure] 对象。

* 查看和编辑已转换的潜在客户权限集

这允许 [!DNL Marketo Measure] 以装饰销售线索。 如果未启用此权限集，则可能会存在大量数据跟踪空白。 您可以在 [[!DNL Salesforce Trailblazer] 社区](https://help.salesforce.com/articleView?id=leads_view_edit_converted.htm&amp;type=5).

* [!DNL Salesforce] 营销用户复选框

的 [!UICONTROL Marketing User] 复选框允许用户创建营销活动并使用营销活动导入向导。 如果未选择此选项，则用户只能查看营销活动和高级营销活动设置，编辑单个潜在客户或联系人的营销活动历史记录，并运行营销活动报表。 [!DNL Marketo Measure] 需要能够读取和写入营销活动对象。

**其他疑难解答**

如果 [!DNL Marketo Measure] 在读取或写入数据时仍遇到问题，调查以下内容可能会有所帮助：

* 访问 [!DNL Salesforce] 队列

如果专用用户无权访问队列中的潜在客户，则无法使用 [!DNL Marketo Measure] 数据。 为此，您可以在层次结构中拥有允许访问队列的角色，或单独授予用户访问权限。

* 字段级别安全性和无障碍性

字段级别安全性和字段可访问性是相关的，但有一些关键区别。 字段级别安全性为给定配置文件定义字段可见性，而字段辅助功能则根据字段级别安全性和页面布局配置确定字段是否可编辑。 使用 [!DNL Marketo Measure] 包的权限集，您将收到必需的字段对象安全设置。 在某些情况下，为了具有正确的字段可访问性，连接的用户将需要具有 [!DNL Marketo Measure] 字段。 [!DNL Marketo Measure] 布局上的字段允许 [!DNL Marketo Measure] 映射到的数据 [!DNL Salesforce]. 这取决于您的特定 [!DNL Salesforce] 环境。

每个组织的 [!DNL Salesforce] 具有个人需求，但我们会向您提供平衡需求的要求 [!DNL Marketo Measure] 使用安全协议进行访问需求。 毫不犹豫地联系 [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}。
