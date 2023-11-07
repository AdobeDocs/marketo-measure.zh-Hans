---
description: 最新发行说明 -  [!DNL Marketo Measure]  - 产品文档
title: 最新发行说明
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: dc4fda07004398207fb5067eb42ecd9e8ffe8624
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# 发行说明：2023年 {#release-notes-2023}

在下方，您将找到2023版的所有新增功能和更新功能。

## 第4季度发行 {#q4-release}

<p>

**了解功能板重新设计**

所有Marketo Measure用户都将体验我们重新设计的应用程序内仪表板，这些仪表板将增强的可用性与附加价值相结合。 我们还引进了新的指标，如“实现的投资回报率”，该指标考虑了营销投资和购买B2B进入市场之间的典型延迟。

这套新的预建仪表板计划分批推出，从10月的第一周开始，年底之前结束。 这些新功能板、产品内信息和文档链接将自动显示在您的实例中。

* [新增发现功能板指南](/help/marketo-measure-discover-ui/dashboards/new-discover-dashboard-guide.md){target="_blank"}
* [了解功能板基础知识](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
* [收入概览仪表板](/help/marketo-measure-discover-ui/dashboards/revenue-overview-dashboard.md){target="_blank"}
* [已归因的收入仪表板](/help/marketo-measure-discover-ui/dashboards/attributed-revenue-dashboard.md){target="_blank"}
* [ROI仪表板](/help/marketo-measure-discover-ui/dashboards/roi-dashboard.md){target="_blank"}
* [Passport信息板](/help/marketo-measure-discover-ui/dashboards/passport-dashboard.md){target="_blank"}

>[!NOTE]
>
>虽然当前功能板将在2024年1月中旬之前弃用，但在此之前，您可以同时使用两个版本，以确保顺利过渡。

### 弃用 {#deprecations}

<p>

* **“custom_properties”字段**

在我们的数据仓库中，“custom_properties”字段一直用作存储固定架构未涵盖的其他数据点。 此字段以JSON格式存储，其使用受限，并且其与SQL查询的集成可能会很复杂，从而影响性能。 鉴于这些因素，我们决定弃用此字段。 此更改将主要影响Azure表存储中的数据处理层以及导出到数据仓库的数据。

* **Dynamics包相关**

   * 若要保持与Dynamics的连接，请安装我们的最新包版本v6.12。旧版本 `(<v6.12)` 将不再受支持。 此更新可优化历史记录的创建，以减少存储用量。

   * 将弃用带RefreshToken的过时OAuth方法。 请参阅 [本指南](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md){target="_blank"} 更新您的凭据以遵循Microsoft使用ClientSecret的最佳实践。

### 即将发生什么？ {#q4-whats-coming}

<p>

**应用程序内自定义报表**

Marketo Measure客户将首次能够在应用程序中创建和保存自己的报表。 这将在预建功能板于2024年初发布后进行。

<br>

## 第2季度发行 {#q2-release}

<p>

* **Salesforce包合并**

我们正在将所有Salesforce包合并到单个全面的包中，以改进用户体验并简化使用。 V1、V2_EXT和Reporting程序包将在下一季度停用。 新的产品包中整合了所有以前的功能，允许更高效地跟踪和更深入的客户洞察。

已安装V2软件包的客户必须将其更新到新的统一版本。

我们添加了两个新字段以增强您的报告功能：

* form_name：现在BT/BAT对象中提供了此字段，可让用户根据表单名称创建报告。
* user_touchpoint_id：此字段允许用户创建具有独特用户接触点计数的报表。

[本文](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} 包含有关从旧版报表包中重新创建报表和功能板的指南。

* **Salesforce API版本更新**

所有Apex类的Salesforce API版本（包括UserActivityContext类）都更新到支持的版本。 (31.0 - 57.0)

* **新包安装**

新的统一包安装链接 [可在此处找到](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### 即将发生什么？ {#q2-whats-coming}

<p>

**IP地址存储中的更改**

出于隐私考虑，我们将不再将IP地址存储在系统中。 我们将继续标识和存储IP地址的地理位置，但格式会发生变化（例如，从“美国”更改为“美国”）。
