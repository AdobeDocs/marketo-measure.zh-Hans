---
unique-page-id: 18874535
description: 转换到 [!DNL Marketo Measure] 从完整圆圈 —  [!DNL Marketo Measure]
title: 转换到 [!DNL Marketo Measure] 从完整圆形
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
feature: Attribution, Fundamentals
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 0%

---

# 转换到 [!DNL Marketo Measure] 从完整圆形 {#transitioning-to-marketo-measure-from-full-circle}

从“完整圆形”移至 [!DNL Marketo Measure]？ 你并不孤单。 以下是要牢记的最大注意事项，以及从其他作出转换的客户那里学到的经验教训。

## 基于营销活动的跟踪与多源跟踪 {#campaign-based-tracking-vs-multi-source-tracking}

中的所有交互 [!UICONTROL Full Circle] 将通过CRM campaign会员资格进行跟踪。 替换为 [!DNL Marketo Measure]，购买历程是通过我们的JavaScript、CRM Campaign会员资格和CRM活动记录的组合编译的。 从“为了使我们的归因报表正常运行，必须在CRM营销活动中跟踪所有交互”转移到“为了使我们的归因报表正常运行，必须在CRM营销活动中跟踪此交互子集”可能会很棘手。

一般来说，下面是具体操作方法 [!DNL Marketo Measure] 为主要类型的交互创建接触点记录：

* 表单填充您的网站： [!DNL Marketo Measure] JavaScript
* 您网站上的页面查看次数：创建者 [!DNL Marketo Measure] 仅当此页面查看推动指定的CRM里程碑时（例如创建潜在客户或机会），才使用JavaScript
* 离线交互，例如会议或商展：CRM营销活动成员资格
* 在Internet上非您网站的任何地方发生的数字交互（例如，在生成列表上传的第三方网站上托管的网络研讨会）： CRM营销活动成员资格
* 与销售团队的交互：CRM活动记录

如果您熟悉CRM营销活动管理，并且希望保留现有流程，那么没关系。 一点也不痛 [!DNL Marketo Measure] 以继续跟踪CRM营销活动中的所有交互。 您可以设计仅从所需的营销活动子集创建接触点的逻辑，以避免接触点重复。

## 可见性与归因 {#visibility-vs-attribution}

通过大多数Full Circle设置，您可以看到人员与您的营销或销售工作的每次交互。 页面查看次数、重复的页面访问次数、三元营销活动中的成员资格 — 全部为全圆曲面。 如果您查看某个页面300次，则Full Circle会创建300个重复的营销活动，并为您提供每个营销活动的成员资格。 [!DNL Marketo Measure] 没有，这是我们有意的设计决定。

[!DNL Marketo Measure] 旨在为您提供一个归因故事，该故事展示有意义的交互，并在最具影响力的接触点之间适当地分配权重。 例如， [!DNL Marketo Measure] 框架不会将页面查看（没有表单填充）显示为常规接触点。 独立页面查看可能不会影响购买历程，但是如果在指定的CRM里程碑之前（例如创建潜在客户或机会）是最近的一次交互，则我们会创建一个接触点。 我们不想让你看到一切。 我们想要从归因的角度向您展示重要的内容。

使用您的 [!DNL Marketo Measure] 代表针对您的团队将不再可用的数据设定适当的期望。

## 预先[!DNL Marketo Measure] 数据 {#pre-marketo-measure-data}

标准建议是从您部署之日起开始报告和收集数据 [!DNL Marketo Measure] JavaScript向前发展，对于以前的Full Circle客户来说更是如此。 请考虑上面的两个部分：您习惯于看到更多数据，并且习惯于来自CRM活动成员资格的所有数据。 如果您选择包括之前的部分或所有数据， [!DNL Marketo Measure] 在整个JavaScript实施日期内，您不会将应用程序与应用程序进行比较。

也就是说，我们当然理解许多客户需要这一历史数据；特别是如果您拥有更长的销售周期（超过90天），则您可能希望提供 [!DNL Marketo Measure] 可预见[!DNL Marketo Measure] 数据。 请仔细与您的 [!DNL Marketo Measure] 代表，并始终牢记，在实施日期之间发生偏差可能会导致渠道性能或参与度出现改进或下降，以及其他潜在的错误推断。

## 摘要 {#in-summary}

您公司情况不错，我们已经帮助许多其他客户处理了这些更改。 使用您的 [!DNL Marketo Measure] 代表了解以上影响以及您可能遇到的任何其他问题。
