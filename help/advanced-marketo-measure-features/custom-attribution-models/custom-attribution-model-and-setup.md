---
unique-page-id: 18874779
description: 自定义归因模型和设置 —  [!DNL Marketo Measure]  — 产品文档
title: 自定义归因模型和设置
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
feature: Attribution, Custom Models
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 0%

---

# 自定义归因模型和设置 {#custom-attribution-model-and-setup}

请参阅下文，了解更多关于 [!DNL Marketo Measure] 自定义归因模型以及如何设置它。

## 自定义归因模型 {#custom-attribution-model}

此 [!DNL Marketo Measure] 自定义归因模型允许用户选择要包含在模型中的接触点或自定义阶段。 用户能够控制归属于这些接触点和阶段的收入点数的百分比，也可以使用 [!DNL Marketo Measure] 机器学习模型。

## 如何设置自定义归因模型 {#how-to-set-up-your-custom-attribution-model}

1. 确定要包含在自定义模型中的阶段。

   要开始构建自定义归因模型，您需要选择哪些阶段对营销团队很重要。 除了 [!DNL Marketo Measure] 里程碑阶段(FT、LC、OC、Closed)您可以在自定义模型中添加最多六个额外的Lead/Contact状态或Opportunity阶段。 例如，MQL阶段通常包含在自定义模型中。 营销团队通常希望了解哪些工作或渠道正在推动向MQL阶段过渡。

   登录 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. 转到 [!UICONTROL My Account] > [!UICONTROL Settings] >并在CRM部分下，选择 **[!UICONTROL Stage Mapping]**.

   在此之后，您需要通过选择 **[!UICONTROL Include in Model]** 盒子。

   >[!NOTE]
   >
   >您最多允许六个自定义阶段（不包括默认值：FT、LC、OC、Closed）。

   ![](assets/1-1.png)

   >[!NOTE]
   >
   >_全部_ Leads/Contacts和Opportunity阶段将显示在此处，即使此阶段处于非活动状态或不再用于 [!DNL Salesforce]. 如果您希望删除这些阶段，则需要在 [!DNL Salesforce].

   选择阶段后，请务必单击 **[!UICONTROL Save & Process]** 按钮进行标记。 此时阶段将显示在 **[!UICONTROL Attribution Settings]** 选项卡中，您将能够向每个阶段分配归因百分比。 自定义阶段还将在Marketing Performance Suite中显示为Demand Waterfall中的Lead或Opportunity阶段。

   如果还有其他阶段要包括在模型中，但它们不在 [!UICONTROL Lead/Contact Status] 或 [!UICONTROL Opportunity Stage] 列表中，您可以根据CRM中的字段定义自己的自定义阶段。

   在以下示例中，使用日期字段定义自定义“MQL”阶段。 规则只是声明，如果MQL日期字段不为空，则应当将其视为MQL并应当包含在自定义模型中。 请注意，创建自定义阶段后对其进行排序也很重要，这样可以跟踪销售周期的进度。

   ![](assets/2-1.png)

   >[!CAUTION]
   >
   >别忘了为自定义字段启用历史记录跟踪。

如果您的自定义模型中正在使用自定义字段，则必须在CRM中启用字段历史记录跟踪。 有关如何启用字段历史记录跟踪的说明， [请单击此处](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md).

1. 确定自定义模型的归因百分比。

   转到 **[!UICONTROL Attribution Settings]** 在 [!DNL Marketo Measure] 应用程序；自定义阶段将显示在归因表中的此处。 归因表显示所有 [!DNL Marketo Measure] 归因模型和每个模型的归因权重。 前五个模型的归因百分比是固定的，无法更改。

   在标记为“”的最右列&#x200B;**[!UICONTROL Custom]**，”您可以在自定义归因模型中为每个阶段设置百分比权重。 只需在“自定义”列下输入每个阶段的值即可。 则 **[!UICONTROL Save and Reprocess]** 完成后。

   “自定义”列的左侧是 **[!DNL Marketo Measure]机器学习模型**. 机器学习模型根据每个自定义阶段发生的操作，根据赢得交易的相对重要性计算归因权重。 有关机器学习模型的更多信息， [请单击此处](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).

   ![](assets/3.png)

## 接触点位置 {#touchpoint-positions}

保存并处理归因百分比后，将更新接触点并接收其新阶段和职位。 在阶段过渡之前最近发生的接触点将获得该阶段的点数（如下所示）。 自定义权重和收入也会重新分配。

![](assets/4.png)

## 漏斗阶段和自定义模型阶段之间的区别 {#the-difference-between-funnel-stages-and-custom-model-stages}

现在，您可以在营销漏斗中看到自定义阶段，即使您未启用自定义模型也是如此。 这将通过使用漏斗暂存功能来实现。 漏斗阶段现在允许您向漏斗添加阶段，但看不到它们的归因。

漏斗暂存仍将作为接触点进行跟踪，并且仍将作为接触点位置显示在CRM中。 如果没有自定义模型，如果存在表单填充（中间接触为10%），这些接触点仍可能会获得中间接触归因，但如果只是Web访问，则不会获得归因点数。

如您所见，我们将“尽职调查”阶段作为漏斗阶段的一部分包括在内。 这意味着，我们将提供头寸包含尽职调查的接触点，但是，如果未启用“自定义模型”（最多为10%），这些接触点将仅获得中间接触归因点数。

![](assets/5.png)

>[!NOTE]
>
>BAT自定义模型的行为是将自定义模型中间接触百分比平均分配给其他阶段，前提是没有中间接触。
