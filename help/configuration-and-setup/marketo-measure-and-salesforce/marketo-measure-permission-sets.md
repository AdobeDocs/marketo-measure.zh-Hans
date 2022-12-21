---
unique-page-id: 18874789
description: '"[!DNL Marketo Measure] 权限集 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] 权限集”'
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# [!DNL Marketo Measure] 权限集 {#marketo-measure-permission-sets}

了解如何访问和分配 [!DNL Marketo Measure] 权限集。

## [!DNL Marketo Measure] 权限集 {#marketo-measure-permission-sets-1}

包含三个权限集 [!DNL Marketo Measure] Salesforce包。 这些权限集提供对 [!DNL Marketo Measure] 适用于管理员、营销人员和标准用户。

要在Salesforce中访问和分配权限集，请执行以下操作：

1. 单击 **[!UICONTROL Setup]**.
1. 在左边距中，单击 **[!UICONTROL Users]**，则 **[!UICONTROL Permission Sets]**.
1. 选择 [!DNL Marketo Measure] 权限集。
1. 单击 **[!UICONTROL Manage Assignments]**，则 **[!UICONTROL Add Assignments]**.
1. 选择权限集的用户并单击 **[!UICONTROL Assign]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] 说明权限集 {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 管理员</strong></span></td> 
   <td><span>使SFDC管理员能够从中创建、读取、写入和删除记录 [!DNL Marketo Measure] 对象。 根据 [!DNL Marketo Measure] 将数据推送到SFDC时应启用此权限集。 此外，建议此许可证能够在潜在客户在之前转换的情况下编辑已转换的潜在客户 [!DNL Marketo Measure] 将数据应用到记录。 这将确保在Salesforce和 [!DNL Marketo Measure]. <a href="http://releasenotes.docs.salesforce.com/en-us/spring17/release-notes/rn_sales_leads_view_converted.htm">有关更多信息，请参阅此处</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 营销用户</strong></span></td> 
   <td><span>使营销用户能够从 [!DNL Marketo Measure] 对象。 营销团队的所有成员都应具有 [!DNL Marketo Measure] 已启用营销用户权限集。 <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 标准用户</strong></span></td> 
   <td><span>允许用户从中读取记录 [!DNL Marketo Measure] 对象。</span></td> 
  </tr> 
 </tbody> 
</table>

入站销售开发团队和客户经理可能会从 [!DNL Marketo Measure] 数据。 如果这些角色希望使用 [!DNL Marketo Measure] 报表中的数据，启用 [!DNL Marketo Measure] 标准用户权限集。

>[!NOTE]
>
>此外，我们通过需要拥有“营销用户”来连接用户 [!DNL Salesforce] 在用户级别启用的用户档案，以便我们访问Campaign对象。 要检查此信息，请单击 **[!UICONTROL Setup]** > **[!UICONTROL Manage Users]** > **[!UICONTROL Profiles]** > **[!UICONTROL Marketing User]** > **分配的用户**.
