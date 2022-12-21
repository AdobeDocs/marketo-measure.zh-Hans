---
unique-page-id: 37356132
description: '"[!DNL Marketo Measure] Dynamics的收入工作流 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] Dynamics的收入工作流”'
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 0%

---

# [!DNL Marketo Measure] Dynamics的收入工作流 {#marketo-measure-revenue-workflows-for-dynamics}

## 第一部分：预计收入与实际收入 {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] 指向一个开箱即用的标准收入字段（实际收入），但Dynamics有两个标准收入字段：实际收入和预计收入。 要在Discover功能板中提供管道收入，需要自定义字段和工作流，以便根据Opportunity是Open还是Closed(Won)，从Estimated Revenue或Actual Revenue字段中捕获正确的金额。

步骤1:在Dynamics中创建自定义业务机会金额字段

>[!NOTE]
>
>所有Dynamics收入字段都有一个基本字段和一个常规字段。 忽略基本字段。

步骤2:创建一个工作流，以更新在步骤1中创建的自定义业务机会金额字段和 [!DNL Marketo Measure] 机会金额字段。

>[!NOTE]
>
>我们不能指向 [!DNL Marketo Measure] Discover中具有Dynamics帐户的Opportunity Amount(bizible2_bizible_opportunity_amount)字段。 Dynamics客户必须为 [!DNL Marketo Measure] 指向Discover。 完成后，客户需要创建可更新的工作流 **both** the [!DNL Marketo Measure] 机会金额(bizible2_bizible_opportunity_amount) **和** 自定义机会金额字段。 的 [!DNL Marketo Measure] Opportunity Amount字段随包一起提供，但必须创建自定义字段。

金额工作流说明：

**工作流#1**:机会 — 更新 [!DNL Marketo Measure] 机会金额字段和自定义字段=预计收入

此工作流在每次Estimated Revenue发生更改时打开的业务机会上运行，并将更新 [!DNL Marketo Measure] Opportunity Amount字段和您的自定义字段等于Estimated Revenue字段。 该工作流应设置为运行“实时”，但也可以“按需”运行以更新打开的Opportunity。

提供 [!DNL Marketo Measure] 联系点，其中包含自定义机会金额字段的名称。 他们将更新 [!DNL Marketo Measure] App Opportunity设置，以包含自定义商机金额字段的名称。 这将告诉Discover在报表中使用哪个字段。

**工作流#2**:机会 — 更新 [!DNL Marketo Measure] 机会金额字段和自定义字段=实际收入

此工作流实时运行。 当用户关闭Opportunity时将启动该活动，并将更新 [!DNL Marketo Measure] 在Opportunity锁定为关闭之前， Opportunity Amount字段和您的自定义字段中的Actual Revenue已添加到Opportunity Close表单中。

## 第2部分：预计关闭日期与实际关闭日期 {#part-estimated-close-date-vs-actual-close-date}

开箱即用的管道收入数据将在功能板中不可用，因为默认情况下，Dynamics有两个库存关闭日期字段：预计关闭日期和实际关闭日期。 [!DNL Marketo Measure] 只能指向功能板中的一个关闭日期字段，而且我们当前指向的是实际关闭日期。

如果未结业务机会的“实际关闭日期”字段中没有数据，则在仪表板中，我们看不到任何未结业务机会的数据。 也就是说，需要基于机会阶段的工作流来支持这两个日期字段。

1. 在Opportunity对象上创建Custom Close Date字段(例如， [!DNL Marketo Measure] 自定义关闭日期)。
1. 创建工作流以更新 [!DNL Marketo Measure] Custom Close Date字段的日期为Estimated Close Date或Actual Close Date ，具体取决于业务机会是打开还是关闭（应保存工作流以实时运行，但需要至少运行一次“按需”以更新所有当前打开的Opp）。
1. 测试工作流并确认其工作。
1. 客户将自定义关闭日期API名称提供给 [!DNL Marketo Measure].
1. [!DNL Marketo Measure] 更新 [!DNL Marketo Measure] 要指向 [!DNL Marketo Measure] 功能板中的自定义关闭日期字段。

   完成上述步骤后，我们将需要运行工作流以更新这两个自定义 [!DNL Marketo Measure] Opp Amount字段和 [!DNL Marketo Measure] 历史销售机会上的Custom Close Date字段，以反映正确的数据。 这可能会更改修改的开/关字段，因此您需要与团队核实，以确定是否出现任何问题。

要更新已结束的商机……

1. 隔离自 [!DNL Marketo Measure] 启动日期，直到工作流处于活动状态。 这是一组需要通过工作流更新的历史业务机会。
1. 将所有记录导出到Excel。
1. 打开Excel文件，启用内容。
1. 将实际关闭日期数据复制到 [!DNL Marketo Measure] 自定义关闭日期。
1. 将实际收入数据复制到 [!DNL Marketo Measure] 自定义业务机会金额 **和** [!DNL Marketo Measure] 机会金额（有两个字段。）
1. 保存文件。
1. 导入文件。 Dynamics会将此识别为包含现有记录的文件进行更新。
1. 检查导入文件失败。

>[!NOTE]
>
>本文档中概述的工作流只是更新字段的一种方法，因此 [!DNL Marketo Measure] 可在Discover中显示正确的数据。 如果您有其他方法来完成同一项任务，您可以执行该任务。 基本上，我们需要从这些工作流中实现以下目标：
>
> * 如果Opp =打开，则更新自定义关闭日期字段、自定义opp金额字段，以及 [!DNL Marketo Measure] opp金额字段分别等于预计关闭日期和预计收入。
> * 如果Opp =关闭的Won，请更新自定义关闭日期字段、自定义opp金额字段和 [!DNL Marketo Measure] opp amount字段的值分别等于实际关闭日期和实际收入。

