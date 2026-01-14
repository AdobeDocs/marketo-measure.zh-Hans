---
description: 了解Account-Based Marketing (ABM)以及Adobe Marketo Measure如何帮助营销和销售团队执行成功的ABM策略。
title: 基于帐户的营销概述
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 0%

---

# 基于帐户的营销概述 {#account-based-marketing-overview}

以下部分简要概述了ABM、[!DNL Marketo Measure] ABM功能的组件以及如何将其添加到[!DNL Salesforce]页面布局。 若要了解有关ABM的更多信息，请查阅Adobe的[ABM博客](https://business.adobe.com/blog/basics/account-based-marketing){target="_blank"}。

有关在[!DNL Salesforce]实例中设置ABM的详细说明，请转到[在Salesforce中设置ABM页面布局](/help/advanced-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}。

## 什么是ABM {#what-is-abm}

基于客户的营销ABM是一种营销策略，您可以将目标定位到整个公司和客户，而不仅仅是个人。 [!DNL Marketo Measure]通过其销售线索到客户的映射功能和预测参与度分数，帮助营销和销售团队执行成功的ABM策略。

要使我们的基于帐户的营销模型开始填充到您的CRM中，[!DNL Marketo Measure]需要满足以下条件：

* 您的CRM需要至少25个拥有至少一个已结束的赢家机会的客户，以更好地衡量一个成功的客户/机会与您的业务的共同之处。
* 另一方面，您的CRM需要至少25个帐户，且不存在任何已关闭的获胜机会（所有获胜方都必须处于“开放”阶段类别或“已关闭的失败”类别中） — 这有助于我们衡量组织中较低级别帐户的成因。

>[!NOTE]
>
>上述“坏”帐户必须至少打开12个月，并且不会累积Closed Won opp；这是确定Opp是否出于模型目的而失效的基本准则。

## 商机到客户的映射 {#lead-to-account-mapping}

线索到账户的映射是有效反弹道导弹办法的关键部分。 通过销售线索到客户的映射，潜在客户或潜在客户将分组到与您的品牌接洽的同一个公司帐户中。 这允许您以一致的方式定位并向来自同一公司的个人进行销售。 无需其他[!DNL Salesforce]配置即可开始从此功能受益。 [!DNL Marketo Measure]潜在客户帐户映射不同的匹配方法：

* 将网站引向帐户网站
* 潜在客户电子邮件域到帐户网站域
* 从商机公司名称到帐户名称
* 潜在客户公司到帐户网站域
* 将网站引向帐户联系人的电子邮件域
* 潜在客户电子邮件域到帐户联系人的电子邮件域
* 将潜在客户网站链接到客户潜在客户的电子邮件域
* 潜在客户电子邮件域到客户潜在客户的电子邮件域

客户的潜在客户/联系人将通过其电子邮件/网站域进行验证，并与潜在客户电子邮件/网站的域或子域匹配。 使用匹配度最高的帐户。

>[!NOTE]
>
>每个Lead将按照上述方法的优选顺序尝试与帐户匹配。 进行匹配后，将立即在潜在客户上设置AccountId，并且不会使用其他方法进行匹配。

## 预测参与度分数 {#predictive-engagement-score}

[!DNL Marketo Measure]预测参与度分数（或PES）是一个动态值，可说明特定帐户与您的营销工作的参与程度。 此得分有助于将帐户分段到目标。 它是一种很有价值的工具，可用于更有效地确定目标客户。

算法中有许多组件用于计算PES。 回访间隔和年龄对得分变化以及上次接触点活动或页面查看次数有很大的影响。 向帐户添加新联系人也会影响PES。 以下是一些PES输入的列表：

* 帐户的页面查看总数
* 平均页面查看次数
* 帐户中的平均人数
* 最后一页查看的年龄
* 页面查看次数的平均年龄
* 帐户中的人数
* 特定重要页面，以及过去30/60/90天内是否有访问
* 如果帐户具有已结束的失败/获胜交易
* 被关闭的输赢可能性有多大

>[!NOTE]
>
>您可能会注意到某些帐户的预测参与度分数中存在“N/A”或“ — ”（破折号）的分级。

_等级为“N/A”只是表示该帐户上没有足够的数据可供模型生成真实等级 — 使用更多数据，最终给出等级。_
_等级“ — ”（短划线符号）表示ABM进程尚未处理此帐户，因为时间有限，偶尔会错过进程等等。 如果您认为某个帐户应该具有基于其他类似帐户或时间范围的等级，请联系并告知[!DNL Marketo Measure]。_

## 在[!DNL Salesforce]中设置ABM页面布局 {#setting-up-abm-page-layout-in-salesforce}

要开始使用PES，必须将PES字段和相关列表添加到[!DNL Salesforce]中的相应页面布局。

1. 导航到&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Accounts]** > **[!UICONTROL Page Layout]**。 然后，选择要编辑的页面布局。
1. 转到[!UICONTROL Fields]并将“预测参与度分数”字段移动到您的帐户信息部分。

   ![](assets/account-marketing-3.png)

1. 最后，转到[!UICONTROL Related Lists]并将“潜在客户”相关列表移动到您的页面布局中。

   ![](assets/account-marketing-4.jpg)

1. 接下来，导航到&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Leads]** > **[!UICONTROL Page Layout]**，并选择要编辑的相应页面布局。
1. 单击&#x200B;**[!UICONTROL Fields]**&#x200B;并添加您认为适合页面的[!UICONTROL Account]字段。

   ![](assets/account-marketing-5.png)

一切就绪！

