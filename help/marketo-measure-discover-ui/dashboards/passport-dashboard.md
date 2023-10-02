---
description: 护照信息板 —  [!DNL Marketo Measure]  — 产品
title: Passport信息板
feature: Reporting
source-git-commit: b984779d8d4795bf43b7494d5cba06ab84ae097d
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# Passport信息板 {#passport-dashboard}

Passport仪表板为营销人员提供了在指定时间段内各个阶段进行过渡时潜在客户、联系人和机会的动态视图。 通过筛选特定日期，用户还可以获取该日期的记录快照。

>[!NOTE]
>
>该仪表板当前处于Beta版。 在此过渡阶段，当前功能板和新功能板都将可供访问。 一旦我们完全过渡并确保实现最佳功能，当前的仪表板将被弃用。

**讨论区回答的问题：**

* 在选择的某一天，每个非终止阶段有多少潜在客户、联系人或机会？
* 在指定的时间段内，有多少不同的潜在客户或联系人在每个过渡阶段中前进？
   * _示例_：如果铅A在2023年1月1日进入阶段1，并在2023年3月31日之前进入阶段5，则2023年第1季度护照分析将按阶段1-5对铅A进行计数。
* 在给定的时间范围内，每个过渡阶段传递了多少个独特的机会？

## 功能板组件 {#dashboard-components}

### 按阶段名称暂存的机会 {#opportunities-in-stage-by-stage-name}

* 每个阶段都显示在给定时间范围内已通过接触点的机会数。
   * 如果一个机会在该跨度内跨越多个阶段，则它将被计入该机会的每个阶段。
* 排除“已关闭的赢家”和“已关闭的输家”等终端阶段。
* 开始日期和结束日期均包含。

![](assets/passport-dashboard-1.png)

### 按阶段名称列出的阶段中的潜在客户或联系人 {#leads-or-contacts-in-stage-by-stage-name}

* 每个阶段显示具有在给定时间范围内通过它们的接触点的Lead或Contact的数量。
   * 显示“潜在客户”还是“联系人”取决于在“设置”>“归因设置”>“默认仪表板对象”中设置的首选项。
   * 如果潜在客户或联系人在该跨度内跨多个阶段进行，则会将其计入每个阶段。
* 排除“已关闭的赢家”和“已关闭的输家”等终端阶段。
* 开始日期和结束日期均包含。

![](assets/passport-dashboard-2.png)

## 筛选器窗格 {#filter-pane}

此仪表板配备了以下设置和过滤器：

* 日期（基于过渡日期）
* 归因模型
* 渠道、子渠道
* Campaign
* 区段

>[!MORELIKETHIS]
>
>[了解功能板基础知识](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
