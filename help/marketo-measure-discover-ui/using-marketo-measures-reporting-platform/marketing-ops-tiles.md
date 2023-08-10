---
unique-page-id: 34406495
description: 营销操作图块 —  [!DNL Marketo Measure]  — 产品文档
title: 营销操作图块
exl-id: e7978a79-6f6e-4bfd-9962-b35b7d46a9ac
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---

# 营销操作图块 {#marketing-ops-tiles}

营销操作允许您验证和诊断 [!DNL Marketo Measure] 能够全面了解每个潜在客户、联系人、客户、营销活动和商机的各个接触点的数据。

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
   <td><p><strong>营销活动ID</strong></p></td> 
   <td><p><strong>Opp Won</strong></p></td> 
   <td><p><strong>Opp创建日期</strong></p></td> 
   <td><p><strong>打开关闭日期</strong></p></td> 
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
   <td><p><strong>营销活动</strong></p></td> 
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

**帐户必须具有接触点数据（仅当启用了ABM时才适用）**

 — 帐户ID：CRM中的帐户ID

-Account Name： CRM中的帐户名称

 — 创建日期： CRM中帐户的创建日期

* 深入分析：请参阅按小时、分钟、时间创建的日期

-Web站点：在“帐户”的“网站”字段中找到的值

 — 参与度评级：由填充的预测参与度分数(PES) [!DNL Marketo Measure]^1

-Opportunities：与帐户关联的机会数

* 追溯：查看相关Opportunity的详细信息

-Contacts：此帐户中列出的联系人数

* 追溯：查看关联联系人的详细信息

 — 潜在客户：通过潜在客户到帐户的映射映射到此帐户的潜在客户数^1

* 追溯：查看已映射到帐户的潜在客户的详细信息

 — 归因接触点：帐户的买方归因接触点数量

* 深入分析：查看购买者归因接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型、归因模型）

 — 接触点：此帐户上的联系人具有的接触点数^2

* 深入分析：查看帐户接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型）

>[!NOTE]
>
>如果您有ABM，它将显示与已通过“潜在客户到帐户的映射”映射的潜在客户相关的接触点。

## 机会磁贴 {#opportunity-tile}

![](assets/two-1.png)

显示与指定的机会相关的以下数据。

-Opportunity ID： CRM中的Opportunity ID

-Opportunity Name： CRM中的机会名称

-Account Name：与商机关联的帐户名称

-Created Date： CRM中机会的创建日期

深入分析：请参阅按小时、分钟、时间创建的日期

-Close Date： CRM中机会的结束日期

向下展开：请参阅按小时、分钟、时间列出的关闭日期

-Amount：商机的总金额

-Contacts：与商机关联的联系人数

追溯：查看关联联系人的详细信息

 — 归因接触点：相关买方归因接触点的数量

深入分析：查看购买者归因接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型、归因模型）

## 联系人拼贴 {#contacts-tile}

![](assets/three-1.png)

显示与指定联系人相关的以下数据。

-Contact ID： CRM中的联系人ID

-Email：联系人记录电子邮件地址

 — 创建日期： CRM中联系人的创建日期

* 深入分析：请参阅按小时、分钟、时间创建的日期

 — 帐户名称：与联系人关联的帐户名称

 — 归因接触点：联系人的买方归因接触点数量

* 深入分析：查看购买者归因接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型、归因模型）

 — 接触点：联系人的买方接触点数量

* 深入分析：查看帐户接触点详细信息（ID、电子邮件、接触点日期、帐户名称、营销活动、渠道、子渠道、营销接触类型）中的联系人

## 潜在客户拼贴 {#leads-tile}

![](assets/four-1.png)

显示与指定的潜在客户相关的以下数据。

-Lead ID： CRM中的潜在客户ID

-Email：潜在客户记录电子邮件地址

 — 创建日期：在CRM中创建商机的时间

* 深入分析：请参阅按小时、分钟、时间创建的日期

 — 公司（来自潜在客户）：客户填充的CRM中记录上列出的公司

-Account Name：帐户名称 [!DNL Marketo Measure] 根据我们的潜在客户到客户的映射填充

 — 接触点：与商机关联的接触点数量

* 深入分析：查看帐户接触点详细信息（ID、电子邮件、接触点日期、帐户名称、营销活动、渠道、子渠道、营销接触类型）中的联系人

## “营销活动”图块 {#campaigns-tile}

![](assets/five-1.png)

显示与指定促销活动相关的以下数据。

-Campaign ID：CRM中的Campaign ID

-Campaign名称： CRM中的Campaign名称

 — 促销活动支出：支出 [!DNL Marketo Measure] 已录制与营销活动关联的节目

 — 归因模型：这将根据所选模型显示相应的归因

 — 归因接触点：与促销活动关联的买方归因接触点数量

* 深入分析：查看购买者归因接触点详细信息（ID、电子邮件、接触点日期、帐户名称、促销活动、渠道、子渠道、营销接触类型、归因模型）

 — 接触点：与营销活动关联的接触点数量

* 深入分析：查看帐户接触点详细信息（ID、电子邮件、接触点日期、帐户名称、营销活动、渠道、子渠道、营销接触类型）中的联系人
