---
unique-page-id: 18874720
description: 竞价管理工具如何影响 [!DNL Marketo Measure] - [!DNL Marketo Measure]  — 产品文档
title: 竞价管理工具如何影响 [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
feature: APIs, Integration, UTM Parameters
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# 竞价管理工具如何影响 [!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

了解竞价管理平台如何影响 [!DNL Marketo Measure] 能够跟踪AdWords和BingAds，以及如何使用我们的参数设置跟踪模板以确保所有内容正确跟踪。

Kenshoo和Marin是绝佳的工具，允许营销人员使用不同的搜索引擎跟踪、管理和优化其广告促销活动。 为了 [!DNL Marketo Measure] 附加到这些广告URL的参数，您将需要使用 [!DNL Marketo Measure] 参数。 无法将您的广告平台连接到 [!DNL Marketo Measure] 帐户并启用自动标记，因为它会导致 [!DNL Marketo Measure] 标记系统与Kenshoo/Marin的标记系统竞争。 这会导致更改并错误附加我们的参数。 要绕过此情况，请使用跟踪模板 [!DNL Marketo Measure] 参数需要在Kenshoo和Marin中设置。

## 对象 [!DNL Adwords] 帐户 {#for-adwords-accounts}

按如下方式设置跟踪模板：

* 单击 **[!UICONTROL Campaigns]** 选项卡。
* 单击 **[!UICONTROL Shared library]** 侧面导航栏中的链接。
* 单击 **URL选项**.
* 单击“跟踪模板”旁边的 **编辑**.
* 填写URL：

   * 如果您的所有广告URL都有“？” 在其中，使用此URL：
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * 如果您的任何广告URL都不包含“？” 在其中，使用此URL：
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## 对象 [!DNL Bing Ads] 帐户 {#for-bing-ads-accounts}

按如下方式设置跟踪模板：

* 单击 **[!UICONTROL Campaigns]** 选项卡。
* 单击 **[!UICONTROL Shared library]** 侧面导航栏中的链接。
* 单击 **URL选项**.
* 单击“跟踪模板”旁边的 **编辑**.
* 填写URL：

   * 如果您的所有广告URL都有“？” 在其中，使用此URL：
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * 如果您的任何广告URL都不包含“？” 在其中，使用此URL：
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
