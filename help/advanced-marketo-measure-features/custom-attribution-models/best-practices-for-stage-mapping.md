---
description: 阶段映射的最佳实践 —  [!DNL Marketo Measure]
title: 阶段映射的最佳实践
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
feature: Tracking, Custom Models
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# 阶段映射的最佳实践 {#best-practices-for-stage-mapping}

## 概述 {#overview}

[!DNL Marketo Measure]帐户的阶段映射部分概述了[!DNL Marketo Measure]自动从您的CRM中提取的阶段，以及您在使用自定义归因模型时定义的任何自定义阶段。 [!DNL Marketo Measure]数据的有效性取决于这些阶段的顺序是否正确，以便[!DNL Marketo Measure]能够准确地了解您的funnel以及记录在整个所述funnel中的进度。

在[!DNL Marketo Measure]实例的“阶段映射”部分中，您将看到CRM中的活动阶段和非活动阶段。 根据您目前的funnel情况，尽最大努力对所有阶段进行排序。

本节中管理的其他功能是Funnel暂存，它使您能够向funnel添加暂存而不应用归因。 funnel暂存将作为接触点进行跟踪，并填充到CRM中的接触点位置字段中。 这些Funnel暂存器还将在[!DNL Marketo Measure]发现中的各个历程展示板中呈现。

## 最佳实践 {#best-practices}

无论您是首次评估暂存映射，还是只审查funnel订单，务必要记住以下最佳实践。

* 秩序就是一切！
   * 考虑到CRM中[!DNL Marketo Measure]同时处于活动和非活动阶段，请确认任何可用于潜在客户/联系人或商机的阶段都分组在一起并相应地排序
* 定义自定义阶段时，请确保为用于定义阶段的任何字段启用字段历史记录跟踪
* 不要使用公式字段定义自定义阶段
   * 布尔字段是最佳实践推荐
* 请注意，“潜在客户”或“联系人”阶段部分分为“丢失”、“打开”和“已转换”；验证阶段是否位于其相应的阶段部分
   * 在不正确的阶段分区中设置阶段可能会导致[!DNL Marketo Measure]数据高度不正确
   * 如果您是Marketo Measure Ultimate客户，并且已将您的默认功能板对象设置为联系人，请不要使用以下两个特定于潜在客户的字段（[了解更多](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}）。
      * b2b.personStatus
      * b2b.isConverted
* 请注意， Opportunity阶段部分分为Lost 、 Open和Won ；验证阶段是否位于其相应的阶段部分
   * 在不正确的阶段区段中放置阶段可能会导致[!DNL Marketo Measure]收入或管道收入数据高度不正确
* 避免使用重复的阶段名称（我们的系统将检测到它们并自动删除一个）。
* 要设置检查NULL值的规则，请将值文本框留空。

## 维护的最佳实践 {#best-practices-for-maintenance}

每年查看一次您的阶段映射，将确保您在[!DNL Marketo Measure]中的Opportunity数据准确且最新。

可能触发阶段映射审阅的其他原因包括……

* 您的营销团队中的人员调整
* 对CRM阶段所做的任何更改
* 贵组织的funnel的更新
* 在[!DNL Marketo Measure]报表中看到不正确的收入数据

>[!MORELIKETHIS]
>
>[Funnel阶段与自定义模型阶段之间的差异](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
