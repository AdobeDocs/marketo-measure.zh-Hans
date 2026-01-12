---
description: 使用数据加载器更新 [!DNL Marketo Measure] 自定义金额字段 —  [!DNL Marketo Measure]
title: 使用数据加载器更新Marketo Measure自定义金额字段
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
feature: Custom Revenue Amount
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---


# 使用数据加载器更新[!DNL Marketo Measure]自定义金额字段 {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure]建议使用数据加载器作为在[!DNL Marketo Measure]中使用自定义收入字段（我们使用开箱即用的金额字段）时更新机会值的方便选项。 与使用[!DNL Marketo Measure]更新脚本相比，首选使用数据加载器，因为此脚本要求用户在[!DNL Marketo Measure]脚本运行时禁用所有Salesforce验证规则。

## 使用数据加载器更新[!DNL Marketo Measure]自定义金额字段{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. 使用以下内容创建Excel工作表：

   * 机会ID
   * 自定义机会金额字段（您的首选收入字段）
   * [!DNL Marketo Measure]机会金额字段

1. 将首选收入字段中的值复制并粘贴到[!UICONTROL [!DNL Marketo Measure] Opportunity Amount]字段中。 然后，使用.csv文件更新这些Opp。

**_或者，您可以进入Salesforce并使用自定义列表视图批量编辑所有机会……_**

1. 为所有业务机会创建自定义列表视图。
1. 为首选收入字段添加筛选器不为空&#x200B;_和_ [!UICONTROL Marketo]度量机会金额字段为空。
1. 单击&#x200B;**[!UICONTROL Mass Edit]**，但实际上不更改任何内容。
1. 单击&#x200B;**[!UICONTROL Save]**。 这将触发工作流使用“软件收入”字段填充[!DNL Marketo Measure]机会金额字段。
