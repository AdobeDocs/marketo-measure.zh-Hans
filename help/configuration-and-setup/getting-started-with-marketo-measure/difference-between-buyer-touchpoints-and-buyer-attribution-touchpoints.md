---
unique-page-id: 18874646
description: 买方接触点和买方归因接触点之间的差异 —  [!DNL Marketo Measure]
title: 买方接触点和买方归因接触点之间的差异
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
feature: Touchpoints
source-git-commit: bdc32fdfe24d57fd7770654f1238896c7b59acf6
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# 买方接触点和买方归因接触点之间的差异 {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

了解什么定义了Buyer Touchpoint (BT)和Buyer Attribution Touchpoint (BAT)，以及二者之间的区别并回答常见问题。

买方接触点和买方归因接触点之间的关键区别在于它们与[!DNL Salesforce]对象的关系。 BT与Lead 、 Contact和Case对象相关，但与Opportunity对象无关。 这意味着永远不会有与买方接触点相关的收入。

虽然Buyer Attribution Touchpoint对象与联系人、帐户和机会对象相关，但与潜在客户对象无关；买方归因接触点未与潜在客户绑定。 在BAT对象中，您将看到与特定营销交互关联的收入。

BT和BAT之间的区别：

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>Buyer Touchpoint (BT)</td> 
   <td>Buyer Attribution Touchpoint (BAT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>与Lead、Contact和Case对象相关</li> 
     <li>与Opportunity对象无关</li> 
     <li>收入未与Buyer Touchpoint关联</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>与Contact、Account和Opportunity对象相关</li> 
     <li>与Lead对象无关</li> 
     <li>由于Buyer Attribution Touchpoint与Opportunity关联，因此所有BAT都有与其关联的收入</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## 常见问题解答 {#faq}

**Buyer Touchpoint何时成为Buyer Attribution Touchpoint？**

一旦此BT与具有关联Opportunity的Contact关联，该BT就会变为BAT。 要了解的一件重要事情是，一个特定的营销交互可以是BT和BAT。

**Buyer Touchpoint能否在Opportunity Creation (OC)中设置接触点位置？**

Buyer Touchpoint的接触点位置将只有首次接触(FT)、潜在客户创建(LC)或表单提交（中间接触点）。 由于BT与Opportunity无关，因此BT不可能具有Opportunity Creation或Closed的接触点位置。

**如何使用Buyer Touchpoint数据？**

通常，客户使用Buyer Touchpoint数据来了解漏斗的顶部以及漏斗参与的中间位置。 这意味着[!DNL Marketo Measure]用户知道哪些人正在提交表单、哪些人正在查看其网站、哪些博客帖子表现良好、哪些AdWords广告在推动哪些转化商等等。 Buyer Touchpoint数据有助于了解潜在客户和联系人的参与情况。

**Buyer Touchpoint在Salesforce中是怎样的？**

以下是[!DNL Salesforce]中BT的屏幕截图：

![](assets/buyer-touchpoints-and-buyer-attribution-touchpoints-1.png){width="600" zoomable="yes"}

**Buyer Attribution Touchpoint在Salesforce中是怎样的？**

以下是[!DNL Salesforce]中BAT的屏幕截图：

![](assets/buyer-touchpoints-and-buyer-attribution-touchpoints-2.png){width="600" zoomable="yes"}
