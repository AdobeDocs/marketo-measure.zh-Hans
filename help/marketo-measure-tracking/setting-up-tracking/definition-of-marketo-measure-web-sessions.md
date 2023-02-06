---
unique-page-id: 18874564
description: 定义 [!DNL Marketo Measure] Web会话 —  [!DNL Marketo Measure]  — 产品文档
title: 定义 [!DNL Marketo Measure] Web会话
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# 定义 [!DNL Marketo Measure] Web会话 {#definition-of-marketo-measure-web-sessions}

了解如何 [!DNL Marketo Measure] 定义web会话。

A **Web会话** 是指某个人在特定时间段内与您网站的交互。 会话在用户登陆您的网站时开始。

例如，Haley访问adobe.com。 她访问网站开始一个会话。 当海莉离开网站时，通过关闭选项卡/网页浏览器或离开网站，会话将结束。

一个用户不能同时打开多个会话。 如果海莉打开 [!DNL adobe.com] 在10个单独的选项卡中，只创建了一个与她访问网站有关的会话。

## 如何 [!DNL Marketo Measure] 定义新会话？ {#how-does-marketo-measure-define-a-new-session}

有几个因素可决定会话何时结束以及新会话何时开始。 两种主要方式 [!DNL Marketo Measure] 会话可以结束如下：

* **基于时间的到期**
* **基于渠道的到期**

## 基于时间的过期 {#time-based-expiration}

**会话会持续多长时间？**

[!DNL Marketo Measure] 会话将在网站上处于非活动状态30分钟后结束。 例如：

哈利访问adobe.com时，会开始一个会话。 她浏览网站几分钟，然后离电脑很远，但网站却保持打开状态。 处于非活动状态30分钟后，会话将结束。

目前， [!DNL Marketo Measure] 仅将页面导航和表单提交视为活动。 在网页上滚动或将鼠标悬停在页面上的某个元素上时，不会被视为活动。 因此，如果哈利访问adobe.com阅读一篇博客文章，并且需要一个小时才能阅读，那么即使她在浏览页面上的内容，她的网络会话也会在30分钟后结束。

## 基于渠道的到期 {#channel-based-expiration}

[!DNL Marketo Measure] 当用户从其他数字营销渠道或外部网站访问您的网站时，将开始新会话。 这包括：

* 推荐网站
* 社交渠道([!DNL Facebook], [!DNL LinkedIn]等)
* 付费或免费搜索渠道([!DNL Google/Bing])

**推荐网站和社交渠道**

每当访客从引荐网站或社交渠道访问您的网站时，都会开始新会话。

说海莉在LinkedIn，点击 [!DNL Marketo Measure] 帖子，并被重定向到Adobe网站。 然后，在滚动浏览时 [!DNL Facebook]海莉又看见了 [!DNL Marketo Measure] 帖子。 当她单击此帖子并被重定向到Adobe网站时，将导致与 [!DNL LinkedIn] 结束，并且与 [!DNL Facebook] 开始。

**付费或免费搜索渠道**

每当用户通过付费或免费搜索渠道访问您的网站时，即会开始新会话。 如果海莉通过免费搜索进入Adobe网站，然后通过Google上的付费广告立即访问您的网站，将创建两个不同的会话。

**Web直接流量**

如果访客通过在地址栏中键入您网站的URL来访问您的网站，则并不总会导致开始新会话。

如果海莉的首次网络会话是通过反向链接网站、社交渠道或付费/免费搜索渠道访问而开始的，那么她直接通过网络访问该网站，就不会导致新的会话开始。

_但是_&#x200B;如果海莉的第一次网络会话源自Web Direct，那么她就会通过 _外部/反向链接网站_，则第一个会话将结束，并且会打开一个与外部/反向链接网站相关的新会话。

## Google Analytics会话 {#google-analytics-sessions}

在如何 [!DNL Marketo Measure] 和Google Analytics定义会话。 有关Google Analytics如何定义会话的更多信息，请访问： [https://support.google.com/analytics/answer/2731565?hl=en](http://support.google.com/analytics/answer/2731565?hl=en){target="_blank"}
