---
unique-page-id: 18874795
description: 正在添加 [!DNL Marketo Measure] 脚本 —  [!DNL Marketo Measure]
title: 正在添加 [!DNL Marketo Measure] 脚本
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 0%

---

# 正在添加[!DNL Marketo Measure]脚本 {#adding-marketo-measure-script}

您希望[!DNL Marketo Measure]跟踪的[!DNL Marketo Measure]JavaScript应尽快添加到所有Web资产中。 部署JavaScript后，[!DNL Marketo Measure]将开始收集您的数字数据。 本文概述了部署[!DNL Marketo Measure] JavaScript的方法以及其他注意事项。

>[!NOTE]
>
>确保除了部署[!DNL Marketo Measure] JavaScript之外，您还[声明了 [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target="_blank"}中的所有相应域。

开始使用[!DNL Marketo Measure]时，可通过两种方式将[!DNL Marketo Measure] JavaScript添加到您的网站：

* 硬编码
* Tag Management

## 硬编码 {#hard-coding}

作为最佳实践，我们强烈建议将[!DNL Marketo Measure]JavaScript硬编码到您的Web资产。 若要对脚本进行硬编码，您需要将脚本放在网站的每个页面的结束`</head>`之前。

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

将JavaScript硬编码到页面的`<head>`中，可确保先加载[!DNL Marketo Measure]脚本，且不会丢失反向链接信息。 [!DNL Marketo Measure] JavaScript将异步加载。 如果进行了硬编码，则必须手动将JavaScript添加到Marketing Automation。

>[!TIP]
>
>了解如何确保您的脚本符合[GDPR](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target="_blank"}。

## Tag Management {#tag-management-systems}

如果无法通过硬编码添加[!DNL Marketo Measure]JavaScript，则另一个选项是使用Tag Management System(如[!DNL Google Tag Manager] (GTM)或Tealium)添加[!DNL Marketo Measure]脚本。

使用标记管理系统部署[!DNL Marketo Measure] JS可能会由于脚本加载时间延迟而导致5-10%的数据丢失。 基本上，如果标签管理工具加载不够快，[!DNL Marketo Measure] JS也无法加载足够快，并且可能会丢失第一个反向链接信息。

一种常见做法是通过标签管理工具部署[!DNL Marketo Measure] JS，直到时间/资源更好地转为硬编码。

要通过标签管理解决方案添加[!DNL Marketo Measure]脚本，您需要创建一个标签并在其中添加我们的JavaScript。 将此标记应用于网站上要跟踪的所有页面。

[!DNL Marketo Measure]建议任何页面查看都应导致触发标记。 此外，最好在触发顺序中为[!DNL Marketo Measure]指定最高优先级，并确保[!DNL Marketo Measure]标记前面没有同步脚本以确保最高数据质量。

可在[此处](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target="_blank"}找到更多信息。

## 其他注意事项 {#additional-considerations}

[!DNL Marketo Measure] JavaScript基于域，因此只要JavaScript位于页面上，并且根域与用于创建Marketo Measure帐户的域相同，它就可以自动处理任何子域。

但是，如果您使用任何单独的域或国际域，请务必通知您的[!DNL Marketo Measure]顾问。 这些域必须在[!DNL Marketo Measure]末尾手动添加到您的帐户，以便[!DNL Marketo Measure]知道将其他域的数据绑定到您的帐户。 因此，请向您的[!DNL Marketo Measure]顾问发送任何单独的/国际域。

如果您使用任何第三方页面，请与您的[!DNL Marketo Measure]顾问讨论您的用例。 通常，您会希望了解是否可以添加[!DNL Marketo Measure] JavaScript的自定义版本来跟踪这些页面（如果适用）。 如果无法执行此操作，我们将与您的[!DNL Marketo Measure]顾问探讨通过CRM Campaign接触点进行跟踪。

您是否有任何表单不应[!DNL Marketo Measure]跟踪，因为它们对归因不一定有意义（例如，取消订阅表单、客户登录等）？ 如果是，则要将此文章[&#128279;](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target="_blank"}中的排除代码添加到每个表单

您是否有任何非安全页面？ 您应该保护它们，因为在安全/非安全页面之间导航会中断跟踪会话。

请确保与您的Web团队进行交谈，以便他们知道[!DNL Marketo Measure] JavaScript应始终位于相应的Web资产上。 如果引入了新页面/表单/站点，请确保部署[!DNL Marketo Measure] JavaScript是协议的一部分。

如果在JavaScript设置期间触发了[!DNL Web Application Firewall (WAF)]警告，则用户可以禁用该WAF规则或允许列表Cookie，如下例所示：

![](assets/adding-marketo-measure-script-1.png)

## Forms将特别关注 {#forms-to-pay-extra-attention-to}

**多表单提交**

* 问题：如果单个表单提交中包含多个链接的表单，那么即使未提交完整表单，第一个表单也可能会生成接触点。
* 解决方案：您需要强制其中一个表单根据缓存的数据向[!DNL Marketo Measure]报告用户并讨论放弃实践。 通常，[报告用户代码](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"}可以解决此问题。

**帐户登录（不是创建）**

* 问题：[!DNL Marketo Measure]建议不要为后续帐户登录创建接触点，因为这些操作会稀释归因故事。
* 解决方案：将“排除代码”添加到帐户/客户/合作伙伴登录表单。

>[!NOTE]
>
>我们建议创建用于创建帐户或试用版的接触点。

**下载资源**

* 问题：如果您的资产被禁止，[!DNL Marketo Measure]会跟踪作为表单填写的下载。 如果您的资源没有限制，则无需自定义即可报告的内容会有一些限制。
* 解决方案：如果您希望[!DNL Marketo Measure] JavaScript跟踪该资源，请将其审核。 如果这不是一个选项，而您仍希望将其作为接触点，请考虑改为同步CRM Campaign。

**iFrames**

* 问题：iFrame基本上可用作页面中的页面。
* 解决方案：必须直接在iFrame标头中部署[!DNL Marketo Measure] JS，我们才能正确地附加到表单。

**灯箱**

* 灯箱通常是包含iFrame的弹出窗口
* 解决方案： [!DNL Marketo Measure] JS必须部署在该托管iFrame的标头中。

**页面上有多个表单**

* 问题：如果页面上有多个托管的表单，则您可能无法分辨哪个特定表单已使用[!DNL Marketo Measure]表单URL字段填写。
* 解决方案：如果您必须知道已填写哪个表单，请尝试使用Web团队设置动态URL哈希处理。

**Forms以`<div>`格式组织**

* 问题： [!DNL Marketo Measure] JS难以识别以`<div>`格式组织的表单，因此可能需要自定义代码。
* 解决方案：您的Web开发团队可以使用这些[报告用户模板](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"}来添加所需的代码。

**聊天**

* 问题：如果您使用聊天提供商，则可能需要特殊处理。
* 解决方案： [!DNL Marketo Measure]集成了Drift、Olark、Livechat、LivePerson和SnapEngage。 所有其他平台都需要通过CRM campaign会员资格进行跟踪。

**第二个域**

* 问题：[!DNL Marketo Measure] JavaScript是特定于域的，因此必须为任何单独的域或国际域采取额外的步骤。 [!DNL Marketo Measure] JS可以在同一根域上处理子域。
* 解决方案：如果您拥有多个根域，并且希望由[!DNL Marketo Measure]跟踪，请确保将JS添加到这些域，并告知[!DNL Marketo Measure]顾问应将哪些域手动关联到您的[!DNL Marketo Measure]帐户。

## 测试[!DNL Marketo Measure]JavaScript {#testing-marketo-measure-javascript}

您的[!DNL Marketo Measure]顾问将帮助您查明网站的测试情况，以确保[!DNL Marketo Measure] JavaScript在所有页面上都存在。 此测试的一部分是提交一些填入明确指示的测试详细信息的表单，以确保正确返回跟踪结果。

但是，您的[!DNL Marketo Measure]顾问可能不像您的Web团队那样熟悉您的网站。 因此，您的Web团队或其他相应的团队务必彻底检查网站，尤其是当存在与上述内容类似的复杂表单正在使用时。 您的团队最终将负责确保正确跟踪所有必需的Web资产，但是如果您了解任何复杂的表单或情况，则欢迎您向[!DNL Marketo Measure]顾问请求测试帮助。

要自行测试表单，请执行以下步骤：

1. 请始终使用无痕浏览器或清除每个表单提交测试之间的缓存，并且每次都使用不同的电子邮件地址。

   答：最佳做法是使用包含表明这是一次测试及时间的内容的假电子邮件。 例如：testing830am@test.com。

1. 记录要提交表单的页面的URL以及使用的电子邮件。

1. 找到在您的CRM（潜在客户或联系人）中为该表单提交创建的记录，并验证是否正确创建了接触点。

   a.您可以使用[!DNL Marketo Measure]库存报表，例如具有买方接触点的销售线索，或者如果您选择使用[!DNL Marketo Measure]详细信息更新页面布局，则可以查看销售线索/联系人页面布局。

   b.这可能需要一些时间来处理数据。
