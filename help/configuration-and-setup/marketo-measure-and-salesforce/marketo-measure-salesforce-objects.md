---
unique-page-id: 18874582
description: '"[!DNL Marketo Measure] Salesforce对象 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] Salesforce对象”'
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce对象 {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>您可能会看到指定“[!DNL Marketo Measure]“ ”，但仍会在您的CRM中看到“Bizible”。 我们正在努力更新该版本，并且该品牌重命名将很快地反映在您的CRM中。

When [!DNL Marketo Measure] 安装在 [!DNL Salesforce] (SFDC)，多个自定义 [!DNL Marketo Measure] 添加对象。 本文对其中一些自定义进行了说明 [!DNL Marketo Measure] 对象。 某些对象 [!DNL Marketo Measure] 添加到 [!DNL Salesforce] 为：

* [买方接触点](#touchpoint)
* [买方归因接触点](#attribution)
* [[!DNL Marketo Measure] 人员](#person)
* [[!DNL Marketo Measure] A/B测试](#ab)
* [[!DNL Marketo Measure] 事件](#events)

由要跟踪的内容捕获的接触点将写入由安装 [!DNL Bizible Salesforce] 包。

[!DNL Marketo Measure] 与特定标准相关的对象 [!DNL Salesforce] 对象。 这样，您便可以报告 [!DNL Marketo Measure] 和 [!DNL Salesforce] 物体一起。 下表显示了 [!DNL Salesforce] 对 [!DNL Marketo Measure] 对象与相关。

![](assets/1-1.png)

## 买方接触点 {#buyer-touchpoint}

的 [!UICONTROL Buyer Touchpoint] (BT)对象用于讲述个人的营销故事。 它存储与潜在客户和联系人生成的营销接触点相关的所有数据。 BT可向您显示以下信息：接触点来自哪个营销渠道，或广告营销活动将该特定潜在客户/联系人带到您的网站。

BT对象在“潜在客户”和“联系人”页面上以 **相关列表** （请参阅下图）。

![](assets/2-1.png)

BT相关列表显示属于潜在客户或联系人的所有接触点。 列表内是自定义的 [!DNL Marketo Measure] 提供每个接触点的更多详细信息的字段。 单击购买者接触点ID号可将您指引到购买者接触点详细信息页面，该页面提供有关接触点的更多详细信息，如该Web会话期间潜在客户/联系人访问的第一个网页(**登陆页面**)。

## 买方归因接触点 {#buyer-attribution-touchpoint}

的 [!UICONTROL Buyer Attribution Touchpoint] Object讲述与机会相关的联系人的营销互动故事。 它会显示 *归因* 与营销接触点相关的数据。 此对象允许您查看每个营销接触点对应的收入点数。 您所使用的归因模型类型将确定归因到接触点的收入百分比。

只有在创建与具有买方接触点(BT)数据的联系人相关的机会后，才会创建买方归因接触点(BAT)。 如果没有Opportunity，将无法创建BAT。 创建Opportunity后，BAT对象将使用 [!DNL Salesforce] *金额* Opportunity中的字段，以了解要归因于接触点的收入。

A **工作流** 如果您使用 [自定义金额字段](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md) 显示Opportunity对象上的收入。 [!DNL Marketo Measure] 无法读取自定义金额字段中显示的信息，因此无法在接触点上填充收入归因数据。 此工作流将使用 **[!DNL Marketo Measure]机会金额** 字段， [!DNL Marketo Measure] 自定义字段，以将自定义金额字段中的收入值映射到机会金额字段。

![](assets/3-1.png)

BAT对象在 [!UICONTROL Opportunity], [!UICONTROL Contact]和 [!UICONTROL Account] 对象作为相关列表。 此列表显示所有接触点，其中归因数据属于Opportunity。 单击购买者归因接触点ID将引导您转到“购买者归因接触点详细信息”页面。 在此，您将能够查看更具体的归因数据以及有关接触点来自何处的信息（类似于从买方接触点对象提供的内容）。

## [!DNL Marketo Measure] 人员 {#marketo-measure-person}

的 [!DNL Marketo Measure] “人员对象”将“潜在客户”和“联系人”对象关联在一起。 现成，Salesforce不提供使用同一报表中的潜在客户和联系人对象创建报表的选项。 通过与潜在客户和联系对象相关， [!DNL Marketo Measure] “人员”(Person)允许您报告同一报表内的两个对象。 当潜在客户已转换为联系人时，此功能特别有用。 在 [!DNL Marketo Measure] 人员记录您将看到对相应的潜在客户和/或联系人记录的查找、与该人员关联的接触点的相关列表以及人员ID（始终是潜在客户/联系人的电子邮件地址）。 自 [!DNL Marketo Measure] 与潜在客户和联系对象相关的人员，将不会 [!DNL Marketo Measure] 与买方归因接触点绑定的人员记录。 以下是 [!DNL Marketo Measure] Salesforce中的人员记录：

![](assets/4.png)

## [!DNL Marketo Measure] A/B测试 {#marketo-measure-a-b-test}

如果您正在运行A/B测试 [!DNL Optimizely] 或VWO(Visual Web Optimizer)，则可以将这些帐户连接到您的 [!DNL Marketo Measure] 帐户，以在Salesforce中查看A/B测试数据。 的 [!DNL Marketo Measure] A/B测试对象主要允许您从Optimizely/VWO中获取A/B测试数据，并将数据绑定到Lead和Contact。

![](assets/5.png)

的 [!DNL Marketo Measure] A/B测试对象在 [!UICONTROL Leads], [!UICONTROL Contacts] 和 [!UICONTROL Opportunity] 页面。 该列表显示您通过Optimizely或VWO运行的所有实验和变量，并允许您查看与特定Lead和Contacts相关的实验/变量。

## [!DNL Marketo Measure] 事件 {#marketo-measure-events}

的 [!DNL Marketo Measure] 事件对象允许您跟踪网站上发生的特定事件。 要跟踪您网站上发生的特定事件，除了 [!DNL Marketo Measure] Javascript。 捕获的信息将显示在 [!DNL Marketo Measure] 对象相关列表，可在 [!UICONTROL Leads], [!UICONTROL Contacts] 和 [!UICONTROL Opportunity] 页面。 的 [!DNL Marketo Measure] 事件对象 *不* 关联到归因数据。 此对象的用途是查看用户是否在您的网站上执行特定操作。

## [!DNL Marketo Measure] 字段 {#marketo-measure-fields}

由 [!DNL Marketo Measure] Javascript将被推送到自定义 [!DNL Marketo Measure] 我们 [!DNL Marketo Measure] 对象。 某些字段将仅存在于某些对象中。 有关 [!DNL Marketo Measure] 字段，请 [单击此处](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md). 对于可视化图表， [!DNL Marketo Measure] 对象 [!DNL Marketo Measure] 字段与 [单击此处](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

## [!DNL Marketo Measure] 报表和功能板 {#marketo-measure-reports-and-dashboards}

的 [!DNL Marketo Measure] 添加到 [!DNL Salesforce] 提供开箱即用的报表和数据可视化功能。 这些是基本的 [!DNL Marketo Measure] 报表可让您快速组织、分析和了解接触点数据。
