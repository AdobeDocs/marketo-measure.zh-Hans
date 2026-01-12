---
description: A/B测试设置和报告 —  [!DNL Marketo Measure]
title: A/B测试设置和报告
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
feature: A/B Testing
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---


# A/B测试设置和报告 {#a-b-testing-set-up-and-reporting}

[!DNL Marketo Measure] A/B测试集成允许您跟踪[优化的](https://www.optimizely.com/){target="_blank"}和VWO网站实验对收入的影响。 本文提供了有关如何将[!DNL Marketo Measure]个A/B测试部分添加到潜在客户、[!UICONTROL Contact]、案例和[!UICONTROL Opportunity]页面布局的说明。 还包括有关运行[!DNL Marketo Measure] A/B报告类型的一般报告实践和建议。

## 设置 {#set-up}

添加有关Lead、Contact、Case和Opportunity的[!DNL Marketo Measure] A/B测试部分。 通过[!DNL Marketo Measure] A/B测试集成，您可以优化地跟踪[VWO](https://www.optimizely.com/){target="_blank"}和[VWO](https://vwo.com/){target="_blank"}网站实验对收入的影响。

1. 验证您是否正在使用包[!DNL Marketo Measure] v3.9或更高版本。 您可以通过转到[!UICONTROL Salesforce] >[!UICONTROL Set Up] > [!UICONTROL Installed packages]来执行此操作。
1. 编辑潜在客户页面布局并将&#x200B;**[!DNL Marketo Measure]A/B测试**&#x200B;相关列表添加到该页面。

   ![显示正在添加的Marketo Measure A/B测试相关列表的潜在客户页面布局编辑器](assets/1.png)

1. 单击[!UICONTROL Wrench]按钮。 从所选字段列表中删除库存“Id”字段。 添加&#x200B;**[!UICONTROL Experiment]**、**[!UICONTROL Variation]**&#x200B;和&#x200B;**[!UICONTROL DateReported]**&#x200B;字段。 将“[!UICONTROL Sort by]”更改为&#x200B;**[!UICONTROL Date Reported]**，然后在下拉列表中选择&#x200B;**[!UICONTROL Descending]**。

   ![字段配置对话框，显示具有排序设置的试验、变量和日期报告字段](assets/2.png)

1. 在[!UICONTROL Buttons]下，取消选中&#x200B;**[!UICONTROL New]**。

   ![按钮部分显示正在取消选择的新按钮](assets/3.png)

1. 请联系您的[!DNL Marketo Measure]代表或[Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}以启用该功能。

## 报告 {#reporting}

客户可以访问几个[!DNL Marketo Measure]个A/B报告类型，这些类型允许您报告与潜在客户、联系人和机会相关的A/B测试：

* [!DNL Marketo Measure]个A/B测试集
* 与联系人的[!DNL Marketo Measure]个A/B测试集
* [!DNL Marketo Measure]个A/BTests和潜在客户
* [!DNL Marketo Measure]个具有机会的A/B测试

![显示Lead、Contact和Opportunity的Marketo Measure A/B测试报告类型的报告列表](assets/4.png)

A/B报告类型用于报告哪些Lead或Contact或Opportunity参加了A/B测试。 这些报告还会向您显示与A/B测试所暴露的Opportunity相关的收入额。

请注意， Optimizly/VWO是一个内容变体平台，而不是营销渠道，这一点很重要。 因此，这[!DNL Marketo Measure] A/B报告类型与Buyer Touchpoint报告使用方式不同。 买方接触点报表类型用于了解哪个营销渠道（付费广告、Web直播、社交）将潜在客户或联系人引导至特定页面。 但是，[!DNL Marketo Measure] A/B报告类型不能用于报告变量如何影响Lead或Opportunity。 由于A/B测试变体不是渠道，因此有关变体的详细信息不会显示在购买者接触点上。

以下是报告A/B测试时建议使用的一些字段，以帮助提高清晰度和insight：

* 商机已转化
* 试验
* 试验Id
* 变量
* 变量ID
* 报告日期

## [!DNL Salesforce]示例报告 {#salesforce-example-reports}

**[!DNL Marketo Measure]个A/B测试与潜在客户**

![显示Marketo Measure A/B测试及包含试验和变体的潜在客户数据的示例Salesforce报告](assets/5.png)

**[!DNL Marketo Measure]个A/B测试（带有机会）**

![示例Salesforce报告显示具有Opportunity数据的Marketo Measure A/B测试，包括收入影响](assets/6.png)
