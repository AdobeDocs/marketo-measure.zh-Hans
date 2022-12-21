---
description: 分段最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 分段最佳实践
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# 分段最佳实践 {#best-practices-for-segmentation}

## 概述 {#overview}

[!DNL Marketo Measure] 分段允许您根据CRM字段定义基本上是过滤器的规则，以将它们存储到单个区段中。 然后，这些区段将可在您的Discover功能板以及 [!DNL Salesforce] 报表。

分段对于您的 [!DNL Marketo Measure] 帐户，特别是在Discover展示板中。 因为 [!DNL Marketo Measure] Discover展示板仅限于预定的一组过滤器，通过分段，您可以像在中一样在Discover中分析数据 [!DNL Salesforce] 报表。

推送到时 [!DNL Salesforce]，区段值将写入“区段”字段，并位于任何买方接触点报表类型内。 这允许跨两个平台进行统一报告。 此区段还可在任何接触点的“接触点详细信息”中找到。

将区段推送到Discover后，所有展示板上的过滤器下拉菜单中将显示为可用过滤器。

## 最佳实践 {#best-practice}

无论您是首次定义分段，还是仅查看之前已建立的分段，请牢记以下最佳实践。

* 保持简单！
* 将区段名称与组织的命名方式保持一致，即类别=过滤器名称、区段=过滤器值
* 请勿在规则中使用公式字段
* 尽可能地，根据潜在客户/联系人和机会构建分段，以便您在整个漏斗中使用分段
   * 并非每个区段类别都会在整个漏斗中保持一致
      * 例如，“机会类型”的区段类别不会与潜在客户相关，但与“区域”相关的区段可能是整个漏斗中可定义的类别
* 请考虑您当前喜欢的数据切片方式，无论它位于CRM还是BI工具中，都应考虑将此数据作为区段在 [!DNL Marketo Measure] 以便您在Discover中拥有相同的报表

## 维护最佳实践 {#best-practice-for-maintenance}

每年至少审查两次您的区段，可确保区段是最新的。 作为最佳实践，我们建议在“[!UICONTROL Segments]“ ”选项卡 [!DNL Marketo Measure] 帐户设置，以及在 [!DNL Salesforce] 查看区段的实际操作情况。 这些步骤将帮助您和您的团队对您的细分以及随后的细分有信心 [!DNL Marketo Measure] 报表。

可能会触发对您的区段进行审核的其他原因包括……

* 营销团队的营业额
* 对用于定义区段的字段所做的更改
* 已建立的区段的添加或更改

>[!MORELIKETHIS]
>
>[如何设置自定义分段](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
