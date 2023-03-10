---
unique-page-id: 35586105
description: 参与路径 —  [!DNL Marketo Measure]  — 产品文档
title: 参与路径
exl-id: 104d803f-9f40-4ab6-872d-6432f8c087e9
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 0%

---

# 参与路径 {#engagement-path}

“参与度路径”允许您从首次联系到结束，全面了解潜在客户、联系、帐户和商机参与。

![](assets/one-2.png)

## 图块描述 {#tile-description}

**事件类型：** 接触点类型（会话、CRM营销活动、CRM事件、CRM任务、展示次数）

**买方接触点位置：** 接触点潜在客户/联系人的位置

**买方归因接触点位置：** 采购员归因接触点机会的位置

**接触点日期：** 对于在线源：参与发生的日期和时间。 对于离线事件：在Salesforce营销活动中设置的日期和时间。 对于活动接触点：活动配置中引用的接触点日期字段

**电子邮件：** 与参与关联的电子邮件

**营销接触类型：** 参与类型（Web访问、Web窗体、Web聊天、CRM、活动类型）

**渠道：** 促进参与的营销渠道

**媒介：** 参与媒介

* 如果参与来自API连接的平台(Adwords/BingAds)媒体，则CPC为
* 如果参与度的登陆页面包含utm_medium，我们将解析
* 如果参与来自CRM营销活动，则媒体来自CRM营销活动的“类型”字段

**Web源：** 此列将显示参与的来源

* 如果参与来自API连接的平台，则Web源将显示广告平台的名称
* 如果接触点来自自然搜索，则此字段将显示搜索引擎的名称
* 如果#1或#2没有，并且接触点的登陆页面URL中存在utm_source值，则该值将显示在此处
* 如果#1或#2不存在，并且不存在utm_source值，则此处将显示反向链接URL的根域。
* 如果没有以上任何内容，则将显示Web Direct或Web

**首次与人员互动：** 如果接触点是个人首次交互，则此列将显示“是”或“否”

**归因收入：** 此列将根据所选的归因模型显示归因到该接触点的收入

## 过滤器描述 {#filter-description}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>过滤器名称</th> 
   <th>描述</th> 
  </tr> 
  <tr> 
   <td><p>帐户名称/ID</p></td> 
   <td><p>允许通过右侧的加号“+”添加过滤器来添加多个值。 多个筛选值将具有“或”关系，这意味着拼贴将显示两个筛选值的结果。 如果有任何过滤器值无效，则功能板将不会生成无效值的结果，但仍会根据有效的过滤器值进行过滤。 不区分大小写。</p></td> 
  </tr> 
  <tr> 
   <td><p>机会名称/ID</p></td> 
   <td><p>允许通过右侧的加号“+”添加过滤器来添加多个值。 多个筛选值将具有“或”关系，这意味着拼贴将显示两个筛选值的结果。 如果有任何过滤器值无效，则功能板将不会生成无效值的结果，但仍会根据有效的过滤器值进行过滤。 不区分大小写。</p></td> 
  </tr> 
  <tr> 
   <td><p>潜在客户ID/电子邮件</p></td> 
   <td><p>允许通过右侧的加号“+”添加过滤器来添加多个值。 多个筛选值将具有“或”关系，这意味着拼贴将显示两个筛选值的结果。 如果有任何过滤器值无效，则功能板将不会生成无效值的结果，但仍会根据有效的过滤器值进行过滤。 不区分大小写。</p></td> 
  </tr> 
  <tr> 
   <td><p>联系人ID/电子邮件</p></td> 
   <td><p>允许通过右侧的加号“+”添加过滤器来添加多个值。 多个筛选值将具有“或”关系，这意味着拼贴将显示两个筛选值的结果。 如果有任何过滤器值无效，则功能板将不会生成无效值的结果，但仍会根据有效的过滤器值进行过滤。 不区分大小写。</p><p>帐户名称/ID、潜在客户ID/电子邮件、联系人ID/电子邮件过滤器是“或”关系，这意味着如果潜在客户过滤器和联系人过滤器都具有值，则它将显示任一ID的所有记录。</p></td> 
  </tr> 
  <tr> 
   <td><p>归因模型</p></td> 
   <td><p>指定应计算归因收入的模型。 允许的值：“完整路径归因”、“首次联系归因”、“自定义模型归因”、“潜在客户创建归因”、“U型归因”、“W型归因”。</p></td> 
  </tr> 
  <tr> 
   <td><p>事件类型</p></td> 
   <td><p>按用户接触点所基于的事件类型过滤历程。 允许通过右侧的加号“+”添加过滤器来添加多个值。 允许的值：“会话”、“CRM促销活动”、“CRM事件”、“CRM任务”、“展示次数”。</p></td> 
  </tr> 
  <tr> 
   <td><p>潜在客户阶段</p></td> 
   <td><p>按用户接触点所基于的潜在客户阶段过滤旅程。 允许通过右侧的加号“+”添加过滤器来添加多个值。 默认的过滤器设置为“等于”将显示建议以供选择，但建议使用“包含”作为分阶段的多个过滤器的过滤器标准。</p></td> 
  </tr> 
  <tr> 
   <td><p>机会阶段</p></td> 
   <td><p>按机会阶段过滤用户接触点所基于的历程。 允许通过右侧的加号“+”添加过滤器来添加多个值。 默认的过滤器设置为“等于”将显示建议以供选择，但建议使用“包含”作为分阶段的多个过滤器的过滤器标准。</p></td> 
  </tr> 
  <tr> 
   <td><p>接触点日期</p></td> 
   <td><p>按接触点日期/时间过滤历程。</p></td> 
  </tr> 
  <tr> 
   <td><p>用户接触点电子邮件</p></td> 
   <td><p>按用户接触点的电子邮件过滤历程。 这允许过滤与潜在客户/联系人/帐户无关联的电子邮件。</p></td> 
  </tr> 
  <tr> 
   <td><p>营销接触类型</p></td> 
   <td><p>按营销接触类型过滤历程。</p></td> 
  </tr> 
  <tr> 
   <td><p>渠道</p></td> 
   <td><p>按渠道筛选历程。</p></td> 
  </tr> 
  <tr> 
   <td><p>中</p></td> 
   <td><p>按媒介筛选历程。</p></td> 
  </tr> 
  <tr> 
   <td><p>Web源</p></td> 
   <td><p>按Web源过滤历程。</p></td> 
  </tr> 
  <tr> 
   <td><p>首次与人员互动</p></td> 
   <td><p>按用户接触点表上的“是首次接触”列过滤历程。</p></td> 
  </tr> 
  <tr> 
   <td><p>归因收入</p></td> 
   <td><p>按归因收入值过滤历程。</p></td> 
  </tr> 
 </tbody> 
</table>
