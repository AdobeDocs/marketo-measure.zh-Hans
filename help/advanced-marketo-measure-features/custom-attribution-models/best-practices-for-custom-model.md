---
description: 自定义模型的最佳实践 —  [!DNL Marketo Measure]
title: 自定义模型的最佳实践
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
feature: Custom Models
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# 自定义模型的最佳实践 {#best-practices-for-custom-model}

## 概述 {#overview}

除了 [!DNL Marketo Measure] 现成的归因模型，第2层及更高层的客户可以访问自定义归因模型。

此 [!DNL Marketo Measure] 自定义归因模型允许用户选择要包含在模型中的里程碑接触点位置和/或自定义阶段。 此外，用户可以控制模型中每个阶段的归因点数百分比（用户最多可以定义6个其他自定义阶段），也可以使用 [!DNL Marketo Measure] 机器学习模型。

自定义归因模型有两个关键方面：

**自定义阶段** 允许用户定义与其业务和流程相关的漏斗。 自定义阶段应该在整个购买者历程中代表“里程碑”，非常类似于 [!DNL Marketo Measure] 里程碑（“首次联系”、“潜在客户创建联系”、“机会创建联系”和“非公开联系”）在股票归因模型中执行。 在您的帐户中正确定义和映射自定义阶段非常重要，这样可以确保 [!DNL Marketo Measure] 正在正确跟踪阶段过渡。 这是为了确定应该与每个阶段关联的接触点，并相应地归因点数。 自定义阶段映射本质上是标准“阶段映射”的扩展，应遵循相同的实践。

>[!NOTE]
>
>有关更多详细信息，请参阅阶段映射最佳实践资源

**自定义归因建模** 在选择“自定义暂存”漏斗后定义。 然后，用户可以控制应当为每个自定义阶段分配多少归因点数以及 [!DNL Marketo Measure] 里程碑阶段。 用户可以按自己认为合适的方式为每个阶段分配点数，也可以参考 [!DNL Marketo Measure] 机器学习模型，作为基于历史数据的“建议模型”。

必须正确定义自定义模型的这两个方面，以确保 [!DNL Marketo Measure] 正在生成准确的自定义归因模型。

## 最佳实践 {#best-practice}

无论您是首次设置自定义模型，还是查看之前已建立的模型，务必要牢记以下最佳实践。

* 开始简单
   * 确定您要添加到自定义模型中的关键阶段，这些阶段对您的至关重要 [!DNL Marketo Measure] 报表。 通常，这些阶段是您经常会衡量或希望获得洞察的阶段
   * 您可以随时添加到自定义模型
* 利用 [!DNL Marketo Measure] 机器学习模型
   * 如果您难以确定归因划分的百分比， [!DNL Marketo Measure] 机器学习模型可帮助您在设置自定义归因模型时做出明智的决策。
   * 查看机器学习模型时，每个阶段的归因百分比反映了营销工作的潜在影响
      * 较高的百分比意味着营销可以直接影响漏斗在该点的运动
      * 归因百分比越低，意味着阶段对团队进行监控的重要性就越低
* 您必须根据“潜在客户”或“联系人”阶段定义漏斗顶部的阶段，而不是同时定义这两个阶段
   * 这意味着，您必须确保所有人员都通过相对对象上的该阶段
      * 例如：如果您从Lead对象定义MQL阶段，则所有人员必须作为Lead进入您的系统，并在其Lead记录中标记为MQL，以便 [!DNL Marketo Measure] 以准确反映哪个接触与Lead过渡到MQL有关。 如果不是这种情况，并且一些人会在成为MQL作为潜在客户之前进展到联系， [!DNL Marketo Measure] 将无法精确说明您的接触点数据中的此情况，因此我们将必须假设该人员已拥有MQL。 [!DNL Marketo Measure] 无法考虑跳台事件，因此我们将推断阶段已通过，即使它们没有通过。
* 确保为您用于定义合并的自定义阶段的所有字段启用字段历史记录跟踪
* 请勿使用公式字段定义自定义阶段
   * 布尔字段是最佳实践推荐
* 不要将自定义阶段合并到自定义模型中，因为该模型与 [!DNL Marketo Measure] 里程碑接触点位置（FT、LC、OC、已结束的赢家/输家）
   * 如果您这样做，这些位置将始终同时出现，并且可能导致漏斗的部分属性点数夸大。
* 与您的Sales Opp团队合作
   * 引入与阶段工作最密切的团队，以及他们的意义将确保您使用正确的阶段，并且他们的定义正确

## 维护的最佳实践 {#best-practice-for-maintenance}

每年至少两次查看您的自定义模型，将确保您的自定义归因报告准确可靠。

如果您的自定义模型使用机器学习模型，则应每季度在自定义模型中查看其应用，以确保自定义模型尽可能最新。

可能触发自定义模型审阅的其他原因包括……

* 您的营销团队中的人员调整
* 对CRM阶段所做的任何更改
* 组织漏斗的更新
* 在您的网站中看到不准确的收入数据 [!DNL Marketo Measure] 应用自定义模型时报告
* 查看填充与组织漏斗不再相关的接触点位置

>[!MORELIKETHIS]
>
>* [自定义归因模型和设置](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [为自定义模型启用字段历史记录跟踪](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [机器学习模型](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)
