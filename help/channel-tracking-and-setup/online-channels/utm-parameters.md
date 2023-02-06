---
unique-page-id: 18874606
description: UTM参数 —  [!DNL Marketo Measure]  — 产品文档
title: UTM参数
exl-id: 2b20f3c4-1f39-4ac5-bad1-cb1d630d60e9
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 0%

---

# UTM参数 {#utm-parameters}

标记URL是一种捕获有关数字营销工作数据的简单而有效的方法。 这是向收集和记录数据的URL的末尾添加参数的过程。 最常用的参数是Urchin跟踪模块(UTM)，该模块受Google支持。 有五个主要的UTM参数可用：媒介、来源、营销活动、内容和术语。 下一节将更详细地讨论这些内容。

UTM参数可手动添加到URL中，或通过自动标记来附加到某些平台（例如AdWords）中。 自动标记可自动将参数附加到URL的过程。 此外， [URL生成器](https://ga-dev-tools.appspot.com/campaign-url-builder/){target="_blank"} 以加快手动标记URL的速度。 使用URL生成器，您只需指定每个参数所使用的值即可，生成器会为您设置URL格式。

## 什么是UTM参数？ {#what-are-utm-parameters}

要了解UTM参数的工作方式，让我们查看一个不带UTM的典型URL。

`http://www.adobe.com`

现在，让我们查看包含UTM的URL:

`http://www.adobe.com?utm_medium=socialmedia&utm_source =facebook&utm_campaign=seasonal-sale&utm_content=photo-400x700px`

如您所见，第二个链接包含的文本要多得多。 UTM参数始终位于顶级域（本示例中为.com）之后，并以问号开头。 在此之后，参数的顺序无关紧要，但建议遵循一致的命名约定。 需要在每个参数之间放置与号以分隔每个UTM。 现在，我们可以进一步详细了解每个参数代表的内容。

了解 [设置UTM参数的最佳实践](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md).

**utm_medium**

* Medium标识您用来营销公司的工具。
* 它回答了一个问题：“他们怎么对你？”
* 它表示最高级别的渠道。
* 社交媒体、电子邮件、免费搜索和付费搜索都是潜在中值的示例。
* 此参数将数据映射到 [!DNL Marketo Measure] “中”字段。
* _[!DNL Marketo Measure]最佳实践：_ 请勿使用此字段调用子渠道，否则，在生成实际渠道的报表时可能会遇到困难。 使用它来识别您的营销工具或渠道。 例如，如果您想使用电子邮件来营销产品，则媒介为电子邮件。

**utm_source**

* 来源标识作为流量源的子渠道。
* 它回答了一个问题：“这人从哪来？”
* 在社交媒体示例中，流量源是所使用的社交媒体平台。
   * 在本例中， [!DNL Facebook] 是源值。 其他示例包括Twitter和Instagram。 如果UTM Medium为 [!DNL Paid Search]，而UTM源可以是AdWords或BingAds。

* 此参数映射到 [!DNL Marketo Measure] SFDC中的“接触点源”字段。
* _[!DNL Marketo Measure]最佳实践：_ 此参数会跟踪您的流量源，因此不适合使用它来指示广告类型，例如重定向、赞助商等。 它最适合用于跟踪较高级别的子渠道。 记住，你在回答“我的流量来自哪里？”的问题 您正在查找反向链接。 在此示例中，UTM源是您的广告所在的位置（不是实际的网页，因为它会在标记外自动跟踪）。 如果您跟踪的是滴漏电子邮件营销活动，则滴漏电子邮件是源。

**utm_campaign**

* 促销活动用于标识特定的营销活动。
* 它回答了一个问题：“他们为什么会来找你？”
* 使用此标记表示广告营销活动在中存在的名称 [!DNL Google AdWords] 或 [!DNL BingAds]，或指明您在内部识别营销活动时使用的名称。 您甚至可以使用此标记指定其他信息，如地理位置或广告网络类型。
* 此参数映射到 [!DNL Marketo Measure] SFDC中的“广告促销活动名称字段”。
* _[!DNL Marketo Measure]最佳实践_:在确定促销活动名称时，请避免在词语之间使用标点符号或空格，因为使用它们可能会导致浏览器编码错误。 为获得最佳结果，请改用下划线。

**utm_content**

* 如果要跟踪单个网页上存在的多个营销文章，请使用UTM内容参数。 例如，如果您有“请求演示”按钮和“注册参加我们的每周新闻稿”按钮，并且想知道哪个新闻稿的流量最多，则需要为每个新闻稿命名并使用UTM内容标记来跟踪它们。 每段“内容”的名称即为标记的值。
* 此参数映射到 [!DNL Marketo Measure] SFDC中的“广告内容”字段。
* _[!DNL Marketo Measure]最佳实践_:这是一个可选值，但 [!DNL Marketo Measure] 建议使用它。 此标记与您要跟踪的广告或营销文章的标题关联。 如果您使用图像广告，请确保将图像的尺寸写入其标题中。

**utm_term**

* 术语与UTM Content（UTM内容）参数类似。 术语非常适用于在付费促销活动的广告中识别关键词。 如果您使用自动标记功能，这将为您完成。 如果您没有使用广告平台的自动标记功能，请务必小心添加要跟踪的所有关键词。
* 此参数映射到 [!DNL Marketo Measure] SFDC中的“关键词文本”字段。
* _[!DNL Marketo Measure]最佳实践_:UTM术语标记是可选的，但非常适合跟踪关键词。 仔细检查拼写并避免使用特殊字符。 如果需要多个词，请尝试使用下划线或根本没有空格。

每个参数都会收集与分配值相关的信息。 每个标记的值允许您跟踪和排序所有数字营销活动并回答以下问题：在哪里，如何，为什么？

这是UTM参数的图表 [!DNL Marketo Measure] 解析以及与之关联的相应接触点字段：

| **UTM参数** | **对应 [!DNL Marketo Measure] 字段** |
|---|---|
| utm_medium | 中 |
| utm_source | 接触点源 |
| utm_campaign | 广告促销活动名称 |
| utm_content | 广告内容 |
| utm_term | 关键词文本 |
