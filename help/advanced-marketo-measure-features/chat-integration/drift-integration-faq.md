---
unique-page-id: 27656441
description: 漂移集成常见问题解答 —  [!DNL Marketo Measure]  — 产品文档
title: 漂移集成常见问题解答
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---

# 漂移集成常见问题解答 {#drift-integration-faq}

作为 [!DNL Marketo Measure] 与Drift集成，我们列出了一些最常见的问题。 如果存在以下未列出的任何问题，请联系Adobe客户团队（您的客户经理）或 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

**如何启用集成？**

漂移聊天跟踪 [!DNL Marketo Measure] 默认处于启用状态。 如果您出于任何原因想要禁用它（默认情况下不从“漂移聊天”中创建接触点），我们需要向您的中添加一个附加属性 [!DNL Marketo Measure] Javascript实施，粗体显示如下：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

对于使用的客户 [!DNL Google Tag Manager] 加载 [!DNL Marketo Measure] 脚本，如果要排除符合接触点条件的漂移聊天，则需要添加到以下内容 `<span>` 紧接在 [!DNL Marketo Measure] 脚本：

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**该集成有什么作用？**

集成现在允许 [!DNL Marketo Measure] 用于跟踪最终用户何时在Drift聊天中提供其电子邮件地址。 从那里，我们使用接触点类型“Web聊天”通过这些交互创建接触点。 此集成允许营销人员了解其聊天交互的表现，以及推动人们与这些聊天交互的渠道/子渠道/营销活动。

**如果我通过Campaign同步规则跟踪漂移，该怎么办？**

如果制定了任何Campaign同步规则来为Drift聊天交互创建接触点，您将需要确保停止将这些特定最终用户添加到相应的CRM Campaign。 否则，在启用功能位后，我们将为一个Drift聊天交互创建CRM Campaign接触点和数字接触点。

**如果我通过CRM营销活动跟踪漂移，该怎么办？**

如果设置了CRM营销活动来为Drift聊天交互创建接触点，则需要为这些特定营销活动设置接触点结束日期（接触点结束日期应该是启用Web聊天集成功能位的日期）。

**如果我通过活动跟踪漂移，该怎么办？**

如果制定了活动规则来为Drift聊天交互创建接触点，则需要将额外的逻辑添加到规则中。 您需要使用“任务创建日期”字段添加逻辑，以防止创建接触点的重复（IE CrmTask.CreatedDate早于启用功能位的日期）。 例如，请参阅下面的屏幕截图。

![](assets/activity-rule-drift.png)
