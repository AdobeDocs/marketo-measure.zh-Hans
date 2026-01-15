---
description: 跨BT的接触点位置和生成说明以及Marketo Measure用户的 [!DNL BATs] 指南
title: 跨BT和 [!DNL BATs]的接触点位置和生成说明
exl-id: 4903f917-a366-4767-a126-5216d2377399
feature: Touchpoints
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 0%

---


# 跨BT和[!DNL BATs]的接触点位置和生成说明 {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**生成接触点位置和流过购买者历程**

了解Buyer Touchpoint职位及其触发方式对于成功报告[!DNL Marketo Measure]数据至关重要。 您希望清楚地了解您的潜在客户在买方历程中的行为方式，以及这些行为在接触点数据中会是什么样子。 有关此主题的更多上下文，我们建议查看[[!UICONTROL Touchpoint Generation & Mapping]](/help/configuration-and-setup/touchpoint-generation-and-mapping.md)文章。

[!DNL Marketo Measure]具有由购买者历程中的各个步骤触发的各种接触点位置。 报告[!DNL Marketo Measure]数据时，存在两组接触点数据：买方接触点(BT)和买方归因接触点(BAT)。 您可能会注意到，这些数据集与不同对象之间的位置稍有不同。 有关此主题的更多上下文，我们建议查看[买方接触点(BT)与买方归因接触点(BAT)之间的差异](/help/configuration-and-setup/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)文章。

**购买者接触点(BT)**：这些是与个人及其历程关联的接触点，将是该个人特有的接触点。 以下开箱即用的报表是基于Buyer Touchpoint数据构建的。

* [!DNL Marketo Measure] 101：按ID列出的潜在客户
* [!DNL Marketo Measure] 101：按渠道列出的潜在客户
* [!DNL Marketo Measure] 101：潜在客户/联系人（按ID）
* [!DNL Marketo Measure] 101：按渠道列出的潜在客户/联系人

以下内容概述了Buyer Touchpoint的立场，其中描述了个人在其历程中的位置以及为获得该立场采取了哪些行动。

<table>
 <tbody>
  <tr>
   <th>Buyer Touchpoint (BT)位置</th>
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
   <td>表单填写<strong>或</strong>促销活动/项目包含</td>
   <td>第一个表单用于填充个人（通常是表单提交，但也可能是营销活动/项目包含）</td>
  </tr>
  <tr>
   <td>POST LC</td>
   <td>表单填写<strong>或</strong>促销活动/项目包含</td>
   <td>个人在信用证之后完成的任何形式（或后续促销活动/项目包含）</td>
  </tr>
 </tbody>
</table>

**购买者归因接触点(BATS)**：这些是与Opportunity及其历程关联的接触点。 这些接触点与Opportunity及其Contacts关联，因此与收入关联。 以下开箱即用的报表是基于Buyer Attribution Touchpoint数据构建的。

* [!DNL Marketo Measure] 101：按ID列出的机会
* [!DNL Marketo Measure] 101：按ID渠道列出的机会

<table>
 <tbody>
  <tr>
   <th>Buyer Attribution Touchpoint (BAT)位置</th>
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
   <td>表单填写<strong>或</strong>促销活动/项目包含</td>
   <td>联系人的第一个表单填写（通常是表单提交，但也可能是营销活动/项目包含）</td>
  </tr>
  <tr>
   <td>机会创建</td>
   <td>表单填写<strong>或</strong> Web访问<strong>或</strong>促销活动/项目包含</td>
   <td>创建Opp时最接近的营销交互</td>
  </tr>
  <tr>
   <td>已关闭的赢家/输家</td>
   <td>表单填写<strong>或</strong> Web访问<strong>或</strong>促销活动/项目包含</td>
   <td>Opp关闭时（成功或失败）与之最接近的营销交互</td>
  </tr>
  <tr>
   <td>中间接触</td>
   <td>表单填写<strong>或</strong>促销活动/项目包含</td>
   <td>当联系人填写在线表单并且它与里程碑接触点不符时</td>
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure]拥有这两组接触点数据，以便清楚地了解个人的历程和机会。 这两个接触点数据集为您提供了从funnel顶部到funnel底部所发生情况的清晰地图。

以下示例显示了从买方接触点(BT)到买方归因接触点(BAT)的数据流。 在此示例中，人员A和人员B都是创建日期为2020年7月3日且结束日期为2020年6月3日的同一Opportunity的一部分。

**人员A** Buyer Touchpoint数据集

* 首次联系(FT) — 付费搜索.AdWords - 9/1/2019
* 潜在客户创建(LC) - Organic Search.Google - 11/20/2019
* 发布LC（表单填写） — 网络研讨会 — 2020年3月4日

**人员B** Buyer Touchpoint数据集

* 首次联系(FT) — 付费社交.Facebook - 8/26/2019
* 潜在客户创建(LC) - Organic Search.Yahoo - 2/20/20
* POST LC（表单填写） — 电子邮件 — 5/1/2020

**机会** Buyer Attribution Touchpoint数据将如下所示……

* 首次联系(FT) — 付费社交.Facebook - 8/26/2019
   * （来自&#x200B;**人员B**，因为他们具有帐户/Opp的真&#x200B;_首次联系_）
* 潜在客户创建(LC) - Organic Search.Google - 11/20/2019
   * （来自&#x200B;**人员A**，因为他们具有真正的&#x200B;_潜在客户创建_&#x200B;帐户/Opp）
* 机会创造(OC) — 网络研讨会 — 2020年3月4日
   * （**人员A**&#x200B;的Post LC接触点将成为&#x200B;_OC接触点_，因为它是我们与2020年3月7日创建的Opportunity的最近交互）
* 非公开 — 电子邮件 — 2020年5月1日
   * （**人员B**&#x200B;的Post LC接触点将为&#x200B;_已关闭的成功接触点_，因为它是我们与2020年5月6日关闭的Opportunity的最近交互）
