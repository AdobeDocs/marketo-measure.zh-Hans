---
unique-page-id: 18874676
description: '"[!DNL Marketo Measure] 见解解释 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] 见解解释”'
exl-id: d479a15f-4c92-4302-8ce8-6487645012e1
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---

# [!DNL Marketo Measure] 解释的见解 {#marketo-measure-insights-explained}

了解 [!DNL Marketo Measure] 中的分析视图 [!DNL Salesforce]，包括不同图标表示的内容以及使用该功能的方法。 此功能非常有助于查看潜在客户、联系人或客户的前20场会议。

当某人被 [!DNL Marketo Measure] javascript并在您的网站上填写表单，则该人员将成为您系统中的潜在客户，我们会将他们的数字营销数据推送到Salesforce (SFDC)组织。 发生这种情况时，您会看到接触点数据填充在 [!DNL Marketo Measure] Lead/Contact/Opportunity/Account对象上的Lead Insights部分（一个画布应用程序）。

首先，您将在洞察力的中间部分看到访客在您网站上的会话数。 您可以随意滚动浏览这些会话和导航。

![](assets/1.png)

如果您单击分析中上角的“全部”，可以查看所有会话的汇总。 在这里，您将了解各个会话的日期、驱动这些会话的渠道或来源以及指定更多信息的一组图标。

您首先看到的是FT或LC图标。 这些表示所列会话的接触点位置。 具体来说，FT代表First Touch，LC代表Lead Creation。 您可以有多个会话，但只有一个接触点可以是FT或LC。 您永远不会找到与一个人相关联的多个FT或LC。

看起来像纸张的图标表示页面查看发生在会话中。 每个会话都可能包含此图标。

![](assets/2.png)

看起来像烧杯的图标表示发生了A/B测试试验。 目前，我们与Optimizy和VWO进行了集成。 通过此集成，我们能够推送用户在其特定会话中看到的试验和变体。

![](assets/3.png)

如果单击任何特定会话（可以通过单击会话的实际日期或分组会话的中上部分单击该日期来执行此操作），您将能够查看会话详细信息。 在每个会话中，您可以看到用户查看的所有特定页面，这些页面按日期和时间排序。

![](assets/4.png)

在每个会话的右侧，您可以看到我们推送的更多粒度营销数据 [!DNL Marketo Measure] SFDC中的字段。 在此示例中，您可以看到广告组、广告内容、促销活动、关键词、媒介。 您还可以向下滚动以查看 [!DNL Marketo Measure] 我们提供的数据。

最后，一旦有人拥有大量会话，您便可以在中使用一些过滤器 [!UICONTROL Insights] 以在您的网站上查找其参与的特定部分。 您可以按以下项过滤 [!UICONTROL Touchpoint Position] 例如。

您还可以按页面查看次数、AB测试或Forms进行搜索。
