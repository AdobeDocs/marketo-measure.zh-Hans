---
unique-page-id: 18874535
description: 过渡到 [!DNL Marketo Measure] 从全圈 —  [!DNL Marketo Measure]  — 产品文档
title: 过渡到 [!DNL Marketo Measure] 从全圈
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---

# 过渡到 [!DNL Marketo Measure] 从全圈 {#transitioning-to-marketo-measure-from-full-circle}

从“全圈”移动到 [!DNL Marketo Measure]? 你不孤独。 以下是需要记住的最大考虑事项，以及我们从其他已做出转换的客户那里学到的经验教训。

## 基于促销活动的跟踪与多源跟踪 {#campaign-based-tracking-vs-multi-source-tracking}

中的所有交互 [!UICONTROL Full Circle] 通过CRM促销活动会员资格进行跟踪。 使用 [!DNL Marketo Measure]，则购买历程将通过JavaScript、CRM促销活动成员资格和CRM活动记录的组合进行编译。 要想从“必须在CRM营销活动中跟踪所有交互，才能使归因报表正常工作”转向“只需在CRM营销活动中跟踪此交互子集，即可使归因报表正常工作”，这可能会很棘手。

一般来说，下面是 [!DNL Marketo Measure] 为主要类型的交互创建接触点记录：

* 网站上的表单填充： [!DNL Marketo Measure] Javascript
* 您网站上的页面查看次数：创建者 [!DNL Marketo Measure] 仅当此页面查看驱动了指定的CRM里程碑时（如商机或商机创建），才会使用Javascript
* 会议或贸易展等离线互动：CRM促销活动会员资格
* 在Internet上非您网站的任何位置发生的数字交互（例如，在第三方网站上托管的生成列表上载的网络研讨会）：CRM促销活动会员资格
* 与销售团队的交互：CRM活动记录

如果您熟悉CRM促销活动管理，并且希望保持现有流程就位，那就没问题。 没伤 [!DNL Marketo Measure] 以继续跟踪CRM促销活动中的所有交互。 您可以设计仅从所需营销活动子集创建接触点的逻辑，以避免接触点重复。

## 可见性与归因 {#visibility-vs-attribution}

通过设置大多数“完整圈”，您可以看到客户与您的营销或销售工作进行的每次互动。 页面查看、重复的页面访问、重复和一式三次的营销活动中的成员资格 — 全圈可显示所有这些内容。 如果您查看了300次页面，则“完整圈子”将创建300个重复的营销活动，并为您提供每个活动的会员资格。 [!DNL Marketo Measure] 不是，这是我们有意识的设计决定。

[!DNL Marketo Measure] 旨在为您提供一个归因故事，该故事可显示有意义的交互并适当地在最具影响力的接触点之间分配权重。 例如， [!DNL Marketo Measure] 框架不会将页面查看（不包含表单填充）显示为常规接触点。 独立页面查看不太可能对推动购买历程产生影响，但如果这是指定CRM里程碑之前的最近交互（如商机或商机创建），我们将创建一个接触点。 我们不想给你看一切。 从归因的角度，我们想向您展示一些重要的内容。

使用 [!DNL Marketo Measure] rep会针对哪些数据将不再可供您的团队使用设置适当的期望值。

## 预[!DNL Marketo Measure] 数据 {#pre-marketo-measure-data}

标准建议从您部署 [!DNL Marketo Measure] JavaScript转发，而且对于前Full Circle客户而言，这一比例会翻倍。 请考虑以上两个部分：您习惯于看到更多数据，并且习惯了所有来自CRM促销活动成员资格的数据。 如果您选择在 [!DNL Marketo Measure] 实施时，您不会比较整个JavaScript实施日期的apple和apple。

话虽如此，我们当然明白，许多客户需要这些历史数据；特别是如果销售周期较长（超过90天），您可能希望 [!DNL Marketo Measure] 预先查看[!DNL Marketo Measure] 数据。 请与您的 [!DNL Marketo Measure] 表示，并始终记住，实施日期的偏差可能会导致渠道性能或参与度出现改善或下降，以及其他可能不正确的推论。

## 摘要 {#in-summary}

您的公司状况良好，我们已帮助许多其他客户处理这些更改。 使用 [!DNL Marketo Measure] rep以了解上述影响以及您可能遇到的任何其他问题。
