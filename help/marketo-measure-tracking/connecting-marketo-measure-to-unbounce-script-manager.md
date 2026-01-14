---
description: 正在为Marketo Measure用户将 [!DNL Marketo Measure] 连接到退件脚本管理器指南
title: 正在将 [!DNL Marketo Measure] 连接到退件脚本管理器
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 3%

---


# 正在将[!DNL Marketo Measure]连接到退件脚本管理器 {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure]直接与“退回”集成，允许您直接在[!DNL Salesforce]中跟踪登陆页面转换的数字营销源。 要建立连接，只需将[!DNL Marketo Measure]脚本添加到您的退件脚本管理器中。 操作方法如下：

1. 登录到您的[!DNL Unbounce]帐户。
1. 单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**。
1. 在弹出窗口中，选择[!UICONTROL Custom Script]并将其命名为“[!DNL Marketo Measure Marketing Analytics]”。 单击 **[!UICONTROL Add Script Details]**。
1. 选择Head中的位置。 在主登录页和表单确认对话框中包含脚本。 将下面的[!DNL Marketo Measure]脚本粘贴到框中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 单击 **[!UICONTROL Save]**。

[!DNL Marketo Measure]集成适用于回弹登陆页面，前提是这些页面托管在您的域(例如，landing.mysite.com)上，而不是使用unbounce.com域的域。
