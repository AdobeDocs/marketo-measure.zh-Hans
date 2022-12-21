---
unique-page-id: 18874682
description: 营销渠道和子渠道 —  [!DNL Marketo Measure]  — 产品文档
title: 营销渠道和子渠道
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---

# 营销渠道和子渠道 {#marketing-channels-and-subchannels}

## 用途 {#purpose}

定义渠道和子渠道所在的位置 [!DNL Marketo Measure]、它们与内容的关系、两个分类之间的差异以及在 [!DNL Marketo Measure] 应用程序。

## 概述 {#overview}

营销渠道用于帮助对您的营销活动进行分类（或“分段”），以便于报告，这两项均位于 [!DNL Marketo Measure] ROI Dash以及您的CRM中的ROI Dash。 [!DNL Marketo Measure] 附带12个现成的渠道（您可以自定义/重命名以符合贵组织的惯例），以及进一步创建自定义渠道以进行更精细的过滤的功能。

每当您收到访客访问您网站上的某个内容页面（无论该内容是网页、白皮书下载、页面URL等）时，该潜在客户都将根据URL中找到的多个UTM参数“分段”到渠道/子渠道中：

* 中
* 源
* Campaign
* 登陆页面
* 引荐网站

要根据潜在客户的UTM参数自定义将归入哪个“存储段”，您可以使用渠道规则。 有关设置和维护渠道规则的更多信息， [单击此处](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

了解如何设置 [在线渠道](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) 和 [离线渠道](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)，以及两者之间的差异。

**营销渠道**

营销渠道是最广泛的分类级别，可涵盖各种子渠道。 您可以将这些视为潜在客户来自的子渠道的“类型”。 营销渠道示例包括 **付费搜索、免费搜索、显示、** 和 **付费社交**. 营销渠道通常对应于URL中的utm_medium参数值。

**子渠道**

子渠道是拼合传入的Lead时的拼图的第二个部分。 子渠道准确地讲述了 _哪个_ 使用了营销渠道的迭代。 例如，在付费社交营销渠道中，您可能拥有 **AdWords**, **BingAds**, **Facebook**&#x200B;等。 子渠道通常对应于URL中的utm_source参数值。

## 用例示例 {#use-case-example}

下图说明了基于具有以下URL的网页的营销渠道、子渠道和内容示例：

* [http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial](http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial)*

在这种情况下，用户尝试访问的内容是B2B营销归因简介指南。 [!DNL Marketo Measure] 将使用在此组织中设置的渠道规则分析导致此内容的URL，并使用它们将此潜在客户“存储”到营销渠道“付费社交”和子渠道“LinkedIn”。

![](assets/1.jpg)

更多示例……

**营销渠道（媒介）**

* PPC
* 付费社交
* 有机社交
* 电子邮件
* 活动和会议
* 免费搜索/SEO
* PR
* 推荐计划

**子渠道（接触点源）**

* Google AdWords
* BingAds
* Facebook Ads
* Adroll
* 双击
* 卡普特拉
* 滴漏营销活动
* linkedIn Ads

**内容（白皮书、页面URL、博客文章）**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
