---
unique-page-id: 18874741
description: IFrame Forms和 [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: IFrame Forms和 [!DNL Marketo Measure]
exl-id: fe8d7403-27be-4702-a1b6-d574e1243c0a
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# IFrame Forms和 [!DNL Marketo Measure] {#iframe-forms-and-marketo-measure}

替换为 [!DNL Marketo Measure] 我们的核心功能之一，是通过您网站上的会议和表单提交来跟踪您的数字营销工作。 通常，在将JavaScript放在网站上时，我们会自动附加到网站上的所有表单。 但是，如果表单包含在IFrame中，我们就会遇到此功能的限制。

您可以将IFrame视为页面内的一个页面，因此，正如我们请求将我们的脚本添加到您的网站的所有页面一样，我们需要将脚本放置在IFrame中，以确保我们进行跟踪。

我们发现，在许多情况下，IFrame是通过营销自动化提供商管理的，因此您将需要在该平台内或通过表单提供商进行配置。

我们建议将JavaScript放在IFrame的头部，然后自动附加到该框架中的表单。

![](assets/1-1.png)

如果您对将我们的JavaScript添加到IFrame表单有任何疑问，请联系Adobe客户团队（您的客户经理）或 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
