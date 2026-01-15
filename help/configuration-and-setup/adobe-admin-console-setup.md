---
description: 指南通过Adobe Admin Console配置文件设置Marketo Measure访问权限并登录
title: Adobe Admin Console设置
feature: Installation
exl-id: f9edacae-79e0-408c-ac37-bbe67c185f2d
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---

# Adobe Admin Console设置 {#adobe-admin-console-setup}

使用[!DNL Marketo Measure]的第一步是创建并登录您配置的Adobe Admin Console。 如果您没有收到包含登录说明的电子邮件，请联系您的[!DNL Marketo Measure]客户代表。

## 设置您的Adobe Admin Console和身份提供程序 {#set-up-your-adobe-admin-console-and-identity-provider}

作为Adobe套件中的产品，[!DNL Marketo Measure]使用Adobe Admin Console for Identity Management的完整功能。 更多资源可在[此处](https://helpx.adobe.com/cn/enterprise/using/admin-console.html)找到。

建议您查看可用于[Identity Management](https://helpx.adobe.com/cn/enterprise/using/set-up-identity.html)的资源、最佳实践和选项。

有关在Adobe Admin Console中设置Identity Management的指导和审查，请联系您的[!DNL Marketo Measure]客户代表。

为了便于对您的[!DNL Marketo Measure]实例进行用户身份验证和授权，需要在Adobe Admin Console中执行以下步骤：

**设置[!DNL Marketo Measure]产品卡**

访问Adobe Admin Console时，您会看到“概述”部分中存在您的[!DNL Marketo Measure]产品实例。

![访问Adobe Admin Console时，您会看到您的Marketo Measure](assets/adobe-setup-1.png)

单击[!DNL Marketo Measure]产品卡可显示所有[!DNL Marketo Measure]实例。 默认情况下，每个[!DNL Marketo Measure]实例都有自己的前缀为“[!DNL Marketo Measure]”的配置文件。 添加到此配置文件或此实例中的任何其他配置文件的任何管理员或用户都可以登录到[!DNL Marketo Measure]。

![单击Marketo Measure产品卡可显示您的所有](assets/adobe-setup-2.png)

无需执行任何操作即可在[!DNL Marketo Measure]产品实例中创建配置文件。

要开始添加可以访问[!DNL Marketo Measure]的用户，请参阅下面的[添加 [!DNL Marketo Measure] 管理员和 [!DNL Marketo Measure] 用户](#adding-marketo-measure-admins-and-marketo-measure-users)部分。

## 正在添加[!DNL Marketo Measure]管理员和[!DNL Marketo Measure]用户 {#adding-marketo-measure-admins-and-marketo-measure-users}

下一步是通过添加用户来授予对[!DNL Marketo Measure]应用程序的访问权限。 可以在[!DNL Marketo Measure]产品卡的admins and users目录中执行此操作。

| 用户类型 | 描述 |
|---|---|
| 管理员 | 这些是[!DNL Marketo Measure]应用程序的管理员和超级用户，完全能够更新和管理特定于[!DNL Marketo Measure]的配置选项 |
| 用户 | 这些是[!DNL Marketo Measure]应用程序的标准用户，在[!DNL Marketo Measure]应用程序中拥有只读权限 |

将用户添加到其相应组时，您会看到列出其[标识类型](https://helpx.adobe.com/cn/enterprise/using/set-up-identity.html)。

>[!NOTE]
>
>要成为[!DNL Marketo Measure]管理员(位于[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}中)，必须将用户添加为用户&#x200B;_和_，并将用户添加为[!DNL Marketo Measure]产品信息卡中任何[!DNL Marketo Measure]产品配置文件的管理员。

**登录到[!DNL Marketo Measure]**

将用户添加到产品配置文件后，通过在[!DNL Marketo Measure]experience.adobe.com/marketo-measure **上选择**&#x200B;使用Adobe ID登录[选项，他们可以访问其](https://experience.adobe.com/marketo-measure){target="_blank"}实例。

![将用户添加到产品配置文件后，他们能够](assets/adobe-setup-3.png)
