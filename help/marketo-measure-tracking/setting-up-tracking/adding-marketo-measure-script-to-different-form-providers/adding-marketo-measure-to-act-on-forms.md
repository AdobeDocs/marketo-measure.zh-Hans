---
unique-page-id: 18874753
description: 正在添加 [!DNL Marketo Measure] 要实施Forms，请执行以下操作： [!DNL Marketo Measure]  — 产品文档
title: 正在添加 [!DNL Marketo Measure] 实施Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 0%

---

# 正在添加 [!DNL Marketo Measure] 实施Forms {#adding-marketo-measure-to-act-on-forms}

## 方向 {#directions}

1. 在正在编辑的表单中，选择 **[!UICONTROL Settings]** 选项。
1. 查找标记为的区域 [!UICONTROL "External Web Analytics."] 您将在此处放置 [!DNL Marketo Measure] 跟踪代码段。

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>此区域中可能已有其他跟踪代码片段，例如 [!DNL Google Analytics] 代码。 请务必使用分号分隔它们 `;` 和单个空间，如下所示：
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
