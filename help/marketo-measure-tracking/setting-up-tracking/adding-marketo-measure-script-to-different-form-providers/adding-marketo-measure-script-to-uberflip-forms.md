---
unique-page-id: 18874749
description: 正在添加 [!DNL Marketo Measure] 编写脚本至 [!DNL Uberflip] FORMS - [!DNL Marketo Measure]
title: 正在添加 [!DNL Marketo Measure] 编写脚本至 [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# 正在添加 [!DNL Marketo Measure] 编写脚本至 [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

如果您当前使用 [!DNL Uberflip] 要管理您的内容，请务必采取以下必要步骤，以确保 [!DNL Marketo Measure] 正在跟踪这些表单提交。 您的成功经理 [!DNL Uberflip] 您也应该能够协助您完成这项工作。

1. 将此脚本添加到 [!DNL Uberflip]的 [!UICONTROL Custom Code>HTML] 部分。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 确保此 [!DNL Marketo Measure] 前导代码在页面加载和AJAX页面更改时触发。 执行以下操作的时间范围 [!UICONTROL Custom Code>JS] 部分

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   将此序言添加到两个 [!DNL Hubs.onLoad] 和 [!DNL Hubs.onPageChange] AJAX JavaScript事件挂接如下所示。 (注意：在这些事件挂接中，您可能还包含其他代码。 确保也包含前言。)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. 创建并定义一个函数，以便在提交表单CTA时将数据推送到Bizible。 该内容将放入 [!UICONTROL Custom Code>JavaScript] 部分。 （注意：此函数仅需要Uberflip提供的ctaData参数，但如果用户希望自定义其代码以同时传递此数据，则可以包含其他参数ctaId和ctaName）。

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. 在提交表单CTA时，请确保您的 [!DNL Marketo Measure] 函数按照以下执行。 此操作可在以下时间内完成 [!UICONTROL Custom Code>JS] 部分。 （注意：Hubs.onCtaFormSubmitSuccess JavaScript事件挂接中可能有其他代码，请确保同时包含此函数调用）。

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
