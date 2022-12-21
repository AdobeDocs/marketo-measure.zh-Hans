---
description: '"[!DNL Marketo Measure] 安装和设置Salesforce包 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] [!DNL Salesforce] 软件包安装和设置”'
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---

# [!DNL Marketo Measure] 安装和设置Salesforce包 {#marketo-measure-salesforce-package-installation-and-set-up}

安装之前 [!DNL Marketo Measure] [!DNL Salesforce] 基本包中，您需要确定是否首先在 [!DNL Salesforce] 沙盒，然后再移到Salesforce生产实例。

>[!NOTE]
>
>一旦 [!DNL Marketo Measure] 帐户已连接到 [!DNL Salesforce] 生产实例中，您无法向后移动并连接到沙盒。 此外， [!DNL Marketo Measure] 帐户只能连接到一个 [!DNL Salesforce] 生产实例。

的 [!DNL Marketo Measure] 基本包包含：

* 7自定义 [!DNL Marketo Measure] 对象
* 自定义 [!DNL Marketo Measure] 字段
* 25 [!DNL Stock] 报表

[!DNL Marketo Measure] 能读标准 [!DNL Salesforce] 但是，对象、字段和记录 [!DNL Marketo Measure] 将永远不会更新数据或将数据推送到他们。 收集的所有数据 [!DNL Marketo Measure] Javascript将在 [!DNL Marketo Measure] 自定义对象和字段。

按照以下步骤安装 [!DNL Marketo Measure Salesforce] 基本包。

1. 使用隐身浏览器，转到 [Salesforce Appexchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target=&quot;_blank&quot;}并登录。

1. 在 [!DNL Marketo Measure] 包。

1. 登录到 [!DNL Salesforce] 作为管理员。

1. 选择 **[!UICONTROL Install]（适用于所有用户）**.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-1.png)

1. 安装完成后，您即可查看。

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-2.png)

完成安装后，您可以更新 [[!DNL Salesforce] 页面布局](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md){target=&quot;_blank&quot;} [!DNL Marketo Measure] 字段。

>[!NOTE]
>
>阅读 [!DNL Marketo Measure] 创建和 [如何使用](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md){target=&quot;_blank&quot;}。

## 安装 [!DNL Marketo Measure] 功能板包 {#install-marketo-measure-dashboard-package}

的 [!UICONTROL Dashboard] 扩展包包含三个预建功能板。 我们建议安装 [!UICONTROL within] 适用于所有用户的生产环境。

1. 从安装包 [[!DNL Salesforce] Appexchange](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t610000001jI6){target=&quot;_blank&quot;}。

1. 选择 **[!UICONTROL Install for All Users]**.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-3.png)

## 创建 [!DNL Marketo Measure] 配置文件和用户 {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure] 通过连接的 [!DNL Salesforce] 用户 [!DNL Marketo Measure] 应用程序。

要将接触点数据推送到 [!DNL Salesforce] 实例中，连接的用户必须具有 [!DNL Marketo Measure] 自定义对象（例如，买方接触点和买方归因接触点）以及标准 [!DNL Salesforce] 对象，如潜在客户和联系人。

创建 [!DNL Marketo Measure] 配置文件，以确保在将数据推送到Salesforce时不会遇到验证错误。

步骤1:创建特定 [!DNL Marketo Measure] 个人资料

1. 分配以下权限：

* &quot;[!DNL Marketo Measure] 管理员权限集”
   * 受管权限集使SFDC管理员能够从中创建、读取、写入、删除记录 [!DNL Marketo Measure] 对象。
* &quot;查看和编辑已转换的潜在客户权限集&quot;
   * 这允许 [!DNL Marketo Measure] 以装饰销售线索。 如果未启用此权限集，则可能会存在大量数据跟踪空白。

>[!NOTE]
>
>此配置文件可以是“系统管理员”配置文件的克隆。

步骤2:创建专用 [!DNL Marketo Measure] 用户，以便跟踪 [!DNL Marketo Measure] 在 [!DNL Salesforce] 实例

1. 分配新 [!DNL Marketo Measure] 向该用户发送用户档案。

1. 启用“营销用户”作为用户级别权限。

* 的 [!UICONTROL Marketing User] 复选框允许用户创建营销活动并使用营销活动导入向导。 如果未选择此选项，则用户只能查看营销活动和高级营销活动设置，编辑单个潜在客户或联系人的营销活动历史记录，并运行营销活动报表。 [!DNL Marketo Measure] 需要能够读取和写入营销活动对象。

步骤3:从所有触发器、工作流和流程中排除此用户档案

步骤4:登录到 [!DNL Marketo Measure] 帐户并重新授权 [!DNL Salesforce] 与新用户的连接

1. 转到apps.bizible.com ，然后使用新用户生产环境登录 [!DNL Salesforce] 凭据。

1. 选择 **[!UICONTROL Settings]** 在 **[!UICONTROL My Account]** 下拉菜单。

1. 选择 **[!UICONTROL Connections]** 在 **[!UICONTROL Integrations]** 分组。

1. 单击当前连接对象右侧的键图标 [!DNL Salesforce] 连接，选择 **通过生产重新授权**. 再次使用新用户凭据登录（如果出现提示）。
