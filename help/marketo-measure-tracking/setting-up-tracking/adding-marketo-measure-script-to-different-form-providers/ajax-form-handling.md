---
unique-page-id: 18874745
description: AJAX表单处理 —  [!DNL Marketo Measure]  — 产品文档
title: AJAX表单处理
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# AJAX表单处理 {#ajax-form-handling}

要人工报告客户转化至 [!DNL Marketo Measure]，我们提供了一个非常简单的API，可供您使用。 如果您拥有我们的跟踪代码，则这两个Javascript API都可以在您的网站上自动使用。 无需执行任何特殊操作即可访问它们。

## 场景1 — 包含AJAX提交的HTML表单 {#scenario-html-form-with-an-ajax-submit}

使用包含AJAX（或其他机制）的表单将转化日期从客户端提交到我们的服务器时， [!DNL Marketo Measure] 可能不知道客户通过我们监控的任何标准路径进行的转化。 在此方案中，我们可以利用简单的API（如下所示）。

如果您处理自己的表单提交，则可以明确调用 [!DNL Marketo Measure] 从Javascript访问。 [!DNL Marketo Measure] 将从表单中收集所有相关信息，并将其异步发布到我们的服务器。

**以下是使用JQuery的代码示例（假设表单上的ID为“formId”）：**

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

## 方案2 — 以非HTML表单收集的商机信息 {#scenario-lead-information-collected-in-a-non-html-form}

如果使用Javascript或简单文本字段（不带html表单）收集来自已转化商机的信息，则此解决方案将适用于您。 以下共享的是要在此方案中使用的API：

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.  
Bizible.Push('User', {
eMail: 'user@gmail.com' // required  
});  
```

在此代码中， [!UICONTROL email] 字段为必填项。 [!DNL Marketo Measure] 会异步将此数据发布到我们的服务器。

## 场景3 — 在感谢页面中报告用户信息 {#scenario-report-user-information-from-the-thank-you-page}

在某些情况下，将潜在客户信息报告到会更加方便 [!DNL Marketo Measure] 在提交表单后，从感谢页面访问。 报告此信息的最简单方法是，向包含表单提交信息的页面添加隐藏元素，并且 [!DNL Bizible.js] 将在加载感谢页面后阅读此信息。

**例如：**

```html
<div id="bizible.reportUser" style="display:none"  
data-email="user@gmail.com">  
```

隐藏元素是div、脚本还是任何其他标记类型都无关紧要。 [!DNL Marketo Measure] 查找id=&quot;bizible.reportUser&quot;以读取信息。
