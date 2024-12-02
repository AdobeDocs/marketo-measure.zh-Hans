---
unique-page-id: 37356027
description: '[!DNL Marketo Measure] CRM无包集成 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] CRM无包集成'
exl-id: a4f31d82-63ec-4bb2-bc8b-d3495e61af4f
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# [!DNL Marketo Measure] CRM无包集成 {#marketo-measure-crm-packageless-integration}

并非所有营销团队都希望（或有权访问）在CRM之外运行营销报表，无论这是由于访问权限受限、CRM所有权、实现价值的时间较长还是法律影响。 按照[!DNL Marketo Measure]快速入门的路径运行，您能够在尽可能少依赖于CRM的情况下有效地实施和运行[!DNL Marketo Measure]。

## 标准[!DNL Marketo Measure]安装 {#standard-marketo-measure-installation}

通过标准[!DNL Marketo Measure]安装，您需要安装[!DNL Salesforce]包或[!DNL Microsoft Dynamics]托管解决方案。 该安装包括添加到CRM的自定义对象/实体和自定义字段，然后[!DNL Marketo Measure]可以向其写入数据。

与[!DNL Marketo Measure]的无包集成适用于不想在CRM中创建自定义对象/实体或自定义字段的客户。 对于使用外部Data Warehouse的客户来说，这也是一个很好的选择。

## 权限 {#permissions}

[!DNL Marketo Measure] CRM无包集成仍需要访问标准CRM对象，如潜在客户和联系人。 建议将专用用户作为已连接的用户，因为他们具有适当的数据访问权限。

为确保从CRM正确提取所有数据，我们要求以下安全和辅助功能设置：查看专用用户配置文件的所有数据。 此权限集授予[!DNL Marketo Measure]从标准对象下载数据所需的访问权限。 此权限集在配置文件级别。

## 设置您的身份提供程序和数据连接 {#setup-your-identity-provider-and-data-connections}

在以下指南中，跳过安装[!DNL Salesforce]包或[!DNL Microsoft Dynamics]托管解决方案的步骤，仅按照权限和集成说明进行操作。

[!DNL Salesforce]客户单击[此处](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)。

[!DNL Microsoft Dynamics]客户单击[此处](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md)。

完成这些步骤后，集成应该可以正常运行。 如果您遇到任何问题，请联系您的[!DNL Marketo Measure]代表或[Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。

>[!NOTE]
>
>如果您从[!DNL Marketo Measure] CRM无包集成开始，则以后可以安装Salesforce包或Microsoft Dynamics托管解决方案。
