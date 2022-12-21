---
unique-page-id: 18874757
description: 添加 [!DNL Marketo Measure] JavaScript到 [!DNL Pardot] - [!DNL Marketo Measure]  — 产品文档
title: 添加 [!DNL Marketo Measure] JavaScript到 [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# 添加 [!DNL Marketo Measure] JavaScript到 [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot] 除了要在网站上放置脚本之外，表单需要在表单模板内进行其他处理，才能 [!DNL Marketo Measure] 以识别表单提交。 流程简单；它只需要将 [!DNL Marketo Measure] 跟踪脚本 [!DNL Pardot] 表单模板。

## 分步说明 {#step-by-step-instructions}

登录 [!DNL Pardot] 帐户，请执行以下步骤。

1. 导航到 **[!UICONTROL Marketing]**.

1. 单击 **[!UICONTROL Landing Pages]**.

1. 选择 **[!UICONTROL Layout Template]**.

   ![](assets/1-3.png)

1. 确定相应的布局模板并单击 **[!UICONTROL Edit]** 右边。

   ![](assets/2-1.png)

1. 复制并粘贴 [!DNL Marketo Measure] JavaScript代码，紧靠HTML页面上的关闭标头标记之前。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 对于所有适用的登陆页面布局模板，请按照以下步骤操作。

1. 确保 [!DNL Marketo Measure] JavaScript也位于常规网站页面上。

   在 [!DNL Pardot] 布局模板中，代码将如下所示：

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## 其他说明 {#additional-notes}

如果 [!DNL Pardot] IFrame具有以下HTML标记：

`<base href="http://go.pardot.com">`

_和_ 当我们尝试在 [!DNL Pardot] 如果为IFrame，浏览器将尝试在HTTPS页面上加载我们脚本的HTTP版本，该版本将失败，并阻止我们跟踪。 解决方案是在 [!DNL Pardot] IFrame来加载脚本的安全版本：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

此外，此区域中可能已存在其他跟踪代码片段，例如 [!DNL Google Analytics] 代码。 一定要用分号分隔 `;` 和单个空格，如本例所示：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
