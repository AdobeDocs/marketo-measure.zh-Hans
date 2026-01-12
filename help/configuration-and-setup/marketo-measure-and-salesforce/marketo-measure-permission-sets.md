---
description: '[!DNL Marketo Measure]权限集 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]权限集'
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---


# [!DNL Marketo Measure]权限集 {#marketo-measure-permission-sets}

了解如何在Salesforce中访问和分配[!DNL Marketo Measure]权限集。

## [!DNL Marketo Measure]权限集 {#marketo-measure-permission-sets-1}

[!DNL Marketo Measure] Salesforce包中包含三个权限集。 这些权限集为管理员、营销人员和标准用户提供了对[!DNL Marketo Measure]的访问权限。

要在Salesforce中访问和分配权限集，请执行以下操作：

1. 单击 **[!UICONTROL Setup]**。
1. 单击左边距中的&#x200B;**[!UICONTROL Users]**，然后单击&#x200B;**[!UICONTROL Permission Sets]**。
1. 选择要分配的[!DNL Marketo Measure]权限集。
1. 单击&#x200B;**[!UICONTROL Manage Assignments]**，然后单击&#x200B;**[!UICONTROL Add Assignments]**。
1. 选择权限集的用户并单击&#x200B;**[!UICONTROL Assign]**。

   ![&#x200B; 5](assets/1-5.png)

## 解释[!DNL Marketo Measure]权限集 {#marketo-measure-permission-sets-explained}

<table>
 <tbody>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] 管理员</strong></span></td>
   <td><span>使SFDC管理员能够从[!DNL Marketo Measure]对象创建、读取、写入和删除记录。 [!DNL Marketo Measure]将数据推送到SFDC所用的许可证应启用此权限集。 此外，建议此许可证能够在以下情况下编辑转化的Lead：在[!DNL Marketo Measure]将数据应用于记录之前Lead已转化。 这可确保Salesforce和[!DNL Marketo Measure]之间报表的准确性。 <a href="https://help.salesforce.com/articleView?id=release-notes.rn_sales_leads_view_converted.htm&type=5&release=206&language=en_us">在此阅读更多</a>。</span></td>
  </tr>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] 营销用户</strong></span></td>
   <td><span>使营销用户能够从[!DNL Marketo Measure]对象中读取和写入记录。 营销团队的所有成员都应启用[!DNL Marketo Measure]营销用户权限集。 <br></span></td>
  </tr>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] 标准用户</strong></span></td>
   <td><span>允许用户从[!DNL Marketo Measure]对象中读取记录。</span></td>
  </tr>
 </tbody>
</table>

入站销售开发团队和客户执行官可以从[!DNL Marketo Measure]数据中受益。 如果这些角色希望在报告中使用[!DNL Marketo Measure]数据，请启用[!DNL Marketo Measure]标准用户权限集。

>[!NOTE]
>此外，我们通过连接的用户必须在用户级别启用“营销用户”[!DNL Salesforce]配置文件，以便我们访问Campaign对象。 要检查此项，请单击&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Manage Users]** > **[!UICONTROL Profiles]** > **[!UICONTROL Marketing User]** > **已分配用户**。
