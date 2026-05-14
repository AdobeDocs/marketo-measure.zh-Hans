---
unique-page-id: 18874753
description: 正在将 [!DNL Marketo Measure] 添加到实际操作Forms - [!DNL Marketo Measure]
title: 正在将 [!DNL Marketo Measure] 添加到实作Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
TQID: https://experienceleague.adobe.com/BUdHiCxfaG7a8Tays-Oqg9ZJQjSZJMM4-ChPHuF0RCg
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 73
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
