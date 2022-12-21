---
unique-page-id: 18874779
description: 自定义归因模型和设置 —  [!DNL Marketo Measure]  — 产品文档
title: 自定义归因模型和设置
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 0%

---

# 自定义归因模型和设置 {#custom-attribution-model-and-setup}

请参阅下文，了解 [!DNL Marketo Measure] 自定义归因模型及其设置方法。

## 自定义归因模型 {#custom-attribution-model}

的 [!DNL Marketo Measure] 自定义归因模型允许用户选择要包含在模型中的接触点或自定义阶段。 用户能够控制归因于这些接触点和阶段的收入点数百分比，或者可以使用 [!DNL Marketo Measure] 机器学习模型。

## 如何设置自定义归因模型 {#how-to-set-up-your-custom-attribution-model}

1. 确定要包含在自定义模型中的阶段。

   要开始构建自定义归因模型，您需要选择哪些阶段对您的营销团队而言非常重要。 除 [!DNL Marketo Measure] 里程碑阶段（FT、LC、OC、已关闭）您可以在自定义模型中添加最多六个其他潜在客户/联系人状态或商机阶段。 例如，MQL阶段通常包含在自定义模型中。 营销团队通常希望了解哪些工作或渠道正在推动过渡到MQL阶段。

   登录到 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}。 转到 [!UICONTROL My Account] > [!UICONTROL Settings] >，然后在CRM部分下，选择 **[!UICONTROL Stage Mapping]**.

   在此，您需要通过选择 **[!UICONTROL Include in Model]** 框中。

   >[!NOTE]
   >
   >最多允许您六个自定义阶段（不包括默认阶段）：FT、LC、OC、关闭)。

   ![](assets/1-1.png)

   >[!NOTE]
   >
   >_全部_ 潜在客户/联系人和机会阶段将显示在此处，即使该阶段处于非活动状态或不再在中使用 [!DNL Salesforce]. 如果要删除这些阶段，则需要在 [!DNL Salesforce].

   选择阶段后，请确保单击 **[!UICONTROL Save & Process]** 按钮。 这些阶段现在将显示在 **[!UICONTROL Attribution Settings]** 选项卡，您将能够向每个阶段分配归因百分比。 自定义阶段也将在营销绩效套件中作为需求瀑布中的潜在客户或机会阶段显示。

   如果要在模型中包含其他阶段，但它们不在 [!UICONTROL Lead/Contact Status] 或 [!UICONTROL Opportunity Stage] 列表中，您可以根据CRM中的字段定义自己的自定义阶段。

   在以下示例中，使用日期字段定义了自定义“MQL”阶段。 该规则仅声明，如果“MQL日期”字段不为空，则应将其视为MQL，并应包含在自定义模型中。 请注意，在创建自定义阶段后，务必对其进行排序，以便其遵循销售周期的进展。

   ![](assets/2-1.png)

   >[!CAUTION]
   >
   >请不要忘记为自定义字段启用历史记录跟踪。

如果自定义模型中正在使用自定义字段，则必须在CRM中启用字段历史记录跟踪。 有关如何启用字段历史记录跟踪的说明， [请单击此处](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md).

1. 确定自定义模型的归因百分比。

   转到 **[!UICONTROL Attribution Settings]** in [!DNL Marketo Measure] 应用程序；自定义阶段将显示在归因表的此处。 归因表将显示 [!DNL Marketo Measure] 归因模型，以及每个模型的归因权重。 前五个模型的归因百分比是固定的，无法更改。

   在最右侧的列中，标有“**[!UICONTROL Custom]**，”您可以在自定义归因模型中为每个阶段设置百分比权重。 只需在“自定义”列下输入每个阶段的值即可。 然后 **[!UICONTROL Save and Reprocess]** 完成后。

   “自定义”列的左侧是 **[!DNL Marketo Measure]机器学习模型**. 机器学习模型根据在每个自定义阶段发生的事件对于赢得交易的相对重要性来计算归因权重。 有关机器学习模型的更多信息， [请单击此处](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).

   ![](assets/3.png)

## 接触点位置 {#touchpoint-positions}

保存并处理归因百分比后，接触点将更新并接收其新阶段和位置。 最近在阶段过渡之前发生的接触点将收到该阶段的点数（如下所示）。 自定义权重和收入也会重新分配。

![](assets/4.png)

## 漏斗阶段与自定义模型阶段之间的差异 {#the-difference-between-funnel-stages-and-custom-model-stages}

现在，即使您未启用自定义模型，您也可以在营销漏斗中看到自定义阶段。 这将通过使用我们的漏斗阶段功能。 漏斗阶段现在允许您向漏斗中添加阶段，但看不到这些阶段的归因。

漏斗阶段仍将作为接触点进行跟踪，并且仍将在您的CRM中显示为接触点位置。 如果没有自定义模型，则这些接触点在填写表单（中间接触为10%）时仍可能会收到中间接触归因，但如果只是Web访问，则归因点数为零。

如下所示，我们除了漏斗阶段之外，还加入了“尽职调查”阶段。 这意味着，我们将拥有职位包含“尽职调查”的接触点，但这些接触点将仅在未启用“自定义模型”（最多10%）的情况下才会收到“中间接触归因”点数。

![](assets/5.png)

>[!NOTE]
>
>BAT自定义模型的行为是在没有中间接触的情况下，将自定义模型的中间接触百分比平均分配到其他阶段。
