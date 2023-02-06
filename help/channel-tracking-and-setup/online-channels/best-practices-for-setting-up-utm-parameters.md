---
unique-page-id: 18874732
description: 设置UTM参数的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 设置UTM参数的最佳实践
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# 设置UTM参数的最佳实践 {#best-practices-for-setting-up-utm-parameters}

UTM参数是对营销数据进行细分的绝佳方法。 [!DNL Marketo Measure] 使用并捕获所有UTM参数，以填充Salesforce和 [!DNL Marketo Measure] 应用程序。 利用此信息，您将能够详细了解潜在客户、商机和已结/已赢交易的来源。

您可以利用 [Google URL生成器](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"} to set up your UTM parameters and add them to your links within your marketing efforts. Use this [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} 如果您希望更轻松地跟踪所有UTM链接，请执行以下操作。

## 每个参数的高级值 {#high-level-values-for-each-parameter}

**utm_medium**:此字段映射到“中”字段。 使用utm_medium表示高级别通道。

例如： [!UICONTROL Social], CPC，电子邮件， Web，免费

请勿使用此字段调用子渠道。

**utm_source**:此字段映射到接触点源字段。 使用utm_source定义潜在客户源自的子渠道。

例如：Facebook、Twitter、Linkedin、Drip_email、Email_blast、新闻通讯。

保持简单。 请勿使用此参数表示广告类型，如重定向、赞助商等。 请勿添加utm_source = homepage、webdirect、website。 [!DNL Marketo Measure] 会自动为您填写此信息。

**utm_campaign**:此字段映射到广告促销活动名称。 使用utm_campaign表示广告平台中存在的营销活动标题，或者内部引用的营销活动标题。

这也是表示地理位置、广告网络类型（显示v.搜索）等的一个好参数。

我们建议使用下划线而不是空格，并避免使用标点符号。 这样可以降低浏览器在读取参数时对错误进行编码的可能性。

例如：AU_Idea_for_an_App_50k

**utm_content**:这会映射到广告内容。 在utm_content参数中使用广告标题。 如果它是图像广告，请使用广告标题并包含广告维度。

例如： [广告标题] 200x400px

**utm_term**:这会映射到关键词文本。 使用此参数表示与广告触发相关的关键词。

如果没有与广告相关的关键词，请将此参数留空。

例如：iPhone应用程序构思

**简明扼要。 请勿重复工作、术语和渠道。**

我们设想UTM层次结构如下：

中> [!UICONTROL Source] > [!UICONTROL Campaign] > [!UICONTROL Content/Term]

例如：如果 [!UICONTROL display] 广告放置在Facebook上，我们建议执行以下操作：

fakewebsite.com/

?utm_medium=social

&amp;utm_source=facebook

&amp;utm_campaign=Display_campaign_ID

&amp;utm_content=content_of_campaign

请注意，术语/渠道不重复，并且此例中不使用utm_term。

如有任何问题，请联系您的客户成功经理或 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
