---
unique-page-id: 18874710
description: 触点移除和触点抑制 —  [!DNL Marketo Measure]  — 产品文档
title: 触点移除和触点抑制
exl-id: 201af648-6525-4a80-a7e5-3cbeeb1670b6
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---

# 触点移除和触点抑制 {#touchpoint-removal-and-touchpoint-suppression}

了解如何从CRM中删除或禁止符合特定条件的接触点。 如果您具有 [!DNL Salesforce] 数据存储限制。

“接触点删除”规则与“接触点抑制”规则之间有一个关键区别：

* 删除接触点 —  [!DNL Marketo Measure] 将从CRM中清除（即删除）任何符合规则标准的接触点。 数据 _can_ 在 [!DNL Marketo Measure] ROI功能板，但不再在CRM中。
* 接触点抑制 — 与删除接触点类似，但数据无法在ROI仪表板中报告。

在开始创建接触点删除/抑制规则之前，最好与营销和销售运营团队共享您的实施计划。 您应该已经知道要删除哪些类型或值。 一些常见用例包括：

* 从已结束的丢失机会中删除接触点
* 从非常旧的潜在客户中删除接触点
* 从不合格的潜在客户中删除接触点

保存规则后， [!DNL Marketo Measure] 将清理并重新分发您的归因模型。 这意味着里程碑和职位将发生更改，而您渠道的归因点数将发生更改！ 这将修改您的数据，因此，如果您需要帮助，请联系您的成功经理。

`1)` 有两个部分用于删除/抑制设置。 您可以选择为买方接触点（潜在客户和联系人）或买方归因接触点（联系人、机会和帐户）进行设置。

首先添加规则并选择将定义标准的字段。

从与下一组值相关的运算符列表中进行选择，您将在下一列中添加这些值。

![](assets/1-1.png)

>[!TIP]
>
>要在字段中添加多个值，请使用“matches any”运算符，并使用逗号分隔每个值。

>[!TIP]
>
>要考虑字段中的空值或空值，只需将“值”框留空。 这将考虑各种情景，例如针对没有表单URL的接触点进行评估。

>[!NOTE]
>
>公式字段不能在规则中使用，也不会显示在选取列表中。 由于公式在后台计算而不修改记录， [!DNL Marketo Measure] 无法检测记录是否符合规则。

`2)` 在同一组中添加规则，以在语句中使用“AND”逻辑。
或者，在组外添加新语句，以在语句中使用“OR”逻辑。

![](assets/2.png)

`3)` 如果您的规则变得复杂，并且您需要重新创建组并对每个语句进行细微更改，请使用“克隆”选项简化操作。

![](assets/3.png)

如果你犯了错，别担心。 您也可以删除语句或完整组的各个行。

![](assets/4.png)

`4)` 如果希望将买方归因接触点应用于两个对象，请为它们设置规则。 我们的灵活性允许您为一个对象或两个对象设置规则，如果应用，则可以选择为这两个对象设置规则。

![](assets/5.png)

要完成，请保存并处理您的规则。 如果您进行了许多更改，请确保在执行过程中保存您所做的更改。 [!DNL Marketo Measure] 在单击 **保存并处理** 按钮。

| **运算符** | **用例** |
|---|---|
| 等于 | 单个值 — 精确匹配 |
| 包含 | 单个值 — 包含值 |
| 匹配任意 | 多个值 — 精确匹配 |
| 匹配任意（包含） | 多个值 —  &#42;值&#42;, &#42;值， &#42;值&#42; |

对于使用Dynamics的客户，如果希望根据Status和/或Statecode设置Suppression规则，则在设置规则时，我们需要以下格式： `[Object].Statecode` 等于/不等于 `[Status Value]`. 例如，如果Dynamics中的Statecode在联系人上读取“1”，而Status在读取“Inactive”，并且您想要禁止所有此类联系人，则对于您的“禁止”规则，以下格式将不正确：Contact.Statecode等于1。 您而是希望使用以下格式 — 因为Statecode和Status是一对， [!DNL Marketo Measure] 从查询中的状态中读取值：Contact.Statecode等于“不活动”。
