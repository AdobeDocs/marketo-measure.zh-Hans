---
description: 阶段映射的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 阶段映射的最佳实践
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
source-git-commit: b8388c4f89734f55ec779ef23b75b34b07da6f58
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# 阶段映射的最佳实践 {#best-practices-for-stage-mapping}

## 概述 {#overview}

的“阶段映射”部分 [!DNL Marketo Measure] 帐户概述了以下阶段 [!DNL Marketo Measure] 如果使用自定义归因模型，则会自动从您的CRM和您定义的任何自定义阶段拉取。 有效期 [!DNL Marketo Measure] 数据依赖于这些阶段的正确排序，以便 [!DNL Marketo Measure] 可以准确地了解漏斗以及整个漏斗中记录的进度。

在的“阶段映射”部分中 [!DNL Marketo Measure] 实例中，您将从CRM中看到活动阶段和非活动阶段。 根据您当前的漏斗情况，尽全力对所有阶段进行排序。

本节中管理的附加功能是漏斗阶段，通过该功能，您可以将阶段添加到漏斗而不应用归因。 漏斗阶段将作为接触点进行跟踪，并将填充到您CRM的接触点位置字段中。 这些漏斗阶段还将显示在中的各个历程展示板中 [!DNL Marketo Measure] 探索。

## 最佳实践 {#best-practices}

无论您是第一次评估暂存映射，还是只查看漏斗顺序，请务必牢记以下最佳实践。

* 秩序就是一切！
   * 正在考虑 [!DNL Marketo Measure] 从CRM中提取活动和非活动阶段，确认任何可用于Lead/Contact或Opportunity的阶段都分组在一起并相应地排序
* 定义自定义阶段时，请确保为用于定义阶段的任何字段启用字段历史记录跟踪
* 不要使用公式字段定义自定义阶段
   * 布尔字段是最佳实践推荐
* 请注意，“潜在客户”或“联系人”阶段部分分为“丢失”、“打开”和“已转换”；验证阶段是否位于其相应的阶段部分中
   * 在不正确的阶段分区中设置阶段可能会导致高度不正确 [!DNL Marketo Measure] 数据
* 请注意， Opportunity阶段部分分为Lost 、 Open和Won ；验证阶段是否位于其相应的阶段部分
   * 在不正确的阶段分区中设置阶段可能会导致高度不正确 [!DNL Marketo Measure] 收入或管道收入数据
* 避免使用重复的阶段名称（我们的系统将检测到它们并自动删除一个）。
* 要设置检查NULL值的规则，请将值文本框留空。

## 维护的最佳实践 {#best-practices-for-maintenance}

每年审查一次您的阶段映射，将确保您的Opportunity数据位于 [!DNL Marketo Measure] 准确且最新。

可能触发阶段映射审阅的其他原因包括……

* 您的营销团队中的人员调整
* 对CRM阶段所做的任何更改
* 对贵组织漏斗的更新
* 在中看到不正确的收入数据 [!DNL Marketo Measure] 报告

>[!MORELIKETHIS]
>
>[漏斗阶段和自定义模型阶段之间的区别](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
