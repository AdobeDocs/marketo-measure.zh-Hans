---
unique-page-id: 18874682
description: 营销渠道和子渠道 —  [!DNL Marketo Measure]
title: 营销渠道和子渠道
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
feature: Channels
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 2%

---

# 营销渠道和子渠道 {#marketing-channels-and-subchannels}

## 用途 {#purpose}

定义[!DNL Marketo Measure]中的渠道和子渠道、它们与您的内容的关系、两个分类之间的区别以及它们在[!DNL Marketo Measure]应用程序中的使用方式。

## 概述 {#overview}

营销渠道用于帮助对您的营销活动进行分类（或“分段”），以方便报告，包括在[!DNL Marketo Measure] ROI短划线中以及在CRM中。 [!DNL Marketo Measure]附带12个现成的渠道（您可以根据组织的惯例自定义/重命名这些渠道），以及进一步创建自定义渠道以实现更精细筛选的能力。

每当您收到您网站上某个内容页面（无论该内容是网页、白皮书下载、页面URL等）的访客时，该Lead将根据URL中找到的几个UTM参数“分段”到渠道/子渠道中：

* 媒介
* 来源
* 活动
* 登陆页面
* 引用网站

要根据销售线索的UTM参数自定义销售线索将归入哪个“存储桶”，您可以使用渠道规则。 有关设置和维护渠道规则的更多信息，[单击此处](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)。

了解如何设置[在线渠道](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)和[离线渠道](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)以及它们之间的区别。

**营销渠道**

营销渠道是最广泛的分类级别，可以涵盖各种子渠道。 您可以考虑这些是您的潜在客户所来自的子渠道的“类型”。 营销渠道示例包括&#x200B;**付费搜索、免费搜索、显示、**&#x200B;和&#x200B;**付费社交**。 营销渠道通常对应于在URL中找到的utm_medium参数值。

**子渠道**

子渠道是存储传入的潜在客户时遇到的第二个难题。 子渠道仅讲述使用了您的营销渠道的&#x200B;_哪个_&#x200B;迭代的故事。 例如，在付费社交营销渠道中，您可能有&#x200B;**AdWords**、**BingAds**、**Facebook**&#x200B;等等的子渠道。 子渠道通常对应于在URL中找到的utm_source参数值。

## 用例示例 {#use-case-example}

下图说明了基于具有以下URL的网页的营销渠道、子渠道和内容的示例：

`http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&utm_medium=paidsocial`

在这种情况下，用户尝试访问的内容是《B2B营销归因简介指南》。 [!DNL Marketo Measure]将使用此组织中设置的渠道规则分析指向此内容的URL，并使用它们“分段”此潜在客户到营销渠道“付费社交”和子渠道“LinkedIn”。

![](assets/1.jpg)

其他示例……

**营销渠道(Medium)**

* PPC
* 付费社交
* 自然社交
* 电子邮件
* 活动和会议
* 自然搜索/SEO
* PR
* 反向链接程序

**子渠道(接触点Source)**

* Google AdWords
* BingAds
* Facebook广告
* Adroll
* 双击
* Capterra
* Drip营销活动
* LinkedIn 广告

**内容（白皮书、页面URL、博客文章）**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
