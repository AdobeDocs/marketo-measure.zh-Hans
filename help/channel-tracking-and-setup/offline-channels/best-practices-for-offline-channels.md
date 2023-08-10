---
description: 离线渠道的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 离线渠道的最佳实践
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 0%

---

# 离线渠道的最佳实践 {#best-practices-for-offline-channels}

## 概述 {#overview}

以获得准确结果 [!DNL Marketo Measure] 因此，必须正确设置您的营销渠道。 “[!UICONTROL Marketing Channel]”字段显示接触点可所属的最高级别营销策略组（例如，事件、网络研讨会、内容联合等）。

设置营销渠道有两个方面：在线和离线。 本文档将重点介绍 [!DNL Marketo Measure] 有关设置和维护离线渠道以及如何与同步它们的最佳实践建议 [!DNL Marketo Measure] 通过CRM Campaigns。

离线渠道有两个关键方面：

1. 脱机渠道映射，框架用于告知 [!DNL Marketo Measure] 离线接触点属于哪个渠道和子渠道
1. 离线Campaign同步，即创建离线接触点

离线接触点是从CRM Campaign创建的，旨在跟踪任何无法通过 [!DNL Marketo Measure] 在您网站的页面上实施的JavaScript。 CRM营销活动与同步时 [!DNL Marketo Measure]，则会为营销活动中的已定义营销活动成员创建接触点。

这些接触点的“营销渠道”值基于活动上的“类型”字段。 “CRM Campaign类型”到“营销渠道”和“子渠道”的映射在的“离线渠道”选项卡中管理。 [!DNL Marketo Measure] 帐户设置。 确保您的离线渠道映射准确且为最新将确保您的离线接触点数据被归因到您网站内的正确营销渠道和子渠道。 [!DNL Marketo Measure] 报表。

## 最佳实践 |离线渠道映射 {#best-practice-offline-channel-mapping}

无论您是首次映射离线渠道，还是只检查离线渠道以检查其准确性，请牢记以下最佳实践。

* 为离线渠道创建经过深思熟虑的框架
   * 请花些时间来考虑营销活动的组织结构以及它们如何适应 [!DNL Marketo Measure] 框架。 确定离线渠道中应该显示哪些渠道和子渠道，以及哪些CRM Campaign类型使这些渠道彼此不同
* 首先努力利用当前CRM Campaign的“类型”值
   * 离线渠道由CRM Campaign“类型”定义，但是，可能需要创建自定义CRM Campaign“类型”值以适应理想的离线渠道和子渠道值。 理想的自定义CRM Campaign“类型”值应采用如下所示的命名约定：
      * 渠道 — 子渠道
      * 示例：事件 — 商展
      * 这可确保到子渠道级别的映射尽可能简单和干净
* 一个子渠道只能映射到一个CRM Campaign“类型”
   * 多个CRM Campaign“类型”可以映射到单个渠道，但只有一个CRM Campaign“类型”可以映射到每个渠道内的每个子渠道
* 只应将离线CRM Campaign“类型”映射到离线渠道，因为只与离线营销活动同步 [!DNL Marketo Measure] 要创建接触点，请执行以下操作：
   * ONLINE CRM Campaign“类型”应映射到 [!UICONTROL Marketing Channel] =“NULL”。 建议使用此值，因为它作为“红色标记”，表示您的离线渠道已审核，并且任何映射到“NULL”的CRM Campaign“类型”都在线“类型”，不应与 [!DNL Marketo Measure]. 与在线CRM Campaign“类型”相关的接触点将已经通过进行跟踪 [!DNL Marketo Measure] 在线功能和渠道。 同步这些营销活动存在“重复”接触点/重复计数的风险

## 最佳实践 |脱机Campaign同步 {#best-practice-offline-campaign-sync}

* 确保每个CRM Campaign的“类型”字段均准确
   * “类型”确定在同步后源自营销活动的任何接触点的营销渠道和子渠道
* 使用基于CRM的Campaign同步方法（启用买方接触点）还是 [!DNL Marketo Measure] 基于应用程序的同步方法（自定义Campaign同步）[!UICONTROL Campaigns]的&#39;选项卡 [!UICONTROL Marketo Measure] 仅当Campaign成员与Campaign和您的品牌有实际的离线接触时，才应创建离线接触点：
   * 对于活动或网络研讨会等离线渠道：“注册”通常通过网站上的表单提交进行跟踪，并且 [!DNL Marketo Measure] 联机功能。 因此，状态为“已注册”的营销活动成员不应从营销活动接收离线接触点，以避免重复计数。 离线接触点应仅代表活动或网络研讨会的“出席情况”。
   * 某些离线渠道（如内容联合）通常更直接，因为每个营销活动成员都具有相同的“已响应”状态，这表示他们确实对营销活动做出了响应，在这种情况下，请在第三方网站上下载内容，因此应该会收到离线接触点
* 在中使用自定义Campaign同步方法时 [!DNL Marketo Measure] 在应用程序中，确保“接触点日期”字段基于来自促销活动或促销活动成员的日期字段，该日期字段最能表明何时实际发生接触点交互
* 如果您需要覆盖源自CRM Campaign的任何离线接触点的“接触点日期”，请利用“批量更新接触点日期”按钮。 “接触点日期”需要尽可能准确，以确保接触点占据尽可能准确的“接触点位置”，从而确定适当的归因点数

## 维护的最佳实践 {#best-practice-for-maintenance}

初始设置后，离线渠道设置将继续相应地创建离线接触点。 作为最佳实践，我们建议您每年至少两次审查离线设置。 这将保证买方接触点数据干净而准确。

此外，如果您对Campaign管理或流程进行了任何更改，则需要确保更新您的 [!DNL Marketo Measure] 脱机渠道映射和/或同步过程。

更改可能会触发您的团队更新中的离线渠道设置 [!DNL Marketo Measure] 可能包括：

* 已创建或编辑CRM营销活动“类型”
* 已创建或编辑营销活动成员“状态”
* 如果通过“启用买方接触点”字段使用CRM Campaign同步方法，请确保为创建的每个CRM Campaign审查和更新此字段。 如果忽略此字段，则不会有任何相关的离线接触点数据
* 如果您从CRM Campaign遇到任何看起来像在线接触点的离线接触点（营销渠道= NULL），请确保已审核相关的CRM Campaign并禁用同步

如果您的团队最近经历过以上任何情况， [!DNL Marketo Measure] 建议您查看离线渠道映射和离线营销活动，以便做出适当的更改并确保它们正确同步。

>[!MORELIKETHIS]
>
>* [脱机渠道设置](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [自定义Campaign同步 — 应用程序同步](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [同步离线营销活动 — CRM同步](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [脱机Campaign和Campaign成员 — CRM同步](/help/channel-tracking-and-setup/offline-channels/campaigns-and-campaign-members.md)
>* [Campaign同步日期 — CRM同步](/help/channel-tracking-and-setup/offline-channels/campaign-sync-dates.md)
>* [多个营销活动记录类型的配置](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [创建营销活动列表视图](/help/channel-tracking-and-setup/offline-channels/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [同步历史数据](/help/channel-tracking-and-setup/offline-channels/syncing-historical-data.md)
