---
unique-page-id: 18874694
description: Salesforce沙盒到生产环境的迁移 —  [!DNL Marketo Measure]  — 产品文档
title: Salesforce沙盒到生产环境的迁移
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# Salesforce沙盒到生产环境的迁移 {#salesforce-sandbox-to-production-migration}

如果您选择测试 [!DNL Marketo Measure] 在 [!DNL Salesforce] 沙盒环境，请在您准备就绪后，按照以下说明迁移到生产。 下面的说明假定您已下载 [!DNL Marketo Measure] 打包到您的沙盒组织中，执行了必要的测试并准备推送 [!DNL Marketo Measure] 到生产。

## 步骤1：安装 [!DNL Marketo Measure] 将包放入生产环境 [!DNL Salesforce] 实例 {#install-marketo-measure-packages-into-your-production-salesforce-instance}

* 安装两个 [!DNL Marketo Measure] 使用&quot;[!UICONTROL All Users]”设置

   * [基础包](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}
   * [功能板扩展包](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t610000001jI6){target="_blank"}

* 欲知关于 [!DNL Marketo Measure] 关系 [!DNL Salesforce]，查看 [本文](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* 一点 [!DNL Salesforce] 配置是必需的。 下面列出了具体的操作项目 [下面的步骤4](#salesforce-configuration)

## 步骤2：删除中的当前沙盒CRM连接 [!DNL Marketo Measure] 应用程序 {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* 登录到 [!DNL Marketo Measure] experience.adobe.com/marketo-measure上的应用程序
* 导航到我的帐户>[!UICONTROL Settings] >[!UICONTROL Connections]
* 单击SFDC连接旁边的垃圾桶图标以删除
* 系统将提示您确认删除操作。 请确保仔细阅读提示并了解删除的后果

  ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * 键入确认模型中提示的业务名称，然后单击“我了解后果，删除此连接”
* 这将触发删除过程，并需要一些时间才能完成

## 步骤3：连接中的生产CRM实例 [!DNL Marketo Measure] 应用程序 {#connect-the-production-crm-instance-in-marketo-measure-app}

* 登录到 [!DNL Marketo Measure] experience.adobe.com/marketo-measure上的应用程序
* 导航到 [!UICONTROL My Account] >[!UICONTROL Settings] > [!UICONTROL Connections]
* 成功删除沙盒连接后，连接将从页面中消失，否则连接仍会存在，并且状态为正在删除
* 单击 &quot;[!UICONTROL Set up New CRM connection]&quot;
* 在&quot;[!UICONTROL Select CRM Connection]”模式对话框，单击“[!UICONTROL Connect]”操作 [!DNL Salesforce] 平台，选择&#39;&#39;[!UICONTROL Production]”选项
* 系统会提示您输入凭据，请确保输入生产登录详细信息

## 步骤4：Salesforce配置 {#salesforce-configuration}

[页面布局](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[权限集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[共享报告](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0){target="_blank"}

[隐藏不必要的报表类型](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[自定义工作流（如果适用）](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
