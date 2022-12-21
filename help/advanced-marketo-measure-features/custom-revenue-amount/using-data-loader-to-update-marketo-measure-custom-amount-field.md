---
unique-page-id: 18874771
description: 使用数据加载器更新 [!DNL Marketo Measure] 自定义金额字段 —  [!DNL Marketo Measure]  — 产品文档
title: 使用数据加载器更新Marketo测量自定义金额字段
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%

---

# 使用数据加载器更新 [!DNL Marketo Measure] 自定义金额字段 {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] 建议在使用 [!DNL Marketo Measure]. 与使用 [!DNL Marketo Measure] 更新脚本，因为脚本要求用户在 [!DNL Marketo Measure] 脚本运行。

## 使用数据加载器更新 [!DNL Marketo Measure] 自定义金额字段{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. 使用创建Excel工作表：

   * 机会Id
   * Custom Opportunity Amount字段（您的首选收入字段）
   * [!DNL Marketo Measure] “机会金额”字段

1. 将首选收入字段的值复制并粘贴到 [!UICONTROL [!DNL Marketo Measure] Opportunity Amount] 字段。 然后，使用.csv文件更新这些Opp。

**_或者，您也可以进入Salesforce并使用自定义列表视图批量编辑所有业务机会……_**

1. 为所有Opportunity创建Custom List视图。
1. 为首选收入字段添加过滤器不为空 _和_ [!UICONTROL Marketo] “度量业务机会金额”字段为空。
1. 单击 **[!UICONTROL Mass Edit]**，但是不要改变任何内容。
1. 单击 **[!UICONTROL Save]**. 这将触发用于填充 [!DNL Marketo Measure] 包含“软件收入”字段的“机会金额”字段。
