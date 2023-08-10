---
description: '"[!DNL Marketo Measure] 与Adobe Analytics的集成 —  [!DNL Marketo Measure]  — 产品文档”'
title: "[!DNL Marketo Measure] 与集成 [!DNL Adobe Analytics]"
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 0%

---

# [!DNL Marketo Measure] 与Adobe Analytics的集成 {#marketo-measure-integrations-with-adobe-analytics}

B2B客户属性集成使共同用户能够 [!DNL Marketo Measure] 和Adobe Analytics让他们 [!DNL Adobe Analytics] 包含宝贵元数据的用户配置文件，派生自 [!DNL Marketo Measure] 归因引擎及其与CRM的同步功能([!DNL Microsoft Dynamics] 和 [!DNL Salesforce])。 所有使用的客户都可以免费使用 [!DNL Adobe Analytics] 和 [!DNL Marketo Measure].

>[!PREREQUISITES]
>
>您必须同时拥有两个活动的订阅 [!DNL Marketo Measure] 和 [!DNL Adobe Analytics].

## 配置集成 {#configuring-the-integration}

1. 首先，在Experience Cloud控制台中创建一个新的客户属性数据源。 详细说明 [可在此处找到](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

   请注意以下信息，因为在此过程中的某些后续步骤中您将需要这些信息：

   * 别名ID，可以是您希望它成为的任何值。 我们建议使用“marketomeasure_id”

   * FTP服务器主机名和凭据（用户名和密码）

1. 创建客户属性数据源后，导航到 **[!UICONTROL Integrations]** > **[!UICONTROL Connections]** 中的屏幕 [!DNL Marketo Measure] 管理员菜单。

1. 单击 **[!UICONTROL Set Up New Customer Attributes Connection]** 按钮并按照说明配置客户属性集成。 UI将提示您输入在核心服务控制台中创建客户属性源时获得的别名ID和FTP连接信息，并提示您选择要同步到的一组帐户属性 [!DNL Adobe Analytics] 帐户。

   您还需要输入您的Adobe IMS组织ID。 此ID显示在Adobe Experience CloudAdmin Console的右下角。 有关查找此ID的更多帮助，请咨询Adobe客户团队（您的客户经理）。

1. 完成创建连接后，请在 [!DNL Marketo Measure] 帐户，您需要返回Experience Cloud控制台以便 [验证架构](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/validate-schema.html). 您无需担心FTP文件上传， [!DNL Marketo Measure] 已为您自动执行该部件。 您只需转到在步骤1中创建的客户属性来源的“查看/编辑”架构屏幕，告诉Adobe每个属性的数据类型是什么， [!DNL Marketo Measure] 已代表您上传。 如果需要，您还可以为上传的属性创建新的显示友好型名称。

   如果您选择从CRM帐户对象同步属性，强烈建议您为这些对象选择新的显示名称，如 [!DNL Marketo Measure] 将仅填充这些属性的API级别名称，这些名称通常对报表不友好。

1. 最后一步是为要在其中使用属性的Experience Cloud应用程序配置属性预订。  您可以配置订阅 [!DNL Adobe Analytics] 或 [!DNL Adobe Target].  有关如何执行此操作的更多信息 [可在此处找到](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html).

## 属性描述 {#attribute-descriptions}

当您创建新的B2B客户属性连接时， [!DNL Marketo Measure] 将自动为您创建一组标准的B2B客户属性。 下表介绍了这些属性。

除了下面列出的属性之外，您还可以在CRM中上传附加到帐户对象的任何属性。 如果多个帐户与给定用户关联， [!DNL Marketo Measure] 将以分号分隔的列表填充所有匹配的帐户属性值。

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><b>属性名称</b></td> 
   <td><b>描述</b></td>
  </tr> 
  <tr> 
   <td>Account.Name</td> 
   <td>与给定Web访客关联的帐户名称。 如果多个帐户与给定用户关联， [!DNL Marketo Measure] 将以分号分隔的列表填充所有匹配的帐户名称。<br/>
   <strong>注意：</strong> account.name是account对象上name属性的Salesforce-API级别名称。 您可以在集成配置的架构验证步骤（步骤4）中，为此属性选择更好的显示名称（例如“公司”）。</td>
  </tr>
  <tr> 
   <td>已归因收入 — “模型”</td> 
   <td>根据客户与您CRM中成功交易机会的关联而归属于此客户的收入，计算公式为 [!DNL Marketo Measure] 归因引擎。<br/>
   对于您拥有的每个归因模型，都将有一个属性 [!DNL Marketo Measure] 订阅允许（例如，“归因收入 — 完整路径”）。</td>
  </tr>
  <tr> 
   <td>最深漏斗阶段</td> 
   <td>与给定用户关联的任何打开机会的最深漏斗阶段。</td>
  </tr>
  <tr> 
   <td>打开机会</td> 
   <td>根据您的CRM数据，以分号分隔的给定用户绑定的机会ID列表。</td>
  </tr> 
 </tbody> 
</table>

**有关属性限制的注释**

请注意，通过此集成显现的属性仍将计入中的合同属性限制 [!DNL Adobe Analytics] 和 [!DNL Adobe Target]. 仅限通过属性订阅显示的属性（中的步骤5） [配置集成](#configuring-the-integration))将计入您对订阅应用程序的限制中。

## 常见问题解答 {#faqs}

**如何通过此集成更改要共享的属性集？**

为了共享的属性 [!DNL Marketo Measure] 添加到您的Adobe IMS组织，以便在以下位置显示和使用 [!DNL Adobe Analytics]，它需要通过核心服务控制台中配置的属性订阅显示。 因此，如果要删除某个属性，使其不再显示于 [!DNL Adobe Analytics]，您只需删除属性订阅即可实现此目的。

您还可以删除中的B2B客户属性连接 [!DNL Marketo Measure] ，并使用您不希望再共享的连接配置中排除的属性重新创建连接。 同样，要将属性添加到集成，您需要删除现有连接，并使用添加到配置的所需属性创建新连接。

鉴于上述情况，强烈建议在首次配置属性连接时，在选择属性时尽可能具有包容性。

**此集成有哪些示例用例？**

1. 基于帐户的流量量度：使用“帐户名称”属性，您可以在Adobe Analytics中创建一个或多个目标帐户的区段，并仅分析源自目标帐户的部分流量的网站流量量度。
1. 内容分析：使用收入量度分析哪些网站内容对最终购买您的产品或服务的客户或那些达到感兴趣的特定漏斗阶段的客户最有吸引力。
1. 现场交易支持：通过分析与CRM中特定开放机会关联的用户的网站行为，为销售团队提供可操作的洞察信息。
