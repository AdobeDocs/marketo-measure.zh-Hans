---
description: '[!DNL Marketo Measure] Salesforce包的安装和设置 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] [!DNL Salesforce] 包安装和设置'
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
feature: Installation, Salesforce
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce包的安装和设置 {#marketo-measure-salesforce-package-installation-and-set-up}

在安装[!DNL Marketo Measure] [!DNL Salesforce]基础包之前，您必须先确定是否在[!DNL Salesforce]沙盒中安装该基础包，然后再迁移到Salesforce生产实例。

>[!NOTE]
>
>一旦您的[!DNL Marketo Measure]帐户连接到[!DNL Salesforce]生产实例，您就无法向后移动并连接到沙盒。 此外，[!DNL Marketo Measure]帐户只能连接到一个[!DNL Salesforce]生产实例。

[!DNL Marketo Measure]基本包包含：

* 7个自定义[!DNL Marketo Measure]对象
* 自定义[!DNL Marketo Measure]字段
* 25个[!DNL Stock]报告

[!DNL Marketo Measure]能够读取标准[!DNL Salesforce]对象、字段和记录，但是[!DNL Marketo Measure]永远不会更新数据或将数据推送到这些对象。 由[!DNL Marketo Measure] JavaScript收集的所有数据将显示在[!DNL Marketo Measure]自定义对象和字段中。

请按照以下步骤安装[!DNL Marketo Measure Salesforce]基本包。

1. 使用无痕浏览器，转到[Salesforce AppExchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}并登录。

1. 在沙盒或生产环境的[!DNL Marketo Measure]包中安装。

1. 以管理员身份登录到[!DNL Salesforce]。

1. 为所有用户&#x200B;**[!UICONTROL Install]选择**。

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-1.png)

1. 安装完成后，即可进行查看。

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-2.png)

完成安装后，您可以根据需要使用[[!DNL Salesforce] 字段更新](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md){target="_blank"}页面布局[!DNL Marketo Measure]。

>[!NOTE]
>
>了解[!DNL Marketo Measure]权限集创建情况和[它们的使用方式](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md){target="_blank"}。

## 创建[!DNL Marketo Measure]配置文件和用户 {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure]通过[!DNL Salesforce]应用内连接的[!DNL Marketo Measure]用户发送和接收数据。

要将接触点数据推送到[!DNL Salesforce]实例，连接的用户必须有权访问[!DNL Marketo Measure]自定义对象(例如Buyer Touchpoint和Buyer Attribution Touchpoint)以及商机和联系人等标准[!DNL Salesforce]对象。

创建[!DNL Marketo Measure]配置文件以确保在将数据推送到Salesforce时不会遇到验证错误。

步骤1：创建特定[!DNL Marketo Measure]配置文件

1. 分配以下权限：

* [!DNL Marketo Measure]管理员权限集
   * 托管权限集使SFDC管理员能够从[!DNL Marketo Measure]对象创建、读取、写入和删除记录。
* “查看和编辑已转化商机权限集”
   * 这允许[!DNL Marketo Measure]在潜在客户转换为联系人后对其进行修饰。 如果未启用此权限集，则可能存在显着的数据跟踪缺口。

>[!NOTE]
>
>此配置文件可以是系统管理员配置文件的克隆。

步骤2：创建专用[!DNL Marketo Measure]用户，以便跟踪[!DNL Marketo Measure]对您的[!DNL Salesforce]实例的影响

1. 将新的[!DNL Marketo Measure]配置文件分配给该用户。

1. 启用“营销用户”作为用户级别权限。

* 通过[!UICONTROL Marketing User]复选框，用户可创建营销活动并使用营销活动导入向导。 如果未选择此选项，则用户只能查看营销活动和高级营销活动设置，编辑单个潜在客户或联系人的营销活动历史记录，以及运行营销活动报表。 [!DNL Marketo Measure]必须能够读取和写入营销活动对象。

步骤3：从所有触发器、工作流和流程中排除此配置文件

步骤4：登录到您的[!DNL Marketo Measure]帐户并重新授权与新用户的[!DNL Salesforce]连接

1. 转到apps.bizible.com并使用新的用户生产[!DNL Salesforce]凭据登录。

1. 在&#x200B;**[!UICONTROL Settings]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL My Account]**。

1. 在&#x200B;**[!UICONTROL Connections]**&#x200B;分组中选择&#x200B;**[!UICONTROL Integrations]**。

1. 单击当前连接的[!DNL Salesforce]连接右侧的键图标，然后选择&#x200B;**使用生产重新授权**。 使用新用户凭据再次登录（如果出现提示）。

>[!MORELIKETHIS]
>
>* [集成权限概述](/help/api-connections/utilizing-marketo-measures-api-connections/integration-permissions-overview.md){target="_blank"}
>
>* [Adobe Admin Console安装程序](/help/configuration-and-setup/getting-started-with-marketo-measure/adobe-admin-console-setup.md){target="_blank"}
