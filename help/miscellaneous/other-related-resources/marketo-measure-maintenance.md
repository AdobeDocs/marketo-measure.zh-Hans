---
unique-page-id: 18874556
description: '"[!DNL Marketo Measure] 维护 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] 维护”'
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# [!DNL Marketo Measure] 维护 {#marketo-measure-maintenance}

[!DNL Marketo Measure] 每天从您的CRM中提取几乎所有需要的内容，但您需要定期安排一些维护任务来保留 [!DNL Marketo Measure] 哼唱并输出最准确的信息。

**同步新离线促销活动的购买者接触点（2x/月）**

正如你在入门时所学到的， [!DNL Marketo Measure] 通过与CRM的营销活动同步，获取有关离线营销工作的信息。 在贵组织启动新促销活动时，请务必为每个促销活动启用“买方接触点”(Buyer Touchpoints)，以便在需要时进行。 查看 [本文](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)以了解更多信息。

**所有渠道的上传花费（1x/月）**

利用全面收入和ROI报告功能，[!DNL Marketo Measure]，您需要告诉 [!DNL Marketo Measure] 您在每个营销渠道和子渠道上的花费。 我们建议指定每个渠道/子渠道的所有者，并让这些人员向负责按月上传新成本信息的单一交易方报告支出。

通过阅读 [本文](/help/marketing-spend/spend-management/marketing-channel-costs.md).

**更新要跟踪的域列表（1x/月）**

Marketo Measure会跟踪Javascript处于活动状态的所有页面和子域，但仅适用于我们了解的域。 如果您最近首次公开一个新域、在国际范围内展开或更改了您的主域，请联系 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 以确保我们相应地更新您的帐户。

**查看自定义渠道映射的准确性（1x/月）**

在入门过程中，您可以为在线和离线营销工作设置自定义渠道映射。 随着您的营销策略和Marketo Measure用法的不断发展，您将希望关注该映射逻辑，以确保对您的所有接触点进行适当分类。

记住， [!DNL Marketo Measure] 在编辑映射逻辑时会重新处理数据，因此您将无法每7天更改一次这些规则。

参考 [本文](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) 对于联机设置， [本文](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md) 对于离线设置，以及从我们的客户那里策划的最佳实践列表：

* 查看当前属于您设置的任何“其他”或“空”渠道的接触点。 如果适用，请更新映射逻辑，以便将这些接触点重新分类为更准确的渠道。
* 查看当前属于您的直接渠道的接触点。 如果您的某些电子邮件营销活动或其他工作缺少UTM参数，则很可能会将流量不适当地存储到直接渠道中。 考虑更新UTM参数以捕获引荐源。

**评估接触点抑制设置（1x/季度）**

如果您看到许多接触点，则您不希望在归因文章中(从 [!DNL Login] 或 [!DNL Unsubscribe forms]、职业页面或内部应用程序（例如），您可能需要评估现有的接触点抑制设置。 每季度一次，找出产生不必要噪声的任何接触点组，并适当更新抑制逻辑。 [这是一篇有用的文章](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)  和操作方法。

**查看自定义阶段映射的准确性（1x/季度）（如果适用）**

如果您使用任何自定义 [!UICONTROL Lead], [!UICONTROL Contact]或 [!UICONTROL Opportunities] 阶段时，您可能还自定义了这些阶段映射到的管道的哪些部分，以及这些阶段是否包含在自定义归因模型中。 每季度访问一次 [本文](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md) 要在自定义阶段映射上刷新内存，并确保准确跟踪自定义阶段。

**将机器学习模型与自定义模型权重（1x/季度）进行比较（如果适用）**

如果您获得 [!DNL Marketo Measure] 自定义模型中，您还可以在 [!UICONTROL Settings] > [!UICONTROL Attribution Settings]. MLM使用您帐户中的接触点数据计算每个阶段的重要性，并可能帮助您确定如何在自定义模型中分配归因权重。 我们建议每季度将MLM与您的自定义模型进行比较一次，并讨论对您的自定义模型的潜在更改与您的SM的影响。

有关 [!DNL Marketo Measure] 机器学习模型，查看 [本文](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).
