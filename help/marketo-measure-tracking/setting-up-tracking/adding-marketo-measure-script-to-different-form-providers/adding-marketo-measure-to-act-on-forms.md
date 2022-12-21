---
unique-page-id: 18874753
description: 添加 [!DNL Marketo Measure] Forms。 [!DNL Marketo Measure]  — 产品文档
title: 添加 [!DNL Marketo Measure] 行动Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 0%

---

# 添加 [!DNL Marketo Measure] 行动Forms {#adding-marketo-measure-to-act-on-forms}

## 方向 {#directions}

1. 在您编辑的窗体中，选择 **[!UICONTROL Settings]** 选项。
1. 查找标记为 [!UICONTROL "External Web Analytics."] 这是您放置 [!DNL Marketo Measure] 跟踪代码段。

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>此区域中可能已存在其他跟踪代码片段，例如 [!DNL Google Analytics] 代码。 请务必使用分号分隔它们 `;` 和单个空间，如此：
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
