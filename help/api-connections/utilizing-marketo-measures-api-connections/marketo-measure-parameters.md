---
unique-page-id: 18874608
description: '"[!DNL Marketo Measure] 参数 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] 参数”'
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# [!DNL Marketo Measure] 参数 {#marketo-measure-parameters}

## [!DNL Marketo Measure] 参数说明 {#marketo-measure-parameters-explained}

为了从使用UTM获得更深入的洞察， [!DNL Marketo Measure] 将自定义参数附加到 [!DNL Google] AdWords、Bing Ads和 [!DNL Facebook] 广告。 [!DNL Marketo Measure] 与这些平台集成，以自动完成大部分设置过程。 如果您选择使用自动标记， [!DNL Marketo Measure] 会自动将其参数附加到您广告的URL。 [!DNL Marketo Measure] 还将自动从平台下载营销成本，并将其加载到 [!DNL Marketo Measure] 应用程序。

不带参数的URL示例：

`http://adobe.com/landing-page?myParam=foo`

URL的示例 [!DNL Marketo Measure] 参数：

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## AdWords参数 {#adwords-parameters}

* `_bk={keyword}`
   * 表示搜索引擎中使用的人员的关键词。
   * 它类似于UTM术语参数。

* `_bt={creative}`
   * 表示创作ID或名称。
   * 它类似于UTM内容参数。

* `_bm={matchtype}`
   * 表示关键词匹配的程度。
   * 关键词匹配类型有助于控制哪些搜索会触发您的广告。 例如，您可以使用广泛匹配向广泛受众显示您的广告，也可以使用精确匹配来了解特定的客户群。
   * 三种匹配类型为：宽泛、模糊且准确。

>[!NOTE]
>
>有关匹配类型的更多信息，请 [这是一篇相关的AdWords文章](https://support.google.com/adwords/answer/2497836?hl=en){target="_blank"}.

* `_bn={network}`
   * 表示广告网络类型 —  [显示或搜索](https://support.google.com/adwords/answer/1752334?hl=en){target="_blank"}.
   * 这类似于UTM Source参数。

* `_bg={adgroupID}`
   * 表示广告所属的广告组的ID

## Bing Ads参数 {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## Facebook参数 {#facebook-parameters}

* `_bf ={creative}`
   * 这表示创作ID或名称
