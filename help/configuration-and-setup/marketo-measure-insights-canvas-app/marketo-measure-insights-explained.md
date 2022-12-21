---
unique-page-id: 18874676
description: '"[!DNL Marketo Measure] 分析说明 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] 分析说明”'
exl-id: d479a15f-4c92-4302-8ce8-6487645012e1
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---

# [!DNL Marketo Measure] 分析说明 {#marketo-measure-insights-explained}

了解 [!DNL Marketo Measure] 中的分析视图 [!DNL Salesforce]，包括不同图标所表示的内容以及如何使用该功能。 此功能对于查看潜在客户、联系人或帐户的前20个会话非常有用。

在 [!DNL Marketo Measure] javascript并在您的网站上填写表格，该人员将成为您系统中的潜在客户，我们会将他们的数字营销数据推送到您的Salesforce(SFDC)组织。 发生此情况时，您会在 [!DNL Marketo Measure] 潜在客户/联系人/机会/帐户对象上的潜在客户分析部分(Canvas App)。

首先，您将在分析的中部看到访客在您的网站上已进行的会话数。 您可以滚动浏览这些会话并随意导航。

![](assets/1.png)

如果单击分析中上半部分的“全部”，则可以查看所有会话的汇总。 在这里，您将了解各个会话的日期、这些会话的推动者是哪些渠道或来源，以及一组指定更多信息的图标。

你首先会看到的是英国《金融时报》或LC的图标。 这些值表示所列会话的接触点位置。 具体而言，FT代表“首次接触”，LC代表“创造铅”。 您可以有多个会话，但只能有一个接触点是FT或LC。 您永远找不到与一个人关联的多个FT或LC。

看起来像纸张的图标表示在会话中发生了页面查看。 每个会话都可能包含此图标。

![](assets/2.png)

看起来像烧杯的图标表示发生了A/B测试实验。 此时，我们将与Optimizely和VWO集成。 通过此集成，我们能够推送用户在其特定会话中看到的实验和变体。

![](assets/3.png)

如果单击任何特定会话（可以通过单击会话的实际日期或分组会话的中上部分来执行此操作），您将能够看到会话详细信息。 在每个会话中，您可以按日期和时间查看用户查看的所有特定页面。

![](assets/4.png)

在每个会话的右侧，您可以看到我们要推送的更多粒度营销数据 [!DNL Marketo Measure] 字段。 在此示例中，您可以看到“广告组”、“广告内容”、“促销活动”、“关键词”、“媒体”。 您还可以向下滚动，以查看 [!DNL Marketo Measure] 我们提供的数据。

最后，当某人拥有大量会话时，您可以在 [!UICONTROL Insights] 以在您的网站上查找其参与的特定部分。 您可以按 [!UICONTROL Touchpoint Position] 例如。

您还可以按页面查看次数、AB测试或Forms进行搜索。
