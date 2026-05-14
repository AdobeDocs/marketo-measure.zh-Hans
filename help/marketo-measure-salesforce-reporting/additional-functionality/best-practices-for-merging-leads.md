---
unique-page-id: 18874734
description: 合并潜在客户的最佳实践 —  [!DNL Marketo Measure]
title: 合并潜在客户的最佳实践
exl-id: d9293ed7-a794-4e52-a269-20a7fb36ce50
feature: Tracking
TQID: https://experienceleague.adobe.com/VonT7Suvlt5VjzPqZ9UWoVe3ZTpPsk4c-7q-0wLplA0
product_v2: id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 3%

---

# 合并潜在客户的最佳实践 {#best-practices-for-merging-leads}

在[!DNL Salesforce]中合并Lead时，最好始终保持谨慎，以确保不会丢失任何数据。

供您参考，这里提供了[!DNL Salesforce]支持团队中[如何合并潜在客户](https://help.salesforce.com/s/articleView?id=leads_merge.htm&language=en_US&type=5)的细目。

[!DNL Marketo Measure]的进入时间是选择填充在合并记录上的字段。 选择主记录后，验证是否选择了[!DNL Marketo Measure]字段以结转到新记录。

如果有包含[!DNL Marketo Measure]数据的多个记录，请确保主记录具有为首先创建的Lead选择的字段。 其他[!DNL Marketo Measure]数据将显示在分析部分中。 此外，请确保跟踪的Lead的电子邮件地址是保留的电子邮件地址，因为它允许我们继续使用任何新的归因数据更新该Lead。

从此处，您应该可以自由合并潜在客户，并且[!DNL Marketo Measure]数据将被传送到新记录中。

如果您有任何问题，请随时联系Adobe客户团队（您的客户经理）或[Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。

![](assets/1.jpg)
