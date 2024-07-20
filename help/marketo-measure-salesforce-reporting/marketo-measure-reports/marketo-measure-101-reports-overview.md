---
description: "[!DNL Marketo Measure] 101报告概述 —  [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] 101报告概述"
exl-id: 83977b81-8055-47fd-8a6b-5ef32d280269
feature: Reporting
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 0%

---

# [!DNL Marketo Measure] 101报告概述 {#marketo-measure-101-reports-overview}

>[!NOTE]
>
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

所有使用[!DNL Marketo Measure]和[!DNL Salesforce]的[!DNL Marketo Measure]客户都可以访问其SFDC实例中的“买方接触点报告”文件夹。 此文件夹包含许多预建报表，可帮助您开始使用Buyer Touchpoint数据进行报告。

![](assets/bizible-101-reports-overview-1.png)

虽然这些报表中有许多已经确定了特定的报告目标，但仍有六个“_[!DNL Marketo Measure]101..._”由三种关键报表类型表示，它们涵盖了大部分的报告需求。

* 具有买方接触点的潜在客户
* 具有买方接触点的[!DNL Marketo Measure]人员
* 带有机会的买方归因接触点

![](assets/bizible-101-reports-overview-2.png)

这些报告为您提供了要创建的任何[!DNL Marketo Measure]相关报告所需的基本字段和基础结构。 我们鼓励所有客户（新老客户）在探索营销归因问题时，从这些报表开始。 下面您将找到六个“_[!DNL Marketo Measure]101..._”报告中的每一个报告的说明。

_如果找不到买方接触点报告文件夹或该文件夹中的六个“_[!DNL Marketo Measure] 101..._”报告，请联系支持人员以寻求帮助。_

具有买方接触点的&#x200B;**潜在客户** | 以下两种变体，报告潜在客户及其买方接触点。 尽管它们使用相同的基本报表类型，但会按不同的量度（商机ID与营销渠道）进行分组，以提供数据的两个关键视图。 此报表类型专为漏斗报表顶部而设计，非常适合探索潜在客户如何参与营销工作。 在进行任何自定义之前，以下两个报表会显示以下内容：

**[!DNL Marketo Measure]101：潜在客户（按渠道）** | 从较高层面了解营销渠道如何影响潜在客户的创建及其额外参与。
**[!DNL Marketo Measure]101：按ID排列的潜在客户** | 这会显示Lead案例，并且是一个更加精细的报告，其中显示了每个Lead及其相关的Buyer Touchpoint。

**有买方接触点的潜在客户/联系人** | 这些报告通常称为[!DNL Marketo Measure]人员报告。 他们使用[!DNL Marketo Measure]自定义对象&#x200B;_[!DNL Marketo Measure]Person_，而不是上述报告中的Lead对象。

[!DNL Marketo Measure]人员对象将潜在客户和联系人对象关联在一起。 开箱即用的，[!DNL Salesforce]不提供在同一报告中使用Lead和Contact对象创建报告的选项。 通过使用人员的唯一标识符（即其电子邮件）关联商机和联系人对象，则[!DNL Marketo Measure]人员可以在同一报表中报告与商机和联系人相关的买方接触点。 此报表类型是验证任何[!DNL Marketo Measure]帐户设置的理想选择，因为它是最具包容性的接触点报表级别。

以下两个报表变体使用相同的报表类型，但按不同的量度“人员ID”（电子邮件）和“营销渠道”分组。 这些是漏斗顶部/漏斗中间的报告，在寻找寻找潜在客户和联系人如何参与营销工作时，这些报告非常棒。 在进行任何自定义之前，以下两个报表会显示以下内容：

**[!DNL Marketo Measure]101：按渠道列出的潜在客户/联系人** | 从较高层面了解营销渠道如何影响潜在客户或联系人的创建及其附加参与。 当您想要了解整个营销渠道的总参与度以及哪些营销渠道在您的Salesforce实例中促成全新的名称时，此报表非常理想。
**[!DNL Marketo Measure]101：潜在客户/联系人（按ID**） | 这会显示每个[!DNL Marketo Measure]人的故事，并且是一个更加精细的报告，可显示每个个人及其购买者接触点，无论这些接触点是在他们作为潜在客户还是作为联系人时发生的。

**具有买方归因接触点的机会** | 最后两个“_[!DNL Marketo Measure]101..._”报告位于漏斗报告的底部，这些报告显示了与机会相关的Buyer Attribution Touchpoint数据。 这些报告的主要区别在于，它们由&#x200B;_买方归因接触点_&#x200B;生成，这些接触点与Opportunity和Opportunity级别的数据（如收入）相关。 每当您希望报告机会或归因的收入时，都应使用此报告类型。 以下两个报表使用相同的报表类型，但是，它们按不同的量度“机会ID”与“营销渠道”分组。 在进行任何自定义之前，以下两个报表会显示以下内容：

**[!DNL Marketo Measure]101：渠道商机** | 从较高层面了解您的营销渠道如何影响并提升您的业务机会的归因收入。
**[!DNL Marketo Measure]101：按ID列出的机会** | 此精细的报告版本显示了您的机会的完整历程。 在此报表中，您可以看到与一个Opportunity关联的每个Buyer Attribution Touchpoint ，以及通过各种归因模型得出的归因收入。

将“_[!DNL Marketo Measure]101..._”报告视为模板以满足您的报告需求被视为最佳实践。 从以上某个报表开始，可节省您的时间并确保您使用的是与[!DNL Marketo Measure]数据相关的正确字段。 始终确保您在自定义“_[!DNL Marketo Measure]101..._”模板时执行“另存为”操作，以保留报表的原始变体。

“Buyer Touchpoint报表”文件夹旨在帮助您开始使用[!DNL Marketo Measure]报表，对于可操作报表，您需要自定义这些报表，以便根据您的报表需求进行自定义。 您将需要添加必要的过滤器，以确保报告中的记录（及其相关接触点）与您的报告目标保持一致。

当您熟悉&quot;_[!DNL Marketo Measure]101..._&quot;报告时，您可能希望从自定义报告类型重新创建它们，以满足更多自定义报告需求。 通过创建[[!DNL Marketo Measure] 自定义报表类型](/help/marketo-measure-salesforce-reporting/new-report-types/creating-custom-marketo-measure-report-types.md)，您可以提取可能在其他CRM报表中常用的自定义字段。 这将帮助您将[!DNL Marketo Measure]报告提升到新的水平！
