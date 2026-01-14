---
description: 正在为Marketo Measure用户添加 [!DNL Marketo Measure] 至 [!DNL Hubspot] 指南
title: 正在将 [!DNL Marketo Measure] 添加到 [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 1%

---

# 正在将[!DNL Marketo Measure]添加到[!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

了解如何添加[!DNL Marketo Measure] JavaScript以跟踪[!DNL Hubspot]登陆页面和表单提交。

Hubspot与其他营销自动化系统略有不同，因为它可以托管您的登陆页面/表单以及您的网站。 请务必注意，以下说明适用于在[!DNL Marketo Measure]托管的页面中跟踪[!DNL Hubspot]活动。 如果您使用[!DNL Hubspot]以外的CMS（例如Wordpress）为网站提供支持，则还需要将[!DNL Marketo Measure] JavaScript添加到该CMS。

>[!NOTE]
>
>如果您通过标签管理提供程序（如[!DNL Google Tag Manager]）部署JavaScript，则无需手动将[!DNL Marketo Measure] JavaScript硬编码到您的网站中。

## 快速入门 {#getting-started}

登录[!DNL Hubspot]帐户后，请按照以下步骤操作。

1. 导航到内容。

1. 单击 **[!UICONTROL Content Settings]**。

1. 在[!UICONTROL Content Settings]内，单击站点标题HTML（参阅下图）。

1. 在`<header>`中添加以下脚本：

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   它应如下所示：

```html
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>此区域中可能已有其他跟踪代码片段，例如Google Analytics代码。 请确保用分号`;`和单个空格分隔它们，如下所示：
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
