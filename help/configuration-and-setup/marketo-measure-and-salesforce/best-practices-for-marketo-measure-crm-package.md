---
description: ' [!DNL Marketo Measure] CRM包的最佳实践 —  [!DNL Marketo Measure]'
title: ' [!DNL Marketo Measure] CRM包的最佳实践'
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# [!DNL Marketo Measure] CRM包的最佳实践 {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但仍可在CRM中看到“Bizible”。 该更新了，并且品牌再造将很快反映在您的CRM中。

## 概述 {#overview}

[!DNL Marketo Measure]同时与[!DNL Salesforce]和[!DNL Microsoft Dynamics]集成，本文档侧重于为[!DNL Salesforce]设计的CRM包的[!DNL Marketo Measure]最佳实践。

在实施过程中，以下两个包将安装到您的[!DNL Salesforce]实例中。

基本包：这是包含自定义对象和字段的基本包。 建议所有用户都在生产环境中安装。
功能板扩展包：这是我们的功能板扩展包，其中包含三个预建的功能板。 我们建议所有用户都在生产环境中安装。 这是可选操作，但我们鼓励客户安装。

通过这些包，您的[!DNL Marketo Measure]用户可在其[!DNL Salesforce]实例中轻松访问接触点数据。 确认已正确配置这些包是验证页面布局、权限集、报表和功能板是否按预期向[!DNL Marketo Measure]用户呈现的关键。

## 最佳实践 {#best-practice}

在实施和管理[!DNL Marketo Measure] [!DNL Salesforce]包时，请牢记以下最佳实践。

* 确认每个必要的团队成员都可以访问[!DNL Marketo Measure]报表文件夹。 应该有1-3个[!DNL Marketo Measure]文件夹（下面对此进行了说明）。 要打开访问权限，安装包的用户必须与相应的用户或角色共享报表文件夹。
   * **Buyer Touchpoint报告** — 可供所有人使用
   * **[!DNL Marketo Measure]基于帐户的营销报表** — 报表将仅填充到第2层及更高层的客户
   * **Buyer Touchpoint功能板** — 可供所有人使用，不过此包是可选的。

## 维护的最佳实践 {#best-practice-for-maintenance}

虽然在初始实施期间涵盖了CRM包的设置，但建议您每年审查一次CRM包的设置。 此审核确认所有页面布局均已正确设置，并且所有相应的团队成员都有权访问[!DNL Marketo Measure]报告和仪表板。

其他可能触发审阅的原因……

* 添加新的团队成员
* [!DNL Salesforce]页面布局的更新
* 将[!DNL Salesforce] Classic迁移到Lighting
* 升级您的[!DNL Marketo Measure]合同
* 检查您是否在[!DNL Salesforce]中安装了最新版本的买方接触点包

>[!NOTE]
>
>当您禁用Marketo Measure将数据导出到Salesforce时，它不会删除任何现有数据。 要删除它，请按照[此Salesforce帮助文章](https://help.salesforce.com/s/articleView?language=en_US&amp;id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target="_blank"}中的步骤操作。

>[!MORELIKETHIS]
>
>* [更新Buyer Touchpoint包](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] 权限集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [共享报告和仪表板文件夹](https://help.salesforce.com/s/articleView?language=en_US&amp;id=analytics_share_folder.htm&amp;type=0)
>* [将Marketo Measure连接到Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
