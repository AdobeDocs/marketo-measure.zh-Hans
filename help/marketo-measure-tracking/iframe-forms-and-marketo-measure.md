---
description: IFrame Forms和 [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: IFrame Forms和 [!DNL Marketo Measure]
exl-id: fe8d7403-27be-4702-a1b6-d574e1243c0a
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---


# IFrame Forms和[!DNL Marketo Measure] {#iframe-forms-and-marketo-measure}

通过[!DNL Marketo Measure]，核心功能之一是通过网站上的会话和表单提交跟踪您的数字营销工作。 通常，在网站上放置Marketo JavaScript时，我们会自动附加到网站上的所有表单。 但是，如果表单包含在IFrame中，则此功能存在限制。

可以将IFrame想象为页面中的一个页面，因此，就像我们请求将脚本添加到您的网站的所有页面一样，我们需要将脚本放置在IFrame中，以确保我们进行跟踪。

我们发现，在许多情况下，IFrame是通过营销自动化提供商管理的，因此您将需要在该平台内或通过表单提供商进行配置。

建议将JavaScript放在IFrame的头部，然后我们将自动附加到该框架中的表单。

![HTML代码](assets/1-1.png)

如果您对将我们的JavaScript添加到IFrame表单有任何疑问，请联系Adobe客户团队（您的客户经理）或[Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。
