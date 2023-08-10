---
unique-page-id: 18874743
description: 正在连接 [!DNL Marketo Measure] 要取消退回脚本管理器，请执行以下操作 —  [!DNL Marketo Measure]  — 产品文档
title: 正在连接 [!DNL Marketo Measure] 用于取消退回脚本管理器
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---

# 正在连接 [!DNL Marketo Measure] 用于取消退回脚本管理器 {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] 直接与退件集成，允许您直接在中跟踪登陆页面转换的数字营销源 [!DNL Salesforce]. 要建立连接，只需添加 [!DNL Marketo Measure] 脚本到您的退件脚本管理器。 具体方法如下。

1. 登录 [!DNL Unbounce] 帐户。
1. 单击 **[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**.
1. 在弹出窗口中，选择 [!UICONTROL Custom Script] 并将其命名为”[!DNL Marketo Measure Marketing Analytics]“ 单击 **[!UICONTROL Add Script Details]**.
1. 选择Head中的位置。 在主登录页和表单确认对话框中包含脚本。 粘贴 [!DNL Marketo Measure] 将下面的脚本插入框中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 单击 **[!UICONTROL Save]**.

此 [!DNL Marketo Measure] 集成仅在Unbounce登陆页面上工作，前提是这些页面托管在您的域(例如，landing.mysite.com)上，而不是使用unbounce.com域的域上。
