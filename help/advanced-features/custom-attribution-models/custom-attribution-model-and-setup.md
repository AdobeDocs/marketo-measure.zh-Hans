---
description: 自定义归因模型和设置 —  [!DNL Marketo Measure]
title: 自定义归因模型和设置
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
feature: Attribution, Custom Models
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 0%

---


# 自定义归因模型和设置 {#custom-attribution-model-and-setup}

有关[!DNL Marketo Measure]自定义归因模型以及如何设置的概述，请参阅下文。

## 自定义归因模型 {#custom-attribution-model}

[!DNL Marketo Measure]自定义归因模型允许用户选择要包含在模型中的接触点或自定义阶段。 用户能够控制归属于这些接触点和阶段的收入点数的百分比，也可以使用[!DNL Marketo Measure]机器学习模型建议的归因百分比值。

## 如何设置自定义归因模型 {#how-to-set-up-your-custom-attribution-model}

1. 确定要包含在自定义模型中的阶段。

   要开始构建自定义归因模型，您需要选择哪些阶段对营销团队很重要。 除了[!DNL Marketo Measure]里程碑阶段(FT、LC、OC、Closed)之外，您还可以在自定义模型中添加最多六个额外的Lead/Contact状态或Opportunity阶段。 例如，MQL阶段通常包含在自定义模型中。 营销团队通常希望了解哪些工作或渠道正在推动向MQL阶段过渡。

   登录到[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}。 转到[!UICONTROL My Account] > [!UICONTROL Settings] >，然后在CRM部分下，选择&#x200B;**[!UICONTROL Stage Mapping]**。

   接下来，通过选择&#x200B;**[!UICONTROL Include in Model]**&#x200B;框选择要包括的Leads/Contacts和Opportunity阶段。

   >[!NOTE]
   >您最多允许六个自定义阶段（不包括默认值：FT、LC、OC、Closed）。

   ![ 1](assets/1-1.png)

   >[!NOTE]
   >_所有_&#x200B;潜在客户/联系人和机会阶段将显示在此处，即使该阶段已停用或不再用于[!DNL Salesforce]也是如此。 如果要删除这些阶段，则需要在[!DNL Salesforce]中硬删除它们。

   选择阶段后，请确保单击页面底部的&#x200B;**[!UICONTROL Save & Process]**&#x200B;按钮。 阶段现在将显示在&#x200B;**[!UICONTROL Attribution Settings]**&#x200B;选项卡中，您将能够向每个阶段分配归因百分比。 自定义阶段还将在Marketing Performance Suite中显示为Demand Waterfall中的Lead或Opportunity阶段。

   如果您希望在模型中包含其他阶段，但这些阶段不在[!UICONTROL Lead/Contact Status]或[!UICONTROL Opportunity Stage]列表中，则可以根据CRM中的字段定义自己的自定义阶段。

   在以下示例中，使用日期字段定义自定义“MQL”阶段。 规则只是声明，如果MQL日期字段不为空，则应当将其视为MQL并应当包含在自定义模型中。 创建自定义阶段后，对其进行排序也很重要，这样可以跟踪销售周期的进度。

   ![ 1](assets/2-1.png)

   >[!CAUTION]
   >别忘了为自定义字段启用历史记录跟踪。

如果您的自定义模型中使用了自定义字段，则必须在CRM中启用字段历史记录跟踪。 有关启用字段历史记录跟踪的说明，请参阅[自定义模型设置：启用字段历史记录跟踪](/help/advanced-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)。

1. 确定自定义模型的归因百分比。

   转到&#x200B;**[!UICONTROL Attribution Settings]**&#x200B;应用程序中的[!DNL Marketo Measure]；自定义阶段将显示在归因表中。 归因表显示所有[!DNL Marketo Measure]归因模型以及每个模型的归因权重。 前五个模型的归因百分比是固定的，无法更改。

   在标记为“**[!UICONTROL Custom]**”的最右列中，您可以为自定义归因模型中的每个阶段设置百分比权重。 在自定义列下输入每个阶段的值，完成后，单击&#x200B;**[!UICONTROL Save and Reprocess]**。

   _自定义_&#x200B;列的左侧是&#x200B;**[!DNL Marketo Measure]机器学习模型**。 机器学习模型根据每个自定义阶段发生的操作，根据赢得交易的相对重要性计算归因权重。 有关机器学习模型的详细信息，请参阅[机器学习模型常见问题解答](/help/advanced-features/custom-attribution-models/machine-learning-model-faq.md)。

   ![显示自定义模型权重的“归因设置”表](assets/3.png)

## 接触点位置 {#touchpoint-positions}

保存并处理归因百分比后，将更新接触点并接收其新阶段和职位。 在阶段过渡之前最近发生的接触点将获得该阶段的点数（如下所示）。 自定义权重和收入也会重新分配。

应用了自定义阶段的![接触点位置](assets/4.png)

## funnel阶段和自定义模型阶段之间的区别 {#the-difference-between-funnel-stages-and-custom-model-stages}

现在，您可以在营销Funnel中查看自定义阶段，即使您未启用自定义模型也是如此。 可以通过使用我们的Funnel Stage功能实现这一点。 funnel暂存现在允许您向funnel添加暂存，但无法查看其归因。

funnel暂存仍将作为接触点进行跟踪，并且仍将作为接触点位置显示在CRM中。 如果没有自定义模型，如果存在表单填充（中间接触为10%），这些接触点仍可能会获得中间接触归因，但如果只是Web访问，则不会获得归因点数。

如您所见，我们将“尽职调查”阶段作为Funnel Stages的一部分包括在内。 这意味着，我们将提供头寸包含尽职调查的接触点，但是，如果未启用“自定义模型”（最多为10%），这些接触点将仅获得中间接触归因点数。

![营销funnel包括自定义尽职调查阶段接触点](assets/5.png)

>[!NOTE]
>BAT自定义模型的行为是将自定义模型中间接触百分比平均分配到其他阶段，前提是没有中间接触。
