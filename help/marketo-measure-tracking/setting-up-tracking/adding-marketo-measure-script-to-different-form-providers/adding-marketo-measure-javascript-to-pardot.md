---
unique-page-id: 18874757
description: 正在将 [!DNL Marketo Measure] JavaScript添加到 [!DNL Pardot] - [!DNL Marketo Measure]
title: 正在将 [!DNL Marketo Measure] JavaScript添加到 [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# 正在将[!DNL Marketo Measure]个JavaScript添加到[!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot]表单需要在表单模板中进行其他处理，而不仅仅是为[!DNL Marketo Measure]在站点上放置脚本以识别表单提交。 此过程很简单；它只需要将[!DNL Marketo Measure]跟踪脚本放入[!DNL Pardot]表单模板中。

## 分步说明 {#step-by-step-instructions}

登录[!DNL Pardot]帐户后，请按照以下步骤操作。

1. 导航到&#x200B;**[!UICONTROL Marketing]**。

1. 单击 **[!UICONTROL Landing Pages]**。

1. 选择 **[!UICONTROL Layout Template]**。

   ![](assets/1-3.png)

1. 确定适当的布局模板，然后单击右侧的&#x200B;**[!UICONTROL Edit]**。

   ![](assets/2-1.png)

1. 将[!DNL Marketo Measure]JavaScript代码复制并粘贴到HTML页面上的关闭页眉标记之前。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 对于所有适用的登陆页面布局模板，请按照以下步骤操作。

1. 确保[!DNL Marketo Measure] JavaScript也在常规站点页面上。

   在[!DNL Pardot]布局模板中，代码如下所示：

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## 其他说明 {#additional-notes}

如果[!DNL Pardot] IFrame具有以下HTML标记：

`<base href="http://go.pardot.com">`

_和_ IFrame本身实际上是一个安全页面(HTTPS)而不是不安全(HTTP)，在[!DNL Pardot] IFrame中加载脚本时，浏览器会尝试在HTTPS页面上加载脚本的HTTP版本，这样会失败，从而中断跟踪。 解决方案是更新[!DNL Pardot] IFrame上的脚本以加载脚本的安全版本：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

此区域可能已有其他跟踪代码片段，如[!DNL Google Analytics]代码。 请确保用分号`;`和单个空格分隔它们，如以下示例所示：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
