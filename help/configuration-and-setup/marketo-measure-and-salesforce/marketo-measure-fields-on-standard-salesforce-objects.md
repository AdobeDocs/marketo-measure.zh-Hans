---
unique-page-id: 18874574
description: '"[!DNL Marketo Measure] 标准字段 [!DNL Salesforce] 对象 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] 标准字段 [!DNL Salesforce] 对象”'
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1273'
ht-degree: 0%

---

# [!DNL Marketo Measure] 标准字段 [!DNL Salesforce] 对象 {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>您可能会看到说明“[!DNL Marketo Measure]”，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

了解各种 [!DNL Marketo Measure] 已添加到的字段 [!DNL Salesforce] 标准对象。

## 帐户 {#account}

预测参与度得分：此字段与我们的ABM功能一起使用，以提供与帐户的参与度相关的得分，并考虑许多因素，例如页面查看的回访间隔、与帐户关联的联系人数量，是否存在已关闭的打开等。

## Case {#case}

我们会将字段添加到与首次联系和潜在客户创建联系里程碑相关的Case对象。 这适用于使用Case对象来代替Lead或Contact的客户，并且还起到另一种查看数据的作用，以防客户不希望我们创建接触点记录。

接触点来源(FT)：这是首次接触交互的来源。

接触点来源(LC)：这是商机创建接触交互的来源。

营销渠道(FT)：这是首次联系交互的营销渠道。

营销渠道(LC)：这是商机创建接触交互的营销渠道。

广告营销活动名称(FT)：这是UTM营销活动、广告网络中的广告营销活动，或 [!DNL Salesforce] 首次接触交互的营销活动。

广告营销活动名称(LC)：这是UTM营销活动、广告网络中的广告营销活动，或 [!DNL Salesforce] 的营销活动 [!UICONTROL lead creation] 触控交互。

登陆页面(FT)：这是首次接触交互的登陆页面。

登陆页面(LC)：这是 [!UICONTROL lead creation] 触控交互。

接触点日期(FT)：这是首次接触交互的日期。

接触点日期(LC)：这是商机创建接触交互的日期。

## 营销活动 {#campaign}

仅添加了4个字段、1个按钮和1个验证规则。

UniqueID：该字段供我们在内部使用，以跟踪与同步的不同营销活动 [!DNL Marketo Measure].

启用买方接触点：此字段用于实际同步离线归因包含和历史数据的营销活动。

接触点开始日期：此字段用于设置将接触点应用于历史营销活动的开始日期。

接触点结束日期：此字段用于设置将接触点应用于历史营销活动的结束日期。 一个常见的示例是包含数字营销活动之前[!DNL Marketo Measure] 然后将结束日期设置为应用脚本的日期。

批量更新接触点日期（按钮）：此按钮用于管理在同步营销活动时营销活动成员的接触点日期，因为我们将引用营销活动成员资格日期或第一个开箱即用的响应日期。 如果这些日期字段不能准确表示实际接触点日期，我们将使用此按钮设置接触点日期。

更新 [!DNL Marketo Measure] 归因（验证规则）：在包版本6.0之后不再使用此规则。

## 营销活动成员 {#campaign-member}

该包中添加了5个字段和1个Apex触发器。

接触点状态（潜在客户）：这是与未开箱即用的功能相关的诊断字段。 我们通过它来了解是否根据相关的Lead记录创建了接触点，如果没有，为什么。

接触点状态（联系人）：这是与未开箱即用的功能相关的诊断字段。 我们通过它来了解是否根据相关的Contact记录创建了接触点，如果没有，为什么。

接触点状态（机会）：这是与未开箱即用的功能相关的诊断字段。 我们通过它来了解是否根据相关的Opportunity记录创建了接触点，如果没有，为什么。

接触点状态日期：这是填充诊断字段的日期。

买方接触点日期：此日期与 [!UICONTROL Bulk Update Touchpoint date] 按钮。 使用该日期时，我们会向营销活动成员应用定义的接触点日期。

OnCampaignMemberDelete：现成 [!DNL Salesforce] 在删除营销活动成员时不会显示，这可能会导致无法生成准确的归因报表。 删除营销活动成员时，将触发以通知 [!DNL Marketo Measure] ，移除与该不存在的营销活动成员相关的接触点。

## 联系人 {#contact}

我们会将字段添加到与首次联系和潜在客户创建联系里程碑相关的Contact对象。 这适用于希望将归因直接报告给字段而不是创建接触点记录的客户。 我们的大多数客户采用接触点记录途径，但也在他们的自动化平台中使用这些字段。

接触点来源(FT)：这是首次接触交互的来源。

接触点来源(LC)：这是商机创建接触交互的来源。

营销渠道(FT)：这是首次联系交互的营销渠道。

营销渠道(LC)：这是商机创建接触交互的营销渠道。

广告营销活动名称(FT)：这是UTM营销活动、广告网络中的广告营销活动，或 [!DNL Salesforce] 首次接触交互的营销活动。

广告营销活动名称(LC)：这是UTM营销活动、广告网络中的广告营销活动，或 [!DNL Salesforce] 的营销活动 [!UICONTROL lead creation] 触控交互。

登陆页面(FT)：这是首次接触交互的登陆页面。

登陆页面(LC)：这是 [!UICONTROL lead creation] 触控交互。

接触点日期(FT)：这是首次接触交互的日期。

接触点日期(LC)：这是商机创建接触交互的日期。

BizibleID：将此与我们的活动归因和calltrackingmetrics集成关联使用，以实现联系人与接触点的关联。

## 商机 {#lead}

我们会将字段添加到与首次联系和潜在客户创建联系里程碑相关的Lead对象。 这适用于希望将归因直接报告给字段而不是创建接触点记录的客户。 我们的大多数客户采用接触点记录途径，但也在他们的自动化平台中使用这些字段。

接触点来源(FT)：这是首次接触交互的来源。

接触点来源(LC)：这是商机创建接触交互的来源。

营销渠道(FT)：这是首次联系交互的营销渠道。

营销渠道(LC)：这是商机创建接触交互的营销渠道。

广告营销活动名称(FT)：这是UTM营销活动、广告网络中的广告营销活动，或 [!DNL Salesforce] 首次接触交互的营销活动。

广告营销活动名称(LC)：这是UTM营销活动、广告网络中的广告营销活动，或 [!DNL Salesforce] 商机创建接触交互的营销活动。

登陆页面(FT)：这是首次接触交互的登陆页面。

登陆页面(LC)：这是商机创建接触交互的登陆页面。

接触点日期(FT)：这是首次接触交互的日期。

接触点日期(LC)：这是商机创建接触交互的日期。

BizibleID：将其用于“潜在客户”与接触点的关联关联中的活动归因和calltrackingmetrics集成。

## 帐户 {#account-1}

这用于我们的ABM功能的Lead to Account映射。 我们将填充此字段以创建两个对象之间的查找关系。

## 机会 {#opportunity}

[!DNL Marketo Measure] 机会金额：此字段用在对Opportunity使用自定义金额字段的情况下。 我们将该自定义字段值映射到 [!DNL Marketo Measure] 使用工作流的Opportunity Amount ，然后为买方归因接触点对象上的Revenue attribution字段读取此字段。

## 活动 {#activity}

BizibleID：这适用于将接触点关联到活动归因和调用跟踪量度集成的活动。

买方接触点日期：此字段可以通过工作流填充，以用作活动归因的日期，并填充用于我们的calltrackingmetrics集成以了解何时发生交互。
