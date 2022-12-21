---
unique-page-id: 37356027
description: '"[!DNL Marketo Measure] CRM无包集成 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] CRM无包集成”'
exl-id: a4f31d82-63ec-4bb2-bc8b-d3495e61af4f
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# [!DNL Marketo Measure] CRM无包集成 {#marketo-measure-crm-packageless-integration}

我们了解，并非所有营销团队都希望（或有权）在CRM之外运行营销报告，无论是因为访问权限有限、CRM所有权、较长的价值实现时间，还是法律影响。 沿着 [!DNL Marketo Measure] 快速入门使您能够有效地实施和运行 [!DNL Marketo Measure] 尽可能少地依赖CRM。

## 标准 [!DNL Marketo Measure] 安装 {#standard-marketo-measure-installation}

通过标准 [!DNL Marketo Measure] 安装时，您需要安装 [!DNL Salesforce] 包或 [!DNL Microsoft Dynamics] 托管解决方案。 安装包括添加到CRM的自定义对象/实体和自定义字段 [!DNL Marketo Measure] 然后可以将数据写入。

与 [!DNL Marketo Measure] 适用于不想在CRM中创建自定义对象/实体或自定义字段的客户。 对于使用外部data warehouse的客户而言，这也是一个不错的选择。

## 权限 {#permissions}

A [!DNL Marketo Measure] CRM无包集成仍需要访问标准CRM对象，如潜在客户和联系人。 我们强烈建议专用用户作为连接的用户，因为他们将拥有适当的数据访问权限。

为确保从CRM中正确提取所有数据，我们需要以下安全性和辅助功能设置：查看专用用户配置文件的所有数据。 此权限集将提供 [!DNL Marketo Measure] 从标准对象下载数据所需的访问权限。 此权限集位于配置文件级别。

## 设置身份提供程序和数据连接 {#setup-your-identity-provider-and-data-connections}

在以下指南中，跳过安装 [!DNL Salesforce] 包或 [!DNL Microsoft Dynamics] 托管解决方案，并仅按照权限和集成说明操作。

[!DNL Salesforce] 客户，单击 [此处](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md).

[!DNL Microsoft Dynamics] 客户，单击 [此处](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

完成上述所有步骤后，即可使用。 如果您在路途中遇到任何问题，请随时联系 [!DNL Marketo Measure] 代表或 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}。

>[!NOTE]
>
>如果您从 [!DNL Marketo Measure] CRM无包集成，您以后将能够安装Salesforce包或Microsoft Dynamics Managed Solution。
