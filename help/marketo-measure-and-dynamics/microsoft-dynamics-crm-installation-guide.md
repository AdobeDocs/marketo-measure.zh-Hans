---
description: '[!DNL Microsoft Dynamics] CRM安装指南'
title: '[!DNL Microsoft Dynamics] CRM安装指南'
exl-id: bc422c98-60bb-49ea-9bd1-c4149ae628b1
feature: Installation, Microsoft Dynamics
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 0%

---


# [!DNL Microsoft Dynamics] CRM安装指南 {#microsoft-dynamics-crm-installation-guide}

>[!NOTE]
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

## 支持的版本 {#supported-versions}

[!DNL Marketo Measure]支持以下[!DNL Microsoft Dynamics CRM]版本：

* [!DNL Microsoft Dynamics 2016] （在线和内部部署）
* [!DNL Microsoft Dynamics 365] （在线和内部部署）

对于连接和身份验证，[!DNL Marketo Measure]支持以下Active Directory联合服务(ADFS)版本：

* ADFS 4.0 - [!DNL Windows Server 2016]
* ADFS 5.0 - [!DNL Windows Server 2019]

## 安装托管解决方案 {#install-the-managed-solution}

[下载并安装](assets/marketo-measure-dynamics-extension.zip) Dynamics CRM中的zip文件。

**[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Solutions]** > **[!UICONTROL Import]** （按钮） > **[!UICONTROL Choose File]**。

使用“导入”按钮![Dynamics CRM解决方案导入屏幕](assets/1.png)

>[!NOTE]
>以下两个屏幕截图可能与您的屏幕截图略有不同，因为它们在解决方案升级过程中拍摄。

![显示包选择的解决方案导入向导](assets/2.png)

![解决方案导入确认屏幕](assets/3.png)

## 创建[!DNL Marketo Measure]用户 {#creating-a-marketo-measure-user}

建议在Dynamics中创建专用的Marketo Measure用户作为“应用程序用户”，以通过导出和导入数据，从而避免CRM中的其他用户出现任何问题。 记下创建[!DNL Marketo Measure]帐户时使用的用户名和密码以及端点URL。

## 安全角色 {#security-roles}

如果您的组织使用Dynamics安全角色，请确保连接的用户或专用[!DNL Marketo Measure]用户具有所需实体的足够读/写权限。

安全角色位于此处： **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Security Roles]**。

对于[!DNL Marketo Measure]自定义实体，我们需要所有实体的完全权限。

除了标准实体的读/写权限之外，还需要Campaign“创建”权限。

>[!NOTE]
>关闭商机的用户还需要完全权限。

![Dynamics安全角色配置屏幕显示权限](assets/4.png)

对于Dynamics标准实体，请参阅[!DNL Marketo Measure] Dynamics架构文档。 从较高层面来看，[!DNL Marketo Measure]读取某些实体以收集适当的数据并写入随托管解决方案一起安装的自定义字段。 不会创建标准记录，也不会更新标准字段。

## 在页面布局中包含接触点： {#include-touchpoints-on-page-layouts}

1. 对于每个实体，导航到表单编辑器。 您可以在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Customize the System]** > `[Entity]` > **[!UICONTROL Forms]**&#x200B;下找到此项。 或者，您可以在查看记录时通过设置找到它。

   * 要配置的实体：Account、Opportunity、Contact、Lead和Campaign。

   * 要配置营销活动，必须在&#x200B;**[!UICONTROL CRM]** > **[!UICONTROL Campaigns]**&#x200B;中打开“营销活动同步”选项。

   在Marketo Measure设置中切换![Campaign同步](assets/5.png)

1. 页面布局：首先在希望接触点存在的部分中添加一个“[!UICONTROL One Column]”拼贴。 在该新列中，我们需要向您的Account 、 Opportunity 、 Contact和Lead实体中的每个表单添加一个子网格。

   ![表单编辑器显示一个列分区布局](assets/6.png)

   正在将子网格组件![添加到表单布局](assets/7.png)

1. 选择应在子网格中呈现的对象（买方归因接触点或买方接触点），具体取决于对象关系。 （可选）通过单击编辑按钮更改显示的列。 默认布局由托管解决方案设置。

   Buyer Attribution Touchpoint子网格 — 客户、商机和联系人
Buyer Touchpoint子网格 — 潜在客户和联系人

   ![显示对象选择选项的“子网格属性”对话框](assets/8.png)

1. 完成表单更新后，发布并保存更改。

## 与架构相关的注意事项 {#schema-related-considerations}

**收入**

默认情况下，[!DNL Marketo Measure]指向标准“实际收入”字段。 如果您没有使用此功能，请说明您如何作为自定义工作流向解决方案工程师或成功经理报告收入。

**关闭日期**

[!DNL Marketo Measure]指向现成的“实际关闭日期”字段。 如果您没有使用此字段，也没有使用预计关闭日期字段，请向解决方案工程师或成功经理说明您的流程。 可能需要自定义工作流来考虑这两个字段。

## 配置连接和数据提供程序 {#configuring-your-connections-and-data-providers}

登录[!DNL Marketo Measure]应用程序并在Adobe Admin Console中设置为用户后，下一步是设置各种数据连接。

**CRM作为数据提供程序**

1. 在您的[!DNL Marketo Measure]帐户中，单击&#x200B;**[!UICONTROL My Account]**&#x200B;下拉菜单并选择&#x200B;**[!UICONTROL Settings]**。

   ![Marketo Measure“我的帐户”下拉菜单的“设置”选项突出显示](assets/microsoft-dynamics-crm-installation-guide-16.png)

1. 在左侧导航栏中的[!UICONTROL Integrations]下，单击&#x200B;**[!UICONTROL Connections]**。

   在左侧导航中使用“连接”选项的![设置页面](assets/microsoft-dynamics-crm-installation-guide-17.png)

1. 单击&#x200B;**[!UICONTROL Set Up New CRM Connection]**&#x200B;按钮。

   ![设置新CRM连接按钮的连接页面](assets/microsoft-dynamics-crm-installation-guide-18.png)

1. 在[!UICONTROL Microsoft Dynamics CRM]旁边，单击&#x200B;**[!UICONTROL Connect]**&#x200B;按钮。

   ![CRM连接选项显示Microsoft Dynamics CRM with Connect按钮](assets/microsoft-dynamics-crm-installation-guide-19.png)

1. 选择 [!UICONTROL Credentials] 或 [!UICONTROL OAuth]。

   ![Microsoft Dynamics CRM身份验证方法选择屏幕](assets/microsoft-dynamics-crm-installation-guide-20.png)

   >[!NOTE]
   >有关OAuth的详细信息，请访问[本文](/help/marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md)。 如果您对流程有任何疑问，请联系您的[!DNL Marketo Measure]客户代表。

1. 在本例中，我们选择了“凭据”。 输入您的凭据，然后单击&#x200B;**[!UICONTROL Next]**。

连接后，您将在CRM/MAP连接列表中看到您的Dynamics连接的详细信息。

**Ad帐户连接**

若要将您的广告帐户与[!DNL Marketo Measure]连接，请首先访问[!UICONTROL Connections]应用程序中的[!DNL Marketo Measure]选项卡。

1. 按照上述&#x200B;_CRM as a Data Provider_&#x200B;部分中的步骤1和2操作。

1. 单击&#x200B;**[!UICONTROL Set up New CRM Connection]**&#x200B;按钮。

   显示“设置新CRM连接”按钮的![连接页面](assets/microsoft-dynamics-crm-installation-guide-21.png)

1. 选择所需的平台。

   ![包含各种广告平台选项的广告帐户平台选择屏幕](assets/microsoft-dynamics-crm-installation-guide-22.png)

**[!DNL Marketo Measure]Javascript**

若要让[!DNL Marketo Measure]跟踪您的Web活动，需要执行多个设置步骤。

1. 点击 **[!UICONTROL My Account]** 下拉菜单，并选择 **[!UICONTROL Account Configuration]**。

   ![带有帐户配置选项的“我的帐户”下拉列表](assets/microsoft-dynamics-crm-installation-guide-23.png)

1. 输入您的电话号码。 对于网站，输入用于在网站上跟踪[!DNL Marketo Measure]的主根域。 完成后单击&#x200B;**[!UICONTROL Save]**。

   ![包含电话号码和网站字段的“帐户配置”页面](assets/microsoft-dynamics-crm-installation-guide-24.png)

   >[!NOTE]
   >要添加多个根域，请联系您的[!DNL Marketo Measure]客户代表。

1. 然后，必须将[[!DNL Marketo Measure] JavaScript](/help/marketo-measure-tracking/adding-marketo-measure-script.md)放置在整个网站和登陆页面中。 我们建议在登陆页面的标题中对该脚本进行硬编码，或通过Tag Management系统(如[Google标签管理器](/help/marketo-measure-tracking/adding-marketo-measure-script-via-google-tag-manager.md))进行添加。

   >[!NOTE]
   >默认情况下，[!DNL Marketo Measure]在每次作业将数据发送到您的CRM时，将每个API点数导出200条记录。 对于大多数客户而言，这提供了[!DNL Marketo Measure]使用的API积分与CRM上的CPU资源要求之间的最佳平衡。 但是，对于具有复杂CRM配置（如工作流和触发器）的客户，较小的批处理大小可能有助于提高CRM性能。 为此，[!DNL Marketo Measure]允许客户配置CRM导出批次大小。 此设置在[!DNL Marketo Measure] Web应用程序的“设置”>“CRM”>“常规”页面上可用，客户可以选择批量为200（默认值）、100、50或25。
   >在修改此设置时，请记住，较小的批次大小会消耗您的CRM中的更多API积分。 仅当您在CRM中遇到CPU超时或CPU负载较高时，才建议减小批次大小。

   >[!NOTE]
   >禁用Marketo Measure将数据导出到Dynamics时，它不会删除任何现有数据。 有关删除现有数据的帮助，请与Dynamics支持部门联系。

   >[!MORELIKETHIS]
   >[错误通知](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
