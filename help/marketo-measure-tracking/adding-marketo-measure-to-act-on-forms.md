---
description: '正在向Marketo Measure用户的实际Forms指南中添加 [!DNL Marketo Measure] '
title: 正在将 [!DNL Marketo Measure] 添加到实作Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 0%

---

# 正在将[!DNL Marketo Measure]添加到实作Forms {#adding-marketo-measure-to-act-on-forms}

## 方向 {#directions}

1. 在正在编辑的表单中，选择右上角的&#x200B;**[!UICONTROL Settings]**&#x200B;选项。
1. 查找标记为[!UICONTROL "External Web Analytics."]的区域。您将在此处放置[!DNL Marketo Measure]跟踪代码段。

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>此区域可能已有其他跟踪代码片段，如[!DNL Google Analytics]代码。 请确保使用分号`;`和单个空格分隔它们，如下所示：
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
