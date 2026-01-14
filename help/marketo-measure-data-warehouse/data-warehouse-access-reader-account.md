---
description: 介绍如何设置和使用读者帐户来访问Marketo Measure Data Warehouse
title: Data Warehouse访问权限 — Reader帐户
exl-id: 2aa73c41-47ab-4f11-96d8-dafb642308fc
feature: Data Warehouse
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---

# Data Warehouse访问权限 — Reader帐户 {#data-warehouse-access-reader-account}

## Snowflake访问链接 {#snowflake-access-link}

要访问Snowflake Data Warehouse，您必须导航到Snowflake帐户的特定URL。 登录到[!DNL Marketo Measure]并按照以下步骤导航到Data Warehouse信息页面，即可找到此访问链接。

1. 在[!DNL Marketo Measure]中，单击页面顶部的&#x200B;**[!UICONTROL My Account]** > **[!UICONTROL Settings]**。

   ![](assets/data-account-7.png)

1. 在左侧菜单的“安全”下，单击&#x200B;**[!UICONTROL Data Warehouse]**。

   ![](assets/data-account-8.png)

1. 此页面包含指向Snowflake Data Warehouse和用户名的链接。

   ![](assets/data-account-9.png)

   >[!NOTE]
   >
   >这是一个只读帐户，可供贵组织使用，而不仅仅限于个人用户。 贵公司内任何有权访问[!DNL Marketo Measure]的用户都可以使用此帐户登录Snowflake Data Warehouse读取器帐户。

1. 单击Snowflake URL中提供的链接，这会将您转到Snowflake登录页面，您可以在其中输入用户名和密码。 _如果没有密码，请参阅以下步骤重置密码_。

   ![](assets/data-account-5.png)

1. 登录后，单击页面顶部的&#x200B;**[!UICONTROL Worksheets]**。

   ![](assets/data-account-6.png)

1. BIZIBLE_ROI_V3数据库对象位于屏幕左侧。 在查询窗口顶部的下拉选项中输入仓库、数据库和方案。 每个选项应只有一个选项。 现在，您可以在Snowflake查询编辑器中执行查询了。

   ![](assets/data-account-4.png)

## 重置密码 {#reset-your-password}

[!DNL Marketo Measure]无权访问您的Snowflake登录密码。 如果必须重置密码，请单击Data Warehouse信息页面上的[!UICONTROL Reset Password]按钮，然后按照说明操作。 临时密码会立即显示在用户界面中。 下次登录Data Warehouse时，系统将提示您创建自己的密码。

>[!NOTE]
>
>* 重置密码会为您组织中的所有[!DNL Marketo Measure]用户重置密码，而不仅仅是当前登录的用户。
>* 我们仅在UI中显示临时密码。 将不会发送电子邮件。

![](assets/data-account-3.png)

![](assets/data-account-1.png)

## 通过第三方工具连接到Snowflake {#connecting-to-snowflake-via-third-party-tools}

您需要输入几条信息以将Snowflake Data Warehouse连接到第三方工具。

>[!NOTE]
>
>每个工具的连接要求各不相同；建议您查阅文档以了解要连接的特定工具。

* **URI** （始终必需）
   * 这是Snowflake帐户的域名。 它包含在Snowflake登录链接的一部分中。
* **用户名** （始终必需）
   * 用户名在[!DNL Marketo Measure]的Data Warehouse信息页面上列出。
* **密码** （始终必需）
   * 这是您首次登录Snowflake帐户时设置的密码。 要重置密码，请参阅上述步骤。
* **数据库名称** （并非总是必需的）
   * 数据库就是将数据存储在Snowflake中的地方。 它是存储资源。 数据库名称列在[!DNL Marketo Measure]的Data Warehouse信息页中。
* **仓库名称** （并非总是必需的）
   * Warehouse就是在Snowflake中执行查询的地方。 它是计算资源。 仓库名称在[!DNL Marketo Measure]的Data Warehouse信息页面上列出。

  ![](assets/data-account-2.png)
