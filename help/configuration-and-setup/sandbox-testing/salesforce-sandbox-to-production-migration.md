---
unique-page-id: 18874694
description: Salesforce沙盒到生产环境的迁移 —  [!DNL Marketo Measure]
title: Salesforce沙盒到生产环境的迁移
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---

# Salesforce沙盒到生产环境的迁移 {#salesforce-sandbox-to-production-migration}

如果您选择在[!DNL Salesforce]沙盒环境中测试[!DNL Marketo Measure]，请在准备就绪后按照以下说明迁移到生产环境。 以下说明假定您已经将[!DNL Marketo Measure]包下载到沙盒组织、执行了必要的测试并准备将[!DNL Marketo Measure]推送到生产环境。

## 步骤1：将[!DNL Marketo Measure]包安装到生产[!DNL Salesforce]实例中

* 使用“[!UICONTROL All Users]”设置将[!DNL Marketo Measure]包安装到生产环境中

   * [基本包](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}

* 有关与[!DNL Salesforce]的[!DNL Marketo Measure]关系的详细信息，请参阅[本文](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* 需要[!DNL Salesforce]位配置。 下面的[步骤4中概述了具体的操作项](#salesforce-configuration)

## 步骤2：删除[!DNL Marketo Measure]应用程序中的当前沙盒CRM连接 {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* 登录到[!DNL Marketo Measure]应用程序，网址为experience.adobe.com/marketo-measure
* 导航到“我的帐户”>[!UICONTROL Settings] >[!UICONTROL Connections]
* 单击SFDC连接旁边的垃圾桶图标以删除
* 系统会提示您确认删除操作。 请确保仔细阅读提示并了解删除的后果

  ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * 键入确认模型中提示的业务名称，然后单击“我了解后果，删除此连接”
* 这将触发删除过程，并需要一些时间才能完成

## 步骤3：连接[!DNL Marketo Measure]应用程序中的生产CRM实例 {#connect-the-production-crm-instance-in-marketo-measure-app}

* 登录到[!DNL Marketo Measure]应用程序，网址为experience.adobe.com/marketo-measure
* 导航到[!UICONTROL My Account] >[!UICONTROL Settings] > [!UICONTROL Connections]
* 成功删除沙盒连接后，该连接将从页面中消失，否则连接仍会存在，并且状态为“正在删除”
* 单击“[!UICONTROL Set up New CRM connection]”
* 在“[!UICONTROL Select CRM Connection]”模式对话框中，单击[!DNL Salesforce]平台旁边的“[!UICONTROL Connect]”操作，选择“[!UICONTROL Production]”选项
* 系统会提示您输入凭据，请确保输入生产登录详细信息

## 步骤4：Salesforce配置 {#salesforce-configuration}

[页面布局](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[权限集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[共享报告](https://help.salesforce.com/s/articleView?language=en_US&id=analytics_share_folder.htm&type=0){target="_blank"}

[隐藏不必要的报表类型](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[自定义工作流（如果适用）](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
