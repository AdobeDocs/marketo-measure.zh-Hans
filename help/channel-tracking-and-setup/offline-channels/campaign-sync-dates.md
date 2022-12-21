---
unique-page-id: 18874684
description: 促销活动同步日期 —  [!DNL Marketo Measure]  — 产品文档
title: 促销活动同步日期
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# 促销活动同步日期 {#campaign-sync-dates}

了解Campaign同步日期功能的功能，并为此功能提供一些用例。

**[!DNL Marketo Measure]需要包：6.9或更高版本**

此功能由 [!DNL Salesforce] 营销活动对象：

* 接触点开始日期
* 接触点结束日期

在特定促销活动上启用买方接触点后，促销活动同步日期将允许您在单个促销活动上设置接触点日期参数。 因此，如果您要在2017年3月1日添加接触点结束日期， [!DNL Marketo Measure] 将仅在该日期之前添加到营销活动的营销活动成员上创建接触点。 [!DNL Marketo Measure] 将不会为2017年3月1日之后添加的营销活动成员创建接触点。

![](assets/1.gif)

同样，如果您要在营销活动上添加接触点开始日期（例如，2017年1月1日），则 [!DNL Marketo Measure] 不会在2017年1月1日之前添加到营销活动的营销活动成员上创建接触点。 如果添加接触点结束日期，则无需添加接触点开始日期，反之亦然。

## 用例 {#use-cases}

**回填接触点**

有时，营销团队可能会错过向特定营销工作添加utm参数。 促销活动同步日期允许您（如果您使用SFDC促销活动进行在线工作）回填一些遗漏的数据。 假设您运行的电子邮件促销活动始于5月1日，但您的团队直到5月15日才在该电子邮件促销活动上添加utm参数。 如果您通过SFDC营销活动跟踪电子邮件转化，则可以在该营销活动上设置5月15日的接触点结束日期，并为“已响应”营销活动成员启用接触点。 此操作将说明 [!DNL Marketo Measure] 为所有这些响应创建接触点，直到5月15日。

**可回溯的促销活动成员资格接触点**

如果你是新来的 [!DNL Marketo Measure] 客户，您可能有兴趣通过SFDC促销活动获取您跟踪的一些营销数据。 但是，如果要为在线SFDC促销活动启用接触点，则可能会遇到重复计数归因的问题，因为 [!DNL Marketo Measure] 自动为您的在线营销工作创建接触点。 为避免重复计数数据，您可以使用促销活动接触点结束日期来设置由 [!DNL Marketo Measure] 在SFDC营销活动上。 例如，如果您想要为您在SFDC中跟踪的社交促销活动添加追溯转化，但您了解已将 [!DNL Marketo Measure] JavaScript（正在创建在线接触点），然后您可以编辑Social SFDC促销活动以包含等于7月1日的接触点结束日期，并为该促销活动启用购买者接触点。

接触点结束日期可能还有许多其他用例。 如果你需要帮助找出具体情况，请毫不犹豫地联系 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}。

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 大学：营销活动和营销活动成员字段](https://learn.bizible.com/2-bizible-customization/137720https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
