---
unique-page-id: 18874574
description: 标准 [!DNL Salesforce] 对象上的[!DNL Marketo Measure]字段 —  [!DNL Marketo Measure]
title: 标准 [!DNL Salesforce] 对象上的[!DNL Marketo Measure]字段
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
feature: Salesforce
source-git-commit: 05ba9e487d492ba4352a7f0577c7221f6ec9567e
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 0%

---

# 标准[!DNL Salesforce]对象上的[!DNL Marketo Measure]字段 {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

了解添加到[!DNL Salesforce]标准对象的各种[!DNL Marketo Measure]字段。

## 帐户 {#account}

预测参与度得分：此字段与我们的ABM功能一起使用，以提供与帐户的参与度相关的得分，并考虑许多因素，例如页面查看的回访间隔、与帐户关联的联系人数量，是否存在已关闭的打开等。

## Campaign {#campaign}

仅添加了4个字段、1个按钮和1个验证规则。

UniqueID：此字段内部用于跟踪与[!DNL Marketo Measure]同步的不同营销活动。

启用买方接触点：此字段用于实际同步离线归因包含和历史数据的营销活动。

接触点开始日期：此字段用于设置将接触点应用于历史营销活动的开始日期。

接触点结束日期：此字段用于设置将接触点应用于历史营销活动的结束日期。 一个常见示例是包括[!DNL Marketo Measure]之前的数字营销活动，然后将结束日期设置为应用脚本的日期。

批量更新接触点日期（按钮）：此按钮用于管理在同步营销活动时营销活动成员的接触点日期，因为我们将引用营销活动成员资格日期或第一个开箱即用的响应日期。 如果这些日期字段不能准确表示实际接触点日期，我们将使用此按钮设置接触点日期。

更新[!DNL Marketo Measure]归因（验证规则）：在包版本6.0之后已弃用此规则。

## 营销活动成员 {#campaign-member}

该包中添加了5个字段和1个Apex触发器。

接触点状态（潜在客户）：这是与未开箱即用的功能相关的诊断字段。 我们通过它来了解是否根据相关的Lead记录创建了接触点，如果没有，为什么。

接触点状态（联系人）：这是与未开箱即用的功能相关的诊断字段。 我们通过它来了解是否根据相关的Contact记录创建了接触点，如果没有，为什么。

接触点状态（机会）：这是与未开箱即用的功能相关的诊断字段。 我们通过它来了解是否根据相关的Opportunity记录创建了接触点，如果没有，为什么。

接触点状态日期：这是填充诊断字段的日期。

Buyer Touchpoint日期：这与Campaign对象中的[!UICONTROL Bulk Update Touchpoint date]按钮相关。 使用该日期时，我们会向营销活动成员应用定义的接触点日期。

OnCampaignMemberDelete：删除营销活动成员时，开箱即用的[!DNL Salesforce]不会显示，这可能会导致无法生成准确的归因报表。 删除营销活动成员时，将触发此事件以通知[!DNL Marketo Measure]删除与该不存在的营销活动成员相关的接触点。

## 潜在客户 {#lead}

Bizible Account字段用于我们的ABM功能的Lead to Account映射。 我们将填充此字段以创建两个对象之间的查找关系。

## 帐户 {#account-1}

这用于我们的ABM功能的Lead to Account映射。 我们将填充此字段以创建两个对象之间的查找关系。

## 机会 {#opportunity}

[!DNL Marketo Measure]业务机会金额：此字段用在业务机会中使用自定义金额字段的方案中。 我们使用工作流将该自定义字段值映射到[!DNL Marketo Measure]机会金额，然后为Buyer Attribution Touchpoint对象上的收入归因字段读取此字段。

## 活动 {#activity}

BizibleID：这适用于将接触点关联到活动归因和调用跟踪量度集成的活动。

Buyer Touchpoint日期：可以通过工作流填充此字段以用作活动归因的日期，将填充此字段以便calltrackingmetrics集成知道交互何时发生。
