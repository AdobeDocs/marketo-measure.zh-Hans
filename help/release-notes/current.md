---
description: 最新发行说明 —  [!DNL Marketo Measure]
title: 最新发行说明
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 00a362a2e143749e1a132672b847eb06dcab6b9c
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# 发行说明：2024年 {#release-notes-2024}

有关2024版的所有新增功能和更新功能，请参阅下文。

## 第2季度发行 {#q2-release}

<p>

**为响应第三方Cookie逐步淘汰，弃用Marketo Measure功能**

为应对日益增长的隐私担忧，第三方Cookie正在逐步淘汰，Google Chrome的2024年第三季度截止日期标志着其淘汰。 Marketo Measure将弃用依赖于第三方Cookie的某些功能，特别是跨域跟踪和浏览转化归因，这些功能依赖于Google/DoubleClick展示次数Cookie。 此更改不会影响其他Marketo Measure功能或第一方Cookie的使用。 按照Google的时间表，这些功能预计将在6月1日之前弃用，尽管客户仍然可以访问在此日期之前收集的数据。

* [在Marketo Measure中适应第三方Cookie弃用](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure Cookies](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**分阶段推出我们的增强错误处理**

我们将分阶段推出增强导出作业的错误处理功能，从权限错误的即时应用程序内脉冲通知开始，并在4月25日过渡到导出作业将在错误点暂停的新方法。 此更改旨在提高数据完整性和可见性，确保我们的用户拥有更顺畅、更可靠的数据管理流程。 为了确保顺利过渡并将对操作的中断降至最低，我们将分两个阶段实施这些更改：

* Pulse通知的立即可用性：在导出作业期间，您将收到有关权限错误的应用程序内脉冲通知。 这不会中断您的导出，但将帮助您了解错误而不影响当前作业。
* 4月25日实施作业暂停：从4月25日开始，如果我们的系统在导出作业期间遇到权限错误，它将暂停作业以确保不会跳过任何数据。 您会收到任何问题的通知，一旦权限得到纠正，导出作业将从之前停止的位置无缝恢复。

_为什么这很重要_

增强的数据完整性和面向未来的集成：我们会在出现问题迹象时停止作业，以防止数据丢失并确保准确性。 这有助于快速解决问题，提高数据导出质量和系统可靠性。

即时可见性：引入脉冲通知后，可以对权限错误做出即时响应，从而防止对操作造成潜在影响。

_支持您的过渡_

为了帮助您适应这种变化， [我们已创建文档](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} 提供了清晰的错误描述和全面的故障排除步骤。
