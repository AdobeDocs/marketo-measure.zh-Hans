---
unique-page-id: 18874745
description: AJAX表单处理 —  [!DNL Marketo Measure]  — 产品文档
title: AJAX表单处理
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# AJAX表单处理 {#ajax-form-handling}

要手动报告客户转化，请执行以下操作 [!DNL Marketo Measure]，我们提供了一个非常简单的API，您可以使用它。 如果您的网站上包含我们的跟踪代码，则这两个Javascript API都会自动在您的网站上可用。 无需执行任何特殊操作即可访问这些组件。

## 情景1 -HTML包含AJAX提交的表单 {#scenario-html-form-with-an-ajax-submit}

使用包含AJAX（或其他机制）的表单将转换日期从客户端提交到我们的服务器时， [!DNL Marketo Measure] 可能无法了解客户通过我们监控的任何标准路径进行的转化。 在此方案中，我们可以利用一个简单的API（如下所示）。

如果您处理自己的表单提交，则可以明确调用 [!DNL Marketo Measure] 从Javascript中。 [!DNL Marketo Measure] 将从表单中收集所有相关信息，并将其异步发布到我们的服务器。

**下面是使用JQuery的代码示例（假定表单上的ID为“formId”）：**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the JQuery Selector for the form and we'll collect the data automatically.  
Bizible.Push('Form',$('#*formId*'));
```

**以下是未使用JQuery的代码示例（假定表单上的ID为“formId”）：**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the Form ID and we'll collect the data automatically.
Bizible.Push('Form','MyFormID');
```

## 情景2 — 在非HTML表单中收集潜在客户信息 {#scenario-lead-information-collected-in-a-non-html-form}

如果使用Javascript或没有HTML表单的简单文本字段收集转化潜在客户的信息，则此解决方案将适合您。 下面共享了在此方案中使用的API:

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.  
Bizible.Push('User', {
eMail: 'user@gmail.com' // required  
});  
```

在此代码中， [!UICONTROL email] 字段。 [!DNL Marketo Measure] 会将此数据异步发布到我们的服务器。

## 情景3 — 从“感谢”页面报告用户信息 {#scenario-report-user-information-from-the-thank-you-page}

在某些情况下，将潜在客户信息报告给 [!DNL Marketo Measure] 在表单提交后，从“感谢”页面。 报告此信息的最简单方法是，向保存表单提交信息的页面中添加一个隐藏元素， [!DNL Bizible.js] 将在“感谢”页面加载后阅读此信息。

**例如：**

```html
<div id="bizible.reportUser" style="display:none"  
data-email="user@gmail.com">  
```

隐藏的元素是div、script还是任何其他标记类型都无关紧要。 [!DNL Marketo Measure] 查找id=&quot;bizible.reportUser&quot;以读取信息。
