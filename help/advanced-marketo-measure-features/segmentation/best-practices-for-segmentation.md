---
description: 分段的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 分段的最佳实践
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
feature: Segmentation
source-git-commit: 7bb458941e513b6155b834d27f76f0b5df4e0a09
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# 分段的最佳实践 {#best-practices-for-segmentation}

## 概述 {#overview}

[!DNL Marketo Measure] 分段允许您根据CRM字段定义规则（本质上是过滤器），以将其分段为单独的区段。 然后，这些区段将可用于您的探索功能板以及您的 [!DNL Salesforce] 报表。

分段对于利用您的资源至关重要 [!DNL Marketo Measure] 帐户，尤其是在您发现讨论区内。 因为 [!DNL Marketo Measure] 发现展示板仅限于一组预先决定的过滤器，通过分段，您可以在发现中剖析数据，就像在发现中一样 [!DNL Salesforce] 报表。

推送到 [!DNL Salesforce]，则区段值将写入“区段”字段，并且位于任何买方接触点报表类型中。 这允许跨两个平台进行统一报告。 区段还可以在任何接触点的“接触点详细信息”中找到。

推送到“发现”后，区段将作为可用过滤器显示在位于所有展示板上的过滤器下拉菜单中。

## 最佳实践 {#best-practice}

无论您是首次定义分段，还是只查看之前已建立的分段，请牢记以下最佳实践。

* 保持简单！
* 将区段名称与组织的命名法保持一致，即，类别=筛选器名称，区段=筛选器值
* 请勿在规则中使用公式字段
* 如有可能，请同时在Lead/Contact和Opportunity上构建分段，以便您可以在整个漏斗中使用它
   * 如果您是Marketo Measure Ultimate客户并将您的默认功能板对象设置为Contact，请不要使用下面两个特定于Lead的字段([在此处了解详情](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"})。
      * b2b.personStatus
      * b2b.isConverted
   * 并非每个区段类别在整个漏斗中都保持一致
      * 例如，“Opportunity Type”的区段类别不会与Lead相关，但与“Region”相关的区段可能是可以在整个漏斗中定义的类别
* 考虑您当前希望对数据进行切片的方式，无论它位于CRM还是BI工具中，都可以考虑将其构建为中的区段 [!DNL Marketo Measure] 这样您便可以在发现中使用相同的报表

## 维护的最佳实践 {#best-practice-for-maintenance}

每年至少两次查看您的区段以确保您的区段处于最新状态。 作为最佳实践，我们建议您在以下位置查看规则：[!UICONTROL Segments]的&#39;选项卡 [!DNL Marketo Measure] 帐户设置以及提取报表 [!DNL Salesforce] 以查看您的区段的实际操作情况。 这些步骤将帮助您和您的团队对您的细分以及随后的 [!DNL Marketo Measure] 报表。

可能触发审阅您的分段的其他原因包括……

* 您的营销团队中的人员调整
* 更改了用于定义区段的字段
* 已建立之分部之增加或变动

>[!MORELIKETHIS]
>
>[如何设置自定义分段](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
