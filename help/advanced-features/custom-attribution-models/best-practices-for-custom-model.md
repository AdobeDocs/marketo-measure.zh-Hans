---
description: Marketo Measure用户自定义模型指南的最佳实践
title: 自定义模型的最佳实践
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
feature: Custom Models
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 0%

---

# 自定义模型的最佳实践 {#best-practices-for-custom-model}

## 概述 {#overview}

除了现成的归因模型[!DNL Marketo Measure]之外，第2层及更高层客户还可以访问自定义归因模型。

[!DNL Marketo Measure]自定义归因模型允许用户选择要包含在模型中的里程碑接触点位置和/或自定义阶段。 此外，用户可以控制模型中每个阶段的归因点数百分比（用户最多可定义6个额外的自定义阶段），也可以使用[!DNL Marketo Measure]机器学习模型建议的归因百分比值。

自定义归因模型有两个关键方面：

**自定义阶段**&#x200B;允许用户定义与其业务和流程相关的funnel。 自定义阶段应该在整个购买者历程中代表“里程碑”，就像股票归因模型中的[!DNL Marketo Measure]里程碑（首次联系、潜在客户创建联系、机会创建联系和已关闭的成功联系）一样。 必须在帐户中正确定义和映射自定义阶段，以确保[!DNL Marketo Measure]正确跟踪阶段过渡，这一点至关重要。 这是为了确定应该与每个阶段关联的接触点，并相应地归因点数。 自定义阶段映射本质上是标准“阶段映射”的扩展，应遵循相同的实践。

>[!NOTE]
>
>有关更多详细信息，请参阅阶段映射最佳实践资源

**自定义归因建模**&#x200B;会在您选择自定义阶段funnel后定义。 然后，用户可以控制应该为每个自定义阶段以及[!DNL Marketo Measure]里程碑阶段分配多少归因点数。 用户可以在他们认为合适的时候为每个阶段分配点数，或者引用[!DNL Marketo Measure]机器学习模型，该模型基于历史数据用作“建议模型”。

自定义模型的这两个方面定义得准确和准确，这一点至关重要，以确保[!DNL Marketo Measure]生成准确的自定义归因模型。

## 最佳实践 {#best-practice}

无论您是首次设置自定义模型，还是查看之前已建立的模型，务必要牢记以下最佳实践。

* 开始简单
   * 确定要添加到自定义模型中的关键阶段，这些阶段对[!DNL Marketo Measure]报表至关重要。 通常，这些阶段是您经常会衡量或希望获得insight的阶段
   * 您可以随时添加到自定义模型
* 利用[!DNL Marketo Measure]机器学习模型
   * 如果您难以确定归因划分的百分比，则[!DNL Marketo Measure]机器学习模型可以帮助您在设置自定义归因模型时做出明智的决策。
   * 查看机器学习模型时，每个阶段的归因百分比反映了营销工作的潜在影响
      * 百分比越高意味着营销活动会直接影响funnel在该点的移动
      * 归因百分比越低，意味着阶段对团队进行监控的重要性就越低
* 您必须根据Lead或Contact阶段定义funnel顶部的阶段，而不是同时定义这两个阶段
   * 这意味着，您必须确保所有人员都通过相对对象上的该阶段
      * 例如：如果从Lead对象定义MQL阶段，则所有人员必须作为Lead进入您的系统，并在其Lead记录中标记为MQL，以便[!DNL Marketo Measure]能够准确地反映与该Lead向MQL的过渡相关的接触。 如果不是这种情况，并且某些人在成为MQL作为潜在客户之前进度到联系，[!DNL Marketo Measure]将无法准确地在您的接触点数据中说明这一点，我们将必须假设该人员已经拥有MQL。[!DNL Marketo Measure]无法考虑阶段跳转，因此我们将推断阶段已通过，即使它们尚未通过。
* 确保为您用于定义合并的自定义阶段的所有字段启用字段历史记录跟踪
* 请勿使用公式字段定义自定义阶段
   * 布尔字段是最佳实践推荐
* 不要将自定义阶段合并到自定义模型中，因为自定义模型与[!DNL Marketo Measure]里程碑接触点位置（FT、LC、OC、已结束的胜利/失败）一致
   * 如果您这么做，这些职位始终同时出现，并且可能会导致将夸大归因点数分配给funnel的某些部分。
* 与您的Sales Opp团队合作
   * 引入最接近阶段工作的团队及其含义可确保您使用正确的阶段，并确保正确定义阶段

## 维护的最佳实践 {#best-practice-for-maintenance}

每年至少两次查看您的自定义模型，将确保您的自定义归因报告准确可靠。

如果您的自定义模型使用机器学习模型，则应每季度在自定义模型中查看其应用，以确保自定义模型尽可能最新。

可能触发自定义模型审阅的其他原因包括……

* 您的营销团队中的人员调整
* 对CRM阶段所做的任何更改
* 对贵组织funnel的更新
* 应用自定义模型时，在[!DNL Marketo Measure]报表中看到不准确的收入数据
* 查看填充与您的组织funnel不再相关的接触点位置

>[!MORELIKETHIS]
>
>* [自定义归因模型和设置](/help/advanced-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [为自定义模型启用字段历史记录跟踪](/help/advanced-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [机器学习模型](/help/advanced-features/custom-attribution-models/machine-learning-model-faq.md)
