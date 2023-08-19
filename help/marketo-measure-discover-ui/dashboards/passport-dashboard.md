---
description: 护照信息板 —  [!DNL Marketo Measure]  — 产品
title: Passport信息板
feature: Reporting
source-git-commit: 73f7d14f94b236b5e078a4c8ff7a1e81d13779ee
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 3%

---

# Passport信息板 {#passport-dashboard}

Passport仪表板为营销人员提供了在指定时间段内各个阶段进行过渡时潜在客户、联系人和机会的动态视图。 通过筛选特定日期，用户还可以获取该日期的记录快照。

讨论区回答的问题：

* 在选择的某一天，每个非终止阶段有多少潜在客户、联系人或机会？
* 在指定的时间段内，有多少不同的潜在客户或联系人在每个过渡阶段中前进？
   * _示例_：如果铅A在2023年1月1日进入阶段1，并在2023年3月31日之前进入阶段5，则2023年第1季度护照分析将按阶段1-5对铅A进行计数。
* 在给定的时间范围内，每个过渡阶段传递了多少个独特的机会？

<table style="table-layout:auto"> 
<tbody>
<tr> 
   <th>组件</th> 
   <th>描述</th>
   <th>日期类型</th>
   <th>穿透钻取字段</th>
   <th>过滤器</th>
  </tr>
  <tr>
    <td>机会</td>
    <td><li>每个阶段都显示在给定时间范围内传递的具有BAT的Opportunity的数量。</li>
<ul style="padding-left: 30px;"><li>如果Opportunity在该跨度内跨多个阶段进行，则他们将被计入其传递的每个阶段。</li></ul>
<li>排除“已关闭的赢家”和“已关闭的输家”等终端阶段。</li>
<li>开始日期和结束日期均包含。</li>
<br/><img src="assets/passport-dashboard-1.png" width="600"></td>
    <td rowspan="2">过渡日期</td>
    <td><li>机会ID</li>
<li>机会名称</li>
<li>创建日期</li>
<li>关闭日期</li>
<li>为已关闭(Y/N)</li>
<li>获胜(Y/N)</li>
<li>当前阶段</li>
<li>过渡日期</li>
<li>过渡截止日期</li></td>
    <td rowspan="2"><li>日期</li>
<li>渠道</li>
<li>子渠道</li>
<li>营销活动</li>
<li>区段</li></td>
  </tr>
  <tr>
    <td>潜在客户/联系人</td>
    <td><li>每个阶段显示给定时间范围内已通过BT的潜在客户或联系人数量。</li>
<ul style="padding-left: 30px;"><li>显示“潜在客户”还是“联系人”取决于在“设置”&gt;“归因设置”&gt;“默认仪表板对象”中设置的首选项。</li></ul>
<li>排除“已关闭的赢家”和“已关闭的输家”等终端阶段。</li>
<li>开始日期和结束日期均包含。</li>
<br/><img src="assets/passport-dashboard-2.png" width="600"></td>
    <td><li>潜在客户/联系人ID</li>
<li>潜在客户/联系人电子邮件</li>
<li>创建日期</li>
<li>当前阶段</li>
<li>过渡日期</li>
<li>过渡截止日期</li></td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>
>[了解功能板基础知识](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
