---
unique-page-id: 18874763
description: '"[!DNL Microsoft Dynamics] CRM安装指南 — Marketo Measure — 产品文档”'
title: '"[!DNL Microsoft Dynamics] CRM安装指南”'
exl-id: bc422c98-60bb-49ea-9bd1-c4149ae628b1
feature: Installation, Microsoft Dynamics
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics] CRM安装指南 {#microsoft-dynamics-crm-installation-guide}

>[!NOTE]
>
>您可能会看到说明“[!DNL Marketo Measure]”，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

## 支持的版本 {#supported-versions}

[!DNL Marketo Measure] 支持以下内容 [!DNL Microsoft Dynamics CRM] 版本：

* [!DNL Microsoft Dynamics 2016] （在线和内部部署）
* [!DNL Microsoft Dynamics 365] （在线和内部部署）

对于连接和身份验证， [!DNL Marketo Measure] 支持以下Active Directory Federated Services (ADFS)版本：

* ADFS 4.0 - [!DNL Windows Server 2016]
* ADFS 5.0 - [!DNL Windows Server 2019]

## 安装托管解决方案 {#install-the-managed-solution}

[下载并安装](assets/marketo-measure-dynamics-extension.zip) Dynamics CRM中的zip文件。

**[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Solutions]** > **[!UICONTROL Import]** （按钮） > **[!UICONTROL Choose File]**.

![](assets/1.png)

>[!NOTE]
>
>以下两个屏幕截图可能与您的屏幕截图略有不同，因为它们在解决方案升级过程中拍摄。

![](assets/2.png)

![](assets/3.png)

## 创建 [!DNL Marketo Measure] 用户 {#creating-a-marketo-measure-user}

我们建议在Dynamics中创建专门的Marketo Measure用户作为“应用程序用户”，以便我们通过来导出和导入数据，从而避免您的CRM中的其他用户出现任何问题。 记下用户名和密码以及端点URL，因为它们在创建 [!DNL Marketo Measure] 帐户。

## 安全角色 {#security-roles}

如果您的组织使用Dynamics安全角色，请确保已连接的用户或专用的 [!DNL Marketo Measure] 用户对所需实体具有足够的读/写权限。

安全角色位于此处： **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Security Roles]**.

对象 [!DNL Marketo Measure] 自定义实体，我们将需要所有实体的完全权限。

>[!NOTE]
>
>要关闭商机的用户还需要具有全部权限。

![](assets/4.png)

对于Dynamics标准实体，请参阅 [!DNL Marketo Measure] Dynamics架构文档。 从高层次上说， [!DNL Marketo Measure] 只需读取某些实体即可收集相应的数据并写入将随托管解决方案一起安装的自定义字段。 我们不会创建新的标准记录，也不会更新任何标准字段。

## 在页面布局中包含接触点： {#include-touchpoints-on-page-layouts}

1. 对于每个实体，导航到表单编辑器。 您可以在下找到此内容 **[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Customize the System]** > `[Entity]` > **[!UICONTROL Forms]**. 或者，您可以在查看记录时通过设置找到它。

   * 要配置的实体：Account、Opportunity、Contact、Lead和Campaign。

   * 要配置营销活动，您需要打开中的“营销活动同步”选项 **[!UICONTROL CRM]** > **[!UICONTROL Campaigns]**.

   ![](assets/5.png)

1. 页面布局：首先添加&#39;&#39;[!UICONTROL One Column]”图块位于您希望接触点活动的部分中。 在该新列中，我们将需要在您的Account 、 Opportunity 、 Contact和Lead实体中的每一张表单中添加一个子网格。

   ![](assets/6.png)

   ![](assets/7.png)

1. 选择应在子网格中呈现的对象（买方归因接触点或买方接触点），具体取决于对象关系。 （可选）通过单击“编辑”按钮更改显示的列。 托管解决方案已设置默认布局。

   买方归因接触点子网格 — 客户、商机和联系人\
   买方接触点子网格 — 潜在客户和联系人

   ![](assets/8.png)

1. 完成表单更新后，发布并保存更改。

## 与架构相关的注意事项 {#schema-related-considerations}

**收入**

[!DNL Marketo Measure] 默认指向标准实际收入字段。 如果您没有使用此功能，请说明您如何作为自定义工作流向解决方案工程师或成功经理报告收入。

**关闭日期**

[!DNL Marketo Measure] 指向现成的“实际关闭日期”字段。 如果您没有使用此字段，也没有使用预计关闭日期字段，请向解决方案工程师或成功经理说明您的流程。 可能需要使用自定义工作流来考虑这两个字段。

## 配置连接和数据提供程序 {#configuring-your-connections-and-data-providers}

在您登录 [!DNL Marketo Measure] 应用程序并且已在Adobe Admin Console中设置为用户，下一步是设置各种数据连接。

**CRM作为数据提供程序**

1. 在您的 [!DNL Marketo Measure] 帐户，请单击 **[!UICONTROL My Account]** 下拉并选择 **[!UICONTROL Settings]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-16.png)

1. 下 [!UICONTROL Integrations] 在左侧导航栏中，单击 **[!UICONTROL Connections]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-17.png)

1. 单击 **[!UICONTROL Set Up New CRM Connection]** 按钮。

   ![](assets/microsoft-dynamics-crm-installation-guide-18.png)

1. 旁边 [!UICONTROL Microsoft Dynamics CRM]，单击 **[!UICONTROL Connect]** 按钮。

   ![](assets/microsoft-dynamics-crm-installation-guide-19.png)

1. 选择 [!UICONTROL Credentials] 或 [!UICONTROL OAuth].

   ![](assets/microsoft-dynamics-crm-installation-guide-20.png)

   >[!NOTE]
   >
   >有关OAuth的详细信息，请访问 [本文](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md). 如果您对流程有任何疑问，请联系贵机构的 [!DNL Marketo Measure] 客户代表。

1. 在本例中，我们选择了“凭据”。 输入您的凭据，然后单击 **[!UICONTROL Next]**.

连接后，您将在CRM/MAP连接列表中看到您的Dynamics连接的详细信息。

**Ad帐户连接**

要将您的广告帐户与 [!DNL Marketo Measure]，首先访问 [!UICONTROL Connections] 选项卡 [!DNL Marketo Measure] 应用程序。

1. 按照上面的步骤1和2 _CRM作为数据提供程序_ 部分。

1. 单击 **[!UICONTROL Set up New CRM Connection]** 按钮。

   ![](assets/microsoft-dynamics-crm-installation-guide-21.png)

1. 选择所需的平台。

   ![](assets/microsoft-dynamics-crm-installation-guide-22.png)

**[!DNL Marketo Measure]Javascript**

为了 [!DNL Marketo Measure] 要跟踪Web活动，需要执行多个设置步骤。

1. 单击 **[!UICONTROL My Account]** 下拉并选择 **[!UICONTROL Account Configuration]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-23.png)

1. 输入您的电话号码。 对于网站，输入将用于的主根域 [!DNL Marketo Measure] 对您的网站进行跟踪。 单击 **[!UICONTROL Save]** 完成时。

   ![](assets/microsoft-dynamics-crm-installation-guide-24.png)

   >[!NOTE]
   >
   >要添加多个根域，请联系 [!DNL Marketo Measure] 客户代表。

1. 此 [[!DNL Marketo Measure] JavaScript](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md) 然后需要放置在整个网站和登陆页面中。 我们建议在登陆页面的标题中对脚本进行硬编码，或通过Tag Management系统添加，例如 [Google Tag Manager](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md).

   >[!NOTE]
   >
   >默认情况下， [!DNL Marketo Measure] 每次在作业向CRM发送数据时，将每个API点数导出200条记录。 对于大多数客户而言，这提供了所消耗的API积分之间的最佳平衡。 [!DNL Marketo Measure] 和CRM上的CPU资源要求。 但是，对于具有复杂CRM配置（如工作流和触发器）的客户，较小的批处理大小可能有助于提高CRM性能。 为此， [!DNL Marketo Measure] 允许客户配置CRM导出批次大小。 此设置位于“ ”中的“设置”>“CRM”>“常规”页面 [!DNL Marketo Measure] Web应用程序和客户可以选择批量为200（默认）、100、50或25。
   >
   >在修改此设置时，请记住，较小的批次将消耗您的CRM中的更多API积分。 仅当您在CRM中遇到CPU超时或CPU负载过高时，才建议减小批次大小。

   >[!NOTE]
   >
   >当您禁用Marketo Measure将数据导出到Dynamics时，它不会删除任何现有数据。 有关删除现有数据的帮助，请与Dynamics支持部门联系。

   >[!MORELIKETHIS]
   >
   >[错误通知](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
