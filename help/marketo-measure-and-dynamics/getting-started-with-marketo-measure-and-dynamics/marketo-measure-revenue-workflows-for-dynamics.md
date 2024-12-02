---
unique-page-id: 37356132
description: Dynamics的[!DNL Marketo Measure]收入工作流 —  [!DNL Marketo Measure]
title: Dynamics的[!DNL Marketo Measure]收入工作流
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---

# Dynamics的[!DNL Marketo Measure]收入工作流 {#marketo-measure-revenue-workflows-for-dynamics}

## 第一部分：预计收入与实际收入 {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure]指向一个开箱即用的标准收入字段（实际收入），但Dynamics具有两个标准收入字段：“实际收入”和“预计收入”。 要在Discover Dashboard中提供Pipeline收入，需要自定义字段和工作流以从Estimated Revenue或Actual Revenue字段中捕获正确的金额，具体取决于Opportunity是Open还是Closed (Won)。

步骤1：在Dynamics中创建自定义机会金额字段

>[!NOTE]
>
>所有Dynamics收入字段都有一个基本字段和一个常规字段。 忽略基本字段。

第2步：创建一个工作流，以更新在步骤1中创建的自定义机会金额字段和[!DNL Marketo Measure]机会金额字段。

>[!NOTE]
>
>我们无法指向“使用Dynamics发现”帐户中的[!DNL Marketo Measure]机会金额(bizible2_bizible_opportunity_amount)字段。 Dynamics客户必须创建一个自定义机会金额字段，[!DNL Marketo Measure]才能指向发现。 完成后，客户必须创建一个工作流来更新&#x200B;**两个** [!DNL Marketo Measure]机会金额(bizible2_bizible_opportunity_amount) **和**&#x200B;自定义机会金额字段。 [!DNL Marketo Measure] Opportunity Amount字段随包提供，但必须创建一个自定义字段。

金额工作流说明：

**工作流#1**：机会 — 更新[!DNL Marketo Measure]机会金额字段和自定义字段=预计收入

每次估计收入更改并更新[!DNL Marketo Measure]机会金额字段和您的自定义字段以等于估计收入字段时，此工作流都会在未结机会上运行。 工作流应设置为“实时”运行，但也可以“按需”运行以更新打开的Opportunities。

为您的[!DNL Marketo Measure]联系人提供自定义机会金额字段的名称。 他们更新[!DNL Marketo Measure]应用机会设置以包含自定义机会金额字段的名称。 这可告知Discover在报告中使用哪个字段。

**工作流#2**：机会 — 更新[!DNL Marketo Measure]机会金额字段和自定义字段=实际收入

此工作流在用户关闭Opportunity并更新[!DNL Marketo Measure] Opportunity Amount字段和您的自定义字段（使用添加到Opportunity Close表单中的实际收入进行更新）时启动，之后Opportunity将锁定为已关闭。

## 第2部分：预计关闭日期与实际关闭日期 {#part-estimated-close-date-vs-actual-close-date}

管道收入数据在功能板中现成不可用，因为默认情况下，Dynamics有两个库存关闭日期字段：预计关闭日期和实际关闭日期。 [!DNL Marketo Measure]在仪表板中只能指向一个关闭日期字段，它指向实际关闭日期。

如果“实际关闭日期”字段中未显示任何数据，则控制面板中不会显示任何有关未完成业务机会的数据。 也就是说，需要基于机会阶段的工作流来支持这两个日期字段。

1. 在Opportunity对象上创建自定义关闭日期字段（[!DNL Marketo Measure]自定义关闭日期）。
1. 创建工作流以使用预计关闭日期或实际关闭日期的日期更新[!DNL Marketo Measure]自定义关闭日期字段，具体取决于商机是打开还是关闭（应保存工作流以实时运行，但必须“按需”至少运行一次以更新所有当前打开的商机）。
1. 测试工作流并确认其正常工作。
1. 客户向[!DNL Marketo Measure]提供自定义关闭日期API名称。
1. [!DNL Marketo Measure]更新[!DNL Marketo Measure]应用设置以指向仪表板中的[!DNL Marketo Measure]自定义关闭日期字段。

   完成上述步骤后，运行工作流以更新历史机会上的“自定义[!DNL Marketo Measure]营业额”字段和“自定义关闭日期”字段，以反映正确的数据。 [!DNL Marketo Measure]此操作可能会更改修改日期/依据字段，因此您应该与团队确认这是否会导致任何问题。

要更新已关闭的机会，请执行以下操作……

1. 隔离自[!DNL Marketo Measure]开始日期起关闭的机会，直到工作流处于活动状态。 这是必须通过工作流更新的历史机会组。
1. 将所有记录导出到Excel。
1. 打开Excel文件，启用内容。
1. 将实际关闭日期数据复制到[!DNL Marketo Measure]自定义关闭日期。
1. 将实际收入数据复制到[!DNL Marketo Measure]自定义机会金额&#x200B;**和** [!DNL Marketo Measure]机会金额（有两个字段）。
1. 保存文件。
1. 导入文件。 Dynamics会将其识别为包含要更新的现有记录的文件。
1. 检查导入文件是否失败。

>[!NOTE]
>
>本文档中概述的工作流只是更新字段的一种方法，这样[!DNL Marketo Measure]就可以在Discover中显示正确的数据。 如果你有其他方法完成同样的任务，你可以去做。 基本上，我们需要从这些工作流中获取某种可实现以下目标的工作流：
>
> * 如果Opp =打开，则分别将自定义关闭日期字段、自定义打开金额字段和[!DNL Marketo Measure]打开金额字段更新为等于“预计关闭日期”和“预计收入”。
> * 如果Opp = Closed Won，则分别将自定义关闭日期字段、自定义打开金额字段和[!DNL Marketo Measure]打开金额字段更新为等于Actual Close Date和Actual Revenue。
