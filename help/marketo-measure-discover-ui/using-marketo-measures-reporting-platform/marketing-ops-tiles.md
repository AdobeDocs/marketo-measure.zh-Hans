---
unique-page-id: 34406495
description: 营销运营拼贴 —  [!DNL Marketo Measure]  — 产品文档
title: 营销运营拼贴
exl-id: e7978a79-6f6e-4bfd-9962-b35b7d46a9ac
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---

# 营销运营拼贴 {#marketing-ops-tiles}

营销运营允许您验证和诊断 [!DNL Marketo Measure] 数据，可完全了解每个潜在客户、联系人、帐户、营销活动和机会的各个接触点。

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><br></td> 
   <td><p><strong>帐户 ID</strong></p></td> 
   <td><p><strong>帐户名称</strong></p></td> 
   <td><p><strong>Opp ID</strong></p></td> 
   <td><p><strong>Opp名称</strong></p></td> 
   <td><p><strong>潜在客户或联系人ID</strong></p></td> 
   <td><p><strong>潜在客户或联系人电子邮件</strong></p></td> 
   <td><p><strong>促销活动ID</strong></p></td> 
   <td><p><strong>Opp Won</strong></p></td> 
   <td><p><strong>Opp创建日期</strong></p></td> 
   <td><p><strong>Opp关闭日期</strong></p></td> 
   <td><p><strong>接触点日期</strong></p></td> 
   <td><p><strong>归因模型</strong></p></td> 
  </tr> 
  <tr> 
   <td><p><strong>帐户</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>机会</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>联系人</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>潜在客户</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>促销活动</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
 </tbody> 
</table>

## 帐户磁贴 {#account-tile}

![](assets/one-1.png)

显示与指定帐户相关的以下数据。

**帐户必须具有接触点数据（仅当您启用了ABM时才适用）**

 — 帐户ID:CRM中的帐户ID

 — 帐户名称：CRM中的帐户名称

 — 创建日期：在CRM中创建帐户的日期

* 深入分析：请参阅按小时、分钟、时间创建的日期

 — 网站：在帐户的网站字段中找到的值

 — 参与度评级：预测参与度分数(PES)由 [!DNL Marketo Measure]^1

 — 机会：连接到帐户的机会数

* 深入分析：查看关联的Opportunity的详细信息

 — 联系人：此帐户上列出的联系人数

* 深入分析：查看关联联系人的详细信息

 — 潜在客户：通过潜在客户映射映射到此帐户的潜在客户数量^1

* 深入分析：查看已映射到帐户的潜在客户的详细信息

 — 归因接触点：帐户的购买者归因接触点数

* 深入分析：请参阅购买者归因接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型、归因模型）

 — 触点：此帐户上联系人拥有^2的接触点数

* 深入分析：请参阅帐户接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型）上的接触点

>[!NOTE]
>
>如果您有ABM，它将显示与通过“潜在客户到帐户映射”映射的潜在客户相关的接触点。

## 机会磁贴 {#opportunity-tile}

![](assets/two-1.png)

显示与指定的Opportunity相关的以下数据。

 — 机会ID:CRM中的机会ID

 — 机会名称：CRM中的机会名称

 — 帐户名称：与业务机会关联的帐户名称

 — 创建日期：在CRM中创建Opportunity的日期

深入分析：请参阅按小时、分钟、时间创建的日期

 — 关闭日期：CRM中Opportunity的结束日期

深入分析：请参阅按小时、分钟、时间划分的关闭日期

 — 金额：Opportunity的总金额

 — 联系人：与Opportunity关联的联系人数

深入分析：查看关联联系人的详细信息

 — 归因接触点：相关买方归因接触点的数量

深入分析：请参阅购买者归因接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型、归因模型）

## 联系人拼贴 {#contacts-tile}

![](assets/three-1.png)

显示与指定的联系人相关的以下数据。

 — 联系人ID:CRM中的联系人ID

 — 电子邮件：联系人记录电子邮件地址

 — 创建日期：在CRM中创建联系人的日期

* 深入分析：请参阅按小时、分钟、时间创建的日期

 — 帐户名称：与联系人关联的帐户名称

 — 归因接触点：联系人的购买者归因接触点数量

* 深入分析：请参阅购买者归因接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型、归因模型）

 — 触点：联系人的买方接触点数

* 深入分析：请参阅帐户接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型）上的联系人

## 潜在客户拼贴 {#leads-tile}

![](assets/four-1.png)

显示以下与指定潜在客户相关的数据。

 — 潜在客户ID:CRM中的潜在客户ID

 — 电子邮件：潜在客户记录电子邮件地址

 — 创建日期：在CRM中创建潜在客户时

* 深入分析：请参阅按小时、分钟、时间创建的日期

 — 公司（来自潜在客户）：在CRM的记录中列出的公司，由客户填充

 — 帐户名称：帐户名称 [!DNL Marketo Measure] 根据我们的潜在客户到帐户映射填充

 — 触点：与潜在客户关联的接触点数

* 深入分析：请参阅帐户接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型）上的联系人

## 营销活动拼贴 {#campaigns-tile}

![](assets/five-1.png)

显示以下与指定的促销活动相关的数据。

 — 促销活动ID:CRM中的促销活动ID

 — 营销活动名称：CRM中的促销活动名称

 — 促销活动支出：支出 [!DNL Marketo Measure] 已记录与营销活动关联

 — 归因模型：这将根据所选模型显示相应的归因

 — 归因接触点：与促销活动关联的购买者归因接触点的数量

* 深入分析：请参阅购买者归因接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型、归因模型）

 — 触点：与营销活动关联的接触点数量

* 深入分析：请参阅帐户接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型）上的联系人
