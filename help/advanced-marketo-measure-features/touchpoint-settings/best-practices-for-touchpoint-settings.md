---
description: 接触点设置的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 接触点设置的最佳实践
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
feature: Touchpoints
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# 接触点设置的最佳实践 {#best-practices-for-touchpoint-settings}

## 概述 {#overview}

的接触点设置部分 [!DNL Marketo Measure] 应用程序允许您设置将禁止或从您的应用程序删除接触点的规则 [!DNL Marketo Measure] 数据及相关系统。 这些规则可帮助您隔离不需要在您的买方接触点数据中表示的特定数据集，或者您不希望在不干扰跟踪和数据收集的情况下接收归因点数的数据集。

**接触点移除** 方法 [!DNL Marketo Measure] 将从CRM中清除（即删除）符合规则条件的任何接触点。 数据可在中报告 [!DNL Marketo Measure] ROI功能板（发现），但不显示在CRM中。 通常用于减轻CRM中数据存储限制的压力

**接触点抑制** 与“删除接触点”类似，但无法在ROI功能板中报告数据。 在CRM或发现中无法访问任何被禁止的接触点。 隐藏将确保您的CRM数据和发现数据相匹配。 通常用于优化并进一步指定您要接收归因点数的接触点数据。

在您的 [!DNL Marketo Measure] 在应用程序中，接触点设置部分将划分为四个关键部分。 每个部分隐藏或删除不同的数据集。 使用下面的键确保您的规则禁止或移除所需的接触点。

* 从CRM中删除购买者接触点
   * 当您要创建要删除的规则时，请使用此部分 **买方接触点数据** （与个人关联的接触点，而不是与商机关联的接触点） **CRM**
* 从CRM禁止购买者接触点
   * 当您要创建要删除的规则时，请使用此部分 **买方接触点数据** （与个人关联的接触点，而不是与商机关联的接触点） **CRM** 和 **发现**
* 从CRM中删除买方归因接触点
   * 当您要创建要删除的规则时，请使用此部分 **买方归因接触点** 来自您的的数据（与商机和收入关联的接触点） **CRM**
* 从CRM禁止购买者归因接触点
   * 当您要创建要删除的规则时，请使用此部分 **买方归因接触点** 来自您的的数据（与商机和收入关联的接触点） **CRM** 和 **发现**

## 最佳实践 {#best-practice}

无论您是首次建立接触点设置规则，还是只是审查这些规则以检查准确性，请牢记以下最佳实践。

* 创建规则之前，建立要隐藏或删除的数据列表
* 准确地确定哪些字段将清楚地表示您设置的一个或多个规则
* 确保为规则指定了正确的运算符
* 利用上面的键，确保在接触点设置的正确部分中指定了您的规则
* 在CRM中通过复制买方接触点报表中的规则逻辑，在实施规则之前测试规则，以确保该规则会禁止或删除所需数据

## 维护的最佳实践 {#best-practice-for-maintenance}

查看您的接触点设置非常重要，因为它们可能会在定义不正确时大幅更改您的数据。 作为最佳实践，我们建议您每年至少两次查看您的接触点设置。 这是对在“ ”的接触点设置部分中设置的规则的简单可视化查看 [!DNL Marketo Measure] 应用程序。 通过此审查，您能够确信您的接触点设置是最新的，并且可以相应地做出任何更改。

查看接触点设置的原因包括……

* 您的营销团队中的人员调整
* 对网站结构进行重大更新
* 识别不再有用的接触点数据
   * 无论您何时遇到您认为不应接收归因点数的接触点数据，接触点抑制规则都可以确保您的数据尽可能干净和准确。
* 更改了用于定义禁止显示或删除规则的字段

>[!MORELIKETHIS]
>
>* [接触点移除和抑制概述](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [为什么绝不应该删除接触点](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [买方接触点(BT)与买方归因接触点(BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)
