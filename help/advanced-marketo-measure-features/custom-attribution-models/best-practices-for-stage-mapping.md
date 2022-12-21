---
description: 阶段映射的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 阶段映射最佳实践
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# 阶段映射最佳实践 {#best-practices-for-stage-mapping}

## 概述 {#overview}

您的 [!DNL Marketo Measure] 帐户概述了 [!DNL Marketo Measure] 在使用自定义归因模型时，会自动从您定义的CRM和任何自定义阶段中提取。 您的 [!DNL Marketo Measure] 数据依赖于正确排序这些阶段 [!DNL Marketo Measure] 可以准确了解您的漏斗以及整个漏斗中记录的进展情况。

在 [!DNL Marketo Measure] 例如，您将在CRM中看到活动和不活动阶段。 按照您当前的漏斗方式，将所有阶段排到最佳位置。

此部分中管理的另一项功能是漏斗阶段，通过该功能，您无需应用归因即可向漏斗添加阶段。 漏斗阶段将作为接触点进行跟踪，并在CRM的接触点位置字段中填充。 这些漏斗阶段还将在 [!DNL Marketo Measure] 发现。

## 最佳实践 {#best-practices}

无论您是首次评估阶段映射，还是仅仅查看漏斗顺序，都必须牢记以下最佳实践。

* 秩序就是一切！
   * 考虑 [!DNL Marketo Measure] 从您的CRM中提取活动和不活动阶段，确认可用于潜在客户/联系人或机会的任何阶段被分组在一起并相应地排序
* 在定义自定义阶段时，确保为用于定义阶段的任何字段启用字段历史记录跟踪
* 请勿使用公式字段定义自定义阶段
   * 布尔字段是最佳实践推荐
* 请注意，“潜在客户”或“联系人”阶段分为“丢失”、“打开”和“已转换”；验证阶段是否位于其相应的阶段部分
   * 在不正确的阶段部分中设置阶段可能会导致高度错误 [!DNL Marketo Measure] 数据
* 请注意，Opportunity阶段部分分为Lost 、 Open和Won;验证阶段是否位于其相应的阶段部分
   * 在不正确的阶段部分中设置阶段可能会导致高度错误 [!DNL Marketo Measure] 收入或管道收入数据
* 避免使用重复的阶段名称（我们的系统将检测到重复的阶段名称并自动删除它们）。

## 维护最佳实践 {#best-practices-for-maintenance}

每年审核一次Stage Mapping ，将确保在 [!DNL Marketo Measure] 准确且最新。

可能触发对暂存映射的审核的其他原因包括……

* 营销团队的营业额
* 对CRM阶段所做的任何更改
* 对贵组织漏斗的更新
* 在 [!DNL Marketo Measure] 报告

>[!MORELIKETHIS]
>
>[漏斗阶段与自定义模型阶段之间的差异](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
