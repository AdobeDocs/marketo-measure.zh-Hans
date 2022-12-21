---
unique-page-id: 18874730
description: 基于帐户的营销概述 —  [!DNL Marketo Measure]  — 产品文档
title: 基于帐户的营销概述
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 0%

---

# 基于帐户的营销概述 {#account-based-marketing-overview}

以下是ABM的简要概述， [!DNL Marketo Measure] ABM功能，以及如何将其添加到 [!DNL Salesforce] 页面布局。 要进一步了解ABM，请查看 [本页](https://www.marketo.com/account-based-marketing/){target=&quot;_blank&quot;}。

要直接导航到 [!DNL Salesforce] 实例，请 [单击此处](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target=&quot;_blank&quot;}。

## 什么是ABM {#what-is-abm}

基于帐户的营销(ABM)是一种营销策略，其目标是公司和整个帐户，而不仅仅是个人。 [!DNL Marketo Measure] 借助其潜在客户到帐户映射功能和预测参与度得分，帮助营销和销售团队执行成功的ABM策略。

为了开始在您的CRM中填充基于帐户的营销模型， [!DNL Marketo Measure] 需要满足以下条件：

* 您的CRM至少需要25个客户，这些客户上至少有一个Closed Won Opportunity，因此我们可以更好地衡量您的业务“成功”客户/机会的共性。
* 另一方面，您的CRM至少需要25个帐户，而没有任何已结成的机会(所有选项必须位于我们的“未结”阶段类别，或“已结失”类别中 — 这有助于我们衡量贵组织中级别较低的帐户是什么。

>[!NOTE]
>
>上述“坏”账户需要至少12个月才能开立，而不需要累积已关闭的韩元期权；这是我们为模型目的是否弃用了Opp的基本准则。

## 潜在客户到帐户映射 {#lead-to-account-mapping}

导向对帐制图是有效的反弹道导弹方法的关键部分。 通过商机到帐户映射，潜在客户或潜在客户在与您的品牌互动时被分组到同一公司帐户中。 这样，您便可以以一致的方式定位和销售给来自同一公司的个人。 没有其他 [!DNL Salesforce] 需要进行配置，以便开始从此功能中受益。 的 [!DNL Marketo Measure] 导致帐户映射五种不同的匹配方法：

* 将网站引导到帐户网站
* 将电子邮件域引导到帐户网站域
* 潜在客户公司名称到帐户名称
* 潜在客户公司到帐户网站域
* 通过联系人的电子邮件地址将潜在客户电子邮件地址上的域与帐户匹配

## 预测参与度分数 {#predictive-engagement-score}

的 [!DNL Marketo Measure] 预测参与度分数(PES)是一个动态值，用于说明特定帐户在营销工作中的参与程度。 此分数有助于对帐户进行分段以定位。 它是识别帐户以更有效和高效定位的有价值工具。

算法中有许多组件用于计算PES。 回访间隔和年龄对得分更改以及最后接触点活动或页面查看次数有很大影响。 向帐户添加新联系人也会影响PES。 以下是一些PES输入的列表：

* 帐户中的页面查看总次数
* 平均页面查看次数
* 帐户中的平均人数
* 最后一页查看的年龄
* 页面查看的平均年龄
* 帐户中人数
* 特定重要页面以及过去30/60/90天中是否进行了访问
* 如果帐户已完成“丢失/赢得”交易
* 关闭的可能性是多大，是丢失还是赢

>[!NOTE]
>
>您可能会注意到某些帐户的预测参与度分数中存在“N/A”或“ — ”（短划线符号）等级。

_“不适用”等级只意味着，我们尚没有足够的数据，无法为模型生成真正的等级 — 如果数据更多，最终会给出一个等级。_
_&quot;-&quot;（破折号符号）等级表示，由于时间限制、偶尔遗漏的进程等原因，ABM进程尚未处理此帐户。 如果您认为某个帐户应具有基于其他类似帐户或时间范围的等级，请联系并允许 [!DNL Marketo Measure] 知道。_

## 在中设置ABM页面布局 [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

要开始使用PES，您只需将PES字段和相关列表添加到 [!DNL Salesforce].

1. 导航到 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Accounts]** > **[!UICONTROL Page Layout]**. 然后，选择要编辑的页面布局。
1. 转到 [!UICONTROL Fields] 并将字段“预测参与度分数”移入您的帐户信息部分。

   ![](assets/1.png)

1. 最后，转到 [!UICONTROL Related Lists] 并将“潜在客户”相关列表移入页面布局中。

   ![](assets/2.png)

1. 接下来，导航到 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Leads]** > **[!UICONTROL Page Layout]** 并选择要编辑的相应页面布局。
1. 单击 **[!UICONTROL Fields]** 并添加 [!UICONTROL Account] 字段中显示的“适合”字段。

   ![](assets/3.png)

你们都准备好了！

