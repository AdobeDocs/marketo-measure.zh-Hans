---
description: 在线渠道的最佳实践 —  [!DNL Marketo Measure]
title: 在线渠道的最佳实践
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
feature: Channels
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# 在线渠道的最佳实践 {#best-practices-for-online-channels}

## 概述 {#overview}

要获得准确的[!DNL Marketo Measure]报表，必须正确设置您的营销渠道。 营销渠道字段显示接触点可属于的最高级别营销活动组（例如，付费搜索、直接、社交等）。

设置营销渠道有两个方面：在线和离线。 本文档重点介绍有关设置和维护在线渠道的[!DNL Marketo Measure]最佳实践建议。

在线渠道规则是[!DNL Marketo Measure]如何映射您的数字接触点（即通过您网站上的[!DNL Marketo Measure] JS跟踪和创建的任何接触点）的准则。 如果这些规则不完整，或者未正确排序，则可以将接触点归因于错误的渠道，因此会降低报表的准确性。 确保在线渠道规则准确且为最新将确保您的数字数据归因到[!DNL Marketo Measure]报表中的正确渠道和子渠道。

## 最佳实践 {#best-practice}

无论您是首次设置规则，还是只是检查规则以检查其准确性，请牢记以下最佳实践。

请花些时间考虑营销活动的组织结构以及它们如何适应[!DNL Marketo Measure]框架。 确定您的在线渠道中应该显示哪些渠道和子渠道，以及哪些促销活动、UTM参数或反向链接网站将这些渠道彼此区分开来。

切记事项：

* 所有数字渠道和子渠道应至少用一个规则表示
   * 如果该渠道不能将用户引导至您的网站，则它不是在线渠道
* 一个渠道/子渠道可以有多个规则
   * 多个规则可以视为“投射更宽的网络”，以确保每个接触点都正确映射。 通常，参数可能会错误地添加或完全丢失，因此，最好使用多个规则来捕获通道/子通道，以确保映射准确性。
* [!DNL Marketo Measure]逻辑从电子表格的顶行开始按降序排列接触点映射的优先级，并向下排列
   * [!DNL Marketo Measure]读取每个规则（行），以查找真值和第一个拟合值。 然后，该接触点将映射到该渠道/子渠道
   * 请勿按字母顺序对工作表进行排序，因为这会干扰逻辑规则。
* 维护括号内的规则，请勿编辑或添加到括号内的规则中（例如，[AdWords付费搜索]或[Facebook付费搜索]）
   * 这些是现成的[!DNL Marketo Measure]规则，具有内置逻辑，与[!DNL Marketo Measure]集成关联。 为这些规则指定该渠道/子渠道部分的最高优先级，以确保[!DNL Marketo Measure]集成能够按设计要求工作。
* 上传文件后，您无法在七天内更改任何规则
   * [!DNL Marketo Measure]利用此时间处理和更新接触点，因此请确保在上传之前仔细检查您的规则。

## 维护的最佳实践 {#best-practice-for-maintenace}

保存和处理在线渠道规则后，它们会不断工作以存储您的数字接触点。 但是，某些更改或情况会导致您需要查看联机渠道设置。 [!DNL Marketo Measure]建议您每六个月查看一次在线渠道规则。 这可确保您的[!DNL Marketo Measure]数据与联机渠道/子渠道的内部定义以及UTM的使用保持一致。

可能触发您的团队进行在线渠道维护的其他项目包括....

* 推出新的数字渠道/子渠道
* UTM参数已更新或更改
* 更改渠道组织或命名惯例
* 您的营销团队中的人员调整

如果您的团队最近遇到过上述任何情况，[!DNL Marketo Measure]建议您查看在线渠道规则并进行适当的更改。

>[!MORELIKETHIS]
>
>* [联机渠道设置](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [UTM参数](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [营销渠道和子渠道](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [UTM最佳实践](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)
