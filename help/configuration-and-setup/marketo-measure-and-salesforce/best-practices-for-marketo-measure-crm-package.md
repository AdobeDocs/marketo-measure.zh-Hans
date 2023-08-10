---
description: 的最佳实践 [!DNL Marketo Measure] CRM包 —  [!DNL Marketo Measure]  — 产品文档
title: 的最佳实践 [!DNL Marketo Measure] CRM包
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# 的最佳实践 [!DNL Marketo Measure] CRM包 {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>您可能会看到说明“[!DNL Marketo Measure]”，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

## 概述 {#overview}

[!DNL Marketo Measure] 与两者集成 [!DNL Salesforce] 和 [!DNL Microsoft Dynamics]，本文档将重点介绍 [!DNL Marketo Measure] 专为以下客户设计的CRM包的最佳实践 [!DNL Salesforce].

在实施过程中，以下两个软件包将安装到您的 [!DNL Salesforce] 实例。

基础包：这是我们的基础包，其中包括自定义对象和字段。 我们建议所有用户都在生产环境中安装。
功能板扩展包：这是我们的功能板扩展包，其中包含3个预建的功能板。 我们建议所有用户都在生产环境中安装。 这是可选操作，但我们鼓励客户安装。

这些包支持您的 [!DNL Marketo Measure] 用户可轻松访问其整个环境中的接触点数据 [!DNL Salesforce] 实例。 确认已正确配置这些资源包将是验证页面布局、权限集以及报表和功能板是否向您的展示的关键 [!DNL Marketo Measure] 用户数。

## 最佳实践 {#best-practice}

实施和管理您的 [!DNL Marketo Measure] [!DNL Salesforce] 包，请牢记以下最佳实践。

* 确认每个必要的团队成员都可以访问 [!DNL Marketo Measure] 报表文件夹。 应该有1-3个 [!DNL Marketo Measure] 文件夹（下面将予以说明）。 要打开访问权限，安装包的用户需要与相应的用户或角色共享报表文件夹。
   * **买方接触点报表**  — 可供所有人使用
   * **[!DNL Marketo Measure]基于帐户的营销报表**  — 报表将仅填充给第2层及更高层的客户
   * **买方接触点仪表板**  — 可供所有人使用，不过此包是可选的。

## 维护的最佳实践 {#best-practice-for-maintenance}

虽然在初始实施期间涵盖了CRM包的设置，但我们建议您每年审查一次CRM包的设置。 此审核将确认所有页面布局均已正确设置，并且所有相应的团队成员都有权访问 [!DNL Marketo Measure] 报告和仪表板。

其他可能触发审阅的原因……

* 添加新的团队成员
* 对您的更新 [!DNL Salesforce] 页面布局
* 迁移对象 [!DNL Salesforce] 从经典到轻盈
* 升级至 [!DNL Marketo Measure] 合同
* 检查您是否在中安装了最新版本的买方接触点软件包 [!DNL Salesforce]

>[!NOTE]
>
>当您禁用Marketo Measure将数据导出到Salesforce时，它不会删除任何现有数据。 要删除它，请按照中的步骤操作 [此Salesforce帮助文章](https://help.salesforce.com/s/articleView?id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target="_blank"}.

>[!MORELIKETHIS]
>
>* [更新买方接触点包](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] 权限集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [共享报表和功能板文件夹](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0)
>* [将Marketo Measure连接到Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
