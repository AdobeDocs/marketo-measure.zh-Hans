---
unique-page-id: 18874692
description: 宝美朗阶段方案 —  [!DNL Marketo Measure]  — 产品文档
title: Boomerang阶段方案
exl-id: 150db070-eef5-4741-845c-775ab4034ead
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---

# Boomerang阶段方案 {#boomerang-stage-scenarios}

以下是Boomerang Stage场景的一些示例，用于了解如何 [!DNL Marketo Measure] 将在每种情况下创建接触点。

## 单个潜在客户方案 {#single-lead-scenarios}

**场景1:潜在客户的标准回力镖接触点**

这是最简单的回飞镖场景。 顶线（标记为潜在客户1）表示单个潜在客户的历程，以及其接触点在潜在客户记录中的显示方式。 底线（标有Opportunity）显示Lead接触点如何转化为Opportunity。 接触点的进度将按时间顺序从左到右进行说明。

在此方案中，客户选择将 **MQL** 和 **SQL** 跟踪的舞台。 每个Boomerang接触点位置都将标记有该接触点的阶段和编号(MQL-01、SQL-01、MQL-02)。 等)。 该阶段的最后一个回飞镖接触点在接触点位置也将具有“（最后）”。

然后，潜在客户1将转换为Contact with an Opportunity，这被视为OC接触。

![](assets/1-1.png)

**场景2:Boomerang接触点和潜在客户的自定义阶段**

在此方案中，客户仅选择跟踪 **SQL阶段** 有自食之力接触点。 仍在跟踪MQL和SAL阶段，但使用 [!DNL Marketo Measure] 自定义舞台功能。

![](assets/2-1.png)

请注意， MQL接触点位置未标记数字。 这是因为未选择与Boomerang接触点一起跟踪。 为自定义模型中包含的阶段创建接触点时，但不会通过Boomerang进行跟踪， [!DNL Marketo Measure] 就会从那个阶段开始。

在SAL阶段， [!DNL Marketo Measure] 忽略此阶段的前两次出现。 [!DNL Marketo Measure] 仅为 _最近_ 次数。 在以上示例中，此操作在OC接触点之前发生。

SQL阶段正在与Boomerang接触点进行跟踪，并且已创建三个接触点并相应地标记。

然后，潜在客户1将转换为Contact with an Opportunity，这被视为OC接触。

**情景3:潜在客户未达到/跳过阶段时**

此方案使用与方案2相同的标准。 客户仅选择跟踪具有回力器触点的SQL阶段。 仍在跟踪MQL和SAL，但使用 [!DNL Marketo Measure] 自定义舞台功能。

![](assets/3.png)

在此情景中，潜在客户从未实际过渡到SAL阶段。 它在到达SAL阶段之前转换为联系人，基本上“跳过”SAL阶段。 在这种情况下， [!DNL Marketo Measure] 将假定SAL与OC接触点发生，并且SAL和OC位置将显示在同一接触点上。

然后，潜在客户1将转换为Contact with an Opportunity，这被视为OC接触。

## 具有多个潜在客户的方案 {#scenarios-with-multiple-leads}

以下情形是Boomerang阶段可能变得更加复杂，因为我们正在研究多个潜在客户如何影响Opportunity历程。

顶线（以蓝色标记为“潜在客户1”）表示单个潜在客户的历程，以及其接触点在“潜在客户”记录中的显示方式。 这同样适用于Lead 2（粉红色）和Lead 3（橙色）。 底线（标有Opportunity）显示这两个Lead的接触点如何转换到Opportunity。 接触点的进度将按时间顺序从左到右进行说明。

**场景1:[!UICONTROL Three Leads with Opportunity]**

在此方案中，客户已选择跟踪 **MQL** 和 **SAL阶段** 有自食之力接触点。 SQL阶段正由标准自定义阶段进行跟踪。

![](assets/4.png)

Opportunity上的FT和LC接触点将来自Lead 1（蓝色），因为它们发生在Lead 2的FT和LC之前（粉红色）。 潜在客户2的LC接触点将在Opportunity上显示为“表单”接触点。

Lead 2中的MQL-01（最后一个）将成为Opportunity上的第一个MQL。 潜在客户1的MQL-01不会显示为Opportunity上的接触点，因为潜在客户2的MQL是先发生的。 但是，Lead 1的MQL-02和MQL-03将显示在Opportunity中。

请注意，SQL阶段正在使用自定义阶段进行跟踪，而不是返回。 即使在Lead 1和Lead 2之间出现了三次SQL阶段，但只有最后一个SQL阶段将作为Opportunity上的接触点包含在内。

Lead 1中的SAL-01（最后一个）接触点作为Opportunity上的接触点被传递。 然后，潜在客户1将转换为Contact with an Opportunity，这被视为OC接触。 潜在客户2的SAL-01（最后一个）接触点将创建为接触点，因为此阶段过渡已发生 _after_ OC联系。

潜在客户3的FT、LC和MQL、SQL、SAL触点（橙色）都发生在Opportunity上的OC触点之后。 这些接触点将包含在Opportunity中，但被视为“中间接触”。

当Lead 2和3转换为Contacts时， [!DNL Marketo Measure] 将不会创建另一个OC接触点，因为只能有一个机会创建阶段。

**场景2 -[!UICONTROL Three Leads with Opportunity]**

在此方案中，客户已选择跟踪 **MQL**, **SQL**&#x200B;和 **SAL** 带回美浪接触点的阶段。

从FT到SAL-01（最后）的所有接触点都将包含在机会中。 Lead 2中的LC接触点将作为Form接触点包含在Opportunity上的LC和MQL-01接触点之间。

![](assets/5.png)

Lead 2中的MQL-01（最后一个）最终是Opportunity上的MQL-04（最后一个）接触点。 由于此方案是在一个Opportunity中查看多个Lead的历程，因此当Lead触点被翻译为Opportunity上的接触点时，其定位和编号可能会发生变化。 同样，潜在客户2中的SQL-01（最后）将变为Opp上的SQL-04（最后）。 Lead 2的SAL-01（最后）也成为Opportunity的SAL-02（最后）。

另外，请注意，Opportunity中只包含2个SAL接触点。 [!DNL Marketo Measure] 如果尚未实际发生过渡，则不会尝试为过渡强制/创建接触点。

Lead 3的接触点历程在OC接触之前就开始，但在Lead 1和Lead 2接触FT和LC之后很久。 在这种情况下，Lead 3的FT和LC将作为Opportunity上的Form接触点显示。 然后，潜在客户1将转换为Contact with an Opportunity，这被视为OC接触。

在OC接触后，潜在客户3的MQL、SQL和SAL接触都同时发生。 由于它们发生在OC接触点之后，因此此接触点将显示为Opportunity的表单/中间接触，而不是Boomerang阶段过渡。

**场景2a - Web访问Boomerang接触点**

在此方案中，客户已选择跟踪 **MQL**, **SQL**&#x200B;和 **SAL** 带回美浪接触点的阶段。 这种情况与上述情况几乎相同，只有少数例外。

![](assets/6.png)

从FT到SAL-01（最后）的所有接触点都将包含在机会中。 Lead 2中的LC接触点将作为Form接触点包含在Opportunity上的LC和MQL-01接触点之间。

潜在客户2的MQL-01（上次）（Web访问）将不会创建为Opp上的接触点。 这是因为此接触点是在SQL阶段最后一次发生之后进行的一次Web访问，并且不有助于推动Opportunity向前发展。

Lead 1的阶段变为SAL，然后转换为Contact with an Opportunity;在这种情况下，SAL-01（最后）和OC位置将组合在同一接触点中。

Lead 3的FT、LC触控将创建为Opp上的表单接触点。 只有表单填充操作将在OC接触后创建为接触点。 因此，将不会创建“前导2”的SQL-01（上一个）和SAL-01（最后一个）过渡作为接触点，因为这些接触点是Web访问。

潜在客户3的MQL、SQL、SAL接触将作为接触点包含在内，因为这是表单填充操作。

**场景3 — 回归归归因权重**

在此方案中，客户已选择跟踪 **MQL**, **SQL**&#x200B;和 **SAL** 带回美浪接触点的阶段。

![](assets/7.png)

Opportunity上的FT和LC接触点将来自Lead 1（蓝色），因为它们发生在Lead 2的FT和LC之前（粉红色）。 潜在客户2的LC接触点将在Opportunity上显示为“表单”接触点。

Lead 2中的MQL-01（最后一个）将成为Opportunity上的第一个MQL。 潜在客户1的MQL-01不会显示为Opportunity上的接触点，因为潜在客户2的MQL是先发生的。

潜在客户2中的SQL-01（最后一个）将在Opportunity上成为SQL-01。 潜在客户1上的SQL-01不会显示为商机上的接触点，因为潜在客户2上的SQL-01是先发生的。

请注意，Lead 1在MQL和SQL之间回飞了几次，最终到达SAL阶段。 SQL-01、MQL-02、SQL-02、MQL-03、SQL-03 _将不会_ 作为机会的接触点，因为这些阶段过渡无助于在历程中推动机会向前发展。

来自潜在客户1的SAL-01（最后一个）接触点将是Opp中要包含的下一个接触点。 然后，潜在客户1转化为与业务机会的联系人，从而创建OC接触点。

潜在客户3的FT和LC以及MQL、SQL和SAL接触点将以接触Opportunity的形式显示。

潜在客户2的SQL-01（最后一个）接触点将不会作为Opp上的接触点包含在内，因为它发生在OC接触点之后。 此外，Lead 2的SQL阶段过渡也发生了 _SAL阶段过渡后_，并且无助于推动机会历程向前发展。

## 机会方案 {#opportunity-scenarios}

**情景1 — 具有Opportunity和Boomerang跟踪的联系人**

在此方案中，客户已选择跟踪 **演示和协商阶段过渡** 在 **联系人**. 每个自食其果阶段最多可接收两个接触点。 Contact上的过渡阶段与Lead上的过渡阶段之间的区别在于，Contact阶段的过渡可以在Opportunity上显示为Boomerang接触点 _after_ OC接触点。 对于在潜在客户上发生的过渡，情况并非如此，因为这些过渡将显示为表单接触点。

![](assets/8.png)

在此示例中，Contact 1的Demo和Negotiation Stage过渡作为Demo-01和Negotation-01接触点包含在Opportunity中。 联系人2的演示阶段过渡发生 _after_ 联系1，并在Opportunity上显示为Demo-02（最后一个）接触点。

请注意，没有第二个过渡到谈判阶段；机会立即从Demo-02（上次）移动到Close Won。 在这种情况下， [!DNL Marketo Measure] 将包括与Closed Won接触点的协商过渡。
