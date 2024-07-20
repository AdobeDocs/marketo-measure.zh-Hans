---
description: 接触点设置的最佳实践 —  [!DNL Marketo Measure]
title: 接触点设置的最佳实践
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
feature: Touchpoints
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# 接触点设置的最佳实践 {#best-practices-for-touchpoint-settings}

## 概述 {#overview}

[!DNL Marketo Measure]应用的[!UICONTROL Touchpoint Settings]部分允许您设置规则，这些规则将禁止或删除[!DNL Marketo Measure]数据和相关系统中的接触点。 这些规则可帮助您隔离不需要在您的买方接触点数据中表示的特定数据集，或者您不希望在不干扰跟踪和数据收集的情况下接收归因点数的数据集。

**接触点移除**&#x200B;意味着[!DNL Marketo Measure]将从您的CRM中清除（即移除）符合规则条件的任何接触点。 数据可以在[!DNL Marketo Measure] ROI仪表板（发现）中报告，但不显示在CRM中。 通常用于减轻CRM中数据存储限制的压力

**接触点抑制**&#x200B;类似于删除接触点，但无法在ROI仪表板中报告数据。 在CRM或发现中无法访问任何被禁止的接触点。 隐藏将确保您的CRM数据和发现数据相匹配。 通常用于优化并进一步指定您要接收归因点数的接触点数据。

在您的[!DNL Marketo Measure]应用程序中，[!UICONTROL Touchpoint Settings]部分将划分为四个关键部分。 每个部分隐藏或删除不同的数据集。 使用下面的键确保您的规则禁止或移除所需的接触点。

* 从CRM中删除购买者接触点
   * 当您想要创建一个规则以从您的&#x200B;**CRM**&#x200B;中删除&#x200B;**Buyer Touchpoint数据**（与个人而非机会关联的接触点）时，请使用此部分
* 从CRM禁止购买者接触点
   * 当您想要创建一个规则以从您的&#x200B;**CRM**&#x200B;和&#x200B;**Discover**&#x200B;中删除&#x200B;**Buyer Touchpoint数据**（与个人而非机会关联的接触点）时，请使用此部分
* 从CRM中删除买方归因接触点
   * 当您想要创建一个规则以从您的&#x200B;**CRM**&#x200B;中删除&#x200B;**Buyer Attribution Touchpoint**&#x200B;数据（与商机和收入关联的接触点）时，请使用此部分
* 从CRM禁止购买者归因接触点
   * 当您想要创建一个规则以从您的&#x200B;**CRM**&#x200B;和&#x200B;**Discover**&#x200B;中删除&#x200B;**Buyer Attribution Touchpoint**&#x200B;数据（与商机和收入关联的接触点）时，请使用此部分

## 最佳实践 {#best-practice}

无论您是首次建立接触点设置规则，还是只是审查这些规则以检查其准确性，请牢记以下最佳实践。

* 创建规则之前，建立要隐藏或删除的数据列表
* 准确地确定哪些字段将清楚地表示您设置的一个或多个规则
* 确保为规则指定了正确的运算符
* 利用上面的键，确保在接触点设置的正确部分中指定了您的规则
* 在CRM中通过复制买方接触点报表中的规则逻辑，在实施规则之前测试规则，以确保该规则会禁止或删除所需数据

## 维护的最佳实践 {#best-practice-for-maintenance}

查看您的[!UICONTROL Touchpoint Settings]很重要，因为他们可能会在定义不正确时大幅更改您的数据。 作为最佳实践，我们建议您每年至少两次查看您的接触点设置。 这是对[!DNL Marketo Measure]应用程序的“接触点设置”部分中设置的规则的简单可视化审查。 通过此审查，您能够确信您的接触点设置是最新的，并且可以相应地做出任何更改。

查看[!UICONTROL Touchpoint]设置的原因包括……

* 您的营销团队中的人员调整
* 对网站结构进行重大更新
* 识别不再有用的接触点数据
   * 无论您何时遇到您认为不应接收归因点数的接触点数据，都可以使用[!DNL touchpoint suppression]规则来确保数据尽可能干净和准确。
* 更改了用于定义禁止显示或删除规则的字段

>[!MORELIKETHIS]
>
>* [接触点移除和隐藏概述](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [为什么绝不应该删除接触点](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [买方接触点(BT)与买方归因接触点(BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)

