---
unique-page-id: 18874556
description: '[!DNL Marketo Measure]维护 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]维护'
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
feature: Tracking
source-git-commit: fca2db86611d16f4e74467405521a89dd5d825ab
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# [!DNL Marketo Measure]维护 {#marketo-measure-maintenance}

[!DNL Marketo Measure]每天都会从您的CRM中提取它所需的一切，但您应定期计划一些维护任务，以使[!DNL Marketo Measure]保持运转并输出尽可能准确的信息。

**同步新离线促销活动的购买者接触点（2x/月）**

正如您在入门培训期间了解的那样，[!DNL Marketo Measure]通过与CRM的营销活动同步来获取有关离线营销工作的信息。 在贵组织启动新活动时，请确保为每个活动启用适当的买方接触点。

**上传所有渠道的支出（1x/月）**

要利用[!DNL Marketo Measure]的全部收入和ROI报告功能，您必须告知[!DNL Marketo Measure]您对每个营销渠道和子渠道的支出情况。 指定每个渠道/子渠道的所有者，并让这些人员向每月负责上传新成本信息的单一方报告支出。

通过阅读[本文](/help/marketing-spend/spend-management/marketing-channel-costs.md)，刷新您关于如何上载成本信息的内存。

**更新要跟踪的域列表（1x/月）**

Marketo Measure会跟踪我们的Javascript处于活动状态的所有页面和子域，但仅限于我们知道的域。 如果您最近推出了新域、进行了国际扩展或更改了主域，请联系[Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}，以确保我们相应地更新您的帐户。

**检查自定义渠道映射的准确性（1x/月）**

在新用户引导期间，您可以为在线和离线营销工作设置自定义渠道映射。 随着营销策略和Marketo Measure用法的发展，您需要关注该映射逻辑，以确保对所有接触点进行适当分类。

请记住，编辑映射逻辑时，[!DNL Marketo Measure]会重新处理您的数据，因此您无法每七天多次更改这些规则。

参考[本文](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)进行联机设置，[参考本文](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)进行脱机设置，并参考我们客户策划的最佳实践列表：

* 查看当前属于您可能已设置的任何“其他”或“空”渠道的接触点。 如果适用，请更新您的映射逻辑，将这些接触点重新分类到更准确的渠道中。
* 查看当前属于您的“直接”渠道的接触点。 如果您的某些电子邮件营销活动或其他工作缺少UTM参数，则流量很有可能被不适当地分段到直接渠道中。 请考虑更新UTM参数以捕获反向链接源。

**评估接触点隐藏设置（1x/季度）**

如果您在归因故事中看到许多您不希望考虑的接触点（例如[!DNL Login]或[!DNL Unsubscribe forms]、职业生涯页面或内部应用程序中的接触点），您可能需要评估现有的接触点隐藏设置。 每季度一次，找出任何一组产生不必要噪音的接触点，并适当更新您的抑制逻辑。 [以下是一篇有用的文章](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)介绍操作方法。

**审核自定义阶段映射的准确性（1x/季度）（如果适用）**

如果您使用的是任何自定义[!UICONTROL Lead]、[!UICONTROL Contact]或[!UICONTROL Opportunities]阶段，则您可能还自定义了这些阶段映射到的管道部分，以及这些阶段是否包含在自定义归因模型中。 每季度访问一次[本文](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)以刷新自定义阶段映射上的内存，并确保准确跟踪自定义阶段。

**比较机器学习模型与自定义模型权重（1x/季度）（如果适用）**

如果您已获得[!DNL Marketo Measure]自定义模型的许可，则在[!UICONTROL Settings] > [!UICONTROL Attribution Settings]中还有来自我们的机器学习模型(MLM)的可用数据。 MLM会使用您帐户中的接触点数据计算每个阶段的重要性，并且可能会帮助您确定如何在自定义模型中分配归因权重。 我们建议每季度将MLM与您的自定义模型比较一次，并与您的SM讨论对自定义模型的潜在更改的影响。

有关[!DNL Marketo Measure]机器学习模型的详细信息，请查看[本文](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)。
