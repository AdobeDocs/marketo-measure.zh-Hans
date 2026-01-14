---
description: 为什么您绝不应该删除Marketo Measure用户的接触点指南
title: 为什么绝不应该删除接触点
exl-id: e74c14ff-0399-4ee9-b732-6686823ff5c7
feature: Touchpoints
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 0%

---

# 为什么绝不应该删除接触点 {#why-you-should-never-delete-touchpoints}

如果您发现Opportunity上的某个接触点未正确分配归因点数，请联系您的客户经理以确定后续步骤。 在这些情况下，我们建议使用购买者的接触点抑制功能从SFDC和ROI仪表板中删除接触点。 您的客户经理可帮助创建这些规则。 请勿自己手动删除这些接触点。

[!DNL Marketo Measure]处理系统将不会注册已从SFDC中手动删除接触点。 截至目前，还没有触发程序向我们的系统发出信号以调整数据。 [!DNL Marketo Measure]不会自动推送另一个接触点来替换已删除的接触点，也不会将该接触点位置或归因重新分配给后续接触点。

删除接触点后，它会在归因数据中创建空洞。 通常，这将显示在Opportunity上的归因接触点中。 在下图中，已经删除了本来会收到Opportunity Creation触摸的接触点。 因此，此机会缺少OC接触点，并且此Opp的归因百分比之和不会达到100%。

![](assets/touchpoint-settings-10.png)

如果从SFDC中删除了接触点，请联系[Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}，请求重新导入您的数据。
