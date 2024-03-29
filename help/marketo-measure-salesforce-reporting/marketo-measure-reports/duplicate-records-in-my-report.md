---
unique-page-id: 18874634
description: 我的报告中的重复记录 —  [!DNL Marketo Measure]
title: 我的报告中的重复记录
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
feature: Reporting
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# 我的报告中的重复记录 {#duplicate-records-in-my-report}

>[!NOTE]
>
>您可能会看到说明“[!DNL Marketo Measure]”在文档中，但仍请参见“[!DNL Bizible]”（在您的CRM中）。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

当您潜入 [!DNL Marketo Measure] 报告位置 [!DNL Salesforce]，您可能会开始在报表中找到“重复”记录。 当您回顾时，您可能会遇到这种感觉 [!DNL Marketo Measure] 现成的报告。

在使用“采购员接触点”对象或“采购员归因接触点”对象进行报告时，请务必了解，您不再报告销售线索、联系人或业务机会的数量，而是报告与这些标准对象（销售线索、联系人、业务机会）关联的采购员接触点或采购员归因接触点的数量。

让我们以以下报表为例：

这是 **与采购员接触点进行联系** 报告。 同样，这意味着我们查看的是与单个联系人关联的接触点计数。

![](assets/1.gif)

如您所见，报告中似乎有三个詹姆斯·威廉姆斯的联系人，因此您可能会想，“重复！”

但是，此报表显示了与James相关的接触点数量。 在报表中，您可以看到James具有单个FT（首次接触）、单个LC、Form（潜在客户创建接触）和PostLC接触点（在LC接触点之后发生的表单提交）。

如果要了解“联系人计数”，则可以使用“计数 — 首次联系”、“计数潜在客户创建联系”或“计数 — U型”字段了解有多少联系人进行了营销互动。

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Tutorials：Stock SFDC报表](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/stock-salesforce-reports){target="_blank"}
