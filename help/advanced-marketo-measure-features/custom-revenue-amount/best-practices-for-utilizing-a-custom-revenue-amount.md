---
description: 使用自定义收入金额的最佳实践 —  [!DNL Marketo Measure]
title: 利用自定义收入额的最佳实践
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
feature: Custom Revenue Amount
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# 利用自定义收入额的最佳实践 {#best-practices-for-utilizing-a-custom-revenue-amount}

## 概述 {#overview}

[!DNL Marketo Measure]的核心功能是能够将收入点数分配给购买者历程中的营销接触点。 准确收入归因的关键是[!DNL Marketo Measure]能够引用机会上的正确收入金额，这反过来又通过各种归因模型分布在不同营销接触点上。

除非在实施期间另有指定，否则您的[!DNL Marketo Measure]实例将设置为引用收入归因的标准机会金额（SFDC默认值）。 但是，对于许多[!DNL Marketo Measure]帐户，此字段不能反映机会的准确收入金额。 在这些实例中，[!DNL Marketo Measure]提供为[!DNL Marketo Measure]设置自定义收入金额的功能，以便在归因接触点(BAT)之间引用和分发。

## 最佳实践 {#best-practice}

在设置自定义收入额时，请牢记以下最佳实践，以确保您的[!DNL Marketo Measure]归因数据准确且一致！

切记事项：

* 选择适用于所有业务机会的准确且已使用的收入字段
   * 建议的ARR或合同总值
* 不使用公式字段
* 如果您使用自定义收入金额进行货币转换，则[!UICONTROL Marketo Measure Multiple Currencies]功能是首选方法。
   * [!DNL Marketo Measure]多货币功能引用在[!DNL Salesforce]中建立的兑换率，以最好地确保货币兑换之间保持一致。 这允许您继续使用标准“金额”（SFDC默认值）或与[!DNL Salesforce]转化率相关的任何其他自定义金额字段。
* 如果您更新要[!DNL Marketo Measure]引用的Amount字段，请使用数据加载器更新过去的业务机会，以确保收入数据一致，并通过工作流填充正确的字段

## 维护的最佳实践 {#best-practice-for-maintenance}

每年审查收入额设置可确保您的归因数据准确且与组织其余收入报表保持一致。

如果您使用自定义收入金额，请按照以下方式检查收入设置。

* 在您的[!DNL Marketo Measure]帐户中，转到CRM下的“[!UICONTROL Opportunities]”部分
* 识别[!UICONTROL Custom Opportunity Amount]字段，此处应列出您的[!UICONTROL custom revenue amount API]字段
* 确认这仍然是正确的字段
* 另外，让您的[!DNL Salesforce]管理员确认[!DNL Salesforce]中的自定义收入额工作流仍在运行

除了年度审查外，某些组织变化可能表明需要审查收入额设置……

* 您的营销团队中的人员调整
* 对自定义收入字段的更改
* 组织对收入报告方式所做的更改

>[!MORELIKETHIS]
>
>* [使用自定义收入金额字段](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [使用数据加载器更新自定义金额字段](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [多货币概述](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [多货币设置](/help/advanced-marketo-measure-features/multi-currency/settings.md)
