---
description: 面向Marketo Measure用户的呼叫跟踪集成指南
title: 调用跟踪集成
exl-id: bc35a789-e056-4456-9038-306ed34c2a8e
feature: Tracking, Integration
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 0%

---

# 调用跟踪集成 {#call-tracking-integration}

我们与[!DNL CallTrackingMetrics]的集成旨在将Web会话与电话通话合并。 将电话视为提交给[!DNL Marketo Measure]的表单。 它将Web会话的点数计入在内，否则该会话仅被视为Web访问，因为没有实际提交表单。

## 呼叫跟踪说明 {#call-tracking-explained}

一般而言，“呼叫跟踪”是来自[!DNL CallTrackingMetrics]、[!DNL DiaglogTech]、[!DNL Invoca]或[!DNL CallRail]等公司的产品。 根据用户来自的不同营销渠道或营销活动，向用户显示独特的电话号码。 这允许营销人员查看这些渠道或营销活动的执行情况。

![](assets/other-resources-6.png)

## 之前和之后 {#before-and-after}

查看下面的流程图，了解[!DNL Marketo Measure]如何在没有与CallTrackingMetrics集成的情况下处理电话呼叫。 发生的电话被取消跟踪，因此它被视为网络会话，没有为其创建接触点。 直到下一次用户完成表单访问时，接触点才会最终填充。

通过集成，您可以看到Web会话实际上与电话绑定。 下一个表单填充最终是PostLC触控，并且仍在历程中受到跟踪。

![](assets/other-resources-4.png)

## 工作原理 {#how-it-works}

CallTrackingMetrics必须完成一些开发工作才能使其正常工作。 通过使用它们放置在网站上的JavaScript，CallTrackingMetrics可以从`_biz_uid` Cookie中获取[!DNL Marketo Measure]。 然后，CallTrackingMetrics存储此“BizibleId”。

当访客访问您的网站并拨打电话时，CallTrackingMetrics的工作是将该数据推送到[!DNL Salesforce]。  通常，会创建一个[!DNL Salesforce Task]以填充电话号码、主题、类型等数据，现在还有[!DNL BizibleId]

[!DNL BizibleId]是随[!DNL Marketo Measure]营销归因包的6.7+版本一起安装的字段。

以下是填充[!DNL BizibleId]的Task记录示例。

![](assets/other-resources-5.png)

当[!DNL Marketo Measure]找到已填充已知[!DNL BizibleId]值的Task记录时，[!DNL Marketo Measure]可以将该用户映射到具有相同[!DNL BizibleId]的Web会话，并将该会话归因于电话呼叫而不是Web访问。

## 接触点 {#the-touchpoint}

当[!DNL Marketo Measure]可以导入/下载任务时，我们将在Web会话中处理该详细信息。 通常，它可以与反向链接或广告合并。 在下面的示例中，访客通过付费Google广告找到业务并致电。

[!UICONTROL Touchpoint]类型“Call”是从上方的屏幕快照中提取，在创建任务时该屏幕快照也由CallTrackingMetrics填充。

![](assets/one-one-1.png)

## 报告 {#reporting}

[!DNL Marketo Measure]通常推送的接触点类型值为“Web访问”、“Web窗体”或“Web聊天”，但对于CallTrackingMetrics接触点，接触点类型是“电话”。 这有助于营销人员查看哪些渠道吸引的电话次数最多，并为他们的组织创造收入。

![](assets/other-resources-1.png)

## 常见问题解答 {#faq}

**为什么我的接触点类型为Web访问？**

“接触点类型”是从Task.Type字段中填充的。 如果Task.Type字段为空，则[!DNL Marketo Measure]将自动将接触点类型设置为Web访问。 填充Task.Type字段后，[!DNL Marketo Measure]将读取该值并相应地填充接触点类型。

**电话中接触点填充了哪些其他字段？**

“接触点类型”和“Medium”都包含从Task.Type提取的数据。 所有其他数据点都将从Web跟踪和JavaScript数据中提取。

**为什么此电话未绑定到Web会话？**

首先，检查任务以确保填充[!DNL BizibleId]。 如果没有值，则无法为其创建接触点。 需要使用CallTrackingMetrics将此问题升级。

如果存在值，请注意，我们只认为所有Web会话为30分钟。 如果在12:17pm（网站上的会话开始）点击Google广告，但直到1:05pm才出现电话呼叫，则不会合并Web会话和电话呼叫。 相反，[!DNL Marketo Measure]会创建一个单独的[!DNL Salesforce Task]接触点来跟踪电话呼叫，但不会有任何Web会话数据。

![](assets/other-resources-2.png)

## 伙伴关系 {#partnerships}

[!DNL Marketo Measure]目前有一个正式的Call Tracking合作伙伴，该合作伙伴与我们一起经历了“官方”集成过程，其中包括联合营销和产品培训。 一个合作伙伴是CallTrackingMetrics。
