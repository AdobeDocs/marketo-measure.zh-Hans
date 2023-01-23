---
description: data warehouse访问 — 直接共享 — 产品文档
title: data warehouse访问 — 直接共享
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
source-git-commit: 36ee02b2dfc2651987f72fc7f02fe629717f02a0
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# data warehouse访问 — 直接共享 {#data-warehouse-access-direct-share}

## 要求 {#requirements}

为 [!DNL Marketo Measure] 要设置到data warehouse的直接共享，您必须满足以下要求。

* 您有自己的Snowflake实例。
* 您的Snowflake实例位于Azure East US 2Snowflake区域。
* 您提供 [!DNL Marketo Measure] 和您的Snowflake帐户id。

## 限制 {#limitations}

[!DNL Marketo Measure] 由于当前Snowflake直接共享限制，因此只能与位于Azure East US 2中的帐户设置Snowflake直接共享。 如果您要求在其他Snowflake地区提供您的数据，我们建议在位于Azure East US 2的Snowflake帐户中复制数据，并利用 [Snowflake数据库复制](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"} 功能，以复制您选择的Snowflake地区/帐户中的数据。

## 输入Snowflake帐户ID {#enter-snowflake-account-id}

打开 **设置** 部分，然后导航到 **data warehouse** 页面。 在 **直接共享** ，输入 [Snowflake帐户id](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} ，然后单击 **连接**.

![](assets/data-warehouse-access-direct-share-1.png)

## 访问共享 {#accessing-the-share}

为提供的帐户ID创建共享后，您必须完成 [设置步骤](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} 以访问Snowflake实例中的数据。

>[!NOTE]
>
>您可以选择所需的任何数据库名称。 您可以将权限分配给您选择的任何角色，但前提是该角色存在于您的Snowflake实例中。

* 使用帐户管理员角色

```
USE ROLE ACCOUNTADMIN
```

* 查看可用共享（这将显示已授出共享的名称）

```
SHOW SHARES
```

* 为共享创建数据库

```
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* 授予共享数据库的权限

```
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

有关从SnowflakeUI完成这些步骤的更多详细说明和步骤，请参阅 [Snowflake文档可直接](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}.
