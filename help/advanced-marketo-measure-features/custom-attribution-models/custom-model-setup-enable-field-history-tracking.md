---
unique-page-id: 18874777
description: 自定义模型设置 — 启用字段历史记录跟踪 —  [!DNL Marketo Measure]
title: 自定义模型设置 — 启用字段历史记录跟踪
exl-id: 70328e67-051b-4864-891b-b251e49859c2
feature: Custom Models
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---

# 自定义模型设置：启用字段历史记录跟踪 {#custom-model-setup-enable-field-history-tracking}

## 启用字段历史记录跟踪的原因和时间 {#why-and-when-to-enable-field-history-tracking}

如果您决定在自定义归因模型中包括自定义字段作为阶段，则字段历史记录跟踪 **必须启用** 用于此字段。 启用字段历史记录跟踪将允许 [!DNL Salesforce] 要跟踪自定义字段的任何编辑时间，请在“历史记录跟踪”表中创建记录。 [!DNL Marketo Measure] 可以下载该表并使用此信息衡量“过渡”发生的时间和日期。 如果没有字段历史记录跟踪， [!DNL Marketo Measure] 无法跟踪与此字段相关的更改。

如果 [!UICONTROL Lead Status] 或Opportunity阶段用于自定义模型中，无需打开Field History跟踪，因为它将作为阶段过渡自动进行跟踪。

要启用字段历史记录跟踪，请按照以下说明操作。

## 启用字段历史记录跟踪 {#enable-field-history-tracking}

>[!NOTE]
>
>您需要是系统管理员才能对Lead/Contact/Opportunity对象上的字段进行这些更改。

1. 转到自定义字段所在的对象，然后单击 **[!UICONTROL Set History Tracking]** 按钮。

   ![](assets/1.png)

1. 选择要跟踪更改的字段。

   ![](assets/2.png)

[!DNL Marketo Measure] 仅当发现记录最近被修改时，才能重新导入记录。 从技术上讲，公式字段在记录更改时不会修改记录，因为它在后台进行计算。 我们已经发现跳过了规则的问题，原因如下 [!DNL Marketo Measure] 未看到记录更改，因此建议 **在规则定义中不使用公式字段**. 解决方法是创建一个文本字段，并使用工作流在编辑记录或满足条件时填充该字段以适当的值或计算。 这需要编辑所有记录，以便工作流可以追溯性地处理旧记录。
