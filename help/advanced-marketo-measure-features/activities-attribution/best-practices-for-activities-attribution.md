---
description: 活动归因的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 活动归因的最佳实践
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
feature: Attribution
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 活动归因的最佳实践 {#best-practices-for-activities-attribution}

## 概述 {#overview}

此 [!DNL Marketo Measure] 活动归因功能允许客户根据CRM中的活动记录创建接触点。 这种创建接触点的方法非常灵活，因为它允许您根据任务或事件字段创建规则以通知 [!DNL Marketo Measure] 哪些活动记录它应从中生成接触点，并随后获得归因点数。

此功能最常见的用例是制定规则，这些规则将销售交互并入您的买方接触点数据。 通过活动归因，您可以将销售和营销数据整合到一个历程中。

对于许多 [!DNL Salesforce] 实例中，活动对象可以包含多种记录类型，因此活动规则要针对您尝试转换为接触点的记录进行特定和定制，这一点很重要。 以下最佳实践将有助于确保通过活动归因创建有意义且有价值的接触点。

## 最佳实践 {#best-practice}

无论您是首次定义活动规则，还是只查看之前已设置的活动规则，请牢记以下最佳实践。

* 开始简单
   * 确定要合并到您的中的几个关键类型的活动 [!DNL Marketo Measure] 数据，然后在您习惯于这些接触点的归因方式时添加更多类型
   * 如前所述，此功能的主要用例是创建用于跟踪Sales Development团队效率的接触点，特别是“出站电话呼叫”和“出站电子邮件”

>[!NOTE]
>
>它是 **NOT** 建议跟踪在创建Opportunity之后发生的销售活动，因为跟踪销售执行官过程不会提供多少洞察信息。 其目标是跟踪销售影响以及营销影响，主要是在开发新的机会/渠道产品方面

* 不要使用公式字段定义规则
* 创建具体而精确的规则
   * 您希望创建活动接触点的阈值与表单填写或营销活动成员相同（或相似），即（回复出站电子邮件或已完成的电话对话）
* 始终验证中的新规则 [!DNL Salesforce] 保存和处理之前
   * 在“Tasks &amp; Events”报告类型中复制活动规则将让您清楚地了解将根据该规则创建多少接触点
* 与您的Sales Opp团队合作
   * 引入与您的活动记录或销售支持工具最接近的团队，将确保您使用正确的字段来定义规则

## 维护的最佳实践 {#best-practice-for-maintenance}

每年至少两次查看活动归因规则，将确保您的活动接触点准确且最新。 您需要确保这些规则不会创建稀释买方归因数据的不需要的接触点。 查看规则的定义方式，将有助于您和您的团队对活动归因及其在中的角色充满信心 [!DNL Marketo Measure] 数据。

可能触发活动规则审阅的其他原因包括……

* 您的营销团队中的人员调整
* 更改用于定义活动记录的字段
* 销售支持工具的更改或更新

>[!MORELIKETHIS]
>
>* [活动归因](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [销售活动归因常见问题解答](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

