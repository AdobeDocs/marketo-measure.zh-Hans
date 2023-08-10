---
unique-page-id: 35586069
description: 在Marketo Measure Js中确保同意GDPR - Marketo Measure — 产品文档
title: 在Marketo Measure Js中确保同意GDPR
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# 在Marketo Measure Js中确保同意GDPR {#ensuring-consent-for-gdpr-in-marketo-measure-js}

《通用数据保护条例》(GDPR)是一项欧盟法律，已于2018年5月25日生效。

## 概述 {#overview}

GDPR的目标是加强欧盟(EU)和欧洲经济区(EEA)内数据主体对其个人数据使用和保护方式的权利。 “个人数据”是指与已识别或可识别的自然人相关的任何信息。 GDPR适用于欧盟内外向欧盟和EEA内的数据主体营销商品或服务和/或跟踪数据主体行为的任何组织。 如果您在欧洲与数据主体开展业务，其中涉及对个人数据的处理，则此法规适用于您。 违规者将被处以巨额罚款，违规者将被处以巨额罚款；单次违规的最高罚款额为2,000万欧元，或全球年营业额的4%，以较大者为准。

默认情况下， [!DNL bizible.js] 收集用户的analytics数据，除非将其专门配置为等待同意。 时间 [!DNL bizible.js] 配置为等待用户同意，在征得用户同意之前，不会创建任何Cookie或发送任何Analytics数据。

## 如何等待同意 {#how-to-wait-for-consent}

有两种设置方法 [!DNL bizible.js] 等待同意。

选项1 — 替换默认值 [!DNL bizible.js] 脚本标记替换为：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**如果您使用 [!DNL Google Tag Manager] 安装脚本**，请记住，GTM会删除数据属性，因此请改用以下脚本：

`<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>在本例中， [!DNL bizible.js] 将附加一个单击事件到ID为“ConsentButtonId”的HTML元素。

单击此HTML元素时， [!DNL bizible.js] 将创建一个Cookie以记住已收到用户的同意，并开始照常收集Analytics数据。

**-或-**

选项2 — 替换默认选项 [!DNL bizible.js] 脚本标记替换为：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

这说明 [!DNL bizible.js] 在获得同意之前不会跟踪，这可以使用以下JS API完成：

*窗口[&#39;Bizible&#39;] =窗口[&#39;Bizible&#39;] || { _queue： []，推送：函数(o， p) {this._queue.push({ type： o， data： p })； } }；*

*Bizible.Push(&#39;Consent&#39;， true)；*

**如果您使用 [!DNL Google Tag Manager] 安装脚本**，请记住，GTM会删除数据属性，因此请改用以下脚本：

`<span id="bizible-settings" data-requires-user-consent="true"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>bizible.js将创建一个Cookie，以记住已收到用户的同意，并且仅在调用JS API之后才开始照常收集分析数据。

相反，客户还可以使用此API撤回用户的同意：

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

此代码执行时，将删除符合以下条件的所有Cookie： [!DNL bizible.js] 之前创建，并且只有在用户同意时才恢复分析数据的收集。
