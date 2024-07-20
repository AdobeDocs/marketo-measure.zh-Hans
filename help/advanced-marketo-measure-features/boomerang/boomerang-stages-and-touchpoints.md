---
unique-page-id: 18874558
description: 自走式暂存和接触点 —  [!DNL Marketo Measure]
title: 自走式暂存器和接触点
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
feature: Boomerang, Touchpoints
source-git-commit: ea113b02b910fbc894311200aff83286636d4b32
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 0%

---

# 自走式暂存器和接触点 {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>
>Boomerang功能仅针对第2层和第3层客户启用。 要申请更高的客户层，请联系Adobe客户团队（您的客户经理）。

[!DNL Marketo Measure]已发布回旋镖暂存功能！ 创建了“回车灯”阶段功能，以便为销售周期较长的[!DNL Marketo Measure]客户提供更多关于客户历程的可见度。 此功能允许营销人员为Opportunity历程中发生的所有阶段过渡创建接触点，例如当联系MQL时，然后转到SAL，最后转到MQL阶段。 当联系人“重新进入MQL阶段”或“重新进入MQL”时，MQL将被视为回访阶段。 “回音室”阶段功能与[!DNL Marketo Measure]自定义阶段一起运行。

## 此功能的功能 {#what-this-feature-does}

* 为机会历程中发生的所有阶段过渡创建“回弹”接触点
* 跟踪任何自定义阶段之间的重复过渡(例如 当联系MQL时，移至SAL，然后返回MQL阶段)
* 允许您指定希望在Opportunity中包含的过渡数量和过渡集(例如， 前10个MQL或后5个MQL)
* 如果您是自定义模型用户，则可以确定要分配给每个阶段的归因权重和点数百分比(例如， 将归因权重指定给第一个或最后一个MQL发生次数，或在所有发生次数之间平均分配归因权重)

>[!NOTE]
>
>[关于如何设置回音符阶段的说明](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md)。

## Boomerang阶段和接触点在CRM中的外观 {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

如果没有Boomerang阶段（“之前”），您只会看到与Lead/Contact记录关联的最新MQL或最新的SQL接触点。

![](assets/1.png)

通过回车族阶段和接触点，您可以看到每个阶段过渡中出现的接触点。 这些回默朗接触点的命名约定如下：

**[阶段名称]-00.**

使用以下示例，此[!DNL Marketo Measure]帐户已将MQL和SQL包含在其boomerang阶段中，并已选择每个阶段显示2个boomerang接触点。

![](assets/2.png)

**MQL-01**&#x200B;是第一个MQL阶段转换。

接触点位置的数值表示阶段转换发生的顺序。 最后一个回访接触点将标记为：

MQL-02 **（最后一个）**

## Boomerang阶段如何更改您的现有数据 {#how-boomerang-stages-change-your-existing-data}

自走式分段影响：

**按渠道归因**

* 由于[!DNL Boomerang Stages]创建了更多接触点，这会更改归因在数据中当前存在的接触点之间的分配方式。 因此，这可能意味着收入价值在营销渠道之间转移。 在实施[!DNL Boomerang stages]前应考虑这一点，或与您的客户经理联系以获取更多信息。

**任何使用“等于[接触点位置]”的报表**

* 回滚阶段会向您的数据引入新的接触点位置。 [!DNL Marketo Measure]正在更改接触点位置的格式以包括阶段的出现次数，如“MQL-01”或“MQL-05（最后一个）”。 在此示例中，Boomerang阶段会影响任何使用“接触点位置等于MQL”的报表。 要调整这些报表，过滤器应改用“包含”运算符。

## 常见问题 {#faq}

**我的归因模型中可以包含多少个boomerang阶段？**

您最多可以选择15个阶段。

**问：每个阶段可以有几个“boomerang”接触点？**

每个阶段最多可选择10个回滚接触点。

**问：为什么每个阶段有10个自变量限制？**

[!DNL Marketo Measure]必须限制阶段数才能控制处理时间。 如果您选择在归因模型中包含所有15个回滚流阶段以及每个阶段的10个回滚流接触点，则每个潜在客户/联系人记录可能会有超过150个接触点。

**问：我有Data Warehouse。 我是否获取所有数据？或者“回音符阶段”上限是否也适用于我？**

上限适用于Data Warehouse和CRM，因为[!DNL Marketo Measure]具有处理限制。 Data Warehouse还将看到每个阶段十个接触点的限制。

**问：将Boomerang阶段与自定义建模结合使用有什么好处？**

通过将[!UICONTROL Boomerang]阶段与自定义建模结合使用，您可以将归因权重分配给[!UICONTROL Boomerang]个接触点，从而为这些阶段分配收入点数。

如果没有自定义建模，[!DNL Marketo Measure]将为每个boomerang和阶段过渡创建接触点，但不会为这些接触点分配任何归因点数。 获得归因点数的唯一回访式接触点来自提交接触点。 如果没有自定义模型，[!DNL Boomerang]接触点将视为与“中间接触”相同，并相应地接收归因点数。
