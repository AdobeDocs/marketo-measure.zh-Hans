---
unique-page-id: 18874652
description: '[!DNL Marketo Measure]通过归因常见问题解答 —  [!DNL Marketo Measure]查看'
title: "[!DNL Marketo Measure]通过归因常见问题解答进行查看"
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
feature: Attribution
source-git-commit: 48962b999fdd16fe96d18708ec301e64a39bc76e
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 1%

---

# 通过归因常见问题解答[!DNL Marketo Measure]查看 {#marketo-measure-view-through-attribution-faq}

## 通过归因查看什么？ {#what-is-view-through-attribution}

[!DNL Marketo Measure] [!UICONTROL View Through Attribution]功能包括在归因模型中包含广告展示的功能。

>[!IMPORTANT]
>
>出于隐私考虑，第三方Cookie即将退出。 Google Chrome在2024年第3季度宣布弃用第三方Cookie，这实际上标志着这种跟踪形式的结束。 因此，Adobe将弃用依赖第三方Cookie的Marketo Measure功能，特别是跨域跟踪和浏览归因，后者使用Google/DoubleClick展示次数Cookie。 任何其他Marketo Measure功能都不会受到影响。 第一方Cookie的使用也不受影响。 按照Google的时间表，预计上述两个功能的弃用日期为2024年6月1日。 在此日期之前收集的相关数据仍可供Adobe客户使用。

## 为什么[!UICONTROL View Through Attribution]重要？ {#why-is-view-through-attribution-important}

从历史上看，营销人员很难在归因分析中考虑重新定位或展示广告。 潜在客户可能会一次又一次地接触到重新定位的广告，但他们实际上不太可能单击这些广告之一，并在同一会话中填写表格。 现在，我们的通过归因查看解决方案能够跟踪某人是否接触了展示广告。 此接触点将附加到个人记录中，并将一直执行，直到潜在客户成为客户。 有了这些信息，营销人员现在可以更好地了解其重新定位广告的表现。

## 设置过程中涉及哪些内容？ {#what-is-involved-in-setting-this-up}

为了使[!DNL Marketo Measure]开始测量广告展示，需要在Doubleclick促销活动管理器中放置展示标记。 标记实施后，展示次数会存储在我们的日志中，我们会处理剩余的日志。 如果您有兴趣通过归因测量视图，请联系您的成功经理。

## 支持哪些广告平台？ {#which-ad-platforms-are-supported}

我们当前支持[!DNL Doubleclick]营销活动经理。

## 如何计算归因？ {#how-is-the-attribution-calculated}

我们仔细分析了展示数据及其对所有阶段和营销渠道的转化的影响。 分布会因模型而异，如下表所示：

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><br></th> 
   <th>首次接触</th> 
   <th>潜在客户创建</th> 
   <th>U型</th> 
   <th>W型</th> 
   <th>完整路径</th> 
   <th>自定义模型</th> 
  </tr> 
  <tr> 
   <td><strong>展示次数</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>自定义</td> 
  </tr> 
  <tr> 
   <td><strong>英尺</strong></td> 
   <td>100%</td> 
   <td>0%</td> 
   <td>35%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>自定义</td> 
  </tr> 
  <tr> 
   <td><strong>LC</strong></td> 
   <td>0%</td> 
   <td>100%</td> 
   <td>35%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>自定义</td> 
  </tr> 
  <tr> 
   <td><strong>OC</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>自定义</td> 
  </tr> 
  <tr> 
   <td><strong>已关闭</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>20%</td> 
   <td>自定义</td> 
  </tr> 
  <tr> 
   <td><strong>中间</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>20%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>自定义</td> 
  </tr> 
 </tbody> 
</table>

## 在[!DNL Salesforce?]中会是什么样子 {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure]将在展示广告的任何Lead上创建单印象接触点。 即使用户首次访问您的网站(FT)并填写表单(LC)后，我们仍能映射用户。 接触点将包含广告信息，例如广告促销活动名称/ID、广告ID、广告内容、网站名称/ID、版面名称/ID、营销渠道、地域、反向链接页面等。

浏览转化归因模型取决于客户端及其数据。
