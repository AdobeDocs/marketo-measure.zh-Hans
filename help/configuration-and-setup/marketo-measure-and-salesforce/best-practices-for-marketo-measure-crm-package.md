---
description: 的最佳实践 [!DNL Marketo Measure] CRM包 —  [!DNL Marketo Measure]  — 产品文档
title: 的最佳实践 [!DNL Marketo Measure] CRM包
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
source-git-commit: 00268f49ff6e5dfc105fa7ea21837375eae49647
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# 的最佳实践 [!DNL Marketo Measure] CRM包 {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>您可能会看到指定“[!DNL Marketo Measure]“ ”，但仍会在您的CRM中看到“Bizible”。 我们正在努力更新该版本，并且该品牌重命名将很快地反映在您的CRM中。

## 概述 {#overview}

[!DNL Marketo Measure] 与两者集成 [!DNL Salesforce] 和 [!DNL Microsoft Dynamics]，本文档将重点介绍 [!DNL Marketo Measure] 专为 [!DNL Salesforce].

在实施过程中，您的 [!DNL Salesforce] 实例。

基本包：这是我们的基本包，其中包含我们的自定义对象和字段。 我们建议所有用户在生产环境中进行安装。
功能板扩展包：这是功能板扩展包，其中包含3个预建功能板。 我们建议所有用户在生产环境中进行安装。 这是可选的，但我们建议客户安装。

这些包可启用 [!DNL Marketo Measure] 用户可轻松访问其整个 [!DNL Salesforce] 实例。 确认您正确配置了这些包将是验证页面布局、权限集、报表和功能板是否呈现给您的关键 [!DNL Marketo Measure] 用户。

## 最佳实践 {#best-practice}

在实施和管理 [!DNL Marketo Measure] [!DNL Salesforce] 软件包，请牢记以下最佳实践。

* 确认每个必要的团队成员都有权访问 [!DNL Marketo Measure] 报表文件夹。 应该是1-3 [!DNL Marketo Measure] 文件夹（下文对此进行了说明）。 要打开访问权限，安装包的人员需要与相应的用户或角色共享报表文件夹。
   * **买方接触点报表**  — 适用于所有人
   * **[!DNL Marketo Measure]基于帐户的市场营销报告**  — 报表将仅填充给第2层及更高层的客户
   * **买方接触点功能板**  — 可供每个人使用，但此包是可选的。

## 维护最佳实践 {#best-practice-for-maintenance}

虽然在初始实施期间介绍了CRM包的设置，但我们建议您每年查看一次CRM包的设置。 此审阅将确认已正确设置所有页面布局，并且所有相应的团队成员都有权访问 [!DNL Marketo Measure] 报表和功能板。

其他原因可能会触发审核……

* 新增团队成员
* 您的更新 [!DNL Salesforce] 页面布局
* 迁移 [!DNL Salesforce] 经典到亮光
* 升级到 [!DNL Marketo Measure] 合同
* 检查您是否在 [!DNL Salesforce]

>[!NOTE]
>
>当您禁用将数据导出到Salesforce的Marketo测量时，它不会删除任何现有数据。 要删除它，请按照 [此Salesforce帮助文章](https://help.salesforce.com/s/articleView?id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target=&quot;_blank&quot;}。

>[!MORELIKETHIS]
>
>* [更新采购员接触点包](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] 权限集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [共享报表和功能板文件夹](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0)
>* [将Marketo Measure连接到Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)

