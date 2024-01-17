---
description: ’[!DNL Marketo Measure] 最终实施指南 —  [!DNL Marketo Measure]  — 产品文档'
title: ’[!DNL Marketo Measure] 最终实施指南
feature: Integration, Tracking, Attribution
source-git-commit: 7bb458941e513b6155b834d27f76f0b5df4e0a09
workflow-type: tm+mt
source-wordcount: '997'
ht-degree: 0%

---

# [!DNL Marketo Measure] 最终实施指南 {#marketo-measure-ultimate-implementation-guide}

本文可作为Marketo Measure Ultimate的实施指南，为您提供清晰的步骤和分析，以确保成功的集成和利用。

## 使用Ultimate与标准层的主要区别 {#main-differences-when-using-ultimate-over-standard-tiers}

通过AEP导入B2B数据：营销人员应通过AEP导入其B2B数据（例如，客户、机会、联系人、潜在客户、营销活动、营销活动成员、活动）。 从几乎任何数据源以及同一类型的多个数据源进行摄取，以引入所有数据来进行归因。

* 可与几乎任何CRM一起使用，而不仅仅是Salesforce和Dynamics。
* 将多个CRM实例和/或MAP实例连接到一个Marketo Measure实例。
* 引入第三方网络研讨会注册和参与数据。

Ultimate不再提供直接CRM和Marketo Engage连接。

* Ultimate不会将数据推送回CRM。 客户可以使用数据仓库中的数据。
* 营销人员将继续通过直接连接引入广告平台数据，并通过Marketo Measure javascript跟踪Web活动。

最终用户将配置AEP。 如果他们已经具有AEP，我们将不会重新配置新实例。

* 所设置的AEP版本将仅包括所有源连接器、架构数据建模、数据集、Ad Hoc查询服务和适用于Marketo Measure的目标。

了解有关 [Marketo Measure Ultimate](/help/marketo-measure-ultimate/marketo-measure-ultimate-overview.md){target="_blank"}.

## 架构和数据集 {#schemas-and-datasets}

>[!NOTE]
>
>签出 [架构的构建块](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en#building-blocks-of-a-schema){target="_blank"} 有关架构、类和字段组的概述。

**XDM架构=类+架构字段组&#42;**

* 必填字段不可更改。 客户可以根据需要创建和添加自定义字段。
* 基于层次结构的字段名称示例： accountOrganization.annualRevenue.amount

&#42; _一种架构包括一个类和零个或多个架构字段组。 这意味着您无需使用字段组即可构建数据集架构。_

![](assets/marketo-measure-ultimate-implementation-guide-1.png)

[数据集概述](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html){target="_blank"}：所有成功引入AEP的数据将作为数据集保留在数据湖中。 数据集是用于数据集合的存储和管理结构，通常是表，包含架构（列）和字段（行）。

## 创建架构 {#creating-a-schema}

我们建议使用自动生成实用程序来创建10个标准B2B架构。

* 下载和设置实用程序的步骤 [可在此处找到](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo-namespaces.html#set-up-b2b-namespaces-and-schema-auto-generation-utility){target="_blank"}.

对于拥有 _**CDP权利**_：转到“源”页面创建架构。

* 从源中，选择添加数据>使用模板

![](assets/marketo-measure-ultimate-implementation-guide-2.png)

* 选择一个帐户和所有B2B模板，以创建10个标准B2B架构。

![](assets/marketo-measure-ultimate-implementation-guide-3.png)

## 数据流 {#dataflows}

[数据流概述](https://experienceleague.adobe.com/docs/experience-platform/dataflows/home.html){target="_blank"}

**创建数据流的步骤：**

1. 选择源。
1. 选择现有帐户或创建帐户。
1. 从可用类型列表中选择数据类型，以从源导入。
1. 选择现有数据集或创建新数据集。
1. 将源中的字段映射到架构。

   >[!NOTE]
   >
   >* 如果将一种架构类型映射到另一种相同的架构类型，则会自动完成映射。
   >* 您还可以从系统中的其他流导入映射。
   >* 您可以将一个“源”字段映射到多个目标字段，但无法执行相反操作。
   >* 您可以创建计算字段([数据准备映射函数](https://experienceleague.adobe.com/docs/experience-platform/data-prep/functions.html){target="_blank"})。

   >[!CAUTION]
   >
   >* 您可以编辑数据流，但在更改映射时不会回填数据。
   >* 如果必填字段为NULL，则将拒绝整个流。

   >[!NOTE]
   >
   >[Marketo Measure Ultimate数据完整性要求](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}

1. 设置数据加载节奏。
1. 查看并完成。
1. 检查数据流状态测量UI设置中的“帐户状态”页面。

**监控：**

“源”>“数据流”页检查数据流的状态

* 要查看数据集的活动详细信息，只需单击该数据集即可。
* 要查看数据流错误，请选择一个数据流，选择一个数据流运行，然后单击“错误诊断预览”。

## 数据检测 {#data-inspection}

选项1：要直接从UI运行查询，请访问数据管理下的查询选项卡。

![](assets/marketo-measure-ultimate-implementation-guide-4.png)

选项2： [下载和使用PSQL](https://experienceleague.adobe.com/docs/experience-platform/query/clients/psql.html){target="_blank"} （更快、更可靠）。

## 激活Marketo Measure的数据集 {#activate-dataset-for-marketo-measure}

在开始之前，请转到测量UI设置中的“Experience Platform>沙盒映射”部分，并映射沙盒。

>[!CAUTION]
>
>一旦选择此项，便无法更改。

1. 在AEP中，转到“目标> Marketo Measure页面”以导出数据集。
1. 配置目标。
1. 激活数据集。
1. 检查数据流状态测量UI设置中的“帐户状态”页面。

>[!NOTE]
>
>* 来自给定源的给定实体（例如，帐户）的数据只能进入一个数据集。 每个数据集只能包含在一个数据流中。 违规将在运行时停止数据流。
>* 在AEP中删除整个目标以删除度量中的数据。 禁用将仅停止新数据导出并保留旧数据。
>* 测量配置的外观大致相同，但某些部分（如暂存映射）的外观会有所不同。
>* 新数据流生成流运行需要几个小时，然后定期进行每小时一次。

在衡量标准中，需要在“货币”部分设置默认货币

* 如果您使用多货币，则必须在AEP中填充货币兑换率架构，以便我们读取和进行兑换。

**阶段映射：**

我们不会自动从用户数据导入阶段，因此必须手动映射所有阶段。

* 用户可以映射不同来源的阶段。

![](assets/marketo-measure-ultimate-implementation-guide-5.png)

如果未映射阶段，系统将无法正常运行，因为没有位置可供数据访问。

如果您是Marketo Measure Ultimate客户并将您的默认功能板对象设置为Contact，请不要使用下面两个特定于Lead的字段([在此处了解详情](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"})。

* b2b.personStatus
* b2b.isConverted

**营销活动成员规则：**

需要选择一个数据集并为每个数据集设置规则。

**体验事件规则：**

需要选择一个数据集并选择活动类型。

* 尚不支持自定义活动。
* 如果客户的活动不适合可用选项，我们建议将其分类为“有趣的时刻”，并使用自定义字段区分它们。

**脱机渠道：**

* 我们不执行特定于数据集的渠道映射规则，因此这将是全局的。
* 我们最终需要匹配CRM营销活动类型和渠道，但现在，作为解决方法，我们可以将渠道名称映射到两个字段。
* **渠道规则：回填的数据将没有阶段过渡数据。**

接触点和区段设置保持不变。
