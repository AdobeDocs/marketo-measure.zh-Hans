---
unique-page-id: 18874696
description: 为 [!DNL Marketo Measure] 连接的用户 —  [!DNL Marketo Measure]推荐的 [!DNL Salesforce] 权限
title: 为 [!DNL Marketo Measure] 连接的用户推荐的 [!DNL Salesforce] 权限
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 0%

---

# 建议的[!DNL Marketo Measure]已连接用户的[!DNL Salesforce]权限 {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure]通过[!DNL Marketo Measure]应用内连接的[!DNL Salesforce]用户发送和接收数据。

要将接触点数据推送到[!DNL Salesforce]实例，连接的用户必须有权访问[!DNL Marketo Measure]自定义对象(即Buyer Touchpoint和Buyer Attribution Touchpoint)以及商机和联系人等标准[!DNL Salesforce]对象。 在Salesforce[&#128279;](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)中查看[!DNL Marketo Measure] 。

[!DNL Salesforce]管理员用户许可证可作为已连接的用户，因为默认情况下，这些用户通常具有必要的数据权限。 但是，您的团队可能更喜欢使用集成用户或专用的[!DNL Salesforce]用户许可证来跟踪[!DNL Marketo Measure]对您实例的影响。

我们建议使用以下权限，以确保[!DNL Marketo Measure]数据准确流动：

* 为专用用户设置了[!DNL Marketo Measure]管理员权限

托管权限集使SFDC管理员能够从[!DNL Marketo Measure]对象创建、读取、写入和删除记录。

* 查看和编辑转化后的潜在客户权限集

这允许[!DNL Marketo Measure]在潜在客户转换为联系人后对其进行修饰。 如果未启用此权限集，则可能存在显着的数据跟踪缺口。 您可以在[[!DNL Salesforce Trailblazer] 社区](https://help.salesforce.com/s/articleView?language=en_US&id=leads_view_edit_converted.htm&type=5)中找到更多信息。

* [!DNL Salesforce]营销用户复选框

通过[!UICONTROL Marketing User]复选框，用户可创建营销活动并使用营销活动导入向导。 如果未选择此选项，则用户只能查看营销活动和高级营销活动设置，编辑单个潜在客户或联系人的营销活动历史记录，以及运行营销活动报表。 [!DNL Marketo Measure]必须能够读取和写入营销活动对象。

**其他疑难解答**

如果[!DNL Marketo Measure]在读取或写入数据时仍然遇到问题，则调查以下内容可能会有所帮助：

* 访问[!DNL Salesforce]队列

如果专用用户无权访问队列中的潜在客户，则它无法修改包含[!DNL Marketo Measure]数据的潜在客户。 可以通过在层次结构中拥有允许访问队列或单独授予用户访问权限的角色来实现这一点。

* 字段级安全性和可访问性

字段级安全性和字段可访问性是相关的，但有一些主要区别。 字段级安全性定义给定用户档案的字段可见性，而字段可访问性根据字段级安全性和页面布局配置确定字段是否可编辑。 使用[!DNL Marketo Measure]包的权限集，您将收到必需的字段对象安全设置。 有时，要获得正确的字段可访问性，所连接的用户需要在页面布局上具有[!DNL Marketo Measure]字段。 布局中的[!DNL Marketo Measure]字段允许[!DNL Marketo Measure]数据映射到[!DNL Salesforce]。 这取决于您的特定[!DNL Salesforce]环境。

每个组织的[!DNL Salesforce]都有各自的需求，但我们为您提供平衡安全协议与[!DNL Marketo Measure]访问需求的要求。 请随时联系[[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。
