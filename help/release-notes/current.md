---
description: 最新发行说明 —  [!DNL Marketo Measure]
title: 最新发行说明
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 97a82ae0649ae5b1349d025a7a7cf433bc64bc7e
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 0%

---

# 发行说明：2024年 {#release-notes-2024}

有关2024版的所有新增功能和更新功能，请参阅下文。

## 第3季度发行 {#q3-release}

<p>

**提醒： Salesforce字段弃用 — 6月14日**

正如去年宣布的那样，我们将逐步停止对Lead/Contact对象的导出工作，以简化我们的集成，并消除导出到Salesforce标准对象的需要。 您可以按照以下步骤从接触点对象获取相同的数据 [此处记录](/help/release-notes/previous-releases/2023.md#deprecations){target="_blank"}. 我们还将共享有关创建工作流的文档，以将此数据添加到Lead/Contact对象。 弃用将于2024年6月14日生效。

这一变化将带来两大好处：

* **降低了Salesforce API成本**：客户有望将其Salesforce API成本减少约10%。
* **简化的集成**：我们的导出作业中与这些进程相关的错误数量最高。 删除这些组件将显着简化我们的集成。

**已归因的机会仪表板**

我们很高兴能向大家介绍 [已归因的机会仪表板](/help/marketo-measure-discover-ui/dashboards/attributed-opportunity-dashboard.md){target="_blank"}，旨在让您全面了解营销工作对新兴和成熟的管道机会的贡献。 利用此仪表板，您可以深入了解可归属于您的策略的每个未结和已结业务机会的详细信息，并灵活地按业务机会阶段进行筛选。 它提供了有关哪些渠道、子渠道或营销活动在归因机会数量方面排名最高的见解，并显示归因机会总数以及归因的未结和已结机会计数。

**适用于Marketo Measure Ultimate的Marketo EngageCookie同步**

Marketo EngageCookie同步现在可供Marketo Measure Ultimate使用。 要使用此功能，请执行以下操作：

1. 在“AEP架构”页上，编辑B2B人员架构并添加字段组“Marketo Engage人员详细信息”。
1. 将数据摄取到MMU时，将Cookie ID字段从字段组映射到Marketo Engage中的Cookie字段。

**为第2层客户启用了回滚阶段**

以前仅向第3级客户提供，从2024年6月13日起，所有2级客户也可以使用回旋镖暂存功能。 有关此功能的更多详细信息，请参阅下面的文档。

* [自走式暂存器和接触点](/help/advanced-marketo-measure-features/boomerang/boomerang-stages-and-touchpoints.md){target="_blank"}
* [设置回访单阶段](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md){target="_blank"}
* [回音廊舞台场景](/help/advanced-marketo-measure-features/boomerang/boomerang-stage-scenarios.md){target="_blank"}

<p>

## 第2季度发行 {#q2-release}

<p>

**为响应第三方Cookie逐步淘汰，弃用Marketo Measure功能**

为应对日益增长的隐私担忧，第三方Cookie正在逐步淘汰，Google Chrome的2024年第三季度截止日期标志着其淘汰。 Marketo Measure将弃用依赖于第三方Cookie的某些功能，特别是跨域跟踪和浏览转化归因，这些功能依赖于Google/DoubleClick展示次数Cookie。 此更改不会影响其他Marketo Measure功能或第一方Cookie的使用。 按照Google的时间表，这些功能预计将在6月1日之前弃用，尽管客户仍然可以访问在此日期之前收集的数据。

* [在Marketo Measure中适应第三方Cookie弃用](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure Cookies](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**分阶段推出我们的增强错误处理**

我们将分阶段推出增强导出作业的错误处理，从权限错误的即时应用程序内脉冲通知开始，并过渡到一个导出作业将在错误点暂停的新方法。 此更改旨在提高数据完整性和可见性，确保我们的用户拥有更顺畅、更可靠的数据管理流程。 为了确保顺利过渡并将对操作的中断降至最低，我们将分两个阶段实施这些更改：

* Pulse通知的立即可用性：在导出作业期间，您将收到有关权限错误的应用程序内脉冲通知。 这不会中断您的导出，但将帮助您了解错误而不影响当前作业。
* 在4月25日实施作业暂停： **已延迟**  — 在考虑Marketo Measure用户的反馈后，我们决定推迟原定于4月25日出现错误时暂停导出作业的实施。 我们认识到，停止就业可能不是最有效的办法。 我们致力于寻找更好的解决方案，以维护数据完整性并最大限度地减少中断。 我们将推迟对当前系统进行任何更改，直到我们能够确保解决方案更加符合用户的需求。

_为什么这很重要_

增强的数据完整性和面向未来的集成：我们会在出现问题迹象时停止作业，以防止数据丢失并确保准确性。 这有助于快速解决问题，提高数据导出质量和系统可靠性。

即时可见性：引入脉冲通知后，可以对权限错误做出即时响应，从而防止对操作造成潜在影响。

_支持您的过渡_

为了帮助您适应这种变化， [我们已创建文档](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} 提供了清晰的错误描述和全面的故障排除步骤。

<br>

**linkedIn集成所需的操作**

linkedIn最近发布了其Lead Sync API的更新版本。 请在5月20日之前重新验证Marketo Measure实例中的LinkedIn连接，以避免任何中断。

