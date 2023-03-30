---
description: '"[!DNL Marketo Measure] 与Adobe Analytics集成 —  [!DNL Marketo Measure]  — 产品文档”'
title: "[!DNL Marketo Measure] 集成 [!DNL Adobe Analytics]"
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
source-git-commit: 51397a02872035fef41d308c1f855bcaecc29c4e
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 0%

---

# [!DNL Marketo Measure] 与Adobe Analytics集成 {#marketo-measure-integrations-with-adobe-analytics}

B2B客户属性集成使 [!DNL Marketo Measure] 和Adobe Analytics [!DNL Adobe Analytics] 具有从派生的有价值元数据的用户配置文件 [!DNL Marketo Measure] 归因引擎，并通过其与CRM的同步功能([!DNL Microsoft Dynamics] 和 [!DNL Salesforce])。 它可供使用 [!DNL Adobe Analytics] 和 [!DNL Marketo Measure].

>[!PREREQUISITES]
>
>您必须同时拥有两个活动订阅 [!DNL Marketo Measure] 和 [!DNL Adobe Analytics].

## 配置集成 {#configuring-the-integration}

1. 首先，在Experience Cloud控制台中创建新的客户属性数据源。 详细说明 [可在此处找到](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

   请注意以下信息，因为在此过程的后续步骤中，您将需要此信息：

   * 别名ID，可以是您希望它成为的任何值。 我们建议使用“marketomeasure_id”

   * FTP服务器主机名和凭据（用户名和密码）

1. 创建客户属性数据源后，通过导航到 **[!UICONTROL Integrations]** > **[!UICONTROL Connections]** 屏幕 [!DNL Marketo Measure] 管理菜单。

1. 单击 **[!UICONTROL Set Up New Customer Attributes Connection]** 按钮，并按照配置客户属性集成的说明进行操作。 UI将提示您输入在核心服务控制台中创建客户属性来源时获取的别名ID和FTP连接信息，以及选择要同步到的帐户属性集 [!DNL Adobe Analytics] 帐户。

   您还需要输入Adobe IMS组织ID。 此ID显示在Adobe Experience CloudAdmin Console的右下角。 如需有关查找此ID的更多帮助，请咨询Adobe客户团队（您的客户经理）。

1. 完成在 [!DNL Marketo Measure] 帐户，您需要返回Experience Cloud控制台才能 [验证架构](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/validate-schema.html). 您无需担心FTP文件上传， [!DNL Marketo Measure] 已经为您自动完成了该部件。 您只需转到步骤1中创建的客户属性来源的“查看/编辑”架构屏幕，并告诉Adobe每个属性的数据类型 [!DNL Marketo Measure] 已代表您上传。 如果需要，您还可以为上传的属性创建新的显示友好型名称。

   如果您选择从CRM帐户对象同步属性，强烈建议您为它们选择新的显示名称，如 [!DNL Marketo Measure] 将仅填充这些属性的API级别名称，这些名称通常对报表不友好。

1. 最后一步是为要在中使用属性的Experience Cloud应用程序配置属性订阅。  您可以为配置订阅 [!DNL Adobe Analytics] 或 [!DNL Adobe Target].  有关如何执行此操作的更多信息 [可在此处找到](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html).

## 属性描述 {#attribute-descriptions}

创建新的B2B客户属性连接时， [!DNL Marketo Measure] 将自动为您创建一组标准的B2B客户属性。 下表介绍了这些属性。

除了下面列出的属性之外，您还可以上传附加到CRM中帐户对象的任何属性。 如果多个帐户与给定用户绑定， [!DNL Marketo Measure] 将以分号分隔的列表填充所有匹配的帐户属性值。

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
   <td>与给定Web访客关联的帐户名称。 如果多个帐户与给定用户绑定， [!DNL Marketo Measure] 将以分号分隔的列表填充所有匹配的帐户名称。<br/>
   <strong>注意：</strong> account.name是帐户对象上名称属性的Salesforce-API级别名称。 在集成配置的架构验证步骤（步骤4）中，您可以为此属性选择更好的显示名称（例如，“公司”）。</td>
  </tr>
  <tr> 
   <td>归因收入 — 模型›</td> 
   <td>此客户因与CRM中的闭门销售机会关联而获得的收入(如 [!DNL Marketo Measure] 归因引擎。<br/>
   对于您的 [!DNL Marketo Measure] 订阅允许（例如“归因收入 — 完整路径”）。</td>
  </tr>
  <tr> 
   <td>最深的漏斗阶段</td> 
   <td>与给定用户关联的所有打开机会的最深漏斗阶段。</td>
  </tr>
  <tr> 
   <td>Open Opportunity</td> 
   <td>以分号分隔的机会ID列表，给定用户将根据您的CRM数据绑定到这些机会ID。</td>
  </tr> 
 </tbody> 
</table>

**关于属性限制的说明**

请注意，通过此集成显示的属性仍将根据 [!DNL Adobe Analytics] 和 [!DNL Adobe Target]. 仅通过属性订阅显示的属性( [配置集成](#configuring-the-integration))将计入您对订阅应用程序的限制。

## 常见问题解答 {#faqs}

**如何更改要通过此集成共享的属性集？**

对于共享的属性 [!DNL Marketo Measure] 可通过此集成访问您的Adobe IMS组织，以便在 [!DNL Adobe Analytics]，则需要通过在核心服务控制台中配置的属性订阅来显示该属性。 因此，如果要删除某个属性，使其不再显示在 [!DNL Adobe Analytics]，则只需删除属性订阅即可实现此目的。

您还可以删除 [!DNL Marketo Measure] ，然后使用您不希望再共享的从连接配置中排除的属性重新创建该属性。 同样，要向集成添加属性，您需要删除现有连接，并创建一个新连接，并将所需属性添加到配置中。

鉴于上述情况，强烈建议在首次配置属性连接时，在选择属性时尽可能做到包含在内。

**此集成有哪些示例用例？**

1. 基于帐户的流量量度：使用帐户名称属性，您可以在Adobe Analytics中创建一个或多个目标帐户的区段，并分析网站流量量度，以获取源自目标帐户的流量子集。
1. 内容分析：使用收入量度可分析哪些网站内容最吸引最终购买您的产品或服务的客户，或那些达到特定漏斗阶段的客户。
1. 实时交易支持：通过为与CRM中的特定打开机会关联的用户分析网站行为，为您的销售团队提供可操作的洞察信息。
