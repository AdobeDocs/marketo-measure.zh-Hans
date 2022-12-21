---
description: 接触点设置的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 接触点设置的最佳实践
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# 接触点设置的最佳实践 {#best-practices-for-touchpoint-settings}

## 概述 {#overview}

您的 [!DNL Marketo Measure] 应用程序允许您设置规则，以禁止或删除 [!DNL Marketo Measure] 数据和相关系统。 这些规则可帮助您在不影响跟踪和数据收集的情况下，隔离某些不需要在买方接触点数据中显示或不希望接收归因点数的数据集。

**删除接触点** 手段 [!DNL Marketo Measure] 将从您的CRM中清除（即删除）任何符合规则标准的接触点。 可以在 [!DNL Marketo Measure] ROI功能板(Discover)，但不显示在CRM中。 通常用于缓解CRM中数据存储限制的压力

**接触点抑制** 与删除接触点类似，但数据无法在ROI仪表板中报告。 CRM或Discover中将无法访问禁止的任何接触点。 抑制将确保CRM数据与Discover数据相匹配。 通常用于微调并进一步指定要接收归因点数的接触点数据。

在 [!DNL Marketo Measure] 应用程序中，“接触点设置”部分将划分为四个关键部分。 每个部分禁止或删除一组不同的数据。 使用下面的键，确保您的规则正在禁止或删除所需的接触点。

* 从CRM中删除采购员接触点
   * 当您要创建将删除的规则时，可使用此部分 **买方接触点数据** （与个人关联的接触点，而不是与机会关联的接触点） **CRM**
* 禁止CRM中的买方接触点
   * 当您要创建将删除的规则时，可使用此部分 **买方接触点数据** （与个人关联的接触点，而不是与机会关联的接触点） **CRM** 和 **Discover**
* 从CRM中删除购买者归因接触点
   * 当您要创建将删除的规则时，可使用此部分 **买方归因接触点** 您的 **CRM**
* 禁止CRM中的购买者归因接触点
   * 当您要创建将删除的规则时，可使用此部分 **买方归因接触点** 您的 **CRM** 和 **Discover**

## 最佳实践 {#best-practice}

无论您是首次建立接触点设置规则，还是仅查看规则以检查准确性，请牢记以下最佳实践。

* 在创建规则之前，建立要禁止或删除的数据列表
* 准确确定哪些字段将明确表示您正在设置的规则
* 确保为规则指定了正确的运算符
* 利用上述键，确保在“接触点设置”的正确部分中指定了您的规则
* 在实施规则之前，通过在CRM的买方接触点报表中复制规则逻辑，来确保该规则会禁止或删除所需数据，

## 维护最佳实践 {#best-practice-for-maintenance}

查看接触点设置非常重要，因为如果未正确定义，则这些设置会显着更改您的数据。 作为最佳实践，我们建议您每年至少查看两次接触点设置。 这是对在的“接触点设置”部分中设置的规则的简单直观查看 [!DNL Marketo Measure] 应用程序。 此审阅将让您确信您的接触点设置是最新的，并且可以相应地进行任何更改。

查看接触点设置的原因包括……

* 营销团队的营业额
* 对网站结构进行了重大更新
* 触点数据的标识不再有用
   * 每当您遇到您认为不应接收归因点点数据时，接触点抑制规则即是确保数据尽可能干净准确的功能。
* 对用于定义隐藏或移除规则的字段所做的更改

>[!MORELIKETHIS]
>
>* [接触点移除和抑制概述](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [为什么不应删除接触点](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [买方接触点(BT)与买方归因接触点(BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)

