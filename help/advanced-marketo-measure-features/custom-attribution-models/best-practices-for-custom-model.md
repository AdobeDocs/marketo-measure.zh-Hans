---
description: 自定义模型的最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: 自定义模型的最佳实践
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# 自定义模型的最佳实践 {#best-practices-for-custom-model}

## 概述 {#overview}

除 [!DNL Marketo Measure] 第2层客户及更高层客户可开箱即用地访问自定义归因模型。

的 [!DNL Marketo Measure] 自定义归因模型允许用户选择要包含在模型中的里程碑接触点位置和/或自定义阶段。 此外，用户还可以控制归因到模型中每个阶段的点数百分比（用户最多可以定义6个其他自定义阶段），也可以使用 [!DNL Marketo Measure] 机器学习模型。

自定义归因模型的两个关键方面：

**自定义阶段** 允许用户定义与其业务和流程相关的漏斗。 自定义阶段应表示整个购买者历程中的“里程碑”，与 [!DNL Marketo Measure] 里程碑（首次联系、潜在客户创建联系、机会创建联系和闭合原始联系）在库存归因模型中执行。 必须在您的帐户中正确定义和映射自定义阶段，以确保 [!DNL Marketo Measure] 正确跟踪阶段过渡。 这是为了确定每个阶段应与哪些接触点关联，并适当地分配点数。 自定义阶段映射本质上是标准“阶段映射”的扩展，应遵循相同的实践。

>[!NOTE]
>
>有关更多详细信息，请参阅阶段映射最佳实践资源

**自定义归因建模** 在您选择自定义阶段漏斗后定义。 然后，用户可以控制应将多少归因点数分配给每个自定义阶段，以及 [!DNL Marketo Measure] 里程碑阶段。 用户可以根据自己认为适合的情况将点数分配给每个阶段，或引用 [!DNL Marketo Measure] 机器学习模型，它以历史数据为基础，充当“建议性模型”。

必须正确准确地定义自定义模型的这两个方面，以确保 [!DNL Marketo Measure] 正在生成一个准确的自定义归因模型。

## 最佳实践 {#best-practice}

无论您是首次设置自定义模型，还是查看之前已建立的模型，都必须牢记以下最佳实践。

* 开始简单
   * 确定要添加到自定义模型中对您的 [!DNL Marketo Measure] 报表。 通常，您通常会针对这些阶段进行测量，或者希望了解这些阶段
   * 您始终可以随着时间的推移向自定义模型中添加
* 利用 [!DNL Marketo Measure] 机器学习模型
   * 如果您难以确定属性突破百分比，请 [!DNL Marketo Measure] 机器学习模型可帮助您在设置自定义归因模型时做出明智的决策。
   * 在查看机器学习模型时，每个阶段的归因百分比会反映营销工作的潜在影响
      * 百分比越高，意味着营销会直接影响漏斗在该点的移动
      * 归因百分比越低，表示阶段对您的团队进行监控的重要性就越低
* 您必须根据潜在客户阶段或联系阶段来定义漏斗阶段的排名最前的阶段，而不是同时定义这两个阶段
   * 这意味着您必须确保所有人员都在相对对象上通过该阶段
      * 例如：如果从Lead对象定义MQL阶段，则所有人员都必须作为Lead进入系统，并在其Lead记录中标记为MQL，以便 [!DNL Marketo Measure] 以准确反映哪个接触与潜在客户过渡到MQL相关。 如果情况并非如此，并且有些人在成为MQL作为潜在客户之前会进入“联系”， [!DNL Marketo Measure] 将无法在您的接触点数据中准确地说明这一点，因此我们必须假定该人已经拥有MQL&#39;d。 [!DNL Marketo Measure] 不能考虑跳台，因此我们会推断，即使没有跳台，阶段也已经通过。
* 确保为用于定义您合并的自定义阶段的所有字段启用字段历史记录跟踪
* 请勿使用公式字段定义自定义阶段
   * 布尔字段是最佳实践推荐
* 请勿在与 [!DNL Marketo Measure] 里程碑接触点位置（FT、LC、OC、已关闭的赢/丢失）
   * 如果您这样做，这些位置将始终同时发生，并且可能会导致漏斗中某些部分的归因点数虚增。
* 与您的销售运营团队合作
   * 引入与阶段工作最接近的团队及其含义将确保您使用正确的阶段并正确定义这些阶段

## 维护最佳实践 {#best-practice-for-maintenance}

每年至少审查两次自定义模型可确保自定义归因报告准确可靠。

如果您的自定义模型利用机器学习模型，则应每季在自定义模型中查看其应用程序，以确保自定义模型尽可能是最新的。

可能触发对自定义模型的审核的其他原因包括……

* 营销团队的营业额
* 对CRM阶段所做的任何更改
* 更新了您的组织漏斗
* 在 [!DNL Marketo Measure] 应用自定义模型时报告
* 查看已填充的接触点位置与您的组织漏斗不再相关

>[!MORELIKETHIS]
>
>* [自定义归因模型和设置](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [为自定义模型启用字段历史记录跟踪](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [机器学习模型](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)

