---
unique-page-id: 18874795
description: 添加 [!DNL Marketo Measure] 脚本 —  [!DNL Marketo Measure]  — 产品文档
title: 添加 [!DNL Marketo Measure] 脚本
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 0%

---

# 添加 [!DNL Marketo Measure] 脚本 {#adding-marketo-measure-script}

[!DNL Marketo Measure] 要由跟踪的JavaScript [!DNL Marketo Measure] 应尽快添加到所有Web属性中。 部署JavaScript后， [!DNL Marketo Measure] 将开始收集您的数字数据。 本文概述了部署方法 [!DNL Marketo Measure] JavaScript和需要考虑的其他注意事项。

>[!NOTE]
>
>确保您 [在 [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md)除部署外，还要部署{target=&quot;_blank&quot;} [!DNL Marketo Measure] JavaScript。

入门时 [!DNL Marketo Measure]，您可以通过两种方式添加 [!DNL Marketo Measure] JavaScript到您的网站：

* 硬编码
* Tag Management系统

## 硬编码 {#hard-coding}

作为最佳实践，我们强烈建议进行硬编码 [!DNL Marketo Measure] 将JavaScript转换为Web属性。 要对脚本进行硬编码，您需要将脚本放在关闭之前 `</head>` 在您网站的每个页面上。

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

将JavaScript硬编码到 `<head>` 页面的 [!DNL Marketo Measure] 脚本将先加载，且未遗漏反向链接信息。 的 [!DNL Marketo Measure] JavaScript异步加载。 如果进行硬编码，则必须手动将JavaScript添加到营销自动化。

>[!TIP]
>
>了解如何确保您的脚本为 [符合GDPR](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target=&quot;_blank&quot;}。

## Tag Management系统 {#tag-management-systems}

如果添加 [!DNL Marketo Measure] 无法通过硬编码进行JavaScript，另一个选项是添加 [!DNL Marketo Measure] 使用Tag Management系统(例如 [!DNL Google Tag Manager] (GTM)或Tealium。

请注意，使用标签管理系统来部署 [!DNL Marketo Measure] 由于脚本加载时间延迟，JS可能会导致5-10%的数据丢失。 实际上，如果标签管理工具加载速度不够快， [!DNL Marketo Measure] JS加载速度也不够快，可能会丢失第一个反向链接信息。

常见做法是部署 [!DNL Marketo Measure] JS来替换JS，直到时间/资源配置更适合转为硬编码。

添加 [!DNL Marketo Measure] 通过标签管理解决方案创建脚本时，您将需要创建一个新标记并在其中添加我们的JavaScript。 将此标记应用于您网站上要跟踪的所有页面。

[!DNL Marketo Measure] 建议任何页面查看都应触发标记。 此外，最好将 [!DNL Marketo Measure] 触发顺序中的最高优先级，并确保前面没有同步脚本 [!DNL Marketo Measure] 来确保最高的数据质量。

更多信息可以 [此处](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target=&quot;_blank&quot;}。

## 其他注意事项 {#additional-considerations}

[!DNL Marketo Measure] JavaScript基于域，因此只要JavaScript位于页面上且根域与用于创建Marketo测量帐户的域相同，它就能够自动处理任何子域。

但是，如果您使用的是任何单独的域或国际域，请务必让 [!DNL Marketo Measure] 顾问知道。 需要在 [!DNL Marketo Measure] 结束 [!DNL Marketo Measure] 知道将其他域的数据关联到您的帐户。 因此，请将任何单独的/国际的域发送到您的 [!DNL Marketo Measure] 顾问。

如果您使用任何第三方页面，请与 [!DNL Marketo Measure] 顾问。 通常，您会希望了解是否可以添加 [!DNL Marketo Measure] JavaScript来跟踪这些页面（如果适用）。 如果无法实现，将与您的 [!DNL Marketo Measure] 顾问。

您是否有任何不应被跟踪的表单 [!DNL Marketo Measure] 因为它们不一定适合归因（例如，取消订阅表单、客户登录等）？ 如果是，则需要添加排除代码 [在本文中](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target=&quot;_blank&quot;}

您有任何非安全页面吗？ 如果是，则在安全/非安全页面之间导航将中断跟踪会话时，您将需要保护它们。

请务必与您的Web团队进行对话，以便他们了解 [!DNL Marketo Measure] JavaScript应始终位于相应的Web属性上。 如果引入了新页面/表单/站点，请确保部署 [!DNL Marketo Measure] JavaScript是协议的一部分。

如果 [!DNL Web Application Firewall (WAF)] 在JavaScript设置期间触发警告，用户可以禁用该WAF规则或将Cookie添加到允许列表，如以下示例所示：

![](assets/adding-marketo-measure-script-1.png)

## Forms将格外关注 {#forms-to-pay-extra-attention-to}

**多表单提交**

* 问题：如果您在提交单个表单时有多个链接的表单，则即使未提交完整表单，第一个表单也可能会生成一个接触点。
* 解决方案：您需要强制其中一个表单向 [!DNL Marketo Measure] 基于缓存的数据并讨论放弃实践。 通常， [报告用户代码](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target=&quot;_blank&quot;}可解析此问题。

**帐户登录（而非创建）**

* 问题： [!DNL Marketo Measure] 建议不要为后续帐户登录创建接触点，因为这些接触点可能会稀释归因故事。
* 解决方案：在帐户/客户/合作伙伴登录表单中添加排除代码。

>[!NOTE]
>
>我们建议为创建帐户或试用版创建接触点。

**下载资产**

* 问题：如果你的资产被关闭， [!DNL Marketo Measure] 将在表单填充时跟踪下载。 如果您的资产未受限，则我们无需自定义即可报告的内容存在限制。
* 解决方案：如果您希望跟踪资产，请将其选中 [!DNL Marketo Measure] JavaScript。 如果这不是一个选项，并且您仍希望获得该选项的接触点，请考虑同步CRM营销活动。

**iFrames**

* 问题：iFrame基本上可以用作页面内的页面。
* 解决方案：的 [!DNL Marketo Measure] JS必须直接部署在iFrame标头中，才能正确附加到表单。

**灯箱**

* 灯箱通常是包含iFrame的弹出窗口
* 解决方案：the [!DNL Marketo Measure] JS必须部署在该托管iFrame的标头中。

**页面上的多个表单**

* 问题：如果页面上托管有多个表单，您可能无法分辨是用 [!DNL Marketo Measure] 表单URL字段。
* 解决方案：如果您需要知道已填写哪个表单，请探索如何与您的Web团队设置动态URL哈希处理。

**Forms组织 `<div>` 格式**

* 问题： [!DNL Marketo Measure] JS很难识别 `<div>` 格式，以便需要自定义代码。
* 解决方案：这些 [报告用户模板](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md)您的Web开发团队可以使用{target=&quot;_blank&quot;}来添加所需的代码。

**聊天**

* 问题：如果您使用聊天提供商，则可能需要特殊处理。
* 解决方案： [!DNL Marketo Measure] 与Drift、Olark、Livechat、LivePerson和SnapEngage集成。 需要通过CRM促销活动成员资格来跟踪所有其他平台。

**第二个域**

* 问题： [!DNL Marketo Measure] JavaScript是特定于域的，因此需要为任何单独或国际域执行额外的步骤。 请注意 [!DNL Marketo Measure] JS可以处理同一根域上的子域。
* 解决方案：如果您拥有多个根域，则希望跟踪该域 [!DNL Marketo Measure] 确保将JS添加到域，并 [!DNL Marketo Measure] 顾问知道哪些域应手动关联到您的 [!DNL Marketo Measure] 帐户。

## 测试 [!DNL Marketo Measure] JavaScript {#testing-marketo-measure-javascript}

您的 [!DNL Marketo Measure] 顾问将帮助您发现测试网站，以确保 [!DNL Marketo Measure] JavaScript在所有页面中都存在。 此测试的一部分内容是提交一些填写了明确指示的测试详细信息的表单，以确保正确返回跟踪。

但是，您的 [!DNL Marketo Measure] 顾问可能不像您的Web团队那么熟悉您的网站。 因此，您的Web团队或其他相应团队务必要彻底检查网站，尤其是在使用中存在与上述表单类似的复杂表单时。 您的团队最终将负责确保所有需要的Web属性均得到正确跟踪，但如果您知道任何复杂的表单或情况，欢迎咨询您的 [!DNL Marketo Measure] 帮助测试顾问。

要自行测试表单，请执行以下步骤：

1. 请始终使用隐身浏览器或在每个表单提交测试之间清除缓存，并且每次使用不同的电子邮件地址。

   a.最佳做法是使用一封假电子邮件，其中包含一些指示它是测试和一天中的某个时间的内容。 例如：testing830am@test.com。

1. 记录您要提交表单的页面的URL以及使用的电子邮件。

1. 找到在CRM（潜在客户或联系人）中为表单提交创建的记录，并验证是否已正确创建接触点。

   a.您可以使用 [!DNL Marketo Measure] 库存报表（如具有买方接触点的潜在客户）或查看“潜在客户/联系人”页面布局(如果您选择使用 [!DNL Marketo Measure] 详细信息。

   b.请注意，这可能需要一些时间才能处理数据。
