---
description: '[!DNL Marketo Measure] 最终概述 —  [!DNL Marketo Measure]  — 产品文档'
title: '''[!DNL Marketo Measure] Ultimate Overview`'
exl-id: fada9479-0671-4698-8043-c67d7977577b
source-git-commit: 4a5e720a91e8b229ad2f2889dbf87f5c43767411
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Marketo Measure] 最终概述 {#marketo-measure-ultimate-overview}

[!DNL Marketo Measure] （以前称为Bizible）使营销人员能够洞悉哪些营销工作在增加收入和为公司实现投资回报方面最有效。 [!DNL Marketo Measure] 是一种营销归因解决方案，可自动跟踪和报告渠道性能，从而提供对哪些渠道最能吸引客户的参与，并允许您相应地优化营销支出。

[!DNL Marketo Measure Ultimate] 包含其他功能：

* 从几乎任何数据源以及同一类型的多个数据源中摄取，以导入所有数据进行归因。
   * 与几乎任何CRM一起使用，而不只是与Salesforce和Dynamics结合使用。
   * 将多个CRM实例和/或MAP实例连接到一个 [!DNL Marketo Measure] 实例。
   * 引入第三方网络研讨会注册和参与数据。

* 通过字段映射和转换功能以极大的灵活性转换数据，以确保正确的数据形状。

* 通过包含的data warehouse，使归因分析可用于外部应用程序，以将分析集成到您的工作流中。 更细粒度的结果数据和基于BI的报表，包括SnowflakeData warehouse，它提供了对粒度结果数据的访问，以及使用任何BI工具进行分析和报告的功能。

* 与RTCDP（B2B或B2P版本）集成，为RTCDP客户提供集成的B2B归因解决方案，如RTCDP和 [!DNL Marketo Measure] 这两种方法都可以使用集中式Adobe Experience Platform(AEP)数据。

**[!DNL Marketo Measure]第1-3层**

![](assets/marketo-measure-ultimate-overview-1.png)

**[!DNL Marketo Measure Ultimate]**

![](assets/marketo-measure-ultimate-overview-2.png)

## 的新增功能 [!DNL Marketo Measure Ultimate] {#whats-new-in-marketo-measure-ultimate}

**通过AEP导入B2B数据**

营销人员应通过AEP获取其B2B数据（例如，帐户、机会、联系人、潜在客户、营销活动、营销活动会员、活动）。 直接CRM和Marketo Engage连接不再适用于Ultimate。 营销人员将继续通过直接连接和跟踪Web活动来获取广告平台数据 [!DNL Marketo Measure] javascript。

![](assets/marketo-measure-ultimate-overview-3.png)

**默认货币设置**

[!DNL Marketo Measure Ultimate] 将默认货币设置为USD，直到用户更改它。 设置新的默认货币将更新数据，而无需重新处理。 只要所选货币是目标ISO代码，就无需提交兑换率。

![](assets/marketo-measure-ultimate-overview-4.png)

**[!DNL Marketo Measure Ultimate]沙盒**

[!DNL Marketo Measure Ultimate] 必须先将实例映射到AEP沙盒，然后才能创建 [!DNL Marketo Measure] 目标数据流。

>[!NOTE]
>
>A [!DNL Marketo Measure Ultimate] 生产实例需要映射到AEP生产沙盒， [!DNL Marketo Measure Ultimate] 开发人员实例需要映射到AEP开发人员沙盒。

保存沙盒映射选择后，您此时无法在应用程序中更改它。 要更改它，请联系 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

给定数据源中给定实体（例如，帐户）的数据只能进入一个数据集。 每个数据集只能包含在一个数据流中。 违规将在运行时停止数据流。

![](assets/marketo-measure-ultimate-overview-5.png)

**阶段映射**

全部 [!DNL Marketo Measure Ultimate] 规则特定于数据集。 必须为所有数据集和所有选定阶段创建阶段映射规则。

有六个内置阶段：

* 潜在客户丢失
* 潜在客户打开
* 已转化的潜在客户
* 机会丢失
* 机会开放
* 机会赢

“丢失”、“获胜”和“已转换”部分不允许自定义阶段。 但是，源数据可以通过更新映射规则来映射到内置的丢失/赢取/转换阶段。

只能为打开部分定义自定义阶段。
我们不再在阶段映射中自动包含CRM阶段。

必须用规则映射四个内置阶段(其他两个阶段的映射规则（“潜在客户丢失”和“已转化的潜在客户”是可选的）：

* 潜在客户打开
* 机会丢失
* 机会开放
* 机会赢

规则条件特定于数据集。 必须为所有数据集和所有阶段创建阶段映射规则，“潜在客户丢失”和“已转化的潜在客户”除外。

没有选择漏斗、回力镖和自定义模型。 将为漏斗、回镖和自定义模型选择所有阶段。 我们支持的阶段数量存在限制：15个自定义阶段和6个内置阶段。

![](assets/marketo-measure-ultimate-overview-6.png)

促销活动成员接触点规则和活动接触点规则特定于数据集。

![](assets/marketo-measure-ultimate-overview-7.png)

![](assets/marketo-measure-ultimate-overview-8.png)

归因接触点未写入CRM，因为Ultimate没有直接CRM连接。

[!DNL Marketo Measure] ABM ML服务（客户到帐户匹配和预测参与度得分）不适用于 [!DNL Marketo Measure Ultimate]. 您可以在RT-CDP B2B版中找到免费提供的此类服务。

## 限制 {#limitations}

* 当前，数据转换规则只能使用有限的字段。
* 现有第1/2/3层用户没有迁移路径。 需要新实施，但我们将帮助从现有实例迁移跟踪的Web活动数据。

>[!MORELIKETHIS]
>
>[Marketo Measure Ultimate目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/marketo-measure-ultimate.html?lang=en){target="_blank"}
