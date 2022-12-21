---
description: 活动归因最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 活动归因最佳实践
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 活动归因最佳实践 {#best-practices-for-activities-attribution}

## 概述 {#overview}

的 [!DNL Marketo Measure] 活动归因功能允许客户从CRM中的活动记录创建接触点。 这种创建接触点的方法非常灵活，因为它允许您根据任务或事件字段创建规则以通知 [!DNL Marketo Measure] 哪些活动会记录其应从中产生接触点，然后接收归因点数。

此功能最常见的用例是制定规则，将销售互动纳入您的买方接触点数据中。 通过活动归因，您可以将销售和营销数据整合到一个历程中。

对于许多 [!DNL Salesforce] 实例中，活动对象可以存储各种记录类型，因此，务必要根据您尝试转换为接触点的记录，对活动规则进行特定和量身定制。 以下最佳实践将有助于确保您通过活动归因创建有意义且有价值的接触点。

## 最佳实践 {#best-practice}

无论您是首次定义活动规则，还是仅查看之前已设置的活动规则，请牢记以下最佳实践。

* 开始简单
   * 确定要合并到您的 [!DNL Marketo Measure] 数据，然后在您熟悉这些接触点如何归属时添加更多类型
   * 如上所述，此功能的主要用例是创建触点，以跟踪销售开发团队的成效，特别是叫客电话和叫客电子邮件

>[!NOTE]
>
>是 **NOT** 建议跟踪在创建Opportunity后发生的销售活动，因为跟踪销售执行人员流程不会提供太多洞察信息。 其目标是跟踪销售影响和营销影响，主要是在开发新的Opportunity/pipeline生成

* 请勿使用公式字段定义规则
* 创建特定且精确的规则
   * 您希望活动接触点的创建阈值与表单填写或营销活动成员资格相同（或类似），即（对出站电子邮件或已完成的电话对话的回复）
* 始终在中验证新规则 [!DNL Salesforce] 保存和处理之前
   * 在“任务和事件”报表类型中复制活动规则，可让您清楚地了解将从该规则创建的接触点确切数量
* 与您的销售运营团队合作
   * 引入与您的活动记录或销售支持工具工作最近的团队，可确保您使用正确的字段来定义规则

## 维护最佳实践 {#best-practice-for-maintenance}

每年至少审查两次活动归因规则，可确保活动接触点准确且最新。 您希望确保这些规则不会创建有害的触点，从而稀释您的“购买者归因”数据。 对规则定义方式的审核将帮助您和您的团队对活动归因及其在 [!DNL Marketo Measure] 数据。

可能触发活动规则审核的其他原因包括……

* 营销团队的营业额
* 对用于定义活动记录的字段所做的更改
* 更改或更新了销售支持工具

>[!MORELIKETHIS]
>
>* [活动归因](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [销售活动归因常见问题解答](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)


