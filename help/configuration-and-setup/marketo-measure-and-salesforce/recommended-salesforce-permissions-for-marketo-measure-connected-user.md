---
unique-page-id: 18874696
description: 推荐 [!DNL Salesforce] 权限： [!DNL Marketo Measure] 连接的用户 —  [!DNL Marketo Measure]  — 产品文档
title: 推荐 [!DNL Salesforce] 权限： [!DNL Marketo Measure] 连接的用户
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# 推荐 [!DNL Salesforce] 权限： [!DNL Marketo Measure] 连接的用户 {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] 通过连接的发送和接收数据 [!DNL Salesforce] 用户属于 [!DNL Marketo Measure] 应用程序。

为了将接触点数据推送到 [!DNL Salesforce] 实例中，连接的用户必须有权访问 [!DNL Marketo Measure] 自定义对象（即买方接触点和买方归因接触点）以及标准 [!DNL Salesforce] 潜在客户和联系人等对象(请参阅 [[!DNL Marketo Measure] 在Salesforce中](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] 管理员用户许可证可以作为连接的用户，因为默认情况下，他们通常具有必要的数据权限。 但是，您的团队可能更喜欢使用集成用户或专用的 [!DNL Salesforce] 用于跟踪以下各项影响的用户许可证： [!DNL Marketo Measure] 在您的实例上。

我们建议使用以下权限，以确保 [!DNL Marketo Measure] 数据准确流动：

* [!DNL Marketo Measure] 为专用用户设置的管理员权限

托管权限集使SFDC管理员能够从中创建、读取、写入和删除记录 [!DNL Marketo Measure] 对象。

* 查看和编辑转化后的潜在客户权限集

这允许 [!DNL Marketo Measure] 以便在潜在客户转换为联系人后对其进行修饰。 如果未启用此权限集，则可能存在显着的数据跟踪缺口。 欲知更多信息，请参阅 [[!DNL Salesforce Trailblazer] 社区](https://help.salesforce.com/articleView?id=leads_view_edit_converted.htm&amp;type=5).

* [!DNL Salesforce] “营销用户”复选框

此 [!UICONTROL Marketing User] 通过复选框，用户可创建营销活动并使用营销活动导入向导。 如果未选择此选项，则用户只能查看营销活动和高级营销活动设置，编辑单个潜在客户或联系人的营销活动历史记录，以及运行营销活动报表。 [!DNL Marketo Measure] 需要能够读取和写入campaign对象。

**其他疑难解答**

如果 [!DNL Marketo Measure] 仍在读取或写入数据时遇到问题，调查以下问题可能会有所帮助：

* 访问 [!DNL Salesforce] 队列

如果专用用户无权访问队列中的潜在客户，则它无法通过以下方式修改潜在客户 [!DNL Marketo Measure] 数据。 可以通过在层次结构中拥有允许访问队列或单独授予用户访问权限的角色来实现这一点。

* 字段级安全性和可访问性

字段级安全性和字段可访问性是相关的，但有一些主要区别。 字段级安全性定义给定用户档案的字段可见性，而字段可访问性根据字段级安全性和页面布局配置确定字段是否可编辑。 使用 [!DNL Marketo Measure] 包的权限集，您将收到必需的字段对象安全设置。 在某些情况下，为了具有正确的字段可访问性，连接的用户需要具有 [!DNL Marketo Measure] 页面布局中的字段。 [!DNL Marketo Measure] 布局中的字段允许 [!DNL Marketo Measure] 要映射到的数据 [!DNL Salesforce]. 这取决于您的特定用户 [!DNL Salesforce] 环境。

每个组织的 [!DNL Salesforce] 有不同的需求，但我们会为您提供平衡需求的 [!DNL Marketo Measure] 访问需要安全协议。 请随时联系 [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
