---
unique-page-id: 18874720
description: 竞价管理工具如何影响 [!DNL Marketo Measure] - [!DNL Marketo Measure]  — 产品文档
title: 竞价管理工具如何影响 [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# 竞价管理工具如何影响 [!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

了解竞价管理平台如何影响 [!DNL Marketo Measure] 能够跟踪AdWords和BingAds，以及如何使用我们的参数设置跟踪模板，以确保正确跟踪所有内容。

Kenshoo和Marin是一款出色的工具，可让营销人员通过不同的搜索引擎跟踪、管理和优化其广告促销活动。 为 [!DNL Marketo Measure] 要附加到这些广告URL的参数，您需要使用我们的 [!DNL Marketo Measure] 参数。 无法将广告平台与 [!DNL Marketo Measure] 帐户并启用自动标记，因为它会导致 [!DNL Marketo Measure] 标记系统与Kenshoo/Marin的标记系统相竞争。 这会导致更改和错误地附加参数。 要规避此问题，请使用 [!DNL Marketo Measure] 需要在Kenshoo和Marin中设置参数。

## 对于 [!DNL Adwords] 帐户 {#for-adwords-accounts}

按如下方式设置跟踪模板：

* 单击 **[!UICONTROL Campaigns]** 选项卡。
* 单击 **[!UICONTROL Shared library]** 链接。
* 单击 **URL选项**.
* 在“跟踪模板”旁边，单击 **编辑**.
* 填写URL:

   * 如果您的所有广告URL都具有“？” 在中，使用以下URL:
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * 如果您的所有广告URL都没有“？” 在中，使用以下URL:
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## 对于 [!DNL Bing Ads] 帐户 {#for-bing-ads-accounts}

按如下方式设置跟踪模板：

* 单击 **[!UICONTROL Campaigns]** 选项卡。
* 单击 **[!UICONTROL Shared library]** 链接。
* 单击 **URL选项**.
* 在“跟踪模板”旁边，单击 **编辑**.
* 填写URL:

   * 如果您的所有广告URL都具有“？” 在中，使用以下URL:
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * 如果您的所有广告URL都没有“？” 在中，使用以下URL:
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
