---
unique-page-id: 18874773
description: A/B测试设置和报告 —  [!DNL Marketo Measure]
title: A/B测试设置和报告
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
feature: A/B Testing
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# A/B测试设置和报告 {#a-b-testing-set-up-and-reporting}

此 [!DNL Marketo Measure] A/B测试集成允许您跟踪 [优化的](https://www.optimizely.com/){target="_blank"} 和VWO现场实验。 本文介绍了如何添加 [!DNL Marketo Measure] A/B测试部分到潜在客户， [!UICONTROL Contact]、大小写和 [!UICONTROL Opportunity] 页面布局。 此外，还涵盖了常规报告实践以及运行建议 [!DNL Marketo Measure] A/B报表类型。

## 设置 {#set-up}

添加 [!DNL Marketo Measure] A/B测试部分包括Lead 、 Contact 、 Case和Opportunity。 [!DNL Marketo Measure] A/B测试集成允许您跟踪 [优化的](https://www.optimizely.com/){target="_blank"} and [VWO](https://vwo.com/){target="_blank"} 现场试验。

1. 验证您是否正在使用包 [!DNL Marketo Measure] v3.9或更高版本。 为此，您可以转到 [!UICONTROL Salesforce] >[!UICONTROL Set Up] > [!UICONTROL Installed packages].
1. 编辑潜在客户页面布局并添加 **[!DNL Marketo Measure]A/B测试** 页面的相关列表。

   ![](assets/1.png)

1. 单击 [!UICONTROL Wrench] 按钮。 从所选字段列表中删除库存“Id”字段。 添加 **[!UICONTROL Experiment]**， **[!UICONTROL Variation]**、和 **[!UICONTROL DateReported]** 字段。 更改”[!UICONTROL Sort by]”到 **[!UICONTROL Date Reported]**，并选择 **[!UICONTROL Descending]** 下拉菜单中。

   ![](assets/2.png)

1. 下 [!UICONTROL Buttons]，取消选中 **[!UICONTROL New]**.

   ![](assets/3.png)

1. 联系 [!DNL Marketo Measure] 代表或 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 以启用该功能。

## 报告 {#reporting}

客户可以访问多个 [!DNL Marketo Measure] 允许您报告与销售线索、联系人和业务机会有关的A/B测试的A/B报告类型：

* [!DNL Marketo Measure] A/B测试
* [!DNL Marketo Measure] A/BTests与联系人
* [!DNL Marketo Measure] A/BTests与潜在客户
* [!DNL Marketo Measure] A/BTests与机会

![](assets/4.png)

A/B报告类型用于报告哪些Lead或Contact或Opportunity参加了A/B测试。 这些报告还会向您显示与A/B测试所暴露的Opportunity相关的收入额。

请注意， Optimizly/VWO是一个内容变体平台，而不是营销渠道，这一点很重要。 因此，这些 [!DNL Marketo Measure] A/B报表类型的使用方式不同于买方接触点报表。 买方接触点报表类型用于了解哪个营销渠道（付费广告、Web直播、社交）将潜在客户或联系人引导至特定页面。 但是， [!DNL Marketo Measure] A/B报告类型不能用于报告变化如何影响Lead或Opportunity。 由于A/B测试变体不是渠道，因此有关变体的详细信息不会显示在购买者接触点上。

以下是报告A/B测试时建议使用的一些字段，以帮助提高清晰度和洞察力：

* 商机已转化
* 试验
* 试验Id
* 变量
* 变量ID
* 报告日期

## [!DNL Salesforce] 示例报表 {#salesforce-example-reports}

**[!DNL Marketo Measure]A/B测试（含潜在客户）**

![](assets/5.png)

**[!DNL Marketo Measure]使用Opportunity进行A/B测试**

![](assets/6.png)
