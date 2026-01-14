---
description: 自定义模型设置 — 为Marketo Measure用户启用字段历史记录跟踪指南
title: 自定义模型设置 — 启用字段历史记录跟踪
exl-id: 70328e67-051b-4864-891b-b251e49859c2
feature: Custom Models
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# 自定义模型设置：启用字段历史记录跟踪 {#custom-model-setup-enable-field-history-tracking}

## 启用字段历史记录跟踪的原因和时间 {#why-and-when-to-enable-field-history-tracking}

如果您决定在自定义归因模型中包括自定义字段作为阶段，则必须为此字段启用字段历史记录跟踪&#x200B;**&#x200B;**。 启用字段历史记录跟踪将允许[!DNL Salesforce]通过在“历史记录跟踪”表中创建记录来跟踪任何时候编辑自定义字段的情况。 [!DNL Marketo Measure]可以下载该表并使用此信息来测量发生“过渡”的时间和日期。 如果没有字段历史记录跟踪，[!DNL Marketo Measure]将无法跟踪与此字段相关的更改。

如果自定义模型中只使用了[!UICONTROL Lead Status]或机会阶段，则无需打开字段历史记录跟踪，因为字段历史记录将作为阶段过渡自动进行跟踪。

要启用字段历史记录跟踪，请按照以下说明操作。

## 启用字段历史记录跟踪 {#enable-field-history-tracking}

>[!NOTE]
>
>您需要是系统管理员才能对Lead/Contact/Opportunity对象上的字段进行这些更改。

1. 转到自定义字段所在的对象，然后单击&#x200B;**[!UICONTROL Set History Tracking]**&#x200B;按钮。

   ![](assets/custom-models-1.png)

1. 选择要跟踪更改的字段。

   ![](assets/custom-models-10.png)

[!DNL Marketo Measure]只有在看到记录最近被修改时，才能重新导入记录。 从技术上讲，公式字段在记录更改时不会修改记录，因为它在后台进行计算。 我们看到了跳过规则的问题，因为[!DNL Marketo Measure]没有看到记录更改，所以建议&#x200B;**不要在规则定义中使用公式字段**。 解决方法是创建一个文本字段，并使用工作流在编辑记录或满足条件时填充该字段以适当的值或计算。 这需要编辑所有记录，以便工作流可以追溯性地处理旧记录。
