---
unique-page-id: 18874684
description: 促销活动同步日期 —  [!DNL Marketo Measure]
title: Campaign同步日期
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
feature: Channels
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# Campaign同步日期 {#campaign-sync-dates}

了解Campaign同步日期功能的功能，并提供此功能的一些用例。

>[!NOTE]
>
>本文介绍了一个过时的流程。 我们鼓励用户使用[新的、改进的应用程序内进程](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}。

需要&#x200B;**[!DNL Marketo Measure]包： 6.9或更高版本**

此功能由[!DNL Salesforce]促销活动对象上的两个简单日期字段组成：

* 接触点开始日期
* 接触点结束日期

在特定营销活动上启用购买者接触点后，您可以利用Campaign同步日期为单个营销活动设置接触点日期参数。 因此，如果您要添加的接触点结束日期是2017年3月1日，则[!DNL Marketo Measure]将仅在该日期之前添加到促销活动的促销活动成员上创建接触点。 [!DNL Marketo Measure]不会为2017年3月1日之后添加的活动成员创建接触点。

![](assets/1.gif)

同样，如果您要在营销活动中添加接触点开始日期（比如2017年1月1日），则[!DNL Marketo Measure]不会在2017年1月1日之前添加到营销活动的营销活动成员上创建接触点。 如果添加接触点结束日期，则无需添加接触点开始日期，反之亦然。

## 用例 {#use-cases}

**正在回填接触点**

有时，营销团队可能会错过向特定营销工作添加utm参数。 促销活动同步日期将允许您（如果您使用SFDC促销活动进行在线工作）回填一些缺失的数据。 假设您运行的是5月1日开始的电子邮件营销活动，但您的团队直到5月15日才为该电子邮件营销活动添加utm参数。 如果您通过SFDC营销活动跟踪电子邮件转化，则可将接触点结束日期设置为5月15日，并为该营销活动的“已回复”成员启用接触点。 此操作将告知[!DNL Marketo Measure]为截至5月15日的所有响应创建接触点。

**可追溯的Campaign会员资格接触点**

如果您是新[!DNL Marketo Measure]客户，则可能有兴趣提供一些通过SFDC促销活动跟踪的营销数据。 但是，如果您要为联机SFDC促销活动启用接触点，则可能会遇到重复计算归因的问题，因为[!DNL Marketo Measure]会自动为您的联机营销工作创建接触点。 为避免重复计算数据，您可以使用Campaign接触点结束日期对[!DNL Marketo Measure]在SFDC营销活动中创建的接触点日期设置限制。 例如，如果您要为已在SFDC中跟踪的Social营销活动添加追溯转化，但您知道已在7月1日添加[!DNL Marketo Measure]JavaScript（该活动正在创建在线接触点），则可以编辑Social SFDC营销活动以包含等于7月1日的接触点结束日期，并为该营销活动启用买方接触点。

接触点结束日期可能还有许多其他用例。 如果您需要帮助来了解具体情况，请随时联系[Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。
