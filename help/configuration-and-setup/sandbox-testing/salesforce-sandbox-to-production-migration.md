---
unique-page-id: 18874694
description: 从Salesforce沙盒迁移到生产 —  [!DNL Marketo Measure]  — 产品文档
title: 从Salesforce沙盒迁移到生产
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---

# 从Salesforce沙盒迁移到生产 {#salesforce-sandbox-to-production-migration}

如果您选择测试 [!DNL Marketo Measure] 在 [!DNL Salesforce] 沙盒环境中，请在您准备就绪后按照以下说明迁移到生产。 以下说明假定您已经下载了 [!DNL Marketo Measure] 将包打包到沙盒组织中，执行了必要的测试，并准备好推送 [!DNL Marketo Measure] 生产。

## 步骤1:安装 [!DNL Marketo Measure] 包到生产环境中 [!DNL Salesforce] 实例 {#install-marketo-measure-packages-into-your-production-salesforce-instance}

* 安装两个 [!DNL Marketo Measure] 包到生产中，其中“[!UICONTROL All Users]&quot;设置

   * [基本包](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target=&quot;_blank&quot;}
   * [功能板扩展包](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t610000001jI6){target=&quot;_blank&quot;}

* 有关 [!DNL Marketo Measure] 关系 [!DNL Salesforce]，请查看 [本文](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* 一点 [!DNL Salesforce] 配置是必要的。 具体操作项目在 [下面的步骤4](#salesforce-configuration)

## 步骤2:删除中的当前沙盒CRM连接 [!DNL Marketo Measure] 应用程序 {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* 登录到 [!DNL Marketo Measure] experience.adobe.com/marketo-measure上的应用程序
* 导航到我的帐户>[!UICONTROL Settings] >[!UICONTROL Connections]
* 单击SFDC连接旁边的垃圾桶图标以删除
* 系统将提示您确认删除。 请务必仔细阅读提示并了解删除操作的后果

   ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * 键入确认模型中提示的业务名称，然后单击“我了解结果，删除此连接”
* 这将触发删除过程，并且需要一些时间才能完成

## 步骤3:在中连接生产CRM实例 [!DNL Marketo Measure] 应用程序 {#connect-the-production-crm-instance-in-marketo-measure-app}

* 登录到 [!DNL Marketo Measure] experience.adobe.com/marketo-measure上的应用程序
* 导航到 [!UICONTROL My Account] >[!UICONTROL Settings] > [!UICONTROL Connections]
* 成功删除沙盒连接后，该连接将从页面中消失，否则该连接仍将显示为“正在删除”状态
* 单击 &quot;[!UICONTROL Set up New CRM connection]&quot;
* 在“[!UICONTROL Select CRM Connection]“模式”对话框中，单击“[!UICONTROL Connect]“操作”旁边的 [!DNL Salesforce] 平台，选择[!UICONTROL Production]&quot;选项
* 系统将提示您输入凭据，请确保输入生产登录详细信息

## 步骤4:Salesforce配置 {#salesforce-configuration}

[页面布局](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[权限集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[共享报告](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0){target=&quot;_blank&quot;}

[隐藏不必要的报表类型](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[自定义工作流（如果适用）](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
