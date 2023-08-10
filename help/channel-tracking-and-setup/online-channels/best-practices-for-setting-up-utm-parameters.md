---
unique-page-id: 18874732
description: 设置UTM参数的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 设置UTM参数的最佳实践
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
feature: UTM Parameters
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# 设置UTM参数的最佳实践 {#best-practices-for-setting-up-utm-parameters}

UTM参数是切分营销数据的好方法。 [!DNL Marketo Measure] 使用和捕获所有UTM参数以填充Salesforce和 [!DNL Marketo Measure] 应用程序。 有了这些信息，您将能够详细了解您的潜在客户、机会和已结/成功的交易的来源。

您可以利用 [Google URL生成器](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"} to set up your UTM parameters and add them to your links within your marketing efforts. Use this [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} 如果您希望以更简单的方式跟踪所有UTM链接。

## 每个参数的高级别值 {#high-level-values-for-each-parameter}

**utm_medium**：此字段映射到中字段。 使用utm_medium表示高级通道。

例如， [!UICONTROL Social]， CPC，电子邮件， Web，自然

请勿使用此字段调用子渠道。

**utm_source**：此字段映射到接触点源字段。 使用utm_source定义潜在客户来源的子渠道。

例如，Facebook、Twitter、Linkedin、Drip_email、Email_blast、新闻稿。

保持简单。 请勿使用此参数表示广告类型，如重定位、赞助等。 请勿添加utm_source = homepage、webdirect、website。 [!DNL Marketo Measure] 将自动为您填写此信息。

**utm_campaign**：此字段映射到广告营销活动名称。 使用utm_campaign表示促销活动的标题，如广告平台中的标题，或内部引用的标题。

此参数也是表示地理位置、广告网络类型（显示v.搜索）等的良好参数。

我们建议使用下划线而不是空格，并避免使用标点。 这减少了浏览器在读取参数时编码错误的可能性。

例如，AU_Idea_for_an_App_50k

**utm_content**：此信息映射到广告内容。 在utm_content参数中使用广告标题。 如果是图像广告，请使用广告标题并包含广告尺寸。

例如， [广告标题] 200x400像素

**utm_term**：这映射到关键词文本。 此参数用于表示与广告触发相关的关键词。

如果没有与广告相关的关键词，请将此参数留空。

例如，iPhone应用程序创意

**保持简单明了。 不要重复工作、术语和渠道。**

我们将UTM层次结构想象如下：

中> [!UICONTROL Source] > [!UICONTROL Campaign] > [!UICONTROL Content/Term]

例如，如果 [!UICONTROL display] 广告位于Facebook上，我们建议执行以下操作：

fakewebsite.com/

？utm_medium=social

&amp;utm_source=facebook

&amp;utm_campaign=Display_campaign_ID

&amp;utm_content=content_of_campaign

请注意，在本例中，术语/渠道不会重复，并且不会使用utm_term。

如果有任何问题，请联系Adobe客户团队（您的客户经理）或 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
