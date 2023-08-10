---
unique-page-id: 18874789
description: '"[!DNL Marketo Measure] 权限集 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] 权限集”'
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# [!DNL Marketo Measure] 权限集 {#marketo-measure-permission-sets}

了解如何访问和分配 [!DNL Marketo Measure] Salesforce中的权限集。

## [!DNL Marketo Measure] 权限集 {#marketo-measure-permission-sets-1}

中包含三个权限集 [!DNL Marketo Measure] Salesforce包。 这些权限集提供对 [!DNL Marketo Measure] 适用于管理员、营销人员和标准用户。

要在Salesforce中访问和分配权限集，请执行以下操作：

1. 单击 **[!UICONTROL Setup]**.
1. 在左边距中，单击 **[!UICONTROL Users]**，则 **[!UICONTROL Permission Sets]**.
1. 选择 [!DNL Marketo Measure] 您要分配的权限集。
1. 单击 **[!UICONTROL Manage Assignments]**，则 **[!UICONTROL Add Assignments]**.
1. 选择权限集的用户，然后单击 **[!UICONTROL Assign]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] 权限集解释 {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 管理员</strong></span></td> 
   <td><span>使SFDC管理员能够从中创建、读取、写入和删除记录 [!DNL Marketo Measure] 对象。 许可所依据的 [!DNL Marketo Measure] 将数据推送到SFDC时应启用此权限集。 此外，在以下情况下，建议此许可证能够编辑已转化的Lead：在Lead转化之前 [!DNL Marketo Measure] 将数据应用到记录。 这将确保Salesforce与之间的报告准确性 [!DNL Marketo Measure]. <a href="http://releasenotes.docs.salesforce.com/en-us/spring17/release-notes/rn_sales_leads_view_converted.htm">在此处了解更多信息</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 营销用户</strong></span></td> 
   <td><span>使营销用户能够从中读取和写入记录 [!DNL Marketo Measure] 对象。 营销团队的所有成员应 [!DNL Marketo Measure] 营销用户权限集已启用。 <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 标准用户</strong></span></td> 
   <td><span>使用户能够从以下位置读取记录 [!DNL Marketo Measure] 对象。</span></td> 
  </tr> 
 </tbody> 
</table>

入站销售开发团队和客户经理可能受益于 [!DNL Marketo Measure] 数据。 如果想要使用这些角色 [!DNL Marketo Measure] 报表中的数据，启用 [!DNL Marketo Measure] 标准用户权限集。

>[!NOTE]
>
>此外，我们连接的用户需要具有“营销用户” [!DNL Salesforce] 用户级别启用的用户档案，以便我们访问Campaign对象。 要检查此项，请单击 **[!UICONTROL Setup]** > **[!UICONTROL Manage Users]** > **[!UICONTROL Profiles]** > **[!UICONTROL Marketing User]** > **已分配用户**.
