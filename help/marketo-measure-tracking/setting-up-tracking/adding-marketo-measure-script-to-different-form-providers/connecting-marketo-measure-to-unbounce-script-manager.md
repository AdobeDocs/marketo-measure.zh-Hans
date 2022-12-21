---
unique-page-id: 18874743
description: 连接 [!DNL Marketo Measure] 取消退回脚本管理器 —  [!DNL Marketo Measure]  — 产品文档
title: 连接 [!DNL Marketo Measure] 取消退回脚本管理器
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---

# 连接 [!DNL Marketo Measure] 取消退回脚本管理器 {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] 直接与Unbounce集成，允许您直接在 [!DNL Salesforce]. 要建立连接，只需将 [!DNL Marketo Measure] 脚本到“退回脚本管理器”。 这是方法。

1. 登录到 [!DNL Unbounce] 帐户。
1. 单击 **[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**.
1. 在弹出窗口中，选择 [!UICONTROL Custom Script] 将其命名为“[!DNL Marketo Measure Marketing Analytics].&quot; 单击 **[!UICONTROL Add Script Details]**.
1. 在“头”中选择放置。 在主登陆页面和表单确认对话框中包含脚本。 粘贴 [!DNL Marketo Measure] 脚本。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 单击 **[!UICONTROL Save]**.

的 [!DNL Marketo Measure] 只要登陆页面托管在您的域（例如landing.mysite.com）上，而不是使用unbounce.com域的页面上，集成便可在取消跳出登陆页面上运行。
