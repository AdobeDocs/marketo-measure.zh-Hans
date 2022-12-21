---
unique-page-id: 18874773
description: A/B测试设置和报告 —  [!DNL Marketo Measure]  — 产品文档
title: A/B测试设置和报告
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# A/B测试设置和报告 {#a-b-testing-set-up-and-reporting}

的 [!DNL Marketo Measure] A/B测试集成允许您跟踪 [优化](https://optimizely.com/){target=&quot;_blank&quot;}和VWO站点实验。 本文指南提供了有关如何添加 [!DNL Marketo Measure] A/B测试部分， [!UICONTROL Contact]、案例和 [!UICONTROL Opportunity] 页面布局。 我们还将介绍有关运行的一般报告实践和建议 [!DNL Marketo Measure] A/B报表类型。

## 设置 {#set-up}

添加 [!DNL Marketo Measure] A/B测试部分，介绍潜在客户、联系人、案例和机会。 [!DNL Marketo Measure] A/B测试集成允许您跟踪 [优化](https://optimizely.com/){target=&quot;_blank&quot;}和 [VWO](https://vwo.com/){target=&quot;_blank&quot;}站点实验。

1. 验证您使用的是包 [!DNL Marketo Measure] v3.9或更高版本。 您可以通过以下路径执行此操作： [!UICONTROL Salesforce] >[!UICONTROL Set Up] > [!UICONTROL Installed packages].
1. 编辑潜在客户页面布局并添加 **[!DNL Marketo Measure]A/B测试** 与页面相关的列表。

   ![](assets/1.png)

1. 单击 [!UICONTROL Wrench] 按钮。 从“选定”字段列表中删除“Id”字段。 添加 **[!UICONTROL Experiment]**, **[!UICONTROL Variation]**&#x200B;和 **[!UICONTROL DateReported]** 字段。 更改&quot;[!UICONTROL Sort by]“” **[!UICONTROL Date Reported]**，然后选择 **[!UICONTROL Descending]** 中。

   ![](assets/2.png)

1. 在 [!UICONTROL Buttons]，取消选中 **[!UICONTROL New]**.

   ![](assets/3.png)

1. 联系您的 [!DNL Marketo Measure] rep或rep [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}以启用该功能。

## 报表 {#reporting}

客户可以访问 [!DNL Marketo Measure] A/B报表类型，用于报告A/B测试中与潜在客户、联系人和机会有关的内容：

* [!DNL Marketo Measure] A/BTest
* [!DNL Marketo Measure] 具有联系人的A/BTest
* [!DNL Marketo Measure] 含潜在客户的A/BTest
* [!DNL Marketo Measure] 具有机会的A/BTest

![](assets/4.png)

A/B报表类型用于报告哪些Lead或Contact或Opportunity已经接触过A/B测试。 此外，这些报表还可显示与A/B测试所暴露的Opportunity关联的收入额。

请务必注意， Optimizely/VWO是内容变体平台，而不是营销渠道。 因此，这些 [!DNL Marketo Measure] A/B报表类型的使用方式与购买者接触点报表不同。 购买者接触点报表类型用于了解哪些营销渠道（例如付费广告、Web直接、社交）将潜在客户或联系人推送到特定页面。 但是， [!DNL Marketo Measure] A/B报表类型不能用于报告变体对Lead或Opportunity的影响。 此外，由于A/B测试变体不是渠道，因此有关该变体的详细信息不会显示在买方接触点上。

以下是我们建议在报告A/B测试时使用的一些常见字段，以帮助提高清晰度和洞察力：

* 已转换的潜在客户
* 试验
* 实验ID
* 变量
* 变量ID
* 报告日期

## [!DNL Salesforce] 示例报表 {#salesforce-example-reports}

**[!DNL Marketo Measure]含潜在客户的A/B测试**

![](assets/5.png)

**[!DNL Marketo Measure]A/B测试（带机会）**

![](assets/6.png)
