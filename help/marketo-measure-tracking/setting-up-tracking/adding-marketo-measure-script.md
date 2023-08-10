---
unique-page-id: 18874795
description: 正在添加 [!DNL Marketo Measure] 脚本 —  [!DNL Marketo Measure]  — 产品文档
title: 正在添加 [!DNL Marketo Measure] 脚本
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 0%

---

# 正在添加 [!DNL Marketo Measure] 脚本 {#adding-marketo-measure-script}

[!DNL Marketo Measure] 您希望跟踪的JavaScript [!DNL Marketo Measure] 应尽快添加到所有Web属性中。 部署JavaScript后， [!DNL Marketo Measure] 将开始收集您的数字数据。 本文概述了部署方法 [!DNL Marketo Measure] 要考虑的JavaScript和其他注意事项。

>[!NOTE]
>
>确保您已 [已在 [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target="_blank"} 除了部署 [!DNL Marketo Measure] JavaScript。

开始使用时 [!DNL Marketo Measure]，您可以通过两种方式添加 [!DNL Marketo Measure] JavaScript到您的网站：

* 硬编码
* Tag Management

## 硬编码 {#hard-coding}

作为最佳实践，我们强烈建议使用硬编码 [!DNL Marketo Measure] JavaScript到Web资产。 若要对脚本进行硬编码，您需要将脚本放在结束位置之前 `</head>` 在您网站的每个页面上。

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

将JavaScript硬编码到 `<head>` 页面的URL可确保 [!DNL Marketo Measure] 脚本将首先加载，并且不会错过推荐信息。 此 [!DNL Marketo Measure] JavaScript以异步方式加载。 如果进行硬编码，则必须手动将JavaScript添加到“营销自动化”。

>[!TIP]
>
>了解如何确保您的脚本是 [符合GDPR](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target="_blank"}.

## Tag Management {#tag-management-systems}

如果添加 [!DNL Marketo Measure] 无法通过硬编码使用JavaScript，另一个选项是添加 [!DNL Marketo Measure] 使用Tag Management系统编写脚本，例如 [!DNL Google Tag Manager] (GTM)或Tealium。

请注意，使用标签管理系统进行部署 [!DNL Marketo Measure] 由于脚本加载时间延迟，JS可能会导致5-10%的数据丢失。 基本上，如果标签管理工具加载得不够快， [!DNL Marketo Measure] JS加载速度也无法足够快，并且可能会丢失第一个反向链接信息。

一种常见做法是部署 [!DNL Marketo Measure] JS通过标签管理工具，直到时间/资源更好地转为硬编码。

添加 [!DNL Marketo Measure] 通过标记管理解决方案编写脚本，您将需要创建新标记并在其中添加我们的JavaScript。 将此标记应用于网站上要跟踪的所有页面。

[!DNL Marketo Measure] 建议任何页面查看都应导致触发标记。 另外，最好给予 [!DNL Marketo Measure] 触发顺序中的最高优先级，并确保前面没有同步脚本 [!DNL Marketo Measure] 标记以确保最高数据质量。

更多信息可以是 [在此处找到](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target="_blank"}.

## 其他注意事项 {#additional-considerations}

[!DNL Marketo Measure] JavaScript基于域，因此只要JavaScript位于页面上，并且根域与用于创建Marketo Measure帐户的域相同，它就可以自动处理任何子域。

但是，如果您使用任何单独的域或国际域，请务必让您的 [!DNL Marketo Measure] 咨询师知道。 需要手动将域添加到您帐户的 [!DNL Marketo Measure] 结束 [!DNL Marketo Measure] 知道将其他域的数据绑定到您的帐户。 因此，请将任何单独的/国际域名发送至 [!DNL Marketo Measure] 顾问。

如果您使用任何第三方页面，请与您的团队讨论您的用例 [!DNL Marketo Measure] 顾问。 通常，您会希望了解是否可以添加 [!DNL Marketo Measure] JavaScript可跟踪这些页面（如果适用）。 如果无法执行此操作，我们将会探索通过CRM Campaign接触点进行跟踪，以及 [!DNL Marketo Measure] 顾问。

您是否有任何不应跟踪的表单 [!DNL Marketo Measure] 由于它们不一定适用于归因（例如，取消订阅表单、客户登录等）？ 如果是这样，您将需要添加排除代码 [本文内容](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target="_blank"} 至每个表单

您是否有任何非安全页面？ 如果是这样，您需要保护这些服务器，因为在安全/非安全页面之间导航将中断跟踪会话。

请确保与您的Web团队进行对话，以便他们知道 [!DNL Marketo Measure] JavaScript应始终位于相应的Web属性上。 如果引入了新页面/表单/站点，请确保部署 [!DNL Marketo Measure] JavaScript是协议的一部分。

如果 [!DNL Web Application Firewall (WAF)] 警告在JavaScript设置期间触发，用户可以禁用该WAF规则或允许列出Cookie，如下例所示：

![](assets/adding-marketo-measure-script-1.png)

## Forms将特别关注 {#forms-to-pay-extra-attention-to}

**多表单提交**

* 问题：如果您在提交单个表单时拥有多个链接的表单，那么即使未提交完整的表单，第一个表单也可能会生成接触点。
* 解决方案：您需要强制其中一个表单向用户报告 [!DNL Marketo Measure] 基于缓存的数据并讨论放弃实践。 一般而言， [报表用户代码](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} 可以解决这个问题。

**帐户登录（非创建）**

* 问题： [!DNL Marketo Measure] 建议不要为后续帐户登录创建接触点，因为这些操作可能会稀释归因故事。
* 解决方案：将“排除代码”添加到帐户/客户/合作伙伴登录表单。

>[!NOTE]
>
>我们建议创建用于创建帐户或试用版的接触点。

**下载资源**

* 问题：如果封闭资产， [!DNL Marketo Measure] 会将下载作为表单填写进行跟踪。 如果您的资源没有限制，则无需自定义即可报告的内容会有一些限制。
* 解决方案：如果您希望由跟踪资产，请启动该资产 [!DNL Marketo Measure] JavaScript。 如果这不是一个选项，而您仍希望将其作为接触点，请考虑改为同步CRM Campaign。

**iFrames**

* 问题：iFrame基本上可用作页面中的页面。
* 解决方案： [!DNL Marketo Measure] JS必须直接部署在iFrame标头中，以便我们能够正确附加到表单。

**灯箱**

* 灯箱通常是包含iFrame的弹出窗口
* 解决方案： [!DNL Marketo Measure] JS必须部署在该托管iFrame的标头中。

**页面上的多个表单**

* 问题：如果页面上有多个托管的表单，您可能无法分辨哪个特定表单是使用 [!DNL Marketo Measure] 表单URL字段。
* 解决方案：如果您需要知道已填写哪个表单，请尝试使用Web团队设置动态URL哈希处理。

**Forms组织位置 `<div>` 格式**

* 问题： [!DNL Marketo Measure] JS很难识别以这种方式组织的表单 `<div>` 格式，以便需要自定义代码。
* 解决方案：这些 [报表用户模板](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} 可供您的Web开发团队用于添加所需的代码。

**聊天**

* 问题：如果您使用聊天提供商，则可能需要特殊处理。
* 解决方案： [!DNL Marketo Measure] 与Drift、Olark、Livechat、LivePerson和SnapEngage集成。 所有其他平台都需要通过CRM campaign会员资格进行跟踪。

**第二个域**

* 问题： [!DNL Marketo Measure] JavaScript特定于域，因此需要对任何单独的域或国际域采取额外的步骤。 请注意 [!DNL Marketo Measure] JS可以在同一根域上处理子域。
* 解决方案：如果您拥有多个根域，则希望作为跟踪依据的域 [!DNL Marketo Measure] 请务必将JS添加到域，并允许 [!DNL Marketo Measure] 顾问知道哪些域应手动关联到您的 [!DNL Marketo Measure] 帐户。

## 测试 [!DNL Marketo Measure] JavaScript {#testing-marketo-measure-javascript}

您的 [!DNL Marketo Measure] 顾问将帮助您查明网站的测试情况，以确保 [!DNL Marketo Measure] JavaScript存在于所有页面中。 该测试的部分内容是提交一些填妥并清楚标明测试详细信息的表单，以确保正确返回跟踪结果。

但是，您的 [!DNL Marketo Measure] 顾问可能不像您的Web团队那样熟悉您的网站。 因此，您的Web团队或其他相应的团队务必彻底检查网站，尤其是当存在与上述内容类似的复杂表单正在使用时。 您的团队最终将负责确保正确跟踪所有必需的Web资产，但是如果您了解任何复杂的表单或情况，欢迎您询问 [!DNL Marketo Measure] 测试方面的帮助顾问。

要自行测试表单，请按照以下步骤操作：

1. 请始终使用无痕浏览器或清除每个表单提交测试之间的缓存，并且每次都使用不同的电子邮件地址。

   答：最佳做法是使用包含表明这是一次测试及时间的内容的假电子邮件。 例如：testing830am@test.com。

1. 记录您要提交表单的页面的URL以及使用的电子邮件。

1. 找到在您的CRM（潜在客户或联系人）中为该表单提交创建的记录，并验证是否正确创建了接触点。

   a.您可以使用 [!DNL Marketo Measure] 库存报表，例如具有采购员接触点的销售线索；或者如果您选择使用更新页面布局，请查看“销售线索/联系人”页面布局 [!DNL Marketo Measure] 详细信息。

   b.请注意，这可能需要一些时间来处理数据。
