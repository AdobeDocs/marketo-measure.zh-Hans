---
description: 面向Marketo Measure用户的UTM参数指南
title: UTM参数
exl-id: 2b20f3c4-1f39-4ac5-bad1-cb1d630d60e9
feature: UTM Parameters
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '933'
ht-degree: 0%

---

# UTM参数 {#utm-parameters}

标记URL是一种简单而有效的捕获有关您的数字营销工作数据的方法。 是将参数添加到URL末尾以收集和记录数据的过程。 最常用的参数是Google支持的Urchin跟踪模块(UTM)。 提供了五个主要UTM参数：Medium、Source、Campaign、Content和Term。 下一节将更详细地讨论这些术语。

UTM参数可以手动添加到URL中，或通过自动标记特定平台（如AdWords ）进行附加。 自动标记可自动执行将参数附加到URL的过程。 还可以选择[URL生成器](https://ga-dev-tools.web.app/campaign-url-builder/){target="_blank"}来手动加快标记URL的速度。 使用URL生成器，您只需指定用于每个参数的值，生成器就会为您设置URL的格式。

## 什么是UTM参数？ {#what-are-utm-parameters}

要了解UTM参数的工作方式，请查看不带UTM的典型URL：

`http://www.adobe.com`

现在，让我们查看包含UTM的URL：

`http://www.adobe.com?utm_medium=socialmedia&utm_source =facebook&utm_campaign=seasonal-sale&utm_content=photo-400x700px`

第二个链接包含更多文本。 UTM参数始终位于顶级域（本例中为.com）之后，并以问号开头。 之后，参数的顺序无关紧要，但建议遵循一致的命名约定。 必须在每个参数之间放置与号，以分隔每个UTM。 现在，我们可以更详细地了解每个参数代表的含义。

了解[设置UTM参数的最佳实践](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)。

**utm_medium**

* Medium标识用于向您的公司进行营销的媒介。
* 它回答的问题是：“他们是如何找到你的？”
* 它表示最高级别的通道。
* 社交媒体、电子邮件、免费搜索和付费搜索都是Medium潜在价值的示例。
* 此参数将数据映射到[!DNL Marketo Measure]“Medium”字段。
* _[!DNL Marketo Measure]最佳实践&#x200B;:_请勿使用此字段调用子渠道，否则，在实际渠道上生成报告时可能会遇到困难。 使用它可识别您的营销工具或渠道。 例如，如果您希望使用电子邮件来营销您的产品，则媒介为电子邮件。

**utm_source**

* Source标识作为流量来源的子渠道。
* 它回答的问题是：“这个人来自哪里？”
* 在一个社交媒体示例中，流量的来源是正在使用的社交媒体平台。
   * 在此示例中，[!DNL Facebook]是Source值。 其他例子包括推特和Instagram。 另一方面，如果UTM Medium为[!DNL Paid Search]，则UTM Source可以是AdWords或BingAds。

* 此参数映射到SFDC中的[!DNL Marketo Measure]“接触点Source”字段。
* _[!DNL Marketo Measure]最佳实践&#x200B;:_此参数可跟踪流量的来源，因此不适合使用此参数来指示广告类型，例如，重新定位、赞助等。 它最好用于跟踪更高级别的子信道。 请记住，您回答的是“我的流量来自何处？” 您在查找反向链接。 在此示例中，UTM Source是广告的位置（不是实际的网页，因为这是在标签之外自动跟踪的网页）。 如果您跟踪的是滴答式电子邮件促销活动，则滴答式电子邮件是来源。

**utm_campaign**

* Campaign用于标识特定的营销活动。
* 它回答了以下问题：“他们为什么找你？”
* 使用此标记表示广告促销活动的名称（它存在于[!DNL Google AdWords]或[!DNL BingAds]中），或者表示您在内部标识该促销活动的名称。 您甚至可以使用此标记指定其他信息，例如地理位置或广告网络类型。
* 此参数映射到SFDC中的[!DNL Marketo Measure]“广告促销活动名称字段”。
* _[!DNL Marketo Measure]最佳实践_：在确定促销活动名称时，请避免在单词之间使用标点符号或空格，因为使用这些符号可能会导致浏览器编码错误。 为获得最佳结果，请改用下划线。

**utm_content**

* 如果要跟踪单个网页上存在的多个营销片段，请使用UTM内容参数。 例如，如果您有一个“请求演示”按钮和一个“注册我们的每周新闻稿”按钮，并且想知道哪个按钮产生的流量最多，您可以命名每个按钮，并使用UTM内容标记来跟踪它们。 每段“content”的名称是标记的值。
* 此参数映射到SFDC中的[!DNL Marketo Measure]“广告内容”字段。
* _[!DNL Marketo Measure]最佳实践_：这是一个可选值，但[!DNL Marketo Measure]建议使用它。 此标记与要跟踪的广告或营销文章的标题关联。 如果您使用图像广告，请务必在其标题中写入图像的尺寸。

**utm_term**

* 术语类似于UTM内容参数。 术语非常适合用于标识付费营销活动广告中的关键词。 如果使用自动标记功能，则为您完成此操作。 如果您未使用广告平台的自动标记功能，请务必仔细添加所有要跟踪的关键字。
* 此参数映射到SFDC中的[!DNL Marketo Measure]“关键词文本”字段。
* _[!DNL Marketo Measure]最佳实践_： UTM术语标记是可选的，但非常适合跟踪关键字。 仔细检查拼写，避免使用特殊字符。 如果需要多个单词，请尝试使用下划线或不使用空格。

每个参数都会收集与指定值相关的信息。 每个标记的值允许您跟踪和排序所有数字营销活动，并回答以下问题：位置、方式和原因？

以下是UTM参数[!DNL Marketo Measure]解析的图表以及它们关联的相应接触点字段：

| **UTM参数** | **对应的[!DNL Marketo Measure]字段** |
|---|---|
| utm_medium | 媒介 |
| utm_source | 接触点Source |
| utm_campaign | 广告营销活动名称 |
| utm_content | 广告内容 |
| utm_term | 关键字文本 |
