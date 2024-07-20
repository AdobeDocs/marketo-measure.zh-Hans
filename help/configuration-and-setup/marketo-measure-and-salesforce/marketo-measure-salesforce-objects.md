---
unique-page-id: 18874582
description: '[!DNL Marketo Measure] Salesforce对象 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Salesforce对象'
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
feature: Salesforce
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce对象 {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

在[!DNL Salesforce] (SFDC)中安装[!DNL Marketo Measure]时，添加了多个自定义[!DNL Marketo Measure]对象。 本文为其中一些自定义[!DNL Marketo Measure]对象提供了说明。 [!DNL Marketo Measure]添加到[!DNL Salesforce]的某些对象是：

* [Buyer Touchpoint](#touchpoint)
* [Buyer Attribution Touchpoint](#attribution)
* [[!DNL Marketo Measure]人](#person)
* [[!DNL Marketo Measure] A/B测试](#ab)
* [[!DNL Marketo Measure]个事件](#events)

由要跟踪的内容捕获的接触点将写入安装[!DNL Bizible Salesforce]包创建的自定义对象。

[!DNL Marketo Measure]对象与特定标准[!DNL Salesforce]对象相关。 这允许您一起报告[!DNL Marketo Measure]和[!DNL Salesforce]对象。 下表显示了[!DNL Marketo Measure]对象与哪个[!DNL Salesforce]对象相关。

![](assets/1-1.png)

## Buyer Touchpoint {#buyer-touchpoint}

[!UICONTROL Buyer Touchpoint] (BT)对象讲述个人的营销故事。 它包含与潜在客户和联系人生成的营销接触点相关的所有数据。 BT会显示相关信息，例如接触点来自哪个营销渠道，或者广告促销活动将该特定潜在客户/联系人带到您的网站。

BT对象作为&#x200B;**相关列表**&#x200B;显示在“潜在客户”和“联系人”页面上（请参阅下图）。

![](assets/2-1.png)

BT Related List显示属于Lead或Contact的所有接触点。 列表中包含自定义[!DNL Marketo Measure]字段，这些字段提供有关每个接触点的更多详细信息。 单击Buyer Touchpoint ID号会将您定向到Buyer Touchpoint详细信息页面，该页面提供了有关接触点的更多详细信息，如负责人/联系人在Web会话期间访问的第一个网页（**登陆页面**）。

## Buyer Attribution Touchpoint {#buyer-attribution-touchpoint}

[!UICONTROL Buyer Attribution Touchpoint]对象讲述与商机相关的联系人的营销交互情况。 它显示与营销接触点相关的&#x200B;*归因*&#x200B;数据。 此对象允许您查看有多少收入点数归于每个营销接触点。 您使用的归因模型类型将确定归属于接触点的收入百分比。

只有在创建了Opportunity之后，才会创建买方归因接触点(BAT)，该Opportunity与具有Buyer Touchpoint (BT)数据的联系人相关。 如果没有机会，将不会创建BAT。 创建Opportunity后，BAT对象将使用Opportunity上的[!DNL Salesforce] *Amount*&#x200B;字段来了解有多少收入归因于接触点。

如果您使用[自定义金额字段](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)来显示商机对象上的收入，则必须创建&#x200B;**工作流**。 [!DNL Marketo Measure]无法读取在自定义金额字段中显示的信息，因此无法填充接触点上的收入归因数据。 此工作流将使用&#x200B;**[!DNL Marketo Measure]机会金额**&#x200B;字段（2}自定义字段之一）将收入值从自定义金额字段映射到机会金额字段。[!DNL Marketo Measure]

![](assets/3-1.png)

BAT对象作为相关列表显示在[!UICONTROL Opportunity]、[!UICONTROL Contact]和[!UICONTROL Account]对象中。 此列表显示具有归因数据属于某个Opportunity的所有接触点。 单击Buyer Attribution Touchpoint ID会将您定向到Buyer Attribution Touchpoint详细信息页面。 在这里，您将能够查看更多具体的归因数据和有关接触点来源的信息(与Buyer Touchpoint对象中提供的内容类似)。

## [!DNL Marketo Measure]人 {#marketo-measure-person}

[!DNL Marketo Measure]人员对象将潜在客户和联系人对象关联在一起。 开箱即用的Salesforce不提供在同一报告中使用Lead和Contact对象创建报告的选项。 通过关联潜在客户和联系人对象，[!DNL Marketo Measure]人员允许您在同一报表中报告这两个对象。 当Lead已转换为Contact时，这尤其有用。 在[!DNL Marketo Measure]人员记录中，您将看到对应潜在客户和/或联系人记录的查找、与人员关联的接触点的相关列表以及人员ID（始终是潜在客户/联系人的电子邮件地址）。 由于[!DNL Marketo Measure]人员与潜在客户和联系人对象相关，因此将永远不会有与Buyer Attribution Touchpoint关联的[!DNL Marketo Measure]人员记录。 以下是Salesforce中[!DNL Marketo Measure]人员记录的示例：

![](assets/4.png)

## [!DNL Marketo Measure] A/B测试 {#marketo-measure-a-b-test}

如果您通过[!DNL Optimizely]或VWO (Visual Web Optimizer)运行A/B测试，则可以将这些帐户连接到您的[!DNL Marketo Measure]帐户以在Salesforce中查看A/B测试数据。 [!DNL Marketo Measure] A/B测试对象基本上允许您从Optimizly/VWO中获取A/B测试数据，并将该数据关联到潜在客户和联系人。

![](assets/5.png)

[!DNL Marketo Measure] A/B测试对象在[!UICONTROL Leads]、[!UICONTROL Contacts]和[!UICONTROL Opportunity]页面上显示为相关列表。 该列表显示了您正在优化或VWO中运行的所有试验和变体，并允许您查看与特定潜在客户和联系人相关的试验/变体。

## [!DNL Marketo Measure]个事件 {#marketo-measure-events}

[!DNL Marketo Measure]事件对象允许您跟踪网站上发生的特定事件。 要跟踪您的网站上发生的特定事件，除[!DNL Marketo Measure] Javascript之外，还必须将自定义代码添加到您的页面中。 捕获的信息将显示在[!DNL Marketo Measure]对象相关列表中，该列表可在[!UICONTROL Leads]、[!UICONTROL Contacts]和[!UICONTROL Opportunity]页面上找到。 [!DNL Marketo Measure]事件对象&#x200B;*未与归因数据绑定*。 此对象的目的是查看用户是否在您的网站上执行特定操作。

## [!DNL Marketo Measure]字段 {#marketo-measure-fields}

由[!DNL Marketo Measure] JavaScript捕获的数据将被推送到[!DNL Marketo Measure]对象内的自定义[!DNL Marketo Measure]字段中。 某些字段仅存在于某些对象中。 您可以查看[[!DNL Marketo Measure]字段]](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md)的[词汇表以及相关 [!DNL Marketo Measure] 对象](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md)的[可视化图表。

## [!DNL Marketo Measure]报告和仪表板 {#marketo-measure-reports-and-dashboards}

添加到您的[!DNL Salesforce]的[!DNL Marketo Measure]报表和功能板为您提供现成的报表和数据可视化功能。 这些是基本的[!DNL Marketo Measure]报告，使您能够快速组织、分析和了解接触点数据。
