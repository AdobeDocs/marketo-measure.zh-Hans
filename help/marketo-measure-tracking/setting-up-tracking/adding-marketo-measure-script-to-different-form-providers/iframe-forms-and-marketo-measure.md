---
unique-page-id: 18874741
description: IFrame Forms和 [!DNL Marketo Measure] - [!DNL Marketo Measure]  — 产品文档
title: IFrame Forms和 [!DNL Marketo Measure]
exl-id: fe8d7403-27be-4702-a1b6-d574e1243c0a
source-git-commit: 51397a02872035fef41d308c1f855bcaecc29c4e
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%

---

# IFrame Forms和 [!DNL Marketo Measure] {#iframe-forms-and-marketo-measure}

使用 [!DNL Marketo Measure] 我们的核心功能之一是通过网站上的会话和表单提交来跟踪您的数字营销工作。 通常，当我们的JavaScript置于网站上时，我们会自动将其附加到网站上的所有表单。 但是，如果表单包含在IFrame中，则此功能会受到限制。

您可以将IFrame视为页面中的页面，因此正如我们请求将我们的脚本添加到您网站的所有页面一样，我们需要将脚本放置在IFrame中，以确保我们进行跟踪。

在很多情况下，我们会看到IFrame是通过营销自动化提供商进行管理的，因此您需要在该平台中或通过表单提供商进行配置。

我们建议将JavaScript放置在IFrame的标题中，然后从此处，我们将自动附加到该框架内的表单。

![](assets/1-1.png)

如果您对将我们的JavaScript添加到IFrame表单有任何疑问，请联系Adobe客户团队（您的客户经理）或 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
