---
unique-page-id: 18874720
description: 竞价管理工具如何影响 [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: 竞价管理工具如何影响 [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
feature: APIs, Integration, UTM Parameters
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# 竞价管理工具如何影响[!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

了解竞价管理平台如何影响[!DNL Marketo Measure]跟踪AdWords和BingAds的能力，以及如何使用我们的参数设置跟踪模板以确保所有内容正确跟踪。

Kenshoo和Marin是绝佳的工具，允许营销人员使用不同的搜索引擎跟踪、管理和优化其广告促销活动。 为了将[!DNL Marketo Measure]参数附加到这些广告URL，您需要使用我们的[!DNL Marketo Measure]参数设置跟踪模板。 无法将您的广告平台连接到您的[!DNL Marketo Measure]帐户并启用自动标记，因为这会导致[!DNL Marketo Measure]标记系统与Kenshoo/Marin的标记系统竞争。 这会导致更改并错误附加我们的参数。 若要避免出现这种情况，需要在Kenshoo和Marin中设置包含[!DNL Marketo Measure]参数的跟踪模板。

## 对于[!DNL Adwords]帐户 {#for-adwords-accounts}

按如下方式设置跟踪模板：

* 单击&#x200B;**[!UICONTROL Campaigns]**&#x200B;选项卡。
* 单击侧面导航栏中的&#x200B;**[!UICONTROL Shared library]**&#x200B;链接。
* 单击&#x200B;**URL选项**。
* 在“跟踪模板”旁边，单击&#x200B;**编辑**。
* 填写URL：

   * 如果您的所有广告URL都有“？” 在其中，使用此URL：
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * 如果您的任何广告URL都不包含“？” 在其中，使用此URL：
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## 对于[!DNL Bing Ads]帐户 {#for-bing-ads-accounts}

按如下方式设置跟踪模板：

* 单击&#x200B;**[!UICONTROL Campaigns]**&#x200B;选项卡。
* 单击侧面导航栏中的&#x200B;**[!UICONTROL Shared library]**&#x200B;链接。
* 单击&#x200B;**URL选项**。
* 在“跟踪模板”旁边，单击&#x200B;**编辑**。
* 填写URL：

   * 如果您的所有广告URL都有“？” 在其中，使用此URL：
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * 如果您的任何广告URL都不包含“？” 在其中，使用此URL：
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
