---
unique-page-id: 30082018
description: 延迟的Cookie同步 —  [!DNL Marketo Measure]  — 产品文档
title: 延迟的Cookie同步
exl-id: 394053ed-5642-48e4-b83c-c483a58ebbd7
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# 延迟的Cookie同步 {#delayed-cookie-sync}

此对默认值的修改 [!DNL Marketo Measure] Javascript用于提供 [!DNL bizible.js] API支持，因此您可以将JS配置为临时存储访客的用户活动，但不会将信息发送到 [!DNL Marketo Measure] 服务器，直到用户同意为止。

## 操作方法 {#how-to}

替换默认 [!DNL bizible.js] 脚本标记，其中包含以下内容：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

data-consent-button-id=&quot;ConsentButtonId&quot;属性告知 [!DNL bizible.js] 发送分析数据，直到单击具有该id的HTML元素。

或者，客户也可以将 [!UICONTROL data-consent-button-id] 不存在某些内容（例如“foobar”），并使用以下API来判断 [!DNL bizible.js] 用户同意：

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`
`Bizible.Push("Consent", true });`

>[!NOTE]
>
>用户同意会保存到Cookie中，这意味着用户在同意后便无需在任何后续页面上执行此调用。

## 限制 {#limitation}

因为 [!DNL bizible.js] 临时在客户的第一方cookie中保存未发送的web活动，并且第一方cookie的大小受到限制，因此在任何给定时间都只能保存三个未发送的请求。

如果已经有三个待处理请求，则将忽略任何后续活动；这是为了保留第一次页面查看，其中包含有价值的反向链接信息。
