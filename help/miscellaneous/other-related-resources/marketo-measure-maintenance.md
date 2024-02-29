---
unique-page-id: 18874556
description: "[!DNL Marketo Measure] 维护 —  [!DNL Marketo Measure]"
title: '"[!DNL Marketo Measure] 维护”'
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---

# [!DNL Marketo Measure] 维护 {#marketo-measure-maintenance}

[!DNL Marketo Measure] 每天从您的CRM中提取几乎所需的一切，但您需要定期计划保留一些维护任务 [!DNL Marketo Measure] 哼着唱并输出尽可能准确的信息。

**同步新离线促销活动的购买者接触点（每月2次）**

正如您在入职过程中所学的， [!DNL Marketo Measure] 通过与CRM的营销活动同步，获取有关离线营销工作的信息。 在贵组织启动新活动时，请确保为每个活动启用适当的买方接触点。 签出 [本文](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)以了解更多信息。

**上传所有渠道的支出（1x/月）**

充分利用收入和ROI报告功能，帮助[!DNL Marketo Measure]，您需要告诉 [!DNL Marketo Measure] 您在每个营销渠道和子渠道上的支出金额。 我们建议指定每个渠道/子渠道的所有者，并让这些人员向每月负责上传新成本信息的单一方报告支出。

通过阅读以下内容，刷新您关于如何上传成本信息的内存 [本文](/help/marketing-spend/spend-management/marketing-channel-costs.md).

**更新要跟踪的域列表（1x/月）**

Marketo Measure会跟踪我们的Javascript处于活动状态的所有页面和子域，但仅限于我们知道的域。 如果您最近推出了新域、进行了国际扩展或更改了您的主域，请与 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 以确保我们相应地更新您的帐户。

**审查自定义渠道映射的准确性（1x/月）**

在新用户引导期间，您可以为在线和离线营销工作设置自定义渠道映射。 随着营销策略和Marketo Measure用法的发展，您将需要关注该映射逻辑，以确保对所有接触点进行适当分类。

请记住， [!DNL Marketo Measure] 编辑映射逻辑时会重新处理数据，因此您无法每7天多次更改这些规则。

引用 [本文](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) 对于联机设置， [本文](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md) 对于离线设置，以及我们客户策划的最佳实践列表：

* 查看当前属于您可能已设置的任何“其他”或“空”渠道的接触点。 如果适用，请更新映射逻辑以将这些接触点重新分类为更准确的渠道。
* 查看当前属于您的“直接”渠道的接触点。 如果您的某些电子邮件营销活动或其他工作缺少UTM参数，则流量很有可能被不适当地分段到直接渠道中。 请考虑更新UTM参数以捕获反向链接源。

**评估接触点抑制设置（1x/季度）**

如果您在归因故事中看到了许多您不希望考虑的接触点(来自 [!DNL Login] 或 [!DNL Unsubscribe forms]、职业页面或内部应用程序等)中，您可能想要评估现有的接触点抑制设置。 每季度一次，找出任何一组产生不必要噪音的接触点，并适当更新您的抑制逻辑。 [以下是一篇有用的文章](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)  操作说明。

**检查自定义阶段映射的准确性（1x/季度）（如果适用）**

如果您使用任何自定义 [!UICONTROL Lead]， [!UICONTROL Contact]，或 [!UICONTROL Opportunities] 阶段，您还可以自定义这些阶段映射到的管道部分，以及这些阶段是否包含在自定义归因模型中。 每季度一次，访问 [本文](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md) 刷新自定义阶段映射的内存并确保准确跟踪自定义阶段。

**比较机器学习模型与自定义模型权重（1x/季度）（如果适用）**

如果您获得 [!DNL Marketo Measure] 自定义模型中，您还有来自我们的机器学习模型(MLM)的数据，位于 [!UICONTROL Settings] > [!UICONTROL Attribution Settings]. MLM会使用您帐户中的接触点数据计算每个阶段的重要性，并且可能会帮助您确定如何在自定义模型中分配归因权重。 我们建议每季度将MLM与您的自定义模型比较一次，并与您的SM讨论对自定义模型的潜在更改的影响。

欲知关于 [!DNL Marketo Measure] 机器学习模型，签出 [本文](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).
