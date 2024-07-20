---
unique-page-id: 42762310
description: 正在同步历史数据 —  [!DNL Marketo Measure]
title: 同步历史数据
exl-id: 5a3c1a71-463a-4d75-98b9-fc225839512a
feature: Channels
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '1502'
ht-degree: 0%

---

# 同步历史数据 {#syncing-historical-data}

[!DNL Marketo Measure]是一种提供最细粒度、可操作数据的解决方案。 但是，我们理解您可能拥有想要归因的现有数据。 可以为历史数据生成接触点，但在执行此流程之前务必要考虑几个因素。

>[!NOTE]
>
>本文介绍了一个过时的流程。 我们鼓励用户使用[新的、改进的应用程序内进程](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}。

## 要考虑的因素 {#factors-to-consider}

**数据是否已组织到营销活动中？**

a.数据需要组织到营销活动中以同步到[!DNL Marketo Measure]，才能生成接触点。 如果当前未将数据组织到营销活动中，则需要评估是否值得花费时间和资源将数据区隔到适当的营销活动中。

b.将成员添加到营销活动或标记为已响应的日期用作接触点日期，因此该日期也需要准确。 [!DNL Marketo Measure]在SFDC和MSD中提供了用于更新日期的解决方法，但这可能非常耗时，具体取决于卷。

**您是否拥有相当数量的数据组织到所有渠道（付费搜索、活动、免费等）的营销活动中？**

为了进行准确且“公平”的报告，必须有一个均衡的归因情况。 例如，如果您只有历史离线渠道工作（如事件）的数据，则数据将存在固有偏差，没有历史在线数据对其进行补充。

**您期望的粒度级别是多少？**

您基本上只能知道渠道、子渠道和营销活动名称。

**您未来的报告目标是什么？**

此数据将受到限制，因此考虑如何使用此数据非常重要。 将历史数据与未来数据进行比较可能没有意义。

**您要回溯多久？**

[!DNL Marketo Measure]强烈建议不要超过上一年。

我们强烈建议您首先与您的[!DNL Marketo Measure]联系人讨论此主题。 如果您已考虑上述内容并希望继续，请参阅下面的一般说明（[!DNL Salesforce]和[!DNL Microsoft Dynamics]分开）。

## 正在同步[!DNL Salesforce]中的历史营销活动 {#syncing-historic-campaigns-in-salesforce}

**联机：**

要同步历史在线数据，必须将数据组织到Salesforce Campaigns中，然后通过[!DNL Marketo Measure]应用程序中的[!DNL Salesforce] Campaign同步规则同步到[!DNL Marketo Measure]。 请务必确保在JavaScript上线日期之后，不会从任何这些营销活动生成接触点。 这是为了避免重复的接触点。 在JavaScript上线后，将会自动跟踪在线工作，因此我们不想也通过SFDC促销活动跟踪它们。 要避免出现此问题，请确保为规则添加时间感。 可能类似于“营销活动成员创建日期小于[JavaScript上线日期]”的内容。

![](assets/syncing-historical-data-1.png)

历史在线数据的渠道映射组件可能有点棘手。 我们希望它尽可能地匹配您当前的在线渠道规则（来自在线规则表），以便进行干净的报告。 以下是理想渠道映射的示例。

>[!NOTE]
>
>由于我们使用的是SFDC营销活动，因此此渠道映射在[!DNL Marketo Measure]应用程序的[!UICONTROL Offline Channels]部分中完成。

| Salesforce营销活动类型 | 渠道 | 子渠道 |
|---|---|---|
| 付费搜索 — AdWords | 付费搜索 | AdWords |
| 付费搜索 — Bing | 付费搜索 | Bing |
| 付费搜索 — Yahoo | 付费搜索 | Yahoo |

通过这种方式添加的在线数据的粒度本质上是低于通过JavaScript进行的在线数据[!DNL Marketo Measure]跟踪。 例如，不会填充表单URL、登陆页面、反向链接页面等字段。 因此，建议尽可能将营销活动细分为每个源。 如上面的示例所示，您需要为每个源使用多个促销活动类型，才能在报告中具有粒度。

使用SFDC促销活动类型的数量可能无法支持粒度渠道映射，或者这样做不合理，因此您可能会求助于仅映射到渠道级别而忽略子渠道。 如果渠道级别也不清楚，您可以设置一个代理渠道，如“历史数字”，以便您至少知道这是一次在线接触。

如果您需要批量编辑将为这些历史在线工作推送的接触点日期，请使用[!DNL Marketo Measure]自定义“[!UICONTROL Bulk Update Touchpoint Date]”按钮（该按钮在SFDC中的促销活动对象中作为自定义字段提供）。 如果营销活动具有较短的时间范围，则可能有必要逐日批量编辑接触点日期；如果营销活动具有较长的时间范围，则可能适合每周批量更新。 如果您确实使用批量更新接触点日期功能，请确保更新Campaign同步规则以使用日期字段上的Buyer Touchpoint日期。 请注意，如果此操作仅适用于一两个营销活动，并且不适用于所有营销活动，则可能需要使用Campaign同步规则进行创新。

**脱机：**

离线营销工作的历史数据(无法通过JavaScript进行跟踪的数据)还需要整理到SFDC营销活动中。 SFDC营销活动是[!DNL Marketo Measure]跟踪离线工作的方式，而不管该活动是“历史”还是“当前/后[!DNL Marketo Measure]实施”，因此请遵循在原始离线渠道配置培训中决定的相同渠道映射。

如有必要，请使用“批量更新接触点日期”按钮以批量编辑营销活动成员的接触点日期。 例如，如果您在事件发生后创建SFDC营销活动，则需要批量编辑正确的日期。 如果您确实使用批量更新接触点日期功能，请确保更新Campaign同步规则以使用日期字段上的Buyer Touchpoint日期。 请注意，如果此操作仅适用于一两个营销活动，并且不适用于所有营销活动，则可能需要使用Campaign同步规则进行创新。

## 正在同步[!DNL Dynamics]中的历史营销活动 {#syncing-historic-campaigns-in-dynamics}

只要在[!DNL Dynamics]内将过去发生的交互整理到营销活动中，[!DNL Marketo Measure]便能够逆向生成这些交互的接触点。

这通常涉及CRM中的工作，以便考虑历史日期。 对于在线操作（由JS跟踪）和离线操作（无法由JS跟踪），处理也将不同。

按照下面的说明以可同步到[!DNL Marketo Measure]的格式组织[!DNL Dynamics]中的历史数据。

**联机：**

历史数字数据需要组织为[!DNL Dynamics]个营销活动才能回填。 理想情况下，这种结构已经就位。

如果数据存储在其他位置（例如仍保留在Marketing Automation中），则需要将其推送到[!DNL Dynamics]并组织到相应的营销活动中。 然后，您需要考虑接触点日期，因为您希望它反映过去的日期，而不是您将其推送到[!DNL Dynamics]中的日期。 要覆盖此日期，您可以使用自定义“Buyer Touchpoint日期”字段更改日期。 您需要将其添加到营销列表表单。

![](assets/syncing-historical-data-2.png)

因此，您可以为该营销列表中的所有人批量设置将用于接触点日期的日期。 要获得更准确的历史日期，请为同一营销活动创建多个营销列表，每个列表都具有自己的接触点日期。 如果营销活动具有较短的时间范围，则可能值得每天创建营销列表。 如果营销活动具有较长的时间范围，则每周创建营销列表可能比较合理。

有关同步营销列表的详细信息，请参阅此处： [[!DNL Dynamics] 促销活动和营销列表](/help/channel-tracking-and-setup/offline-channels/legacy-processes/dynamics-campaigns-and-marketing-lists.md)

>[!NOTE]
>
>如果由于任何原因，您有一个在JavaScript上线日期之后处于活动状态的营销活动跟踪在线活动，请务必将&quot;[!UICONTROL Touchpoint End Date]&quot;字段设置为JS上线的日期。 这是为了避免同一交互出现重复的接触点。

注意事项：以这种方式添加的在线数据的粒度本质上低于通过JavaScript进行的在线数据[!DNL Marketo Measure]跟踪。 例如，不会填充表单URL、登陆页面、反向链接页面等字段。 因此，建议尽可能将营销活动细分为每个源。 以下是理想映射的示例。

| 动态营销活动类型 | 渠道 | 子渠道 |
|---|---|---|
| 付费搜索 — AdWords | 付费搜索 | AdWords |
| 付费搜索 — Bing | 付费搜索 | Bing |
| 付费搜索 — Yahoo | 付费搜索 | Yahoo |

如果您无法识别来源，或者这样不值得花时间和精力，则可以使用映射到某个渠道（称为“旧版数字”或“历史网站”）的营销活动类型。

**脱机：**

要将过去离线营销工作的接触点设置为可用，数据必须组织到[!DNL Dynamics]个营销活动中并同步到[!DNL Marketo Measure]。 该过程与当前离线渠道（通过营销列表或营销活动响应同步营销活动）中的过程相同。 以下是渠道映射的示例。

| 动态营销活动类型 | 渠道 | 子渠道 |
|---|---|---|
| 活动 — 赞助的会议 | 事件 | 赞助的会议 |
| 事件 — 合作伙伴事件 | 事件 | 合作伙伴活动 |
| 事件 — 托管事件 | 事件 | 托管事件 |
| 网络研讨会 — 合作伙伴网络研讨会 | 网络研讨会 | 合作伙伴网络研讨会 |

如果此数据尚未整理到具有正确日期集的营销活动中，则可以使用“Buyer Touchpoint日期”字段反映过去离线活动的准确日期。

