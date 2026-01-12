---
description: '[!DNL Marketo Engage]人员集成 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Engage]人员集成'
exl-id: 51930e84-4ff8-4e35-9d44-ea017c24b051
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 1%

---


# [!DNL Marketo Engage]人员集成 {#marketo-engage-people-integration}

Marketo人员集成允许[!DNL Marketo Measure]开始从Marketo下载人员，开始将其跟踪的会话与个人绑定，并将接触点映射到其参与。 以前，[!DNL Marketo Measure]只能将接触点映射到CRM中的人员，因此这有助于营销人员更快地衡量其营销工作，而不是等待阶段或触发器将其同步到CRM。

## 要求 {#requirements}

* 生产Marketo实例
* 生产[!DNL Salesforce]或[!DNL Microsoft Dynamics]实例
* 任何付费的[!DNL Marketo Measure]订阅
* 已启用SOLR (联系[Marketo支持](https://nation.marketo.com/t5/Support/ct-p/Support){target="_blank"}以启用此功能)

## 工作原理 {#how-it-works}

作为当前客户，[!DNL Marketo Measure]已在从您的CRM下载人员。 标准流程是[!DNL Marketo Measure]下载人员并将电子邮件地址映射到我们通过bizible.js跟踪的Web会话。

随着下载Marketo人员的引入，[!DNL Marketo Measure]现在能够将Web会话映射到更大的个人池，即那些尚未与CRM同步的个人。 我们之所以经常看到这种情况，是因为内部流程需要等到用户达到特定状态之后才将其推送到CRM。

当[!DNL Marketo Measure]成功将Marketo人员映射到Web会话时，我们的处理将为其生成任何相关的接触点，这些接触点最终可在[!DNL Marketo Measure Discover]中报告。 如果该Marketo人员被推送到CRM，[!DNL Marketo Measure]将处理重复场景，我们将为CRM人员重新创建接触点，并将初始集标记为“重复”。

为了让我们检测这些重复项，请确保您的[!DNL Marketo-Salesforce]或[!DNL Marketo-Dynamics]同步已填充Marketo人员上的潜在客户和联系人ID。 如果ID正确同步，您应该能够在人员记录中看到CRM ID，如下所示：

![a](assets/5a.png)

![b](assets/5b.png)

客户可以选择报告[!DNL Marketo Measure] Discover中的整组Marketo人员和CRM人员。 如果您只想报告CRM用户，我们建议您创建一个区段来筛选他们。

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

在[!DNL Marketo Measure Discover]中报告潜在客户（人员）时，您将看到Marketo和CRM潜在客户的总数。 要仅报告Marketo人员或CRM潜在客户，您需要为源创建区段类别，然后使用“Source System”字段为Marketo和CRM创建区段规则以定义规则。 创建区段后，您将看到可在您的[!DNL Marketo Measure Discover]功能板中筛选的Source类别。

![Marketo Measure Discover仪表板显示Marketo与CRM潜在客户总数](assets/bizible-discover-1.png)

![发现突出显示Source系统区段的筛选器](assets/bizible-discover-2.png)

## 字段映射 {#field-mappings}

<table>
 <colgroup>
  <col>
  <col>
 </colgroup>
 <tbody>
  <tr>
   <th><p><strong>biz_leads</strong></p></th>
   <th><p><strong>Marketo</strong></p></th>
  </tr>
  <tr>
   <td><p>ID</p></td>
   <td><p>ID</p></td>
  </tr>
  <tr>
   <td><p>MODIFIED_DATE</p></td>
   <td><p>更新时间<strong></strong></p></td>
  </tr>
  <tr>
   <td><p>创建日期</p></td>
   <td><p>createdat</p></td>
  </tr>
  <tr>
   <td><p>电子邮件</p></td>
   <td><p>电子邮件</p></td>
  </tr>
  <tr>
   <td><p>WEB站点</p></td>
   <td><p>网站</p></td>
  </tr>
  <tr>
   <td><p>公司</p></td>
   <td><p>公司</p></td>
  </tr>
  <tr>
   <td><p>IS_CONVERTED</p></td>
   <td><p>不适用</p></td>
  </tr>
  <tr>
   <td><p>ACCOUNT_ID</p></td>
   <td><p>帐户Id (L2A)</p></td>
  </tr>
  <tr>
   <td><p>BIZIBLE_STAGE</p></td>
   <td><p>状态</p></td>
  </tr>
  <tr>
   <td><p>IS_DELETED</p></td>
   <td><p>true/false</p></td>
  </tr>
 </tbody>
</table>

*存在一个已知的行为问题，即Marketo公司实体中的字段不会影响人员的updatedAt值，因此，如果更新了Website或Company等相关字段，[!DNL Marketo Measure]将无法知晓这些值是否已修改，因为updatedAt日期/时间值未更新。 这会影响ABM功能，在这种情况下，我们将没有新数据来解析潜在客户。 目前没有解决方法，但计划将来解决此问题。

## 常见问题解答 {#faq}

**为什么我的CRM和[!DNL Marketo Measure Discover]的潜在客户计数不同？**

由于此集成允许我们为我们直接从Marketo导入的潜在客户创建接触点，因此可能存在未同步到CRM的潜在客户，因此Discover中的计数可能会高于CRM，因为仅针对CRM潜在客户推送接触点。

**这如何代替我的数据？**

此集成实际上会合并当前[!DNL Marketo Measure]实例中的数据集，因此不会替换任何内容。 我们希望从您当前的CRM潜在客户那里获得的是，当我们下载长达2年的Marketo潜在客户时，我们只需更新该潜在客户记录即可表明还有一个匹配项与Marketo潜在客户匹配。 所有这些都在后端发生，预计接触点将保持不变。 我们还希望因为符合条件的Marketo潜在客户而看到更多接触点。 如果能够找到与这些Marketo用户匹配的Web会话，我们将开始看到[!DNL Marketo Measure]中计数的接触点。

**我是否只能从Marketo下载人员并切断CRM连接？**

目前还没有。 我们以后将可以选择此选项，但我们需要构建此Marketo集成的其他阶段，以便我们可以将Marketo中的项目、机会和交易连接到[!DNL Marketo Measure]。

**是否导入我所有的Marketo人员？**

目前，我们最早导入人员的日期为2018年1月1日，因此我们至少拥有2年的数据，这与我们从CRM下载中强制执行的行为相同。 建立Marketo连接后，我们将改进下载滚动的2年期窗口的行为。

我们也不会过滤任何人员类型，因此两年内的所有人员都将获得导入，并符合接触点条件。

**什么是SOLR？为什么要启用它才能使用此功能？**

为您的Marketo实例启用SOLR是一个很简单的步骤，它将在Marketo中打开硬件空间，以便您的订阅可以利用[!DNL Marketo Measure]集成。 如果未启用SOLR，我们将无法访问某些调用，这些调用原本会允许我们从Marketo实例下载相应的人员。
