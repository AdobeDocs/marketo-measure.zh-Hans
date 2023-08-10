---
description: 跨BT和BAT的接触点位置和生成说明 —  [!DNL Marketo Measure]  — 产品文档
title: 跨BT和的接触点位置和生成说明 [!DNL BATs]
exl-id: 4903f917-a366-4767-a126-5216d2377399
feature: Touchpoints
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 0%

---

# 跨BT和的接触点位置和生成说明 [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**生成接触点位置和流经买家历程**

了解买方接触点位置及其触发方式对于成功报告至关重要 [!DNL Marketo Measure] 数据。 您将需要清楚地了解您的潜在客户在买方历程中的行为，进而了解他们在接触点数据中的外观。 有关此主题的更多上下文，我们建议查看 [[!UICONTROL Touchpoint Generation & Mapping]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) 文章。

[!DNL Marketo Measure] 具有由购买者历程中的各个步骤触发的各种接触点位置。 报告时 [!DNL Marketo Measure] 数据包含两组接触点数据：买方接触点(BT)和买方归因接触点(BAT)。 您可能会注意到，这些数据集与不同对象之间的位置稍有不同。 有关此主题的更多上下文，我们建议查看 [买方接触点(BT)与买方归因接触点(BAT)之间的区别](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) 文章。

**买方接触点(BT)**：这些是与个人及其历程关联的接触点，将是该个人特有的接触点。 以下现成报告基于买方接触点数据构建。

* [!DNL Marketo Measure] 101：按ID列出的潜在客户
* [!DNL Marketo Measure] 101：按渠道列出的潜在客户
* [!DNL Marketo Measure] 101：按ID列出的潜在客户/联系人
* [!DNL Marketo Measure] 101：按渠道列出的潜在客户/联系人

下面概述了买方接触点位置，其中描述了个人在历程中的位置以及为获得该位置而采取的操作。

<table> 
 <tbody>
  <tr>
   <th>买方接触点(BT)位置</th> 
   <th>接触点类型（可触发接触点的操作）</th> 
   <th>接触点描述</th> 
  </tr>
  <tr>
   <td>首次联系（英尺）</td> 
   <td>Web访问</td> 
   <td>个人与您的品牌进行的首次营销互动</td> 
  </tr>
  <tr>
   <td>商机创建(LC)</td> 
   <td>表单填写 <strong>或者</strong> 活动/项目包含</td> 
   <td>个人填写的第一个表单（通常是表单提交，但也可能是营销活动/项目包含）</td> 
  </tr>
  <tr>
   <td>POST LC</td> 
   <td>表单填写 <strong>或者</strong> 活动/项目包含</td> 
   <td>个人在信用证之后完成的任何形式（或后续促销活动/项目包含）</td> 
  </tr>
 </tbody>
</table>

**买方归因接触点(BATS)**：这些是与Opportunity及其历程关联的接触点。 这些接触点将连接到收入，因为它们连接到Opportunity及其联系人。 以下现成的报告基于买方归因接触点数据构建。

* [!DNL Marketo Measure] 101：按ID列出的机会
* [!DNL Marketo Measure] 101：按ID渠道列出的机会

<table> 
 <tbody>
  <tr>
   <th>买方归因接触点(BAT)位置</th> 
   <th>接触点类型（可触发接触点的操作）</th> 
   <th>接触点描述</th> 
  </tr>
  <tr>
   <td>首次联系（英尺）</td> 
   <td>Web访问</td> 
   <td>联系人与您的品牌进行的首次营销互动</td> 
  </tr>
  <tr>
   <td>商机创建(LC)</td> 
   <td>表单填写 <strong>或者</strong> 活动/项目包含</td> 
   <td>联系人填写的第一个表单（通常是表单提交，但也可能是营销活动/项目包含）</td> 
  </tr>
  <tr>
   <td>机会创建</td> 
   <td>表单填写 <strong>或者</strong> Web访问 <strong>或者</strong> 活动/项目包含</td> 
   <td>创建Opp时最接近的营销交互</td> 
  </tr> 
  <tr>
   <td>已关闭的赢家/输家</td> 
   <td>表单填写 <strong>或者</strong> Web访问 <strong>或者</strong> 活动/项目包含</td> 
   <td>Opp关闭时（成功或失败）与之最接近的营销交互</td> 
  </tr>
  <tr>
   <td>中间接触</td> 
   <td>表单填写 <strong>或者</strong> 活动/项目包含</td> 
   <td>当联系人填写在线表单并且它与里程碑接触点不符时</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] 具备这两组接触点数据，从而清楚地了解个人的历程以及机会。 这两个接触点数据集为您提供了从漏斗顶部到漏斗底部所发生情况的清晰地图。

以下示例显示了从买方接触点(BT)到买方归因接触点(BAT)的数据流。 在此示例中，人员A和人员B都是创建日期为2020年7月3日且结束日期为2020年6月3日的同一Opportunity的一部分。

**人员A** 买方接触点数据集

* 首次联系(FT) — 付费搜索.AdWords - 9/1/2019
* 潜在客户创建(LC) - Organic Search.Google - 11/20/2019
* 发布LC（表单填写） — 网络研讨会 — 2020年3月4日

**人员B** 买方接触点数据集

* 首次联系(FT) — 付费Social.Facebook - 8/26/2019
* 潜在客户创建(LC) - Organic Search.Yahoo - 2/20/20
* POST LC（表单填写） — 电子邮件 — 5/1/2020

**机会** 买方归因接触点数据如下所示……

* 首次联系(FT) — 付费Social.Facebook - 8/26/2019
   * (从 **人员B** 因为他们有真理 _首次接触_ （针对帐户/Opp）
* 潜在客户创建(LC) - Organic Search.Google - 11/20/2019
   * (从 **人员A** 因为他们有真理 _潜在客户创建_ （针对帐户/Opp）
* 机会创造(OC) — 网络研讨会 — 2020年3月4日
   * (POST LC接触点来自 **人员A** 将为 _OC接触点_ 因为这是我们最近一次与2020年7月3日创建的Opportunity的互动)
* 非公开 — 电子邮件 — 2020年5月1日
   * (POST LC接触点来自 **人员B** 将为 _已关闭的赢家接触点_ 因为这是我们最近一次与2020年5月6日结束的Opportunity的互动)
