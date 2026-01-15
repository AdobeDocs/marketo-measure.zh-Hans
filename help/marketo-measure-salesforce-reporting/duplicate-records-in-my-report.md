---
description: “我的报表”指南中针对Marketo Measure用户的重复记录
title: 我的报告中的重复记录
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
feature: Reporting
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---

# 我的报告中的重复记录 {#duplicate-records-in-my-report}

>[!NOTE]
>
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但在您的CRM中仍会看到“[!DNL Bizible]”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

当您深入研究[!DNL Marketo Measure]中的[!DNL Salesforce]报告时，您可能会开始在报告中找到“重复”记录。 当您查看[!DNL Marketo Measure]现成报告时，您可能会遇到这种感觉。

在使用“采购员接触点”对象或Buyer Attribution Touchpoint对象进行报告时，请务必了解一点，您不再报告销售线索、联系人或业务机会的数量，而是报告与这些标准对象（销售线索、联系人、业务机会）关联的“采购员接触点”或“采购员归因接触点”的数量。

让我们以以下报表为例：

这是具有买方接触点的&#x200B;**联系人**&#x200B;报告。 同样，这意味着我们查看的是与单个联系人关联的接触点计数。

![这是“具有采购员接触点的联系人”报告。 这再次意味着](assets/marketo-reports-1.gif)

如您所见，报告中似乎有三个詹姆斯·威廉姆斯的联系人，因此您可能会想，“重复！”

但是，此报表显示了与James相关的接触点数量。 在报表中，您可以看到James具有单个FT（首次接触）、单个LC、Form（潜在客户创建接触）和PostLC接触点（在LC接触点之后发生的表单提交）。

如果要了解“联系人计数”，则可以使用“计数 — 首次联系”、“计数潜在客户创建联系”或“计数 — U型”字段了解有多少联系人进行了营销互动。

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 教程： Stock SFDC报告](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/stock-salesforce-reports){target="_blank"}
