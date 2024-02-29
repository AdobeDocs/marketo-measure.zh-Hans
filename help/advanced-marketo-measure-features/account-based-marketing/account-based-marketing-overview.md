---
unique-page-id: 18874730
description: 了解Account-Based Marketing (ABM)以及AdobeMarketo Measure如何帮助营销和销售团队执行成功的ABM策略。
title: 基于帐户的营销概述
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# 基于帐户的营销概述 {#account-based-marketing-overview}

以下各节简要概述了ABM，其组件 [!DNL Marketo Measure] ABM功能，以及如何将其添加到您的 [!DNL Salesforce] 页面布局。 要了解有关ABM的更多信息，请查阅Adobe [ABM博客](https://business.adobe.com/blog/basics/account-based-marketing){target="_blank"}.

有关在 [!DNL Salesforce] 实例，转到 [在Salesforce中设置ABM页面布局](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## 什么是ABM {#what-is-abm}

基于客户的营销ABM是一种营销策略，您可以将目标定位到整个公司和客户，而不仅仅是个人。 [!DNL Marketo Measure] 通过销售线索到客户的映射功能和Predictive Engagement Score ，帮助营销和销售团队执行成功的ABM策略。

要使我们的基于帐户的营销模型开始填充到您的CRM中， [!DNL Marketo Measure] 需要满足以下条件：

* 您的CRM需要至少25个拥有至少一个已结束的赢家机会的客户，以更好地衡量一个成功的客户/机会与您的业务的共同之处。
* 另一方面，您的CRM需要至少25个帐户，且不存在任何已关闭的获胜机会（所有获胜方都必须处于“开放”阶段类别或“已关闭的失败”类别中） — 这有助于我们衡量组织中较低级别帐户的成因。

>[!NOTE]
>
>上述“坏”帐户必须至少打开12个月，并且不会累积Closed Won opp；这是确定Opp是否出于模型目的而失效的基本准则。

## 商机到客户的映射 {#lead-to-account-mapping}

线索到账户的映射是有效反弹道导弹办法的关键部分。 通过销售线索到客户的映射，潜在客户或潜在客户将分组到与您的品牌接洽的同一个公司帐户中。 这允许您以一致的方式定位并向来自同一公司的个人进行销售。 没有其他附加的 [!DNL Salesforce] 开始从该功能中获益所需的配置。 此 [!DNL Marketo Measure] Lead to Account Mapping五种不同的匹配方法：

* 将网站引向帐户网站
* 潜在客户电子邮件域到帐户网站域
* 从商机公司名称到帐户名称
* 潜在客户公司到帐户网站域
* 通过联系人的电子邮件地址将潜在客户电子邮件地址中的域与帐户进行匹配

>[!NOTE]
>
>每个Lead将按照上述方法的优选顺序尝试与帐户匹配。 进行匹配后，将立即在潜在客户上设置AccountId，并且不会使用其他方法进行匹配。 如果Lead已具有有效的AccountId，则跳过Lead。

## 预测参与度分数 {#predictive-engagement-score}

此 [!DNL Marketo Measure] 预测参与度分数（或PES）是一个动态值，可说明特定客户与您的营销工作的参与程度。 此得分有助于将帐户分段到目标。 它是一种很有价值的工具，可用于更有效地确定目标客户。

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

_等级“N/A”仅仅意味着该帐户上没有足够的数据来生成真正的等级 — 使用更多数据，最终给出一个等级。_
_等级“ — ”（短划线符号）表示ABM进程尚未处理此帐户，因为时间有限，偶尔会错过进程，依此类推。 如果您认为某个帐户应该具有基于其他类似帐户或时间范围的等级，请联系并让 [!DNL Marketo Measure] 知道。_

## 在中设置ABM页面布局 [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

要开始使用PES，必须将PES字段和相关列表添加到中的相应页面布局 [!DNL Salesforce].

1. 导航到 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Accounts]** > **[!UICONTROL Page Layout]**. 然后，选择要编辑的页面布局。
1. 转到 [!UICONTROL Fields] 并将“预测参与度分数”字段移入“帐户信息”部分。

   ![](assets/1.png)

1. 最后，转到 [!UICONTROL Related Lists] 并将“潜在客户”相关列表移动到您的页面布局中。

   ![](assets/2.png)

1. 接下来，导航到 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Leads]** > **[!UICONTROL Page Layout]** 并选择要编辑的相应页面布局。
1. 单击 **[!UICONTROL Fields]** 并添加 [!UICONTROL Account] 显示在页面上的适当位置的字段。

   ![](assets/3.png)

一切就绪！

