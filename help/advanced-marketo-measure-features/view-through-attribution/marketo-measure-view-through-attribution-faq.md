---
unique-page-id: 18874652
description: '"[!DNL Marketo Measure] 查看归因常见问题解答 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] 查看归因常见问题解答”'
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 9%

---

# [!DNL Marketo Measure] 查看归因常见问题解答 {#marketo-measure-view-through-attribution-faq}

## 什么是通过归因查看？ {#what-is-view-through-attribution}

的 [!DNL Marketo Measure] 通过归因查看功能包括在归因模型中包含广告展示次数的功能。

## 通过归因查看为何重要？ {#why-is-view-through-attribution-important}

过去，在归因分析中，营销人员很难考虑重定位或展示广告。 潜在客户可能会随着时间的推移而接触到重定向广告，但他们实际上不太可能在同一会话中点击其中一个广告并填写表格。 我们的“通过归因查看”解决方案现在能够跟踪某人是否曾接触过展示广告。 此接触点将附加到单个记录中，并一直持续到潜在客户成为客户为止。 利用此信息，营销人员现在将能够更好地了解其重定向广告的效果。

## 设置此设置涉及哪些内容？ {#what-is-involved-in-setting-this-up}

为 [!DNL Marketo Measure] 要开始测量广告展示次数，需要在Doubleclick促销活动管理器中放置一个展示标记。 实施标记后，展示次数会存储在我们的日志中，我们会处理其余的。 如果您有兴趣通过归因来测量视图，请联系您的成功经理。

## 支持哪些广告平台？ {#which-ad-platforms-are-supported}

我们当前支持Doubleclick促销活动管理器。

## 如何计算归因？ {#how-is-the-attribution-calculated}

我们对所有阶段和营销渠道中的展示数据及其对转化的影响进行了仔细分析。 分布因模型而异，如下表所示：

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
   <th>商机创建</th> 
   <th>U型</th> 
   <th>W形</th> 
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
   <td><strong>FT</strong></td> 
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

## 在Salesforce中，这会是什么样子？ {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure] 将在显示广告的任何潜在客户上创建单一展示接触点。 即使用户首次访问您的网站(FT)并填写表格(LC)后，我们仍能映射用户。 接触点将包含广告信息，如广告促销活动名称/ID、广告ID、广告内容、网站名称/ID、版面名称/ID、营销渠道、地域、反向链接页面等。

显示到达归因模型将取决于客户端及其数据。
