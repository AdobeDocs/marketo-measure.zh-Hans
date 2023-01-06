---
unique-page-id: 27656735
description: 概述 —  [!DNL Marketo Measure]  — 产品文档
title: 概述
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# 概述 {#overview}

今天， [!DNL Marketo Measure] 应用程序仅支持单一货币（假定为美元），而我们知道并了解到世界各地的客户需要报告他们自己的公司货币和用户货币。 此功能为用户在查看报告的支出或销售收入时在不同货币之间切换提供了基础。

## 可用性 {#availability}

第2层及更高层。

## 要求 {#requirements}

在 [!DNL Salesforce]，则客户必须启用“激活多种货币”。 （可选）客户还可以选择“是，我要启用高级货币管理”。

在Dynamics中，客户可以在其设置中为多种货币设置静态汇率。 Dynamics中没有“高级货币管理”的概念。

## 条款 {#terms}

| **术语** | 描述 |
|---|---|
| **高级货币** | 客户启用了“高级货币管理”和“多币种”，这意味着客户在不同时间段的换算率可能不同。 |
| **公司货币** | 这些是CRM中由组织列出并声明的各种货币，所有货币均具有兑换率。 [!DNL Marketo Measure] 将导入这些值，并将这些货币提供给我们产品中的用户。 |
| **货币区域设置** | 在公司信息页面上设置的用于组织的单一货币。 |
| **本地货币（或用户货币）** | 在用户配置文件中为单个用户设置的货币，以便他们能够以自己的当地货币查看任何金额。 组织必须先声明并设置货币，用户才能选择其本地货币。 |
| **单一货币** | 用于在CRM中不使用多种货币，但其组织以其他货币运行的客户，因此他们具有“货币区域设置”。 对于组织而言，这仍是单一货币，但不进行任何兑换。 |
| **简单货币** | 客户启用了“多种货币”，但其每种货币的换算率是静态的。 |