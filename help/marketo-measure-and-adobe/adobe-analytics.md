---
description: '[!DNL Marketo Measure]与Adobe Analytics的集成 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]与 [!DNL Adobe Analytics]的集成'
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 0%

---


# [!DNL Marketo Measure]与Adobe Analytics的集成 {#marketo-measure-integrations-with-adobe-analytics}

B2B客户属性集成允许[!DNL Marketo Measure]和Adobe Analytics的共同用户使用从[!DNL Adobe Analytics]归因引擎派生的重要元数据扩充其[!DNL Marketo Measure]用户配置文件，并通过其与CRM （[!DNL Microsoft Dynamics]和[!DNL Salesforce]）的同步功能扩充其用户配置文件。 所有使用[!DNL Adobe Analytics]和[!DNL Marketo Measure]的客户都可以免费使用此功能。

>[!PREREQUISITES]
>您必须同时拥有[!DNL Marketo Measure]和[!DNL Adobe Analytics]的有效订阅。

## 配置集成 {#configuring-the-integration}

1. 在Experience Cloud控制台中创建新的客户属性数据Source 。 您可在此找到[的详细说明](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html)。

   注意后续步骤中所需的以下信息：

   * 别名ID，可以是您希望它成为的任何值。 我们建议使用“marketomeasure_id”

   * FTP服务器主机名和凭据（用户名和密码）

1. 创建客户属性数据Source后，导航到&#x200B;**[!UICONTROL Integrations]**&#x200B;管理员菜单中的&#x200B;**[!UICONTROL Connections]** > [!DNL Marketo Measure]屏幕以继续配置过程。

1. 单击&#x200B;**[!UICONTROL Set Up New Customer Attributes Connection]**&#x200B;按钮并按照说明配置客户属性集成。 UI会提示您输入在核心服务控制台中创建客户属性Source时获得的别名ID和FTP连接信息。 选择要同步到[!DNL Adobe Analytics]帐户的帐户属性集。

   输入您的Adobe IMS组织ID。 此ID显示在Adobe Experience Cloud Admin Console的右下角。 有关查找此ID的更多帮助，请咨询Adobe客户团队（您的客户经理）。

1. 在[!DNL Marketo Measure]帐户中创建完连接后，必须返回Experience Cloud控制台以[验证架构](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/validate-schema.html?lang=en)。 您无需担心FTP文件上传，[!DNL Marketo Measure]已为您自动完成该部分。 转到您在步骤1中创建的客户属性Source的“查看/编辑”架构屏幕，并告知Adobe [!DNL Marketo Measure]代表您上传的每个属性的数据类型。 如果需要，您还可以为上传的属性创建新的显示友好型名称。

   如果您选择从CRM帐户对象同步属性，强烈建议您为这些属性选择新的显示名称，因为[!DNL Marketo Measure]只会填充这些属性的API级别名称，这些名称通常对报表不友好。

1. 最后一步是为要在中使用属性的Experience Cloud应用程序配置属性订阅。 您可以为[!DNL Adobe Analytics]或[!DNL Adobe Target]配置订阅。  有关如何执行[的详细信息，请参阅此处](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/subscription.html)。

## 属性描述 {#attribute-descriptions}

创建B2B客户属性连接时，[!DNL Marketo Measure]会自动为您创建一组标准的B2B客户属性。 下表介绍了这些属性。

除了下面列出的属性之外，您还可以在CRM中上传附加到帐户对象的任何属性。 如果多个帐户与给定用户绑定，[!DNL Marketo Measure]会以分号分隔的列表填充所有匹配的帐户属性值。

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
   <td>与给定Web访客关联的帐户名称。 如果多个帐户与给定用户绑定，[!DNL Marketo Measure]会以分号分隔的列表填充所有匹配的帐户名称。<br/>
   <strong>注意：</strong> account.name是account对象上name属性的Salesforce-API级别名称。 您可以在集成配置的架构验证步骤（步骤4）中为此属性选择更好的显示名称（例如，“公司”）。</td>
  </tr>
  <tr>
   <td>已归因收入 — “模型”</td>
   <td>此客户因与CRM中成功的商机的关联而获得的收入，由[!DNL Marketo Measure]归因引擎计算。<br/>
   您的[!DNL Marketo Measure]订阅允许的每个归因模型都有一个属性（例如，“归因收入 — 完整路径”）。</td>
  </tr>
  <tr>
   <td>最深入的Funnel阶段</td>
   <td>与给定用户关联的任何开放机会的最深funnel阶段。</td>
  </tr>
  <tr>
   <td>打开机会</td>
   <td>根据您的CRM数据，以分号分隔的给定用户绑定的机会ID列表。</td>
  </tr>
 </tbody>
</table>

**有关属性限制的注释**

通过此集成呈现的属性将计入您在[!DNL Adobe Analytics]和[!DNL Adobe Target]中的合同属性限制。 只有通过属性订阅（[配置集成](#configuring-the-integration)中的步骤5）显示的属性才算您对订阅应用程序的限制。

## 常见问题解答 {#faqs}

**如何通过此集成更改要共享的属性集？**

为了使[!DNL Marketo Measure]通过此集成共享到Adobe IMS组织的属性在[!DNL Adobe Analytics]中可见和使用，必须通过核心服务控制台中配置的属性订阅显示该属性。 因此，如果要删除某个属性以便该属性不再出现在[!DNL Adobe Analytics]中，只需删除该属性订阅即可。

您还可以删除[!DNL Marketo Measure]中的B2B客户属性连接，然后使用您不希望再从连接配置中共享的属性重新创建该连接。 同样，要将属性添加到集成，必须删除现有连接并使用添加到配置的所需属性创建新连接。

鉴于上述情况，强烈建议在首次配置属性连接时，在选择属性时尽可能具有包容性。

**此集成有哪些示例用例？**

1. 基于帐户的流量量度：使用“帐户名称”属性，您可以在Adobe Analytics中创建一个或多个目标帐户的区段，并仅分析源自目标帐户的部分流量的网站流量量度。
1. Content Analytics：使用收入量度分析哪些网站内容对最终购买您的产品或服务的客户或那些达到感兴趣的特定funnel阶段的客户最有吸引力。
1. 现场交易支持：通过分析与CRM中特定开放机会关联的用户的网站行为，用可操作的insight武装您的销售团队。
