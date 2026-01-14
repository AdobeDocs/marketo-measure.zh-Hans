---
description: 面向Marketo Measure用户的 [!DNL Marketo Measure] Web会话指导的定义
title: ' [!DNL Marketo Measure] Web会话的定义'
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 0%

---

# [!DNL Marketo Measure] Web会话的定义 {#definition-of-marketo-measure-web-sessions}

了解[!DNL Marketo Measure]如何定义Web会话。

**Web会话**&#x200B;是指在特定时间段内个人与您的网站的交互。 会话在用户登陆您的网站时开始。

例如，Haley访问adobe.com。 她对该网站的访问开始了一个会话。 当Haley通过关闭选项卡/Web浏览器或导航离开站点来离开站点时，会话结束。

一个用户无法同时打开多个会话。 如果Haley在10个单独的选项卡中打开[!DNL adobe.com]，则仅创建了一个与她访问网站相关的会话。

## [!DNL Marketo Measure]如何定义新会话？ {#how-does-marketo-measure-define-a-new-session}

有一些因素可决定会话何时结束以及新会话何时开始。 [!DNL Marketo Measure]会话有两种主要结束方式：

* **基于时间的到期**
* **基于渠道的到期**

## 基于时间的到期 {#time-based-expiration}

**会话持续多长时间？**

[!DNL Marketo Measure]会话将在网站上处于非活动状态30分钟后结束。 例如：

当Haley访问adobe.com时，会话开始。 她浏览网站几分钟，然后离开计算机，但保持网站打开。 30分钟非活动状态后，会话结束。

目前，[!DNL Marketo Measure]仅将页面导航和表单提交视为活动。 在网页中滚动或悬停在页面上的某个元素上不被视为活动。 因此，如果Haley访问adobe.com阅读一篇博客文章，并且阅读需要一小时，那么她的网络会话将在30分钟后结束，即使她滚动浏览页面上的内容。

## 基于渠道的到期 {#channel-based-expiration}

无论用户从其他数字营销渠道还是外部网站访问您的网站，[!DNL Marketo Measure]都会开始新会话。 这包括：

* 推荐网站
* 社交渠道（[!DNL Facebook]、[!DNL LinkedIn]等）
* 付费或免费搜索渠道([!DNL Google/Bing])

**反向链接网站和社交渠道**

无论访客何时从反向链接网站或社交渠道访问您的网站，都会开始一个新会话。

假设Haley在LinkedIn上，请单击[!DNL Marketo Measure]帖子并重定向到Adobe网站。 然后，在滚动[!DNL Facebook]时，Haley会看到另一个[!DNL Marketo Measure]帖子。 当她单击此帖子并重定向到Adobe网站时，这将导致与[!DNL LinkedIn]相关的第一个Web会话结束，并且与[!DNL Facebook]相关的新会话开始。

**付费或免费搜索渠道**

每当用户通过付费或免费搜索渠道访问您的网站时，新会话就会开始。 如果Haley通过免费搜索访问Adobe网站，然后立即通过Google上的付费广告访问您的网站，则会创建两个单独的会话。

**Web直接流量**

如果访客通过在地址栏中键入您网站的URL来访问您的网站，则不会始终导致开始新会话。

如果Haley的第一个Web会话因反向链接网站、社交渠道或付费/有机搜索渠道的访问而开始，然后她通过Web直接访问网站，则不会导致新会话开始。

_但是_，如果Haley的第一个Web会话源自Web Direct，然后她通过&#x200B;_外部/反向链接网站_&#x200B;访问该网站，则第一个会话将结束，并会打开一个与外部/反向链接网站相关的新会话。

## Google Analytics会话 {#google-analytics-sessions}

[!DNL Marketo Measure]和Google Analytics定义会话的方式有一些相似之处。 有关Google Analytics如何定义会话的详细信息，请访问： [https://support.google.com/analytics/answer/2731565?hl=en](https://support.google.com/analytics/answer/2731565?hl=en){target="_blank"}
