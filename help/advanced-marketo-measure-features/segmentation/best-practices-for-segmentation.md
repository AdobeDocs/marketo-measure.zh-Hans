---
description: 分段的最佳实践 —  [!DNL Marketo Measure]
title: 分段的最佳实践
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
feature: Segmentation
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# 分段的最佳实践 {#best-practices-for-segmentation}

## 概述 {#overview}

[!DNL Marketo Measure]分段允许您根据您的CRM字段定义规则（本质上是过滤器），以将其分段为单独的区段。 然后，这些区段将可用于您的发现功能板以及[!DNL Salesforce]报表。

分段对于您的[!DNL Marketo Measure]帐户的使用率至关重要，尤其是在您探索讨论区中。 由于[!DNL Marketo Measure] Discover展示板受限于预先确定的筛选器集，因此分段使您能够剖析您在Discover中的数据，就像您在[!DNL Salesforce]报表中一样。

推送到[!DNL Salesforce]后，区段值将写入“区段”字段，并位于任何买方接触点报表类型中。 这允许跨两个平台进行统一报告。 区段还可以在任何接触点的“接触点详细信息”中找到。

推送到[!UICONTROL Discover]后，区段将作为可用筛选器显示在位于所有展示板上的筛选器下拉菜单中。

## 最佳实践 {#best-practice}

无论您是首次定义分段，还是只查看之前已建立的分段，请牢记以下最佳实践。

* 保持简单！
* 将区段名称与组织的命名法保持一致，即，类别=筛选器名称，区段=筛选器值
* 请勿在规则中使用公式字段
* 如有可能，请同时针对Lead/Contact和Opportunity构建分段，以便您可以在整个funnel中使用它
   * 如果您是Marketo Measure Ultimate客户，并且已将您的默认功能板对象设置为联系人，请不要使用以下两个特定于潜在客户的字段（[在此了解详情](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}）。
      * b2b.personStatus
      * b2b.isConverted
   * 并非每个区段类别都会在整个funnel中保持一致
      * 例如，“Opportunity Type”的Segment类别不会与Lead相关，但与“Region”相关的Segment可能是可以在funnel中定义的类别
* 考虑您当前希望对数据进行切片的方式，无论数据是在CRM还是BI工具中，都可以考虑将其构建为[!DNL Marketo Measure]中的区段，以便您可以在Discover中具有相同的报表

## 维护的最佳实践 {#best-practice-for-maintenance}

每年至少两次查看您的区段以确保您的区段处于最新状态。 作为最佳实践，我们建议在您的[!UICONTROL Segments]帐户设置的“[!DNL Marketo Measure]”选项卡中查看您的规则，并在[!DNL Salesforce]中获取报表以检查正在运行的区段。 这些步骤将帮助您和您的团队对细分以及随后的[!DNL Marketo Measure]报表充满信心。

可能触发审阅您的分段的其他原因包括……

* 您的营销团队中的人员调整
* 更改了用于定义区段的字段
* 已建立之分部之增加或变动

>[!MORELIKETHIS]
>
>[如何设置自定义分段](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
