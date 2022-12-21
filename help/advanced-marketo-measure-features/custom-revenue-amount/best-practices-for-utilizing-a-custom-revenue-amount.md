---
description: 利用自定义收入金额的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 利用自定义收入金额的最佳实践
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# 利用自定义收入金额的最佳实践 {#best-practices-for-utilizing-a-custom-revenue-amount}

## 概述 {#overview}

的核心功能 [!DNL Marketo Measure] 是能够在整个购买者历程中将收入信用分配给营销接触点。 准确的收入归因关键在于 [!DNL Marketo Measure] 参考Opportunity上正确的收入额，而Opportunity又通过各种归因模型在营销接触点中分配。

除非在实施期间另有指定，否则您的 [!DNL Marketo Measure] 实例将设置为引用收入归因的标准机会金额（SFDC默认值）。 但是，对于许多人 [!DNL Marketo Measure] 帐户中，此字段不反映Opportunity的准确收入额。 在这些情况下， [!DNL Marketo Measure] 提供了为 [!DNL Marketo Measure] 在归因接触点(BAT)中引用和分发。

## 最佳实践 {#best-practice}

在设置自定义收入额时，请牢记以下最佳实践，以确保您的 [!DNL Marketo Measure] 归因数据准确一致！

请牢记以下事项：

* 选择准确且用于所有Opportunity的收入字段
   * 建议使用ARR或总合同值
* 请勿使用公式字段
* 如果您使用自定义收入金额进行货币换算，则 [!UICONTROL Marketo Measure Multiple Currencies] 首选方法是功能。
   * 的 [!DNL Marketo Measure] 多币种功能引用了 [!DNL Salesforce] 以最好地确保货币换算之间保持一致。 这允许您继续利用标准“金额”（SFDC默认值），或与 [!DNL Salesforce] 转化率。
* 如果您更新所需的“金额”字段 [!DNL Marketo Measure] 要引用，请使用Data Loader更新以往的Opportunity ，以确保收入数据一致，并通过工作流填充相应的字段

## 维护最佳实践 {#best-practice-for-maintenance}

每年审核收入额设置将确保归因数据准确无误，并与贵组织的其他收入报表保持一致。

如果您使用自定义收入额，请按如下方式检查收入设置。

* 在 [!DNL Marketo Measure] 帐户，转到&#39;[!UICONTROL Opportunities]“部分”
* 识别 [!UICONTROL Custom Opportunity Amount] 字段，给 [!UICONTROL custom revenue amount API] 字段
* 确认这仍然是正确的字段
* 另请 [!DNL Salesforce] 管理员确认 [!DNL Salesforce] 仍在运行

除每年审核外，某些组织更改可能表示需要审核收入额设置……

* 营销团队的营业额
* 对“自定义收入”字段的更改
* 组织对收入报告方式的更改

>[!MORELIKETHIS]
>
>* [使用自定义收入金额字段](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [使用数据加载器更新自定义金额字段](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [多货币概述](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [多货币设置](/help/advanced-marketo-measure-features/multi-currency/settings.md)

