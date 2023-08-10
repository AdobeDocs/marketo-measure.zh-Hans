---
description: 在线渠道的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 在线渠道的最佳实践
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---

# 在线渠道的最佳实践 {#best-practices-for-online-channels}

## 概述 {#overview}

以获得准确结果 [!DNL Marketo Measure] 因此，必须正确设置您的营销渠道。 营销渠道字段显示接触点可属于的最高级别营销活动组（例如，付费搜索、直接、社交等）。

设置营销渠道有两个方面：在线和离线。 本文档将重点介绍 [!DNL Marketo Measure] 有关设置和维护在线渠道的最佳实践建议。

在线渠道规则是指导如何 [!DNL Marketo Measure] 映射您的数字接触点，即通过 [!DNL Marketo Measure] 您网站上的JS。 如果这些规则不完整，或者未正确排序，则可以将接触点归因于错误的渠道，因此会降低报表的准确性。 确保您的在线渠道规则准确且最新，将确保您的数字数据被归因到您的中的正确渠道和子渠道。 [!DNL Marketo Measure] 报表。

## 最佳实践 {#best-practice}

无论您是首次设置规则，还是只是检查规则以检查准确性，请牢记以下最佳实践。

请花些时间来考虑营销活动的组织结构以及它们如何适应 [!DNL Marketo Measure] 框架。 确定您的在线渠道中应该显示哪些渠道和子渠道，以及哪些促销活动、UTM参数或反向链接网站使这些渠道彼此不同。

切记事项：

* 所有数字渠道和子渠道应至少用一个规则表示
   * 如果该渠道不能将用户引导至您的网站，则它不是在线渠道
* 一个渠道/子渠道可以有多个规则
   * 多个规则可以视为“投射更宽的网络”，以确保每个接触点都正确映射。 通常，参数可能会错误地添加或完全丢失，因此，最好使用多个规则来捕获通道/子通道，以确保映射准确性。
* [!DNL Marketo Measure] 逻辑按降序排列接触点映射的优先级，从电子表格的顶行开始向下排列
   * [!DNL Marketo Measure] 读取每个规则（行），寻找真和第一个匹配。 然后，该接触点将映射到该渠道/子渠道
   * 请勿按字母顺序对工作表进行排序，因为这样会干扰逻辑规则。
* 维护括号内的规则，请勿编辑或添加到括号内的规则中(例如； [AdWords付费搜索] 或 [facebook已付费] )
   * 这些是现成的 [!DNL Marketo Measure] 具有内置逻辑的规则，这些逻辑与 [!DNL Marketo Measure] 集成。 将这些规则指定为该渠道/子渠道部分的最高优先级，以确保 [!DNL Marketo Measure] 集成可以按设计要求工作。
* 上传文件后，您无法在七天内更改任何规则
   * [!DNL Marketo Measure] 利用这个时间处理和更新接触点，因此请确保在上传之前仔细检查您的规则。

## 维护最佳实践 {#best-practice-for-maintenace}

保存和处理后，在线渠道规则会不断发挥作用，以存储您的数字接触点。 但是，某些更改或情况会导致您需要查看联机渠道设置。 [!DNL Marketo Measure] 建议您每六个月审查一次在线渠道规则。 这将确保 [!DNL Marketo Measure] 数据与您对在线渠道/子渠道的内部定义以及UTM的使用情况保持一致。

可能触发您的团队进行在线渠道维护的其他项目包括....

* 推出新的数字渠道/子渠道
* UTM参数已更新或更改
* 更改渠道组织或命名惯例
* 您的营销团队中的人员调整

如果您的团队最近遇到过以上任何情况 [!DNL Marketo Measure] 建议您查看联机渠道规则并进行适当的更改。

>[!MORELIKETHIS]
>
>* [在线渠道设置](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [UTM参数](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [营销渠道和子渠道](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [UTM最佳实践](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)
