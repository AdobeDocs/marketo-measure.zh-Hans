---
unique-page-id: 18874646
description: 买方接触点和买方归因接触点之间的差异 —  [!DNL Marketo Measure]
title: 买方接触点和买方归因接触点之间的差异
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# 买方接触点和买方归因接触点之间的差异 {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

了解什么定义了买方接触点(BT)和买方归因接触点(BAT)，以及二者之间的区别，并回答常见问题。

买方接触点和买方归因接触点之间的关键区别在于它们之间的关系 [!DNL Salesforce] 对象。 BT与Lead 、 Contact和Case对象相关，但与Opportunity对象无关。 这意味着永远不会有与买方接触点相关的收入。

虽然买方归因接触点对象与联系人、帐户和商机对象相关，但与Lead对象无关；买方归因接触点未绑定到Lead。 在BAT对象中，您可以看到与特定营销交互关联的收入。

BT与BAT的区别：

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>买方接触点(BT)</td> 
   <td>买方归因接触点(BAT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>与Lead、Contact和Case对象相关</li> 
     <li>与Opportunity对象无关</li> 
     <li>收入未与买方接触点关联</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>与Contact、Account和Opportunity对象相关</li> 
     <li>与Lead对象无关</li> 
     <li>由于买方归因接触点与Opportunity相关联，因此所有BAT都有与其关联的收入</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## 常见问题 {#faq}

**买方接触点何时会成为买方归因接触点？**

一旦该BT与具有关联Opportunity的Contact关联，则BT将成为BAT。 要了解的一件重要事情是，一种特定的营销互动可以是BT和BAT。

**采购员接触点是否可以在Opportunity Creation (OC)中处于接触点位置？**

买方接触点的接触点位置只有首次接触(FT)、潜在客户创建(LC)或表单提交（中间接触点）。 由于BT与Opportunities无关，因此BT不可能具有Opportunity Creation或Closed的接触点位置。

**如何使用买方接触点数据？**

通常，客户使用买方接触点数据来了解漏斗的顶部以及漏斗参与的中间位置。 含义 [!DNL Marketo Measure] 用户可了解哪些人正在提交表单、哪些人正在查看其网站、哪些博客帖子表现良好、AdWords广告在推动哪些内容被转化，等等。 买方接触点数据对于了解您的潜在客户和联系人的参与情况非常有用。

**在Salesforce中，购买者接触点是什么样的？**

这是一个BT in屏幕截图 [!DNL Salesforce]：

![](assets/1.png)

**Salesforce中的买方归因接触点是什么样的？**

这是一个BAT屏幕截图 [!DNL Salesforce]：

![](assets/2.png)
