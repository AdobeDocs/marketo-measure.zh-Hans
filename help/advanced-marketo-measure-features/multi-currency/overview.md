---
unique-page-id: 27656735
description: 概述 —  [!DNL Marketo Measure]  — 产品文档
title: 概述
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
feature: Multi-Currency
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 1%

---

# 概述 {#overview}

今天， [!DNL Marketo Measure] 应用程序仅支持单一货币（假定为USD），而我们知道并知道我们世界各地的客户需要报告自己的公司和用户货币。 通过此功能，用户可以在查看报告支出或销售收入时在CRM中使用的相同货币之间进行切换。 [!DNL Marketo Measure].

## 可用性 {#availability}

第2层及更高层。

## 要求 {#requirements}

[!DNL Marketo Measure] 将自动从客户的CRM中提取货币设置。 中的手动配置 [!DNL Marketo Measure] 不再需要匹配CRM。 可在“常规”页面中的“CRM”下找到货币设置。

在 [!DNL Salesforce]，客户必须启用“激活多种货币”。 （可选）客户也可以选择“是，我要启用高级币种管理”。

在Dynamics中，客户可以在其“设置”中为多种货币设置静态汇率。 Dynamics中没有“高级货币管理”的概念。

## 条款 {#terms}

| **术语** | 描述 |
|---|---|
| **高级货币** | 客户启用了高级货币管理和多种货币，这意味着他们可以在不同的时间期拥有不同的折换率。 |
| **公司货币** | 这些是组织在CRM中列出并声明的各种货币，所有货币都具有兑换率。 [!DNL Marketo Measure] 将导入这些值，并在我们的产品中向用户提供这些货币。 |
| **货币区域设置** | 用于组织的单一货币，在公司信息页面上设置。 |
| **本地货币（或用户货币）** | 在用户配置文件中为单个用户设置的货币，以便他们能够查看任何金额的本地货币。 组织必须先声明和设置货币，用户才能选择其本地货币。 |
| **单一货币** | 用于在CRM中未使用多种货币，但其组织以其他货币运行的客户，因此他们具有“货币区域设置”。 这仍然是组织的单一货币，但没有任何转化。 |
| **简单货币** | 客户启用了多种货币，但每种货币的静态兑换率均相同。 |
