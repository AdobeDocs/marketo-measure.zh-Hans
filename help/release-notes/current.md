---
description: 最新发行说明 —  [!DNL Marketo Measure]
title: 最新发行说明
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 9ea72d0e1cf0f754cc8fe844944b93705fb2b12f
workflow-type: tm+mt
source-wordcount: '1375'
ht-degree: 0%

---

# 发行说明：2024年 {#release-notes-2024}

有关2024版的所有新增功能和更新功能，请参阅下文。

## 第4季度发行 {#q4-release}

### 新会话渠道转移行为

如果新会话在处于不活动状态30分钟后的7天内开始，则上一个会话的渠道现在会结转，仅适用于直接访问（无反向链接或内部反向链接）。 7天未活动后，会话将默认使用“直接”/“其他”。 非直接渠道不会被先前的会话数据覆盖。

此外，使用社交登录(Google、Microsoft或Apple)的会话现在合并到一个连续的会话中，以确保更顺畅的体验。 如果没有此传递切换，则由于外部反向链接差异，社交登录可能会创建单独的会话。

对于新客户，会话渠道转移现在为默认行为。 现有客户可以通过在设置>每次联系归因下打开会话渠道转移开关来启用此功能。 激活后，此设置将无法撤消。

文档： [Marketo Measure Web会话的定义](https://experienceleague.adobe.com/en/docs/marketo-measure/using/marketo-measure-tracking/setting-up-tracking/definition-of-marketo-measure-web-sessions){target="_blank"}

### 关键词ROI仪表板

新的关键字ROI仪表板提供付费搜索促销活动表现的详细见解，从而全面了解关键字级别的成本、归因收入、生成的商机和机会。 此仪表板可帮助您评估Google Adwords、LinkedIn和Bing Ads等中每个关键字的ROI。

文档： [关键字ROI仪表板](https://experienceleague.adobe.com/en/docs/marketo-measure/using/marketo-measure-discover-ui/dashboards/keyword-roi-dashboard){target="_blank"}

### 增强的区段规则

除了“接触点”和“联系人”字段外，您现在还可以使用“营销活动”和“营销活动成员”字段创建区段。 此增强功能使您能够在Discover中更有效地分析和剖析数据。

![增强的区段规则](assets/mm-q4-release-1.png)

### 更新： CRM导出的错误处理设置

我们听取了您有关停止作业方法的反馈，并将在用户界面中引入一项新功能。 从今天开始，您可以选择是否在出现错误时暂停导出作业。 在&#x200B;**我的帐户** > **设置** > **CRM** > **常规**&#x200B;中使用新的切换开关。 默认情况下，此交换机处于打开状态，以增强数据完整性和可见性。 但是，如果您不希望使用此功能，则可以在UI中将其关闭，导出作业将继续。 此更新旨在增强数据管理流程的可靠性，同时为您提供更好的控制力。

#### 关键日期和分阶段推出

1. **立即切换可用性：**&#x200B;切换现在在UI中处于活动状态，并且默认情况下处于启用状态，以防止在导出作业期间跳过数据。 如果您希望导出作业在遇到错误时继续运行，请禁用切换开关。

1. **作业将在10月1日暂停激活：**&#x200B;从2024年10月1日开始，如果切换处于活动状态并且在导出作业期间遇到记录级别的错误，则作业将暂停以确保没有数据丢失。 这些错误通常是由缺少权限、未正确应用自定义验证规则或工作流/触发器中的问题造成的。 您将收到有关问题的通知，问题纠正后，导出作业将从中断点恢复。 如果您选择退出作业暂停，您仍会收到问题通知，且在问题得到更正后，跳过的记录会自动重新导出。

#### 为什么这很重要

* **增强数据完整性和防未来攻击的集成：**&#x200B;通过在问题首次出现时暂停作业，我们可防止数据丢失并确保准确性。 这有助于快速解决错误，从而提高数据导出质量和整体系统可靠性。

* **即时可见性：**&#x200B;通过脉冲通知，您将及时收到权限错误警报，从而允许及时响应，并最大程度地降低对操作的潜在影响。

#### 支持您的过渡

为了帮助您适应此更改，我们创建了有关新功能的文档，并通过全面的故障排除步骤清晰地描述了错误。

* 新文档： [处理CRM导出的设置时出错](/help/configuration-and-setup/marketo-measure-and-salesforce/crm-error-handling.md)
* [错误通知](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md)

## 第3季度发行 {#q3-release}

<p>

### 提醒： Salesforce字段弃用 — 6月14日

如去年所宣布的，我们将逐步停止向Lead/Contact对象[导出作业，以简化我们的集成，并消除导出到Salesforce标准对象的需要。 &#x200B;](https://nation.marketo.com/t5/employee-blogs/marketo-measure-salesforce-lead-and-contact-field-deprecation-06/ba-p/350179){target="_blank"}您可以按照此处介绍的步骤[从接触点对象获取相同的数据](/help/release-notes/previous-releases/2023.md#deprecations){target="_blank"}。 我们还将共享有关创建工作流的文档，以将此数据添加到Lead/Contact对象。 弃用将于2024年6月14日生效。

这一变化将带来两大好处：

* **降低Salesforce API成本**：客户有望将其Salesforce API成本降低10%左右。
* **简化的集成**：我们的导出作业中错误数量最多的是与这些进程相关。 删除这些组件将显着简化我们的集成。

### 已归因的机会仪表板

我们很高兴地介绍新的[归因机会信息板](/help/marketo-measure-discover-ui/dashboards/attributed-opportunity-dashboard.md){target="_blank"}，它旨在让您全面了解您的营销工作如何促进新生的和成熟的管道机会。 利用此仪表板，您可以深入了解可归属于您的策略的每个未结和已结业务机会的详细信息，并灵活地按业务机会阶段进行筛选。 它提供了有关哪些渠道、子渠道或营销活动在归因机会数量方面排名最高的见解，并显示归因机会总数以及归因的未结和已结机会计数。

### 适用于Marketo Measure Ultimate的Marketo Engage Cookie同步

Marketo Engage Cookie Sync现在可用于Marketo Measure Ultimate。 要使用此功能，请执行以下操作：

1. 在“AEP架构”页面上，编辑B2B人员架构并添加字段组“Marketo Engage人员详细信息”。
1. 将数据摄取到MMU时，将Cookie ID字段从字段组映射到Marketo Engage的Cookie字段。

### 为第2层客户启用了回滚阶段

以前仅向第3级客户提供，从2024年6月13日起，所有2级客户也可以使用回旋镖暂存功能。 有关此功能的更多详细信息，请参阅下面的文档。

* [回车族阶段和接触点](/help/advanced-marketo-measure-features/boomerang/boomerang-stages-and-touchpoints.md){target="_blank"}
* [设置回车族阶段](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md){target="_blank"}
* [Boomerang阶段方案](/help/advanced-marketo-measure-features/boomerang/boomerang-stage-scenarios.md){target="_blank"}

<p>

## 第2季度发行 {#q2-release}

<p>

### 为响应第三方Cookie逐步淘汰，弃用Marketo Measure功能

为应对日益增长的隐私担忧，第三方Cookie正在逐步淘汰，Google Chrome2024年第三季度截止日期标志着其淘汰。 Marketo Measure将弃用依赖于第三方Cookie的某些功能，特别是跨域跟踪和浏览转化归因，这些功能依赖于Google/DoubleClick展示次数Cookie。 此更改不会影响其他Marketo Measure功能或第一方Cookie的使用。 按照Google的时间表，这些功能预计将在6月1日之前弃用，尽管客户仍然可以访问在此日期之前收集的数据。

* [在Marketo Measure中适应第三方Cookie弃用](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure Cookie](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

### 分阶段推出我们的增强错误处理

我们将分阶段推出增强导出作业的错误处理，从权限错误的即时应用程序内脉冲通知开始，并过渡到一个导出作业将在错误点暂停的新方法。 此更改旨在提高数据完整性和可见性，确保我们的用户拥有更顺畅、更可靠的数据管理流程。 为了确保顺利过渡并将对操作的中断降至最低，我们将分两个阶段实施这些更改：

* Pulse通知的立即可用性：在导出作业期间，您将收到有关权限错误的应用程序内脉冲通知。 这不会中断您的导出，但将帮助您了解错误而不影响当前作业。
* 4月25日作业暂停的实施： **已延迟** — 在考虑Marketo Measure用户的反馈后，我们决定推迟原定于4月25日出错时暂停导出作业的实施。 我们认识到，停止就业可能不是最有效的办法。 我们致力于寻找更好的解决方案，以维护数据完整性并最大限度地减少中断。 我们将推迟对当前系统进行任何更改，直到我们能够确保解决方案更加符合用户的需求。

_这很重要的原因_

增强的数据完整性和面向未来的集成：我们会在出现问题迹象时停止作业，以防止数据丢失并确保准确性。 这有助于快速解决问题，提高数据导出质量和系统可靠性。

即时可见性：引入脉冲通知后，可以对权限错误做出即时响应，从而防止对操作造成潜在影响。

_支持您的过渡_

为了帮助您适应此更改，[我们创建了文档](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}，其中提供了清晰的错误描述和全面的故障排除步骤。

<br>

### LinkedIn集成所需的操作

LinkedIn最近发布了其Lead Sync API的更新版本。 请在5月20日之前重新验证Marketo Measure实例中的LinkedIn连接，以避免任何中断。
