---
unique-page-id: 18874749
description: 添加 [!DNL Marketo Measure] 脚本到 [!DNL Uberflip] Forms - [!DNL Marketo Measure]  — 产品文档
title: 添加 [!DNL Marketo Measure] 脚本到 [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# 添加 [!DNL Marketo Measure] 脚本到 [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

如果您当前使用 [!DNL Uberflip] 要管理内容，请务必采取这些必要步骤，确保 [!DNL Marketo Measure] 跟踪这些表单提交。 您的成功经理(位于 [!DNL Uberflip] 也能帮您解决这个问题。

1. 将此脚本添加到 [!DNL Uberflip]&#39;s [!UICONTROL Custom Code>HTML] 中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 确保 [!DNL Marketo Measure] 在页面加载和AJAX页面更改时，都会触发前导代码。 在 [!UICONTROL Custom Code>JS] 部分

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   您将在 [!DNL Hubs.onLoad] 和 [!DNL Hubs.onPageChange] AJAX Javascript事件挂钩。 (注：这些事件挂接中也可能包含其他代码。 只要确保您也包含序言。)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. 创建并定义一个函数，该函数将在表单CTA提交时将数据推送到Bizible。 这会进入 [!UICONTROL Custom Code>Javascript] 中。 (注：此函数仅需要Uberflip提供的ctaData参数，但您可以包含其他参数ctaId和ctaName，以防用户希望自定义其代码以传递此数据)。

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. 提交表单CTA后，请确保 [!DNL Marketo Measure] 函数。 此操作在 [!UICONTROL Custom Code>JS] 中。 (注：Hubs.onCtaFormSubmitSuccess Javascript事件挂接中可能有其他代码，只需确保也包含此函数调用即可。)

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
