---
unique-page-id: 42762310
description: 正在同步历史数据 —  [!DNL Marketo Measure]  — 产品文档
title: 正在同步历史数据
exl-id: 5a3c1a71-463a-4d75-98b9-fc225839512a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '1487'
ht-degree: 0%

---

# 正在同步历史数据 {#syncing-historical-data}

[!DNL Marketo Measure] 是一种可提供最精细、最可操作数据的解决方案。 但是，我们了解您可能已拥有要归因的现有数据。 可以为历史数据生成接触点，但在继续执行此过程之前，务必要考虑一些因素。

## 需考虑的因素 {#factors-to-consider}

**数据是否已组织到营销策划中？**

a.数据需要组织到营销活动中，才能与同步到 [!DNL Marketo Measure] 以便生成接触点。 如果它当前未组织到营销活动中，您将需要评估是否需要花费时间和资源将数据细分到相应的营销活动中。

b.将在接触点日期使用成员添加到营销活动或标记为已响应的日期，因此这一日期也需要准确。 [!DNL Marketo Measure] 提供了SFDC和MSD中用于更新日期的解决方法，但这可能会因数量而非常耗时。

**您是否有相当数量的数据被组织到所有渠道的促销活动中（付费搜索、事件、免费等）？**

要获得准确且“公平”的报告，必须平衡归因情况。 例如，如果您只拥有用于事件等历史离线渠道工作的数据，则数据将具有内在偏差，而没有历史在线数据来补充。

**您希望达到何种粒度级别？**

您基本上只知道渠道、子渠道和促销活动名称。

**您将来的报告目标是什么？**

此数据将会受到限制，因此请务必考虑如何使用此数据。 将历史数据与未来数据进行比较可能没什么意义。

**你想走多远？**

[!DNL Marketo Measure] 强烈建议不要过去一年。

我们强烈建议您与 [!DNL Marketo Measure] 先联系。 如果您已考虑上述内容，并且想要继续，请按照常规说明(单独 [!DNL Salesforce] 和 [!DNL Microsoft Dynamics])。

## 在中同步历史营销活动 [!DNL Salesforce] {#syncing-historic-campaigns-in-salesforce}

**在线:**

要同步历史联机数据，必须将数据组织到Salesforce促销活动中，然后您要将其同步到 [!DNL Marketo Measure] 通过 [!DNL Salesforce] 中的促销活动同步规则 [!DNL Marketo Measure] 应用程序。 务必确保在JavaScript启用日期后，不会从其中任何营销活动中生成接触点。 原因是为了避免重复接触点。 JavaScript上线后，将自动跟踪在线工作，因此我们不希望通过SFDC促销活动跟踪这些工作。 要避免出现此问题，请务必为规则添加时间感。 可能类似于“营销活动成员创建日期小于 [JavaScript上线日期]&quot;

![](assets/syncing-historical-data-1.png)

用于历史在线数据的渠道映射组件可能比较棘手。 我们希望它尽可能与您当前的在线渠道规则（从在线规则表中）匹配，以便清理报告。 以下是理想渠道映射的示例。

>[!NOTE]
>
>此渠道映射在 [!UICONTROL Offline Channels] 部分 [!DNL Marketo Measure] 应用程序，因为我们使用的是SFDC营销活动。

| Salesforce促销活动类型 | 渠道 | 子渠道 |
|---|---|---|
| 付费搜索 — AdWords | 付费搜索 | AdWords |
| 付费搜索 — Bing | 付费搜索 | 兵 |
| 付费搜索 — Yahoo | 付费搜索 | Yahoo |

以这种方式添加的在线数据本身将比在线数据更不精细 [!DNL Marketo Measure] 跟踪。 例如，将不会填充表单URL、登陆页面、反向链接页面等字段。 因此，建议尽可能将营销活动划分到每个源。 如上面的示例所示，您需要为每个源具有多个促销活动类型，才能在报表中具有粒度。

SFDC促销活动类型的数量支持粒度渠道映射，这可能是不可能的，也是不合理的，因此您可能只是求助于映射到渠道级别，而忽略子渠道。 如果渠道级别也不为人所知，您可以设置诸如“历史数字”之类的代理渠道，以便您至少知道它是在线联系渠道。

如果您需要批量编辑将推送这些历史联机工作的接触点日期，请使用 [!DNL Marketo Measure] 自定义&quot;[!UICONTROL Bulk Update Touchpoint Date]“ ”按钮（此字段可作为SFDC中促销活动对象上的自定义字段使用）。 如果营销活动的时间跨度较短，则可能有必要在一天间隔内批量编辑接触点日期，而如果营销活动的时间跨度较长，则可能适合每周批量更新。 如果您确实使用批量更新接触点日期功能，请确保更新促销活动同步规则，以在日期字段中使用买方接触点日期。 请注意，如果这仅适用于一个或两个营销活动，而不是全部，则可能需要使用您的营销活动同步规则获得创意。

**脱机：**

离线营销工作的历史数据（无法通过JavaScript跟踪的数据）也需要组织到SFDC营销活动中。 SFDC营销活动是 [!DNL Marketo Measure] 跟踪离线工作，而不考虑活动是“历史”还是“当前/后期”[!DNL Marketo Measure] 实施”，因此请遵循在原始离线渠道配置培训中确定的相同渠道映射。

如有必要，请使用“批量更新接触点日期”按钮批量编辑营销活动成员的接触点日期。 例如，如果您在事件发生后创建SFDC促销活动，则需要在正确的日期进行批量编辑。 如果您确实使用批量更新接触点日期功能，请确保更新促销活动同步规则，以在日期字段中使用买方接触点日期。 请注意，如果这仅适用于一个或两个营销活动，而不是全部，则可能需要使用您的营销活动同步规则获得创意。

## 在中同步历史营销活动 [!DNL Dynamics] {#syncing-historic-campaigns-in-dynamics}

[!DNL Marketo Measure] 能够为过去发生的交互以追溯方式生成接触点，只要这些交互被组织到 [!DNL Dynamics].

这通常涉及在CRM中处理历史日期。 对于在线工作（由JS跟踪）和离线工作（由JS无法跟踪），处理方式也将有所不同。

请按照以下说明组织 [!DNL Dynamics] 格式，可同步到 [!DNL Marketo Measure].

**在线:**

历史数字数据需要组织为 [!DNL Dynamics] 营销活动。 理想情况下，此结构已经到位。

如果数据存储在其他位置（例如仍生活在营销自动化中），则需要将其推送到 [!DNL Dynamics] 并组织到相应的营销活动中。 然后，您需要考虑接触点日期，因为您希望该日期反映过去的日期，而不是您将其推送到的日期 [!DNL Dynamics]. 要覆盖此日期，您可以使用自定义“采购员接触点日期”字段更改日期。 您需要将其添加到营销列表表单。

![](assets/syncing-historical-data-2.png)

因此，您可以批量设置该营销列表中将用于接触点日期的每个人的日期。 要获得更准确的历史日期，请为同一营销活动创建多个营销列表，每个营销列表具有自己的接触点日期。 如果营销活动的时间跨度较短，则可能有必要为每天创建一个营销列表。 如果营销活动的时间跨度较长，则每周创建营销列表可能更合适。

有关同步营销列表的更多信息，请参阅此处： [[!DNL Dynamics] 促销活动和营销列表](/help/marketo-measure-and-dynamics/dynamics-reporting/dynamics-campaigns-and-marketing-lists.md)

>[!NOTE]
>
>如果您的促销活动跟踪在线活动在JavaScript起始日期之前处于活动状态，请务必将“[!UICONTROL Touchpoint End Date]“ ”字段。 这是为了避免同一交互具有重复的接触点。

注意事项：以这种方式添加的在线数据本身将比在线数据更不精细 [!DNL Marketo Measure] 跟踪。 例如，以下字段：将不会填充表单URL、登陆页面、反向链接页面等。 因此，建议尽可能将营销活动划分到每个源。 以下是理想映射的示例。

| Dynamics促销活动类型 | 渠道 | 子渠道 |
|---|---|---|
| 付费搜索 — AdWords | 付费搜索 | AdWords |
| 付费搜索 — Bing | 付费搜索 | 兵 |
| 付费搜索 — Yahoo | 付费搜索 | Yahoo |

如果您无法识别源或不值得花时间和精力，则可以使用一种营销活动类型，将其映射到类似于“旧版数字”或“历史网站”的渠道。

**脱机：**

要为过去的离线营销工作提供接触点，必须将数据组织为 [!DNL Dynamics] 营销活动和同步到 [!DNL Marketo Measure]. 该过程与当前离线渠道的过程相同（通过营销列表或营销活动响应同步营销活动）。 以下是渠道映射示例。

| Dynamics促销活动类型 | 渠道 | 子渠道 |
|---|---|---|
| 活动 — 赞助会议 | 事件 | 赞助会议 |
| 事件 — 合作伙伴事件 | 事件 | 合作伙伴事件 |
| 事件 — 托管事件 | 事件 | 托管事件 |
| 网络研讨会 — 合作伙伴网络研讨会 | 网络研讨会 | 合作伙伴网络研讨会 |

如果此数据尚未组织到设置了正确日期的营销活动中，则可以使用“购买者接触点日期”字段来反映离线活动过去的准确日期。
