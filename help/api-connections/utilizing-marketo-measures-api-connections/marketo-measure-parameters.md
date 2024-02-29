---
unique-page-id: 18874608
description: "[!DNL Marketo Measure] 参数 —  [!DNL Marketo Measure]"
title: '"[!DNL Marketo Measure] 参数”'
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
feature: APIs, Integration, UTM Parameters
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# [!DNL Marketo Measure] 参数 {#marketo-measure-parameters}

## [!DNL Marketo Measure] 参数说明 {#marketo-measure-parameters-explained}

要进一步了解UTM的使用， [!DNL Marketo Measure] 将自定义参数附加到中的广告 [!DNL Google] adwords、Bing Ads和 [!DNL Facebook] 广告。 [!DNL Marketo Measure] 与这些平台集成以自动化大部分设置过程。 如果您选择使用自动标记， [!DNL Marketo Measure] 会自动将其参数附加到广告的URL。 [!DNL Marketo Measure] 系统还会自动从平台下载营销成本，并将其加载到 [!DNL Marketo Measure] 应用程序。

不带参数的URL示例：

`http://adobe.com/landing-page?myParam=foo`

URL示例 [!DNL Marketo Measure] 参数：

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## AdWords参数 {#adwords-parameters}

* `_bk={keyword}`
   * 表示人员在搜索引擎中使用的关键词。
   * 它类似于UTM术语参数。

* `_bt={creative}`
   * 表示创作ID或名称。
   * 它类似于UTM内容参数。

* `_bm={matchtype}`
   * 表示关键字的匹配程度。
   * 关键词匹配类型有助于控制哪些搜索会触发您的广告。 例如，您可以使用广泛匹配将您的广告显示给广泛的受众，或者使用完全匹配来关注特定的客户组。
   * 三种匹配类型是：广泛、模糊和精确。

>[!TIP]
>
>有关匹配类型的详细信息， [以下是一篇相关的AdWords文章](https://support.google.com/adwords/answer/2497836?hl=en){target="_blank"}.

* `_bn={network}`
   * 表示广告网络类型 —  [显示或搜索](https://support.google.com/adwords/answer/1752334?hl=en){target="_blank"}.
   * 这与UTM源参数类似。

* `_bg={adgroupID}`
   * 表示广告所属的广告组的ID

>[!NOTE]
>
>我们不支持重定向URL参数。

## Bing Ads参数 {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## facebook参数 {#facebook-parameters}

* `_bf ={creative}`
   * 这表示创作ID或名称
