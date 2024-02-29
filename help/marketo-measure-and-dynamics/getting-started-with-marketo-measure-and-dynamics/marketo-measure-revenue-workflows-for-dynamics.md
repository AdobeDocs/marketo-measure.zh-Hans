---
unique-page-id: 37356132
description: "[!DNL Marketo Measure] Dynamics的收入工作流 —  [!DNL Marketo Measure]"
title: '"[!DNL Marketo Measure] Dynamics的收入工作流”'
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 0%

---

# [!DNL Marketo Measure] Dynamics的收入工作流 {#marketo-measure-revenue-workflows-for-dynamics}

## 第一部分：预计收入与实际收入 {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] 指向一个现成的标准收入字段（实际收入），但Dynamics具有两个标准收入字段：“实际收入”和“预计收入”。 要在Discover Dashboard中提供Pipeline收入，需要自定义字段和工作流以从Estimated Revenue或Actual Revenue字段中捕获正确的金额，具体取决于Opportunity是Open还是Closed (Won)。

步骤1：在Dynamics中创建自定义机会金额字段

>[!NOTE]
>
>所有Dynamics收入字段都有一个基本字段和一个常规字段。 忽略基本字段。

第2步：创建一个工作流，以更新在步骤1中创建的自定义业务机会金额字段和 [!DNL Marketo Measure] 机会金额字段。

>[!NOTE]
>
>我们不能指向 [!DNL Marketo Measure] Discover with Dynamics帐户中的Opportunity Amount (bizible2_bizible_opportunity_amount)字段。 Dynamics客户必须为其创建一个自定义机会金额字段 [!DNL Marketo Measure] 指向“发现”。 完成后，客户需要创建一个工作流进行更新 **两者** 该 [!DNL Marketo Measure] 业务机会金额(bizible2_bizible_opportunity_amount) **和** 自定义机会金额字段。 此 [!DNL Marketo Measure] Opportunity Amount字段随包提供，但必须创建一个自定义字段。

金额工作流说明：

**工作流#1**：Opportunity — 更新 [!DNL Marketo Measure] 机会金额字段和自定义字段=预计收入

每次预计收入发生变化时，此工作流都会在打开的商机上运行，并将更新 [!DNL Marketo Measure] Opportunity Amount字段和您的自定义字段等于Estimated Revenue字段。 工作流应设置为“实时”运行，但也可以“按需”运行以更新打开的Opportunities。

提供您的 [!DNL Marketo Measure] 具有自定义机会金额字段名称的联系人。 他们将更新 [!DNL Marketo Measure] “应用程序机会设置”可包含自定义机会金额字段的名称。 这将告知探索在报告中使用的字段。

**工作流#2**：Opportunity — 更新 [!DNL Marketo Measure] 机会金额字段和自定义字段=实际收入

此工作流可实时运行。 它将在用户关闭Opportunity时启动，并将更新 [!DNL Marketo Measure] Opportunity Amount字段和您的自定义字段，其中Actual Revenue已添加到Opportunity Close表单中，然后Opportunity锁定为已关闭。

## 第2部分：预计关闭日期与实际关闭日期 {#part-estimated-close-date-vs-actual-close-date}

管道收入数据在功能板中现成不可用，因为默认情况下，Dynamics有两个库存关闭日期字段：预计关闭日期和实际关闭日期。 [!DNL Marketo Measure] 在仪表板中，只能指向一个关闭日期字段，而我们当前指向的是实际关闭日期。

如果“实际关闭日期”字段中没有打开的业务机会数据，则我们在控制面板中不会看到打开的业务机会的任何数据。 也就是说，需要基于机会阶段的工作流来支持这两个日期字段。

1. 在Opportunity对象上创建自定义关闭日期字段(即 [!DNL Marketo Measure] 自定义关闭日期)。
1. 创建工作流以更新 [!DNL Marketo Measure] “自定义关闭日期”字段，其日期为“预计关闭日期”或“实际关闭日期”，具体取决于业务机会是打开还是关闭（应保存工作流以实时运行，但需要“按需”至少运行一次以更新所有当前打开的业务机会）。
1. 测试工作流并确认其正常工作。
1. 要向提供自定义关闭日期API名称的客户 [!DNL Marketo Measure].
1. [!DNL Marketo Measure] 更新 [!DNL Marketo Measure] 指向的应用程序设置 [!DNL Marketo Measure] 仪表板中的自定义关闭日期字段。

   完成上述步骤后，我们将需要运行工作流以更新这两个自定义 [!DNL Marketo Measure] Opp金额字段和 [!DNL Marketo Measure] 历史机会中的自定义关闭日期字段以反映正确的数据。 此操作可能会更改修改日期/依据字段，因此您将需要与团队确认这是否会导致任何问题。

要更新已关闭的机会，请执行以下操作……

1. 隔离自您的网站之后关闭的机会 [!DNL Marketo Measure] 启动日期直到工作流处于活动状态。 这是一组您需要通过工作流更新的历史机会。
1. 将所有记录导出到Excel。
1. 打开Excel文件，启用内容。
1. 将实际关闭日期数据复制到 [!DNL Marketo Measure] 自定义关闭日期。
1. 将实际收入数据复制到 [!DNL Marketo Measure] 自定义机会金额 **和** [!DNL Marketo Measure] 机会金额（包含两个字段。）
1. 保存文件。
1. 导入文件。 Dynamics会将其识别为包含要更新的现有记录的文件。
1. 检查导入文件是否失败。

>[!NOTE]
>
>本文档中概述的工作流只是更新字段的一种方法， [!DNL Marketo Measure] 可以在发现中显示正确的数据。 如果你有其他方法完成同样的任务，你可以去做。 基本上，我们需要从这些工作流中获取一些可实现以下目标的工作流：
>
> * 如果Opp =打开，则更新自定义关闭日期字段、自定义打开金额字段，并且 [!DNL Marketo Measure] opp amount字段分别等于Estimated Close Date和Estimated Revenue。
> * 如果Opp = Closed Won，则更新自定义关闭日期字段、自定义打开金额字段，并且 [!DNL Marketo Measure] opp amount字段分别等于Actual Close Date和Actual Revenue。
