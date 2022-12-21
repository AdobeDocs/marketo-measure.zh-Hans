---
unique-page-id: 35586069
description: 确保Marketo Measure Js - Marketo Measure — 产品文档中的同意GDPR
title: 确保在Marketo Measure Js中同意GDPR
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
source-git-commit: c7d3bbce1f0c6a99409822c06c43961c93cd9458
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# 确保在Marketo Measure Js中同意GDPR {#ensuring-consent-for-gdpr-in-marketo-measure-js}

《通用数据保护条例》(GDPR)是一项欧盟立法，于2018年5月25日正式生效。

## 概述 {#overview}

GDPR旨在加强欧盟(EU)和欧洲经济区(EEA)内数据主体对其个人数据的使用和保护权利。 个人数据是指与已识别或可识别的自然人相关的任何信息。 GDPR适用于欧盟内外任何组织，该组织向欧盟和EEA内的数据主体营销商品或服务，并/或跟踪其行为。 如果您在欧洲与涉及个人数据处理的数据主体开展业务，则本法规适用于您。 对不遵守规定者的处罚相当重大，对违反规定者处以巨额罚款；单次违规的最高罚款为2000万欧元，占全球年营业额的4%，以两者中较高者为准。

默认情况下， [!DNL bizible.js] 收集用户的分析数据，除非专门将其配置为等待同意。 When [!DNL bizible.js] 配置为等待用户同意，则在获得用户同意之后，才会创建任何cookie或发送任何analytics数据。

## 如何等待同意 {#how-to-wait-for-consent}

有两种方法可设置 [!DNL bizible.js] 等待同意。

选项1 — 替换默认 [!DNL bizible.js] 脚本标记：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**如果您使用 [!DNL Google Tag Manager] 安装脚本**，请记住，GTM会删除数据属性，因此请改用以下脚本：

`<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>在这种情况下， [!DNL bizible.js] 将向ID为“ConsentButtonId”的HTML元素附加一个单击事件。

单击此HTML元素后， [!DNL bizible.js] 将创建一个Cookie以记住已收到用户同意，并开始照常收集analytics数据。

**-或-**

选项2 — 替换默认 [!DNL bizible.js] 脚本标记：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

这说明 [!DNL bizible.js] ，可在获得同意后进行跟踪，可使用以下JS API完成此操作：

*窗口[“Bizible”] =窗口[“Bizible”] || { _queue: []，推送：函数(o， p){此。_queue.push({类型：o，数据：p });} };*

*Bizible.Push(&#39;Consent&#39;, true);*

**如果您使用 [!DNL Google Tag Manager] 安装脚本**，请记住，GTM会删除数据属性，因此请改用以下脚本：

`<span id="bizible-settings" data-requires-user-consent="true"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>bizible.js将创建一个Cookie，以记住已收到用户同意，并且仅在调用JS API后才开始正常收集analytics数据。

相反，客户还可以使用此API撤回用户同意：

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

此代码执行时，将删除所有 [!DNL bizible.js] 之前创建的，且仅当用户重新同意时才会恢复analytics数据的收集。
