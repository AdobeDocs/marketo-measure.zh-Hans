---
unique-page-id: 18874648
description: Google Analytics转化与购买者接触点之间的差异 —  [!DNL Marketo Measure]  — 产品文档
title: Google Analytics转化与购买者接触点之间的差异
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Google Analytics转化与购买者接触点之间的差异 {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

了解 [!DNL Google Analytics (GA)] 目标及其与购买者接触点的区别。

**什么是Google Analytics转化？**

[!UICONTROL Google Analytics] 转化完全取决于营销人员或Web开发人员如何在特定网站上编码“目标”完成。 根据Google的说法，目标可以被视为“购买（为电子商务网站）、完成游戏级别（为移动游戏应用程序）或提交联系信息表（为营销或商机拓展网站）”。 大多数情况下，营销人员会将目标/转化视为填写信息性表单的人员。

但是，无法对目标进行编码以管理非常具体的行为。 Web开发人员可以配置一些目标类型。 以下是一些示例：

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
   <td>持续特定时间或更长的会话</td> 
   <td>在支持网站上花费10分钟或更长时间</td> 
  </tr> 
  <tr> 
   <td>每个会话的页面/屏幕数</td> 
   <td>用户查看特定数量的页面或屏幕</td> 
   <td>加载了5个页面或屏幕</td> 
  </tr> 
  <tr> 
   <td>Event</td> 
   <td>将触发定义为事件的操作</td> 
   <td>社交推荐、视频播放、广告点击</td> 
  </tr> 
 </tbody> 
</table>

大多数营销人员将其转化配置为“目标”，这意味着他们通常会在表单后创建感谢页面以将其视为正式转化。

这意味着，Google会将“感谢”页面查看视为一次转化。 从Google Analytics的角度来看，这是大多数营销人员可以接受的。

但是，买方接触点的行为却截然不同。

**买方接触点有何不同？**

[!DNL Marketo Measure] JavaScript跟踪特定网站所有形式上的会话数据和表单提交。 无需通过 [!DNL Marketo Measure] 立场。 此过程是自动的。 对于表单提交， [!DNL Marketo Measure] 每次匿名用户填写特定表单的信息字段并单击表单提交按钮时，都会报告表单完成情况。 [!DNL Marketo Measure] 无需感谢页面即可记录表单提交。

[!DNL Marketo Measure] 将在以下情况下创建表单接触点：

* 与这些转化关联的潜在客户/联系人会显示在您的CRM中。
* 的 [!DNL Marketo Measure] JS存在于包含表单的网页上。
* 表格将在30分钟的会话内提交。

[!DNL Marketo Measure] 将忽略目标Google Analytics转化，条件是：

* 机器人在网站上提交表单（这些机器人通常不会将其纳入客户的CRM中）。
* 用户在首次提交表单后提交更多表单。 [!DNL Marketo Measure] 将仅推送该会话中的第一个转化。
* 用户多次单击表单提交。 [!DNL Marketo Measure] 将仅考虑提交第一个表单。
* 用户多次重新加载感谢页面。
* 用户正在使用任何广告拦截工具。

如您所见，GA与 [!DNL Marketo Measure] 以转化为例。 因此，转化次数和接触点表单数量很可能会有所不同。
