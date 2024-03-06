---
description: Adobe Admin Console设置 — Marketo Measure — 产品文档
title: Adobe Admin Console设置
feature: Installation
exl-id: f9edacae-79e0-408c-ac37-bbe67c185f2d
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Adobe Admin Console设置 {#adobe-admin-console-setup}

使用的第一步 [!DNL Marketo Measure] 是创建并登录到您配置的Adobe Admin Console。 如果您尚未收到包含登录说明的电子邮件，请联系贵机构的 [!DNL Marketo Measure] 客户代表。

## 设置您的Adobe Admin Console和身份提供程序 {#set-up-your-adobe-admin-console-and-identity-provider}

作为Adobe包中的产品， [!DNL Marketo Measure] 使用Adobe Admin Console for Identity Management的完整功能。 更多资源可以 [在此处找到](https://helpx.adobe.com/cn/enterprise/using/admin-console.html).

建议您查看可用的资源、最佳实践和选项，以便用于 [Identity Management](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

有关在Adobe Admin Console中设置Identity Management的指导和审查，请联系 [!DNL Marketo Measure] 客户代表。

为了便于用户使用您的系统验证和授权 [!DNL Marketo Measure] 实例时，需要在Adobe Admin Console中执行以下步骤：

**设置 [!DNL Marketo Measure] 产品卡**

在访问Adobe Admin Console时，您会看到 [!DNL Marketo Measure] 产品实例显示在概述部分中。

![](assets/adobe-admin-console-setup-1.png)

单击 [!DNL Marketo Measure] 产品卡会显示您的所有 [!DNL Marketo Measure] 实例。 默认情况下，每个 [!DNL Marketo Measure] 实例有它自己的配置文件，前缀为“[!DNL Marketo Measure]’。 添加到此配置文件或此实例中的任何其他配置文件的任何管理员或用户都可以登录到 [!DNL Marketo Measure].

![](assets/adobe-admin-console-setup-2.png)

无需执行任何操作即可在 [!DNL Marketo Measure] 产品实例。

开始添加可以访问的用户 [!DNL Marketo Measure]，请参阅 [正在添加 [!DNL Marketo Measure] 管理员和 [!DNL Marketo Measure] 用户](#adding-marketo-measure-admins-and-marketo-measure-users) 部分。

## 正在添加 [!DNL Marketo Measure] 管理员和 [!DNL Marketo Measure] 用户 {#adding-marketo-measure-admins-and-marketo-measure-users}

下一步是授予对 [!DNL Marketo Measure] 添加用户的应用程序。 这可以在的admins and users目录中完成 [!DNL Marketo Measure] 产品卡。

| 用户类型 | 描述 |
|---|---|
| 管理员 | 这些是的管理员和高级用户 [!DNL Marketo Measure] 具有完全更新和管理能力的应用程序 [!DNL Marketo Measure]特定配置选项 |
| 用户 | 这些是 [!DNL Marketo Measure] 在中具有只读权限的应用程序 [!DNL Marketo Measure] 应用程序 |

将用户添加到其各自的组时，您会看到他们的 [身份类型已列出](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

>[!NOTE]
>
>成为 [!DNL Marketo Measure] 管理员(在 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"})，必须将用户添加为用户 _和_ 管理员至任意 [!DNL Marketo Measure] 内的产品配置文件 [!DNL Marketo Measure] 产品卡。

**登录[!DNL Marketo Measure]**

将用户添加到产品配置文件后，他们便能够访问其 [!DNL Marketo Measure] 实例，方法是 **使用Adobe ID登录** 选项位于 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

![](assets/adobe-admin-console-setup-3.png)
