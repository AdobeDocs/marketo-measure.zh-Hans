---
unique-page-id: 18874558
description: 自美浪的阶段和接触点 —  [!DNL Marketo Measure]  — 产品文档
title: 自美朗阶段和接触点
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%

---

# 自美朗阶段和接触点 {#boomerang-stages-and-touchpoints}

[!DNL Marketo Measure] 发布了我们的Boomerang Stage功能！ 创建Boomerang Stage功能是为了更深入地了解客户的历程 [!DNL Marketo Measure] 销售周期较长的客户。 此功能允许营销人员为Opportunity历程中发生的所有阶段过渡创建接触点，例如，当联系人MQL，然后移至SAL，然后还原回MQL阶段时。 当联系人“重新进入MQL阶段”或“重新进入MQL阶段”时，我们将MQL视为回归阶段。 Boomerang舞台功能与 [!DNL Marketo Measure] 自定义阶段。

## 此功能的功能 {#what-this-feature-does}

* 为在机会历程中发生的所有阶段过渡创建一个“回力镖”接触点
* 跟踪任何自定义阶段(例如， 联系MQL时，移到SAL，然后返回到MQL阶段)
* 允许您指定希望在Opportunity中包含多少个过渡和哪组过渡(例如， 前10个MQL或后5个MQL)
* 如果您是自定义模型用户，则能够确定要分配给其中每个阶段(例如， 将归因权重指定给第一个或最后一个MQL发生，或在所有发生之间平均分配归因权重)

>[!NOTE]
>
>[关于如何设置Boomerang舞台的说明](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md).

## Boomerang在您的CRM中的阶段和接触点 {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

如果没有Boomerang阶段（“之前”），您将只看到与潜在客户/联系人记录关联的最新MQL或最新SQL接触点。

![](assets/1.png)

使用Boomerang阶段和接触点，您将看到每个阶段过渡出现的接触点。 这些自食其果触点的命名约定如下：

**[阶段名称]-00.**

使用以下示例， [!DNL Marketo Measure] 帐户已将MQL和SQL包含在其回游过程中，并且已选择在每个阶段显示2个回游过程接触点。

![](assets/2.png)

**MQL-01** 是第一个MQL阶段过渡。

接触点位置的数值将表示阶段过渡的发生顺序。 最后一个自食其果接触点将标记为：

MQL-02 **（最后）**

## Boomerang阶段如何更改您的现有数据 {#how-boomerang-stages-change-your-existing-data}

宝美朗阶段将产生影响：

**按渠道归因**

* 自 [!DNL Boomerang Stages] 将创建更多接触点，这将更改归因在数据中当前存在的触点之间的分配方式。 因此，这可能意味着收入值将在营销渠道之间转移。 在实施之前，请考虑这一点 [!DNL Boomerang stages]，或联系您的客户经理以了解更多信息。

**使用“等于”的任何报表 [接触点位置]&quot;**

* Boomerang阶段将为您的数据引入新的接触点位置。 [!DNL Marketo Measure] 正在更改接触点位置的格式，以包含阶段的出现，如“MQL-01”或“MQL-05（最后）”。 使用此示例，Boomerang阶段将影响使用“接触点位置等于MQL”的任何报表。 要调整这些报表，过滤器应改用“包含”运算符。

## 常见问题解答 {#faq}

**我可以在归因模型中包含多少个自食其果阶段？**

您最多可以选择15个阶段。

**问：我每个阶段可以有多少个“回力镖”接触点？**

每个阶段最多可以选择10个回波镖接触点。

**问：为什么我们每阶段只能返回10个？**

[!DNL Marketo Measure] 必须对阶段数设置限制，以便控制处理时间。 如果您选择在归因模型中包含所有15个Boomerang阶段，并且每个阶段包含10个Boomerang接触点，则每个潜在客户/联系人记录可能有150个以上的接触点。

**问：我有Data warehouse。 我是否获得了所有数据，或者Boomerang Stages的上限也适用于我？**

由于Data warehouse和CRM的处理限制，因此该上限将适用于 [!DNL Marketo Measure] 已经到位。 data warehouse还将看到每个阶段10个接触点的限制。

**问：在自定义建模中使用Boomerang阶段有何好处？**

使用 [!UICONTROL Boomerang] 通过自定义建模的阶段，您可以将归因权重分配给 [!UICONTROL Boomerang] 接触点，将收入信用分配给这些阶段。

没有自定义建模， [!DNL Marketo Measure] 将为每个boomerang和过渡创建接触点，但不会为这些接触点分配任何归因点数。 唯一将收到归因点数的自食其果接触点是表单提交接触点。 没有自定义模型， [!DNL Boomerang] 接触点被视为与“中间接触”相同，并相应地接收归因点数。
