---
unique-page-id: 18874757
description: 正在添加 [!DNL Marketo Measure] javascript到 [!DNL Pardot] - [!DNL Marketo Measure]
title: 正在添加 [!DNL Marketo Measure] javascript到 [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# 正在添加 [!DNL Marketo Measure] javascript到 [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot] 除了在网站上放置脚本外，表单还需要在表单模板中进行其他处理，以便 [!DNL Marketo Measure] 识别表单提交。 该过程非常简单，只需将 [!DNL Marketo Measure] 将脚本跟踪到 [!DNL Pardot] 表单模板。

## 分步说明 {#step-by-step-instructions}

登录 [!DNL Pardot] 帐户，请按照以下步骤操作。

1. 导航到 **[!UICONTROL Marketing]**.

1. 单击 **[!UICONTROL Landing Pages]**.

1. 选择 **[!UICONTROL Layout Template]**.

   ![](assets/1-3.png)

1. 确定相应的布局模板并单击 **[!UICONTROL Edit]** 右边。

   ![](assets/2-1.png)

1. 复制并粘贴 [!DNL Marketo Measure] JavaScript代码，它位于HTML页面上的close header标记之前。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 对于所有适用的登陆页面布局模板，请按照以下步骤操作。

1. 确保 [!DNL Marketo Measure] JavaScript也位于常规站点页面上。

   在 [!DNL Pardot] 布局模板，代码将如下所示：

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## 其他说明 {#additional-notes}

如果 [!DNL Pardot] IFrame具有以下HTML标记：

`<base href="http://go.pardot.com">`

_和_ 当我们尝试将脚本加载到 [!DNL Pardot] 如果为IFrame，则浏览器将尝试在HTTPS页面上加载我们的脚本的HTTP版本，该操作将失败并阻止我们进行跟踪。 解决方案是更新 [!DNL Pardot] IFrame以加载我们的脚本的安全版本：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

此外，此区域中可能已有其他跟踪代码片段，例如 [!DNL Google Analytics] 代码。 请务必用分号分隔 `;` 和单个空格，如以下示例所示：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
