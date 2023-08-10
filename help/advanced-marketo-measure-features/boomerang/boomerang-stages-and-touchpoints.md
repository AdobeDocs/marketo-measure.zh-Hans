---
unique-page-id: 18874558
description: 自走式舞台和接触点 —  [!DNL Marketo Measure]  — 产品文档
title: 自走式暂存器和接触点
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
feature: Boomerang, Touchpoints
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 0%

---

# 自走式暂存器和接触点 {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>
>Boomerang功能仅对第3层客户启用。 若要申请更高的客户层，请联系Adobe客户团队（您的客户经理）。

[!DNL Marketo Measure] 已发布我们的回旋镖舞台功能！ 创建回旋镖暂存功能是为了更加直观地了解客户的历程， [!DNL Marketo Measure] 销售周期较长的客户。 此功能允许营销人员为Opportunity历程中发生的所有阶段过渡创建接触点，例如当联系MQL时，然后移至SAL，然后再移回MQL阶段。 当联系人“重新进入MQL阶段”或“重新进入MQL阶段”时，我们将MQL视为回访阶段。 “回旋镖舞台”功能与 [!DNL Marketo Measure] 自定义阶段。

## 此功能的功能 {#what-this-feature-does}

* 为机会历程中发生的所有阶段过渡创建“回弹”接触点
* 跟踪任何自定义阶段之间的重复过渡(例如 当联系MQL时，移至SAL，然后返回MQL阶段)
* 允许您指定希望在Opportunity中包含的过渡数量和过渡集(例如， 前10个MQL或后5个MQL)
* 如果您是自定义模型用户，则可以确定要分配给每个阶段的归因权重和点数百分比(例如， 将归因权重指定给第一个或最后一个MQL发生次数，或在所有发生次数中平均分配归因权重)

>[!NOTE]
>
>[关于如何设置回访式阶段的说明](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md).

## Boomerang阶段和接触点在CRM中的外观 {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

如果没有Boomerang阶段（“之前”），您将只看到与Lead/Contact记录关联的最新MQL或最新的SQL接触点。

![](assets/1.png)

通过“回车轮”阶段和接触点，您将看到每个阶段过渡中出现的接触点。 这些回默朗接触点的命名约定如下：

**[阶段名称]-00。**

使用下面的示例， [!DNL Marketo Measure] account已将MQL和SQL纳入其回溯站阶段，并已选择在每个阶段显示2个回溯站接触点。

![](assets/2.png)

**MQL-01** 是第一个MQL阶段转换。

接触点位置的数值将表示发生级转变的顺序。 最后一个回访接触点将标记为：

MQL-02 **（最后一个）**

## Boomerang阶段如何更改您的现有数据 {#how-boomerang-stages-change-your-existing-data}

“回车轮”阶段将影响：

**按渠道归因**

* 从 [!DNL Boomerang Stages] 将创建更多接触点，这会更改归因在数据中当前存在的接触点之间的分配方式。 因此，这可能意味着收入值将在营销渠道之间转换。 在实施之前，请将此考虑在内 [!DNL Boomerang stages]，或与您的客户经理联系以获取更多信息。

**任何使用“等于”的报表 [接触点位置]&quot;**

* “回弹”阶段将为您的数据引入新的接触点位置。 [!DNL Marketo Measure] 正在更改接触点位置的格式以包括舞台的出现次数，如“MQL-01”或“MQL-05（最后一个）”。 在此示例中，Boomerang阶段将影响使用“接触点位置等于MQL”的任何报表。 要调整这些报表，过滤器应改用“包含”运算符。

## 常见问题解答 {#faq}

**在我的归因模型中，可以包含多少个“回弹”阶段？**

您最多可以选择15个阶段。

**问：每个阶段可以有多少“回弹”接触点？**

每个阶段最多可选择10个回车族接触点。

**问：为什么每个阶段最多只能有10个回旋镖？**

[!DNL Marketo Measure] 为了控制处理时间，必须对阶段数量进行限制。 如果您选择在归因模型中包含所有15个回滚流阶段以及每个阶段的10个回滚流接触点，则每个潜在客户/联系人记录可能会有超过150个接触点。

**问：我有Data warehouse。 我是否获取了所有数据？或者“回力舱阶段”上限是否也适用于我？**

上限将应用于Data warehouse和CRM，因为处理限制 [!DNL Marketo Measure] 已准备就绪。 data warehouse还将看到每个阶段10个接触点的限制。

**问：将“回车轮”阶段用于自定义建模有什么好处？**

使用 [!UICONTROL Boomerang] 使用自定义建模的阶段允许您向分配归因权重 [!UICONTROL Boomerang] 会将收入点数分配给这些阶段的接触点。

如果没有自定义建模， [!DNL Marketo Measure] 将为每个回访和阶段过渡创建接触点，但不会将任何归因点数分配给这些接触点。 将获得归因点数的唯一回访式接触点是表单提交接触点。 如果没有自定义模型， [!DNL Boomerang] 接触点被视为与“中间接触”相同，并因此获得归因点数。
