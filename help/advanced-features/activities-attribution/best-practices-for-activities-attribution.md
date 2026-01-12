---
description: 活动归因的最佳实践 —  [!DNL Marketo Measure]
title: 活动归因的最佳实践
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
feature: Attribution
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 0%

---


# 活动归因的最佳实践 {#best-practices-for-activities-attribution}

## 概述 {#overview}

[!DNL Marketo Measure]活动归因功能允许客户从CRM中的活动记录创建接触点。 这种创建接触点的方法比较灵活。 它允许您根据“任务”或“事件”字段创建规则，以通知[!DNL Marketo Measure]它应从中生成接触点的活动记录，从而接收归因点数。

此功能最常见的用例是制定规则，这些规则将销售交互并入您的买方接触点数据。 通过活动归因，您可以将销售和营销数据整合到一个历程中。

对于许多[!DNL Salesforce]实例，活动对象可以包含各种记录类型，因此活动规则必须针对您尝试转换为接触点的记录进行特定和定制。 以下最佳实践有助于确保通过活动归因创建有意义且有价值的接触点。

## 最佳实践 {#best-practice}

无论您是首次定义活动规则，还是只查看之前已设置的活动规则，请牢记以下最佳实践。

* 开始简单
   * 识别要合并到[!DNL Marketo Measure]数据中的几个关键活动类型，然后在您了解这些接触点的归因方式后添加更多类型
   * 如前所述，此功能的主要用例是创建用于跟踪Sales Development团队效率的接触点，特别是“出站电话呼叫”和“出站电子邮件”

>[!NOTE]
>**不**&#x200B;建议跟踪在创建Opportunity之后发生的销售活动，因为跟踪Sales Executions流程不能提供太多insight。 其目标是跟踪销售影响以及营销影响，主要是在开发新的机会/渠道产品方面

* 不要使用公式字段定义规则
* 创建具体而精确的规则
   * 创建活动接触点的阈值应该与表单填写或营销活动成员资格相同（或类似）：回复出站电子邮件或已完成的电话对话
* 保存和处理之前，始终在[!DNL Salesforce]中验证新规则
   * 在“Tasks &amp; Events”报告类型中复制活动规则，可让您清楚地了解该规则中有多少接触点
* 与您的Sales Opp团队合作
   * 引入与您的活动记录或销售支持工具最接近的团队，将确保您使用正确的字段来定义规则

## 维护的最佳实践 {#best-practice-for-maintenance}

每年至少两次查看活动归因规则，以确保您的活动接触点准确且最新。 您需要确保这些规则不会创建稀释买方归因数据的不需要的接触点。 查看规则的定义方式将有助于您和您的团队对活动归因及其在[!DNL Marketo Measure]数据中的角色充满信心。

可能触发活动规则审阅的其他原因包括……

* 您的营销团队中的人员调整
* 更改用于定义活动记录的字段
* 销售支持工具的更改或更新

>[!MORELIKETHIS]
> [活动归因](/help/advanced-features/activities-attribution/salesforce-activities-attribution.md)
> [销售活动归因常见问题解答](/help/advanced-features/activities-attribution/activities-attribution-faq.md)
