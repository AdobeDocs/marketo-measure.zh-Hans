---
description: BT和BAT之间接触点位置和生成的说明 —  [!DNL Marketo Measure]  — 产品文档
title: BT和BT的接触点位置和生成说明 [!DNL BATs]
exl-id: 4903f917-a366-4767-a126-5216d2377399
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 0%

---

# BT和BT的接触点位置和生成说明 [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**生成接触点位置并通过购买者历程**

了解购买者接触点位置及其触发方式对于成功报告至关重要 [!DNL Marketo Measure] 数据。 您将希望清楚了解潜在客户在购买者历程中所执行的操作，进而了解接触点数据中的显示情况。 有关此主题的更多上下文，我们建议您查看 [[!UICONTROL Touchpoint Generation & Mapping]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) 文章。

[!DNL Marketo Measure] 具有各种接触点位置，这些接触点位置由购买者历程中的各种步骤触发。 报告 [!DNL Marketo Measure] 数据有两组接触点数据，即购买者接触点(BT)和购买者归因接触点(BAT)。 您可能会注意到这些数据集与不同对象的位置略有不同。 有关此主题的更多上下文，我们建议您查看 [买方接触点(BT)与买方归因接触点(BAT)之间的差异](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) 文章。

**买方接触点(BT)**:这些是与个人及其历程关联的接触点，对于该个人而言将是唯一的。 以下开箱即用的报表是基于买方接触点数据构建的。

* [!DNL Marketo Measure] 101:按ID划分的潜在客户
* [!DNL Marketo Measure] 101:按渠道划分的潜在客户
* [!DNL Marketo Measure] 101:按ID列出的潜在客户/联系人
* [!DNL Marketo Measure] 101:按渠道划分的潜在客户/联系人

以下概述了买方接触点职位，其中描述了个人在其历程中的位置以及他们为获得该职位而采取的操作。

<table> 
 <tbody>
  <tr>
   <th>买方接触点(BT)位置</th> 
   <th>接触点类型（可触发接触点的操作）</th> 
   <th>接触点描述</th> 
  </tr>
  <tr>
   <td>首次接触(FT)</td> 
   <td>Web访问</td> 
   <td>个人与您的品牌进行的首次营销互动</td> 
  </tr>
  <tr>
   <td>商机创建(LC)</td> 
   <td>表单填充 <strong>或</strong> 营销活动/项目包含</td> 
   <td>个人填写的第一个表单（通常是表单提交，但也可能是营销活动/项目包含）</td> 
  </tr>
  <tr>
   <td>Post LC</td> 
   <td>表单填充 <strong>或</strong> 营销活动/项目包含</td> 
   <td>个人在LC（或后续的营销活动/项目包含）之后完成的任何形式</td> 
  </tr>
 </tbody>
</table>

**买方归因接触点(BATS)**:这些是与Opportunity及其历程关联的接触点。 这些接触点将与收入相连，因为它们与Opportunity及其Contact相连。 以下开箱即用的报表是基于买方归因接触点数据构建的。

* [!DNL Marketo Measure] 101:按ID列出的机会
* [!DNL Marketo Measure] 101:按ID渠道列出的机会

<table> 
 <tbody>
  <tr>
   <th>买方归因接触点(BAT)位置</th> 
   <th>接触点类型（可触发接触点的操作）</th> 
   <th>接触点描述</th> 
  </tr>
  <tr>
   <td>首次接触(FT)</td> 
   <td>Web访问</td> 
   <td>联系人与您的品牌进行的首次营销互动</td> 
  </tr>
  <tr>
   <td>商机创建(LC)</td> 
   <td>表单填充 <strong>或</strong> 营销活动/项目包含</td> 
   <td>填写联系人的第一个表单（通常是表单提交，但也可能是营销活动/项目包含）</td> 
  </tr>
  <tr>
   <td>机会创造</td> 
   <td>表单填充 <strong>或</strong> Web访问 <strong>或</strong> 营销活动/项目包含</td> 
   <td>最接近创建Opp时的营销互动</td> 
  </tr> 
  <tr>
   <td>已关闭韩元/亏损</td> 
   <td>表单填充 <strong>或</strong> Web访问 <strong>或</strong> 营销活动/项目包含</td> 
   <td>距离Opp关闭（获胜或失败）最近的营销互动</td> 
  </tr>
  <tr>
   <td>中间接触</td> 
   <td>表单填充 <strong>或</strong> 营销活动/项目包含</td> 
   <td>当联系人填写在线表单，并且它与里程碑接触点不一致时</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] 拥有这两组接触点数据，以清晰地了解个人历程和机会。 这两个接触点数据集为您提供了从漏斗顶部到漏斗底部的明确映射。

以下示例显示从买方接触点(BT)到买方归因接触点(BAT)的数据流。 在本例中，人员A和人员B都是同一Opportunity的一部分，该Opportunity的创建日期为3/7/2020，关闭日期为5/6/2020。

**人员A** 买方接触点数据集

* 首次联系(FT) — 付费搜索.AdWords - 9/1/2019
* 商机创建(LC) — 免费搜索。Google- 11/20/2019
* 帖子LC（表单填写） — 网络研讨会 — 3/4/2020

**人员B** 买方接触点数据集

* 首次联系(FT) — 付费Social.Facebook- 8/26/2019
* 商机创建(LC) — 免费搜索。Yahoo - 2/20/2020
* 帖子LC（表单填写） — 电子邮件 — 5/1/2020

**机会** 买方归因接触点数据将如下所示……

* 首次联系(FT) — 付费Social.Facebook- 8/26/2019
   * (从 **人员B** 因为他们是真的 _首次接触_ 帐户/Opp)
* 商机创建(LC) — 免费搜索。Google- 11/20/2019
   * (从 **人员A** 因为他们是真的 _商机创建_ 帐户/Opp)
* 机会创建(OC) — 网络研讨会 — 3/4/2020
   * (POST LC接触点自 **人员A** 会是 _OC接触点_ 因为这是我们对3/7/2020上正在创建的Opportunity的最近一次互动)
* 闭门原因 — 电子邮件 — 5/1/2020
   * (POST LC接触点自 **人员B** 会是 _已关闭的Won接触点_ 因为这是我们在5/6/2020上要关闭Opportunity的最新互动)
