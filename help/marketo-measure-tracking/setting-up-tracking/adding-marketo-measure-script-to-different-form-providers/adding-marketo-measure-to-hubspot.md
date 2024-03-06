---
unique-page-id: 18874759
description: 正在添加 [!DNL Marketo Measure] 到 [!DNL Hubspot] - [!DNL Marketo Measure]
title: 正在添加 [!DNL Marketo Measure] 到 [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# 正在添加 [!DNL Marketo Measure] 到 [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

了解如何添加 [!DNL Marketo Measure] JavaScript用于跟踪您的 [!DNL Hubspot] 登陆页面和表单提交。

Hubspot与其他营销自动化系统略有不同，因为它可以托管您的登陆页面/表单以及您的网站。 请务必注意，以下说明适用于拥有 [!DNL Marketo Measure] 跟踪活动 [!DNL Hubspot] — 托管的页面。 如果您使用CMS而不是 [!DNL Hubspot] （例如，Wordpress），您需要添加 [!DNL Marketo Measure] 将JavaScript也添加到该CMS中。

>[!NOTE]
>
>如果要通过标签管理提供程序（例如）部署JavaScript，请执行以下操作 [!DNL Google Tag Manager]，您无需手动硬编码 [!DNL Marketo Measure] 将JavaScript导入您的网站。

## 快速入门 {#getting-started}

登录 [!DNL Hubspot] 帐户，请按照以下步骤操作。

1. 导航到内容。

1. 单击 **[!UICONTROL Content Settings]**.

1. 范围 [!UICONTROL Content Settings]，单击站点标题HTML（请参阅下图）。

1. 在中添加以下脚本 `<header>`：

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   它应如下所示：

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>此区域中可能已有其他跟踪代码片段，例如Google Analytics代码。 请务必用分号分隔 `;` 和单个空间，如下所示：
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
