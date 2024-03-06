---
description: Data Warehouse访问 — 直接共享 — 产品文档
title: Data Warehouse访问 — 直接共享
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
feature: Data Warehouse
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 0%

---

# Data Warehouse访问 — 直接共享 {#data-warehouse-access-direct-share}

## 要求 {#requirements}

对象 [!DNL Marketo Measure] 要设置直接共享到Data Warehouse，您必须满足以下要求。

* 您有自己的Snowflake实例。
* 您的Snowflake实例位于Azure East US 2Snowflake区域。
* 您提供 [!DNL Marketo Measure] 使用您的Snowflake帐户ID。

## 限制 {#limitations}

[!DNL Marketo Measure] 由于当前的Snowflake直接共享限制，将只能使用Azure East US 2中的帐户设置Snowflake直接共享。 如果您要求您的数据在其他Snowflake地区可用，我们建议在Azure East US 2的Snowflake帐户中制作数据副本，并使用 [Snowflake数据库复制](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"} 功能，可在您选择的Snowflake地区/帐户中复制您的数据。

## 输入Snowflake帐户ID {#enter-snowflake-account-id}

打开 **设置** Marketo Measure部分，然后导航到 **Data Warehouse** 页面。 在 **直接共享** 部分，输入您的 [Snowflake帐户ID](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} 在提供的框中，然后单击 **连接**.

![](assets/data-warehouse-access-direct-share-1.png)

## 访问共享 {#accessing-the-share}

在为提供的帐户ID创建共享后，您必须完成 [设置步骤](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} 访问Snowflake实例中的数据。

>[!NOTE]
>
>您可以选择所需的任何数据库名称。 您可以为所选的任何角色分配权限，只要该角色存在于Snowflake实例中即可。

* 使用帐户管理员角色

```
USE ROLE ACCOUNTADMIN
```

* 查看可用股份（此处显示已授予股份的名称）

```
SHOW SHARES
```

* 为共享创建数据库

```
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* 授予对共享数据库的权限

```
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

有关从SnowflakeUI完成这些步骤的更多详细说明和步骤，请参阅 [直接查看Snowflake文档](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}.
