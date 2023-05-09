---
description: 最新发行说明 —  [!DNL Marketo Measure]  — 产品文档
title: 最新发行说明
source-git-commit: 8e8ddd80d69102455fa678a32f31a9fe8319822c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# 发行说明：2023年 {#release-notes-2023}

在下面，您将找到我们2023版本的所有新增和更新功能。

## 第2季度版本 {#q2-release}

<p>

**Salesforce资源包整合**

* 我们将所有Salesforce包合并到单个全面的包中，以改善用户体验和简化使用。 V1、V2_EXT和报表包将在下季度停用。 新产品包结合了以前的所有功能，可提供更高效的跟踪和更深入的客户分析。
* 已安装V2包的客户必须将其更新到新的整合版本。
* 我们添加了两个新字段来增强您的报告功能：
   * form_name:现在，在BT/BAT对象中可用，该字段允许用户根据表单名称创建报表。
   * user_touchpoint_id:此字段允许用户创建具有独特用户接触点计数的报表。
* [本文](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} 包括有关从旧版报表包重新创建报表和功能板的指南。

**Salesforce API版本更新**

* Apex类（包括UserActivityContext类）的所有Salesforce API版本均已更新为支持的版本。 (31.0 - 57.0)

**新软件包安装**

* 新的整合包安装链接 [可在此处找到](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### 接下来会怎么样？ {#whats-coming}

<p>

**IP地址存储的更改**

* 根据隐私注意事项，我们将不再在系统中存储IP地址。 我们将继续识别和存储IP地址的地理位置，但格式将更改（例如，“美国”将更改为“美国”）。
