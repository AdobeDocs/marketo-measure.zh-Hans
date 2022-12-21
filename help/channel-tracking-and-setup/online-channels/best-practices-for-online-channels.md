---
description: 在线渠道的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 在线渠道的最佳实践
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---

# 在线渠道的最佳实践 {#best-practices-for-online-channels}

## 概述 {#overview}

准确 [!DNL Marketo Measure] 报表，则您的营销渠道必须正确设置。 营销渠道字段显示接触点可属于的最高级别营销活动组（例如付费搜索、直接、社交等）。

设置营销渠道有两个方面：在线和离线。 本文档将重点介绍 [!DNL Marketo Measure] 设置和维护在线渠道的最佳实践建议。

在线渠道规则是指如何 [!DNL Marketo Measure] 映射您的数字接触点，即通过跟踪和创建的任何接触点 [!DNL Marketo Measure] JS。 如果这些规则不全面或排序不正确，则接触点可能会归因于错误的渠道，从而降低报表的准确性。 确保您的在线渠道规则准确且最新，将确保您的数字数据被归因于您的 [!DNL Marketo Measure] 报表。

## 最佳实践 {#best-practice}

无论您是首次设置规则，还是仅仅查看规则以检查准确性，请牢记以下最佳实践。

请花些时间考虑营销活动的组织方式以及它们如何适合 [!DNL Marketo Measure] 框架。 确定在线渠道中应显示哪些渠道和子渠道，以及哪些营销活动、UTM参数或反向链接网站可区分这些渠道。

请牢记以下事项：

* 所有数字渠道和子渠道都应至少使用一条规则表示
   * 如果渠道没有引导用户访问您的网站，则它不是在线渠道
* 一个渠道/子渠道可以有多个规则
   * 可以将多个规则视为“铸造更宽的网”，以确保每个接触点都正确映射。 通常，参数可能会被错误地添加或完全丢失，因此有多个规则来捕获渠道/子渠道是确保映射准确性的好方法。
* [!DNL Marketo Measure] 逻辑按降序排列接触点映射的优先级，从电子表格的顶行开始，然后向下排列
   * [!DNL Marketo Measure] 读取每个规则（行），查找true和first fit。 接着，接触点被映射到该渠道/子渠道
   * 请勿按字母顺序对工作表进行排序，因为这会妨碍逻辑规则。
* 维护方括号内的规则，不要编辑或添加到方括号内的规则(例如； [AdWords付费搜索] 或 [Facebook付费] )
   * 这些都是开箱即用的 [!DNL Marketo Measure] 内置逻辑的规则，这些规则与 [!DNL Marketo Measure] 集成。 将渠道/子渠道部分的这些规则设置为优先级，以确保 [!DNL Marketo Measure] 集成可以按照设计方式工作。
* 上传文件后，七天内无法更改任何规则
   * [!DNL Marketo Measure] 会利用此时间处理和更新接触点，因此，请确保在上载之前仔细检查您的规则。

## 维护最佳实践 {#best-practice-for-maintenace}

保存并处理后，在线渠道规则会持续工作以存储您的数字接触点。 但是，某些更改或方案会导致您想要查看联机渠道设置。 [!DNL Marketo Measure] 建议您每六个月查看一次在线渠道规则。 这将确保 [!DNL Marketo Measure] 数据与您对在线渠道/子渠道的内部定义以及您对UTM的使用保持一致。

可能触发您的团队执行在线渠道维护的其他项目包括…….

* 新的数字渠道/子渠道已启动
* 更新或更改UTM参数
* 对渠道组织或命名约定的更改
* 营销团队的营业额

如果您的团队最近遇到过上述任何情况 [!DNL Marketo Measure] 建议您查看在线渠道规则并做出相应更改。

>[!MORELIKETHIS]
>
>* [联机渠道设置](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [UTM参数](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [营销渠道和子渠道](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [UTM最佳实践](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)

