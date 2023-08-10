---
description: 最新发行说明 —  [!DNL Marketo Measure]  — 产品文档
title: 最新发行说明
exl-id: 64b8fce8-af7d-4991-b01e-3fcf375d14e7
feature: Release Notes
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# 发行说明：2023年 {#release-notes-2023}

在下方，您将找到2023版的所有新增功能和更新功能。

## 第2季度发行 {#q2-release}

<p>

**Salesforce包合并**

* 我们正在将所有Salesforce包合并到单个全面的包中，以改进用户体验并简化使用。 V1、V2_EXT和Reporting程序包将在下一季度停用。 新的产品包中整合了所有以前的功能，允许更高效地跟踪和更深入的客户洞察。
* 已安装V2软件包的客户必须将其更新到新的统一版本。
* 我们添加了两个新字段以增强您的报告功能：
   * form_name：现在BT/BAT对象中提供了此字段，可让用户根据表单名称创建报告。
   * user_touchpoint_id：此字段允许用户创建具有独特用户接触点计数的报表。
* [本文](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} 包含有关从旧版报表包中重新创建报表和功能板的指南。

**Salesforce API版本更新**

* 所有Apex类的Salesforce API版本（包括UserActivityContext类）都更新到支持的版本。 (31.0 - 57.0)

**新包安装**

* 新的统一包安装链接 [可在此处找到](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### 即将发生什么？ {#whats-coming}

<p>

**IP地址存储中的更改**

* 出于隐私考虑，我们将不再将IP地址存储在系统中。 我们将继续标识和存储IP地址的地理位置，但格式会发生变化（例如，从“美国”更改为“美国”）。
