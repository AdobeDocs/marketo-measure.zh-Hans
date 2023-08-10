---
unique-page-id: 30082018
description: 延迟的Cookie同步 —  [!DNL Marketo Measure]  — 产品文档
title: 延迟的Cookie同步
exl-id: 394053ed-5642-48e4-b83c-c483a58ebbd7
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# 延迟的Cookie同步 {#delayed-cookie-sync}

对默认设置的此修改 [!DNL Marketo Measure] Javascript可提供 [!DNL bizible.js] API支持，因此您可以将JS配置为临时存储访客的用户活动，但不会将信息发送到 [!DNL Marketo Measure] 服务器，直到用户同意这样做。

## 操作方法 {#how-to}

替换默认值 [!DNL bizible.js] 脚本标记包含以下内容：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

data-consent-button-id=&quot;ConsentButtonId&quot;属性告知 [!DNL bizible.js] 在单击具有该id的HTML元素之前不发送分析数据。

或者，客户可以设置 [!UICONTROL data-consent-button-id] 不存在（例如，“foobar”），请使用以下API来告知 [!DNL bizible.js] 用户已同意：

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`
`Bizible.Push("Consent", true });`

>[!NOTE]
>
>用户同意将保存到Cookie中，这意味着一旦用户同意，就无需在任何后续页面上执行此调用。

## 限制 {#limitation}

因为 [!DNL bizible.js] 临时将未发送的Web活动保存在客户的第一方Cookie中，并且第一方Cookie的大小是有限的，在任何给定时间只能保存三个未发送请求。

如果已有三个待处理请求，则将忽略任何后续活动；这是为了保留第一个页面视图，其中包含重要的反向链接信息。
