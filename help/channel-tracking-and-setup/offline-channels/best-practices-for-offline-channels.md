---
description: 离线渠道的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 离线渠道的最佳实践
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 0%

---

# 离线渠道的最佳实践 {#best-practices-for-offline-channels}

## 概述 {#overview}

准确 [!DNL Marketo Measure] 报表，则您的营销渠道必须正确设置。 &#39;[!UICONTROL Marketing Channel]“字段显示接触点可属于的最高级别营销策略组（例如，事件、网络研讨会、内容整合等）。

设置营销渠道有两个方面：在线和离线。 本文档将重点介绍 [!DNL Marketo Measure] 设置和维护离线渠道以及这些渠道如何与同步的最佳实践建议 [!DNL Marketo Measure] 通过CRM促销活动。

离线渠道有两个关键方面：

1. 离线渠道映射，该映射框架用于告知 [!DNL Marketo Measure] 离线接触点所属的渠道和子渠道
1. 脱机营销活动同步，用于创建脱机接触点

离线接触点是从CRM Campaign创建的，用于跟踪任何无法通过数字方式跟踪的营销互动 [!DNL Marketo Measure] 在您网站的页面上实施的JavaScript。 当CRM促销活动与 [!DNL Marketo Measure]，为营销活动中定义的营销活动成员创建接触点。

这些接触点的“营销渠道”值基于营销活动上的“类型”字段。 “CRM促销活动类型”到“营销渠道”和“子渠道”的映射，在 [!DNL Marketo Measure] 帐户设置。 确保离线渠道映射准确且最新，将确保离线接触点数据被归因到您 [!DNL Marketo Measure] 报表。

## 最佳实践 |离线渠道映射 {#best-practice-offline-channel-mapping}

无论您是首次映射离线渠道，还是只是查看以检查其准确性，请牢记以下最佳实践。

* 为离线渠道创建周密的框架
   * 请花些时间考虑营销活动的组织方式以及它们如何适合 [!DNL Marketo Measure] 框架。 确定离线渠道中应显示哪些渠道和子渠道，以及哪些CRM促销活动类型可区分这些渠道
* 首先努力利用您当前的CRM促销活动“类型”值
   * 离线渠道由CRM促销活动“类型”定义，但是，可能需要创建自定义CRM促销活动“类型”值，以适应理想的离线渠道值和子渠道值。 理想的自定义CRM促销活动“类型”值应遵循以下命名约定：
      * 渠道 — 子渠道
      * 示例：事件 — 贸易展
      * 这可确保映射到子渠道级别尽可能简单和干净
* 只能将一个子渠道映射到一个CRM促销活动“类型”
   * 可以将多个CRM促销活动“类型”映射到单个渠道，但只能将一个CRM促销活动“类型”映射到每个渠道中的每个子渠道
* 只应将离线CRM促销活动“类型”映射到离线渠道，因为只有离线促销活动将与 [!DNL Marketo Measure] 要创建接触点，请执行以下操作：
   * 应将在线CRM促销活动“类型”映射到 [!UICONTROL Marketing Channel] = &quot;NULL&quot;。 建议使用此值，因为它用作“红色标记”，表示已审核离线渠道，且任何映射到“NULL”的CRM促销活动“类型”均为ONLINE“类型”，不应与 [!DNL Marketo Measure]. 与在线CRM促销活动“类型”相关的接触点将已通过 [!DNL Marketo Measure] 在线功能和渠道。 同步这些营销活动可能会导致“重复”接触点/重复计数

## 最佳实践 |离线营销活动同步 {#best-practice-offline-campaign-sync}

* 确保“类型”字段在每个CRM促销活动中都准确无误
   * “类型”确定同步后来自营销活动的任何接触点的营销渠道和子渠道
* 是使用基于CRM的促销活动同步方法（启用购买者接触点），还是 [!DNL Marketo Measure] 基于应用程序的同步方法(在“[!UICONTROL Campaigns]“ ”选项卡 [!UICONTROL Marketo Measure] 帐户设置)，则仅当促销活动成员与促销活动和您的品牌具有实际的离线参与时，才应创建离线接触点：
   * 对于活动或网络研讨会等离线渠道：“注册”通常通过网站上的表单提交进行跟踪， [!DNL Marketo Measure] 联机功能。 因此，状态为“已注册”的营销活动成员不应从营销活动中接收离线接触点，以避免重复计数。 离线接触点应仅代表活动或网络研讨会的“出席情况”。
   * 某些离线渠道（如内容整合）通常更加简单明了，因为每个营销活动成员都具有相同的“响应”状态，即表示他们确实对营销活动做出响应，在这种情况下，将内容下载到第三方网站，因此应会收到离线接触点
* 在 [!DNL Marketo Measure] 应用程序中，请确保“接触点日期”字段基于营销活动或营销活动成员中最能指示接触点交互实际发生时间的日期字段
* 如果您需要覆盖源自CRM促销活动的任何离线接触点的“接触点日期”，请使用“批量更新接触点日期”按钮。 “接触点日期”需要尽可能准确，以确保接触点拥有尽可能准确的“接触点位置”，从而获得适当数量的归因点数

## 维护最佳实践 {#best-practice-for-maintenance}

初始设置后，离线渠道设置将继续相应地创建离线接触点。 作为最佳实践，我们建议您每年至少查看两次离线设置。 这将确保买方接触点数据清晰准确。

此外，如果您对促销活动管理或流程进行了任何更改，则需要确保更新 [!DNL Marketo Measure] 脱机渠道映射和/或同步过程。

可能会触发您的团队对 [!DNL Marketo Measure] 可能包括：

* 已创建或编辑CRM促销活动“类型”
* 创建或编辑营销活动成员“状态”
* 如果通过“启用买方接触点”字段使用CRM促销活动同步方法，请确保针对创建的每个CRM促销活动审核并更新此字段。 如果忽略此字段，则不会有任何相关的离线接触点数据
* 如果您遇到CRM促销活动中任何看起来是在线接触点的离线接触点（营销渠道= NULL），请确保对相关的CRM促销活动进行审核并禁用同步

如果您的团队最近遇到过上述任何情况， [!DNL Marketo Measure] 建议您查看离线渠道映射和离线营销活动，以做出相应更改并确保正确同步。

>[!MORELIKETHIS]
>
>* [脱机渠道设置](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [自定义营销活动同步 — 应用程序同步](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [正在同步离线营销活动 — CRM同步](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [离线营销活动和营销活动成员 — CRM同步](/help/channel-tracking-and-setup/offline-channels/campaigns-and-campaign-members.md)
>* [促销活动同步日期 — CRM同步](/help/channel-tracking-and-setup/offline-channels/campaign-sync-dates.md)
>* [多营销活动记录类型的配置](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [创建营销活动列表视图](/help/channel-tracking-and-setup/offline-channels/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [正在同步历史数据](/help/channel-tracking-and-setup/offline-channels/syncing-historical-data.md)

