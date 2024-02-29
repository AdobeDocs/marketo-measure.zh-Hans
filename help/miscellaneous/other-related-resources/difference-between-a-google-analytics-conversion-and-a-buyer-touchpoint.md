---
unique-page-id: 18874648
description: Google Analytics转化和买方接触点之间的区别 —  [!DNL Marketo Measure]
title: Google Analytics转化和买方接触点之间的区别
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Google Analytics转化和买方接触点之间的区别 {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

了解什么是 [!DNL Google Analytics (GA)] 目标为，以及它与“买方接触点”有何区别。

**Google Analytics的转化率是多少？**

[!UICONTROL Google Analytics] 转化完全取决于营销人员或Web开发人员如何在特定网站上编码“目标”完成。 Google认为，Goals可视为“进行购买（针对电子商务网站）、完成游戏级别（针对移动游戏应用程序）或提交联系信息表单（针对营销或潜在客户生成网站）”。 大多数情况下，营销人员将目标/转化视为填写信息表单的人。

但是，无法对目标进行编码以管理非常特定的行为。 而是有Web开发人员可以配置的目标类型。 以下是其中一些示例：

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><strong>目标类型</strong></td> 
   <td><p><strong>描述</strong></p></td> 
   <td><strong>示例</strong></td> 
  </tr> 
  <tr> 
   <td><p>目标</p></td> 
   <td>加载特定位置</td> 
   <td><em>感谢您注册！</em> 网页或应用程序屏幕</td> 
  </tr> 
  <tr> 
   <td>持续时间</td> 
   <td>持续时间特定时间或更长的会话</td> 
   <td>在支持网站上逗留10分钟或更长时间</td> 
  </tr> 
  <tr> 
   <td>每个会话的页面/屏幕</td> 
   <td>用户查看特定数量的页面或屏幕</td> 
   <td>已加载5个页面或屏幕</td> 
  </tr> 
  <tr> 
   <td>活动</td> 
   <td>定义为事件的操作触发</td> 
   <td>社交推荐、视频播放、广告点击</td> 
  </tr> 
 </tbody> 
</table>

大多数营销人员将其转化配置为“目标目标”，这意味着他们通常会在表单之后创建一个感谢页面来将该转化视为正式转化。

这意味着，Google会将“感谢您”页面查看视为转化。 从Google Analytics的角度来看，这是大多数营销人员都认同的一种实现。

但是，买方接触点的行为非常不同。

**买方接触点有何不同？**

[!DNL Marketo Measure] JavaScript跟踪特定站点所有形式的会话数据和表单提交。 无需从对目标进行编码 [!DNL Marketo Measure] 观点。 此过程是自动的。 对于表单提交， [!DNL Marketo Measure] 报告每次匿名用户在特定表单上填写信息字段并单击表单提交按钮时表单完成情况。 [!DNL Marketo Measure] 您不需要感谢页面来记录表单提交。

[!DNL Marketo Measure] 会在以下情况下创建表单接触点：

* 与这些转化关联的潜在客户/联系人会显示在您的CRM中。
* 此 [!DNL Marketo Measure] JS存在于包含表单的网页上。
* 表单会在30分钟的会话中提交。

[!DNL Marketo Measure] 在以下情况下，将忽略目标Google Analytics转化：

* 机器人在网站上提交表单（这些机器人通常不会将其转化为客户的CRM）。
* 用户在首次提交表单后提交更多表单。 [!DNL Marketo Measure] 将仅推送该会话的第一次转化。
* 用户多次单击表单提交。 [!DNL Marketo Measure] 将只考虑第一次提交表单。
* 用户多次重新加载感谢页面。
* 用户正在使用任何广告阻止工具。

如您所见，GA和 [!DNL Marketo Measure] 将转化视为。 因此，很有可能会出现转化次数和形式接触点数量不同的情况。
