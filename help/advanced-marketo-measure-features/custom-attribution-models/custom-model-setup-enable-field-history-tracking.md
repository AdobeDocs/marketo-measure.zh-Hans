---
unique-page-id: 18874777
description: 自定义模型设置 — 启用字段历史记录跟踪 —  [!DNL Marketo Measure]  — 产品文档
title: 自定义模型设置 — 启用字段历史记录跟踪
exl-id: 70328e67-051b-4864-891b-b251e49859c2
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# 自定义模型设置：启用字段历史记录跟踪 {#custom-model-setup-enable-field-history-tracking}

## 启用字段历史记录跟踪的原因和时间 {#why-and-when-to-enable-field-history-tracking}

如果您决定在自定义归因模型中将自定义字段作为阶段包含，则字段历史记录跟踪 **必须启用** 字段。 启用字段历史记录跟踪将允许 [!DNL Salesforce] 通过在“历史记录跟踪”表中创建记录来跟踪任何时候编辑自定义字段的情况。 [!DNL Marketo Measure] 可以下载该表并使用此信息来测量“过渡”发生的时间和日期。 如果没有字段历史记录跟踪， [!DNL Marketo Measure] 无法跟踪与此字段相关的更改。

如果仅 [!UICONTROL Lead Status] 或者，在自定义模型中使用了机会阶段，因此无需打开字段历史记录跟踪，因为它将作为阶段过渡自动跟踪。

要启用字段历史记录跟踪，请按照以下说明操作。

## 启用字段历史记录跟踪 {#enable-field-history-tracking}

>[!NOTE]
>
>您需要是系统管理员，才能对Lead/Contact/Opportunity对象上的字段进行这些更改。

1. 转到自定义字段所在的对象，然后单击 **[!UICONTROL Set History Tracking]** 按钮。

   ![](assets/1.png)

1. 选择要跟踪更改的字段。

   ![](assets/2.png)

[!DNL Marketo Measure] 只有在发现记录最近被修改时，才能重新导入记录。 公式字段在更改记录时从技术上讲不会修改记录，因为它在后台进行计算。 我们遇到了跳过规则的问题，因为 [!DNL Marketo Measure] 未看到记录更改，因此建议 **在规则定义中不使用公式字段**. 解决方案是创建一个文本字段，然后使用工作流在该字段中填充合适的值，或在任何编辑记录或符合标准时进行计算。 这要求对所有记录进行编辑，以便工作流可以追溯处理旧记录。
