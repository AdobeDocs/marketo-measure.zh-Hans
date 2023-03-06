---
unique-page-id: 18874730
description: 基于帐户的营销概述 —  [!DNL Marketo Measure]  — 产品文档
title: 基于帐户的营销概述
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
source-git-commit: 48bff0d1cade7c216988170b16942ebffb71cc63
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---

# 基于帐户的营销概述 {#account-based-marketing-overview}

以下是ABM的简要概述，它是 [!DNL Marketo Measure] ABM功能，以及如何将其添加到您的 [!DNL Salesforce] 页面布局。 要了解有关ABM的更多信息，请查看 [此页面](https://www.marketo.com/account-based-marketing/){target="_blank"}.

要直接导航到有关在中设置ABM的说明，请 [!DNL Salesforce] 实例，请 [单击此处](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## 什么是ABM {#what-is-abm}

基于客户的营销(ABM)是一种营销策略，您可以将目标定位到整个公司和客户，而不仅仅是个人。 [!DNL Marketo Measure] 通过销售线索到客户的映射功能和预测参与度分数，帮助营销和销售团队执行成功的ABM策略。

为了使我们的基于帐户的营销模型开始填充到您的CRM中， [!DNL Marketo Measure] 需要满足以下条件：

* 您的CRM需要至少25个至少有一个已结束的赢家机会的客户，因此我们可以更好地衡量“成功”的客户/机会对您的业务的共性。
* 另一方面，您的CRM需要至少25个帐户，但不存在任何已关闭的未赢机会(所有未关闭的帐户必须属于我们的“开放”阶段类别或“已关闭的未结”类别 — 这有助于我们衡量贵组织中较低级别帐户的成因。

>[!NOTE]
>
>上述“不良”帐户需要开立至少12个月，且不会累积“已关闭的韩元”opp；这是我们判断Opp是否出于模型目的而失效的基本准则。

## 商机到客户的映射 {#lead-to-account-mapping}

线索到账户的映射是有效反弹道导弹方法的一个关键部分。 通过销售线索到客户的映射，当潜在客户或销售线索与您的品牌互动时，它们会被分组到同一个公司帐户中。 这样，您就可以以一致的方式将目标定位并向来自同一公司的个人进行销售。 没有其他附加的 [!DNL Salesforce] 开始从此功能获益所需的配置。 此 [!DNL Marketo Measure] Lead to Account Mapping五种不同的匹配方法：

* 将网站引向帐户网站
* 潜在客户电子邮件域到帐户网站域
* 从商机公司名称到帐户名称
* 从潜在客户公司到帐户网站域
* 通过联系人的电子邮件地址将潜在客户电子邮件地址中的域与帐户进行匹配

>[!NOTE]
>
>每个Lead都尝试按照上述方法的优惠顺序与帐户匹配。 进行匹配后，会立即在Lead上设置AccountId，并且不会使用其他方法进行匹配。 如果Lead已具有有效的AccountId，则跳过Lead。

## 预测参与度得分 {#predictive-engagement-score}

此 [!DNL Marketo Measure] 预测参与度得分（或PES）是一个动态值，可说明特定客户与您的营销工作的参与程度。 此分数有助于将帐户分段到目标。 它是一种很有价值的工具，可用于确定要更有效和更高效地定位的客户。

算法中有许多分量用于计算PES。 回访间隔和年龄对得分变化，以及最后接触点活动或页面查看次数有很大的影响。 向帐户添加新联系人也会影响PES。 以下是一些PES输入的列表：

* 帐户中的页面查看总数
* 平均页面查看次数
* 帐户中的平均人数
* 最后一页查看的年龄
* 页面查看的平均时间
* 帐户中的人数
* 特定重要页面以及过去30/60/90天内是否有访问
* 如果帐户具有已结的失败/获胜交易
* 关闭的可能性有多大：丢失/丢失

>[!NOTE]
>
>您可能会注意到某些帐户的预测参与度分数中的等级为“N/A”或“ — ”（破折号）。

_级别“N/A”仅意味着我们在该帐户上还没有足够的数据来生成真正的级别 — 使用更多数据，最终将会给出一个级别。_
_等级“ — ”（短划线符号）表示由于时间限制、偶尔遗漏流程等，我们的ABM流程尚未处理此帐户。 如果您认为某个帐户应该有一个基于其他类似帐户或时间范围的等级，请联系并让 [!DNL Marketo Measure] 知道了。_

## 在中设置ABM页面布局 [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

要开始使用PES，您只需将PES字段和相关列表添加到中相应的页面布局即可 [!DNL Salesforce].

1. 导航到 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Accounts]** > **[!UICONTROL Page Layout]**. 然后，选择要编辑的页面布局。
1. 转到 [!UICONTROL Fields] 并将“预测参与度分数”字段移入“帐户信息”部分。

   ![](assets/1.png)

1. 最后，转到 [!UICONTROL Related Lists] 并将“潜在客户”相关列表移动到您的页面布局中。

   ![](assets/2.png)

1. 接下来，导航到 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Leads]** > **[!UICONTROL Page Layout]** 并选择要编辑的相应页面布局。
1. 单击 **[!UICONTROL Fields]** 并添加 [!UICONTROL Account] 显示在页面上的适当位置的字段。

   ![](assets/3.png)

一切就绪！

