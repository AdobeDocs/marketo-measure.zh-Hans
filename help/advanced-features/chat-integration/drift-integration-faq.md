---
description: Marketo Measure用户的漂移集成常见问题解答指南
title: 漂移集成常见问题解答
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
feature: Integration
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---

# 漂移集成常见问题解答 {#drift-integration-faq}

作为[!DNL Marketo Measure]与漂移集成的一部分，以下是一些最常见的问题。 如果遇到以下未列出的任何问题，请联系Adobe客户团队（您的客户经理）或[Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。

**如何启用集成？**

默认情况下已启用[!DNL Marketo Measure]的漂移聊天跟踪。 如果要禁用它（默认情况下不从漂移聊天中创建接触点），请向您的[!DNL Marketo Measure] Javascript实施添加一个附加属性，粗体显示如下：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

对于使用[!DNL Google Tag Manager]加载[!DNL Marketo Measure]脚本的用户，如果您希望排除您的漂移聊天符合接触点条件，请直接在您的`<span>`脚本之后添加以下[!DNL Marketo Measure]：

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**集成有什么作用？**

该集成现在允许[!DNL Marketo Measure]跟踪最终用户在Drift聊天中提供其电子邮件地址的时间。 从那里，我们使用接触点类型“Web聊天”通过这些交互创建接触点。 此集成允许营销人员了解其聊天交互的表现，以及推动人们与这些聊天交互的渠道/子渠道/营销活动。

**如果我通过促销活动同步规则跟踪漂移怎么办？**

如果制定了任何Campaign同步规则来为Drift聊天交互创建接触点，请确保停止将这些特定最终用户添加到相应的CRM Campaign。 否则，在启用功能位后，请为一个Drift聊天交互创建CRM Campaign接触点和数字接触点。

**如果我通过CRM营销活动跟踪漂移怎么办？**

如果设置了CRM营销活动来为Drift聊天交互创建接触点，则必须为这些特定营销活动设置接触点结束日期（接触点结束日期应该是启用Web聊天集成功能位的日期）。

**如果我通过活动跟踪漂移怎么办？**

如果制定了活动规则来为Drift聊天交互创建接触点，则必须向规则中添加额外的逻辑。 使用任务创建日期字段添加逻辑，以防止创建接触点重复（IE CrmTask.CreatedDate早于启用功能位的日期）。 例如，请参阅下面的屏幕截图。

![](assets/chat-integration-1.png)
