---
unique-page-id: 18874646
description: 买方接触点与买方归因接触点之间的差异 —  [!DNL Marketo Measure]  — 产品文档
title: 买方接触点与买方归因接触点之间的差异
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# 买方接触点与买方归因接触点之间的差异 {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

了解什么定义了买方接触点(BT)和买方归因接触点(BAT)、两者之间的差异，并回答了常见问题。

买方接触点和买方归因接触点之间的关键区别在于它们与 [!DNL Salesforce] 对象。 BT与Lead 、 Contact和Case对象相关，但与Opportunity对象无关。 这意味着永远不会有与买方接触点相关的收入。

而买方归因接触点对象与联系人、帐户和机会对象相关，但与潜在客户对象无关。 这意味着永远不会有与潜在客户关联的买方归因接触点。 在BAT对象中，您将看到与特定营销交互关联的收入。

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
     <li>与潜在客户、联系人和案例对象相关</li> 
     <li>与Opportunity对象无关</li> 
     <li>收入未与买方接触点关联</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>与联系人、帐户和机会对象相关</li> 
     <li>与潜在客户对象不相关</li> 
     <li>由于买方归因接触点与机会关联，因此所有BAT都有与它们关联的收入</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## 常见问题解答 {#faq}

**购买者接触点何时成为购买者归因接触点？**

一旦此BT与具有关联Opportunity的联系人关联，BT就成为BAT。 一个非常重要的要了解的是，一个特定的营销互动可以是BT和BAT。

**买方接触点是否具有机会创建(OC)的接触点位置？**

买方接触点将仅具有首次接触(FT)、商机创建(LC)或表单提交（中间接触点）的接触点位置。 由于BT与Opportunity无关，因此BT不可能具有Opportunity Creation或Closed的Touchpoint Position。

**如何利用购买者接触点数据？**

通常，客户会利用购买者接触点数据来了解漏斗顶部和漏斗中间参与。 含义 [!DNL Marketo Measure] 用户知道谁在提交表单、谁在查看他们的网站、哪些博客帖子表现良好、AdWords广告促使哪些人转化等。 买方接触点数据非常有助于了解潜在客户和联系人的参与度。

**在Salesforce中，买方接触点是什么样的？**

这是BT的屏幕截图 [!DNL Salesforce]:

![](assets/1.png)

**采购员归因接触点在Salesforce中是什么样的？**

这是中一个蝙蝠的屏幕截图 [!DNL Salesforce]:

![](assets/2.png)
