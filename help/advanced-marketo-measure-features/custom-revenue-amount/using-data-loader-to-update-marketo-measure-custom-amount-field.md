---
unique-page-id: 18874771
description: 使用数据加载器进行更新 [!DNL Marketo Measure] 自定义金额字段 —  [!DNL Marketo Measure]
title: 使用数据加载器更新Marketo Measure自定义金额字段
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
feature: Custom Revenue Amount
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# 使用数据加载器进行更新 [!DNL Marketo Measure] 自定义金额字段 {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] 建议使用Data Loader作为使用中的自定义收入字段（我们使用开箱即用的金额字段）时更新机会值的方便选项 [!DNL Marketo Measure]. 与使用Data Loader相比，后者更可取 [!DNL Marketo Measure] 更新脚本，因为脚本要求用户禁用所有Salesforce验证规则，而 [!DNL Marketo Measure] 脚本运行。

## 使用数据加载器进行更新 [!DNL Marketo Measure] 自定义金额字段{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. 使用以下内容创建Excel工作表：

   * 机会ID
   * 自定义机会金额字段（您的首选收入字段）
   * [!DNL Marketo Measure] 机会金额字段

1. 将首选收入字段中的值复制并粘贴到 [!UICONTROL [!DNL Marketo Measure] Opportunity Amount] 字段。 然后，使用.csv文件更新这些Opp。

**_或者，您可以进入Salesforce并使用自定义列表视图批量编辑所有机会……_**

1. 为所有业务机会创建自定义列表视图。
1. 为首选收入字段添加过滤器不为空 _和_ [!UICONTROL Marketo] “衡量机会金额”字段为空。
1. 单击 **[!UICONTROL Mass Edit]**，但实际上不会更改任何内容。
1. 单击 **[!UICONTROL Save]**. 这将触发工作流以填充 [!DNL Marketo Measure] Opportunity Amount字段和Software Revenue字段。
