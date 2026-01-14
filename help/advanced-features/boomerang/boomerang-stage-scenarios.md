---
description: 面向Marketo Measure用户的Boomerang阶段场景指南
title: 回音廊舞台场景
exl-id: 150db070-eef5-4741-845c-775ab4034ead
feature: Boomerang
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '1768'
ht-degree: 0%

---

# 回音廊舞台场景 {#boomerang-stage-scenarios}

>[!AVAILABILITY]
>
>Boomerang功能仅针对第2层和第3层客户启用。 要请求更高的客户层，请联系Adobe客户团队（您的客户经理）。

以下是Boomerang阶段方案的一些示例，用于了解[!DNL Marketo Measure]如何在每种情况下创建接触点。

## 单一潜在客户方案 {#single-lead-scenarios}

**方案1：潜在客户的标准Boomerang接触点**

这是最简单的“回弹”情景。 顶行（标记为Lead 1）表示单个Lead的历程，以及他们的接触点在Lead记录中的显示方式。 底线（标记为Opportunity）显示Lead的接触点如何转换为Opportunity。 接触点的进展按时间顺序进行，从左到右。

在此方案中，客户已选择使用Boomerangs跟踪其&#x200B;**MQL**&#x200B;和&#x200B;**SQL**&#x200B;阶段。 每个Boomerang接触点位置都标有阶段和发生阶段的数字(MQL-01、SQL-01、MQL-02)。 该舞台的最后一个回访式接触点在接触点位置具有“（最后一个）”。

然后，Lead 1将转换为具有Opportunity的Contact ，后者被视为OC接触。

![](assets/boomerang-boomerang-18.png)

**方案2：潜在客户的回访式接触点和自定义阶段**

在此方案中，客户选择只跟踪带有回滚接触点的&#x200B;**SQL阶段**。 仍在跟踪MQL和SAL阶段，但具有[!DNL Marketo Measure]自定义阶段功能。

![](assets/boomerang-boomerang-19.png)

请注意，MQL接触点位置未标记为数字。 这是因为未选择通过Boomerang接触点跟踪它。 为自定义模型中包含但未使用Boomerang进行跟踪的阶段创建接触点时，[!DNL Marketo Measure]会采用该阶段的最后一次发生次数。

对于SAL阶段，[!DNL Marketo Measure]将忽略此阶段的前两次发生次数。 [!DNL Marketo Measure]只为&#x200B;_最后一个_&#x200B;发生次数创建SAL接触点。 在上面的示例中，这发生在OC接触点之前。

正在使用Boomerang接触点跟踪SQL阶段，并且已创建三个接触点并相应地对其进行标记。

然后，Lead 1将转换为具有Opportunity的Contact ，后者被视为OC接触。

**场景3：潜在客户未到达/跳过阶段**

此方案使用与方案2相同的标准。 客户只选择使用自走式接触点跟踪SQL阶段。 仍在跟踪MQL和SAL，但具有[!DNL Marketo Measure]自定义暂存功能。

![](assets/boomerang-boomerang-20.png)

在此方案中，潜在客户实际上永远不会过渡到SAL阶段。 在到达SAL阶段之前，它将转换为联系人，实际上就是“跳过”SAL阶段。 在此情况下，[!DNL Marketo Measure]假设SAL与OC接触点同时发生，并且SAL和OC位置将出现在同一接触点上。

然后，Lead 1将转换为具有Opportunity的Contact ，后者被视为OC接触。

## 具有多个潜在客户的方案 {#scenarios-with-multiple-leads}

以下情形是自走式暂存越来越复杂的情况，因为我们正在考虑多个潜在客户如何影响Opportunity历程。

顶行（标记为潜在客户1，蓝色部分）表示单个潜在客户的历程，以及他们的接触点在Lead记录中的显示方式。 Lead 2（粉红色）和Lead 3（橙色）也是如此。 底线（标记为Opportunity）显示这两个Lead的接触点如何转化为Opportunity。 接触点的进展按时间顺序进行，从左到右。

**方案1：[!UICONTROL Three Leads with Opportunity]**

在此方案中，客户已选择跟踪带有回访式接触点的&#x200B;**MQL**&#x200B;和&#x200B;**SAL阶段**。 标准自定义阶段正在跟踪SQL阶段。

![](assets/boomerang-boomerang-21.png)

Opportunity上的FT和LC接触点来自Lead 1 （蓝色），因为它们出现在Lead 2 （粉红色）的FT和LC之前。 Lead 2的LC接触点将显示为Opportunity上的“Form”接触点。

来自Lead 2的MQL-01 （最后一个）将成为Opportunity上的第一个MQL。 Lead 1中的MQL-01将不会显示为Opportunity上的接触点，因为Lead 2的MQL是先出现的。 但是， Lead 1的MQL-02和MQL-03将出现在Opportunity中。

SQL阶段使用自定义阶段进行跟踪，而不是使用自举阶段。 即使Lead 1和Lead 2之间有三次出现SQL阶段，但只有最后出现的SQL将作为接触点包含在Opportunity中。

来自Lead 1的SAL-01 （最后一个）接触点将作为Opportunity上的接触点转移。 然后，Lead 1将转换为具有Opportunity的Contact ，后者被视为OC接触。 潜在客户2的SAL-01（上一个）接触点将创建为接触点，因为此阶段过渡在&#x200B;_OC接触_&#x200B;后发生。

Lead 3的FT 、 LC和MQL 、 SQL 、 SAL接触点（橙色）都发生在Opportunity上的OC接触点之后。 这些接触点包含在Opportunity中，但被视为“中间接触”。

当Lead 2和3转化为Contacts时，[!DNL Marketo Measure]将不会创建另一个OC接触点，因为只能有一个机会创建阶段。

**方案2 -[!UICONTROL Three Leads with Opportunity]**

在此方案中，客户已选择跟踪具有回访式接触点的&#x200B;**MQL**、**SQL**&#x200B;和&#x200B;**SAL**&#x200B;阶段。

从FT到SAL-01（最后一个），Lead 1的所有接触点都包含在该商机中。 Lead 2的LC接触点将作为Form接触点包含在Opportunity上的LC和MQL-01接触点之间。

![](assets/boomerang-boomerang-22.png)

来自Lead 2的MQL-01 （最后一个）最终成为Opportunity上的MQL-04 （最后一个）接触点。 由于此情形是查看一个Opportunity中多个Lead的历程，因此Lead的接触点的位置和编号可能会在Opportunity上转换为接触点时发生变化。 同样，Lead 2中的SQL-01 (Last)将变为Opp上的SQL-04 (Last)。 Lead 2的SAL-01 (Last)也变为Opportunity的SAL-02 (Last)。

Opportunity上只包括2个SAL接触点。 如果未发生阶段过渡，[!DNL Marketo Measure]将不会尝试强制/创建接触点。

Lead 3的接触点历程在OC接触发生之前开始，但在Lead 1和Lead 2进行FT和LC接触很久之后开始。 在这种情况下， Lead 3的FT和LC在Opportunity上显示为一个Form接触点。 然后，Lead 1将转换为具有Opportunity的Contact ，后者被视为OC接触。

Lead 3的MQL 、 SQL和SAL接触在OC接触之后同时发生。 由于它们发生在OC接触点之后，因此此接触点将显示为Opportunity上的Form/Middle Touch，而不是Boomerang阶段过渡。

**方案2a - Web访问Boomerang接触点**

在此方案中，客户已选择跟踪具有回访式接触点的&#x200B;**MQL**、**SQL**&#x200B;和&#x200B;**SAL**&#x200B;阶段。 这种情况与上述情况几乎相同，只是有一些例外。

![](assets/boomerang-boomerang-23.png)

从FT到SAL-01（最后一个），Lead 1的所有接触点都将包含在该商机中。 Lead 2的LC接触点将作为Form接触点包含在Opportunity上的LC和MQL-01接触点之间。

潜在客户2的MQL-01（上次）（Web访问）将不会创建为Opp上的接触点。 这是因为此接触点是在最后一次出现SQL阶段之后进行的Web访问，无助于推动Opportunity向前发展。

Lead 1的阶段更改为SAL ，然后转换为具有Opportunity的Contact ；在这种情况下， SAL-01 (Last)和OC职位将在同一接触点中组合在一起。

Lead 3的FT，LC触摸创建为Opp上的表单接触点。 OC接触后，只会将表单填充操作创建为接触点。 因此，不会将Lead 2的SQL-01 (Last)和SAL-01 (Last)阶段过渡创建为接触点，因为这些接触点是Web访问。

潜在客户3的MQL、SQL、SAL接触包含为接触点，因为这是一种表单填充操作。

**场景3 - Boomerang归因权重**

在此方案中，客户已选择跟踪具有回访式接触点的&#x200B;**MQL**、**SQL**&#x200B;和&#x200B;**SAL**&#x200B;阶段。

![](assets/boomerang-boomerang-25.png)

Opportunity上的FT和LC接触点来自Lead 1 （蓝色），因为它们出现在Lead 2 （粉红色）的FT和LC之前。 Lead 2的LC接触点在Opportunity中显示为“Form”接触点。

来自Lead 2的MQL-01 （最后一个）成为Opportunity上的第一个MQL。 Lead 1中的MQL-01将不会显示为Opportunity上的接触点，因为Lead 2的MQL是先出现的。

Lead 2的SQL-01 （最后一个）在Opportunity上变为SQL-01。 Lead 1上的SQL-01将不会显示为Opportunity上的接触点，因为Lead 2上的SQL-01最先发生。

请注意，在最终到达SAL阶段之前，Lead 1会在MQL和SQL之间往返几次。 SQL-01、MQL-02、SQL-02、MQL-03、SQL-03 _将不作为商机上的接触点_&#x200B;包括在内，因为这些阶段转换无助于推动商机在历程中前进。

Lead 1的SAL-01（最后一个）接触点是要包含在Opp上的下一个接触点。 然后，潜在客户1转换为具有机会的联系人，从而创建OC接触点。

Lead 3的FT和LC以及MQL 、 SQL和SAL接触点在Opportunity上显示为形式接触。

Lead 2的SQL-01 (Last)接触点将不会作为Opp上的接触点包含在内，因为它发生在OC接触点之后。 此外，潜在客户2的SQL阶段过渡在最终的SAL阶段过渡&#x200B;_后发生_，无助于推动机会之旅。

## 机会方案 {#opportunity-scenarios}

**场景1 — 具有机会和回访式跟踪的联系人**

在此方案中，客户已选择跟踪&#x200B;**联系人**&#x200B;上的&#x200B;**演示和协商阶段过渡**。 每个自转阶段最多可以接收两个接触点。 Contact上的阶段过渡与Lead上的阶段过渡之间的区别在于，Contact阶段过渡可以在OC接触点&#x200B;_之后_&#x200B;显示为Opportunity上的Boomerang接触点。 对于在Lead上发生的暂存过渡而言，情况并非如此，因为这些过渡显示为表单接触点。

![](assets/boomerang-boomerang-25.png)

在此示例中，Contact 1的Demo和Negotiation阶段过渡包括在Opportunity中作为Demo-01和Negotiation-01接触点。 Contact 2的Demo阶段过渡在&#x200B;_Contact 1的_&#x200B;之后发生，并在Opportunity中显示为Demo-02 （最后一个）接触点。

请注意，没有第二个过渡到“协商”阶段；Opportunity会立即从Demo-02 (Last)移动到Close Won。 在这种情况下，[!DNL Marketo Measure]将包括具有“已关闭的已获得”接触点的协商过渡。
