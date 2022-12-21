---
unique-page-id: 18874759
description: 添加 [!DNL Marketo Measure] to [!DNL Hubspot] - [!DNL Marketo Measure]  — 产品文档
title: 添加 [!DNL Marketo Measure] to [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# 添加 [!DNL Marketo Measure] to [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

了解如何添加 [!DNL Marketo Measure] JavaScript来跟踪 [!DNL Hubspot] 登陆页面和表单提交。

Hubspot与其他营销自动化系统有些不同，因为它可以托管您的登陆页面/表单和您的网站。 请务必注意，以下说明是 [!DNL Marketo Measure] 跟踪活动 [!DNL Hubspot] — 托管页面。 如果您使用除 [!DNL Hubspot] （例如Wordpress），您需要将 [!DNL Marketo Measure] 也可以将JavaScript添加到该CMS。

>[!NOTE]
>
>如果要通过标签管理提供程序(如 [!DNL Google Tag Manager]，则无需手动对 [!DNL Marketo Measure] 将JavaScript导入您的网站。

## 快速入门 {#getting-started}

登录后 [!DNL Hubspot] 帐户，请执行以下步骤。

1. 导航到内容。

1. 单击 **[!UICONTROL Content Settings]**.

1. 在 [!UICONTROL Content Settings]，单击网站标题HTML（请参阅下图）。

1. 在 `<header>`:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   它应该如下所示：

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>此区域中可能已存在其他跟踪代码片段，如Google Analytics代码。 一定要用分号分隔 `;` 和单个空间，如此：
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
