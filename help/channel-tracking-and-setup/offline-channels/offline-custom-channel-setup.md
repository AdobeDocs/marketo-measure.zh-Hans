---
unique-page-id: 18874598
description: 脱机自定义渠道设置 —  [!DNL Marketo Measure]
title: 脱机自定义渠道设置
exl-id: c5697714-1a79-40bd-8b7c-e10768f4ef67
feature: Channels
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 0%

---

# 脱机自定义渠道设置 {#offline-custom-channel-setup}

## 快速入门 {#getting-started}

比较方式 [!DNL Marketo Measure] 处理在线渠道规则，您会注意到离线渠道规则不需要使用电子表格。 但是，实施计划中仍会提供一个工作表，因为这样有助于您思考如何组织离线渠道。

电子表格包含三列：

![](assets/1-2.png)

**[!UICONTROL Salesforce]营销活动类型**  — 添加中标识的营销活动类型 [!DNL Salesforce] 此处

* 例如，这可以是电子邮件、网络研讨会、会议，或者您为此字段创建的任何您希望将接触点归因的值。

**[!UICONTROL Channel]**  — 在此处添加各种营销渠道

**[!UICONTROL Subchannel]**  — 在此处添加任何相应的子渠道

## 脱机渠道逻辑 {#offline-channel-logic}

[!DNL Marketo Measure] 离线渠道逻辑由Campaign对象确定，特别是 [!DNL Salesforce] 营销活动类型。 每个离线工作必须具有 [!DNL Salesforce] 营销活动类型，例如晚宴或商展，因为 [!DNL Marketo Measure] 依靠此字段了解要将哪个渠道和子渠道映射到哪个渠道。

SFDC促销活动类型将显示在离线渠道的选项卡中，列在下 [!DNL Salesforce] 营销活动类型。 请注意 [!DNL Marketo Measure] 只能为具有关联的买方接触点的市场活动导入SFDC市场活动类型。

![](assets/2-2.png)

您可以在此处在中创建渠道/子渠道映射 [!DNL Marketo Measure] 应用程序。 这可能需要在中创建新渠道和子渠道 [!DNL Marketo Measure] ，在应用程序的“创建渠道”部分中完成 — 如下图所示。 需要为创建新渠道和子渠道 [!DNL Marketo Measure] 以了解将接触点推送到何处。 您可以决定您希望如何映射营销活动类型。

![](assets/3-2.png)

## 渠道映射示例 {#channel-mapping-example}

例如，假设您参加了 [!DNL Salesforce] 一年一度的会议。 但是，每个会议都非常不同，并且都有独特的目标受众。 你想知道，这两者中哪一个能带来更多价值。 在您的 [!DNL Salesforce] 环境中，您可以为1月事件指定营销活动类型“会议”，将您的渠道命名为&quot;[!DNL Salesforce]，以及您的子渠道“1月会议”。

现在，您也想为6月份的会议做同样的事情。 您认为，由于这也是一个会议，因此可以为它指定相同的营销活动类型，在本例中为“会议”。 渠道是相同的， [!DNL Salesforce]，而本次第二次会议的子渠道为“六月会议”。 从组织角度看，这是有道理的。 然而，这让人非常困惑 [!DNL Marketo Measure] 逻辑来读取和应用这些规则，因为两个营销活动具有相同的营销活动类型。 [!DNL Marketo Measure] 脚本无法将数据从一个类型映射到两个不同的子渠道。 这意味着您需要为每个子渠道创建新的营销活动类型，但子渠道可以具有相同的渠道。

下面是逻辑示例， [!DNL Marketo Measure] 将无法阅读：

![](assets/4-2.png)

在上述场景中，您将需要创建一个唯一的促销活动类型，因为您不能将相同的促销活动类型映射到两个不同的子渠道。 相反，您需要设置如下所示的唯一类型：

![](assets/5-2.png)

渠道映射中必须包含任何现有的营销活动类型，并应将“NULL”添加为渠道。

请花些时间了解 [!DNL Salesforce] 确定要包含的现有记录类型的数量和性质，以及是否需要根据上述信息创建其他营销活动。 填写完所有必要信息后，即可上传。

了解有关 [脱机同步 [!DNL Salesforce] 促销活动与 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md).

## 为在线营销工作处理SFDC营销活动 {#handling-sfdc-campaigns-for-online-marketing-efforts}

营销团队通常会创建 [!DNL Salesforce] 营销活动，以跟踪各种数字营销工作。 这种做法没有问题；但是，应区别对待这些营销活动与真正的离线营销活动（例如直邮或会议），这一点很重要。 与数字事件（网站上发生的交互）相关的营销活动不应与同步 [!DNL Marketo Measure]. 同步这些营销活动会导致接触点重复，因为 [!DNL Marketo Measure] JavaScript已在跟踪在线工作。

处理在线活动促销活动的另一个技巧是映射 [!DNL Salesforce] Campaign Type为NULL。 为此，请先在中创建一个渠道 [!DNL Marketo Measure] 如下图所示，应用程序标题为NULL 。 此页面位于 [!DNL Marketo Measure] 应用程序位于 **创建渠道** 部分。 在意外同步不应同步的营销活动时，这将很有帮助。 通过查看所有存储在NULL下的内容，可以轻松找到促销活动并更正同步状态。

![](assets/6-2.png)

## 在应用程序中输入离线渠道规则 {#entering-your-offline-channel-rules-to-the-app}

在编辑电子表格并更新您的自定义规则后，下一步是在 [!DNL Marketo Measure] 应用程序 — 您实际上不会上传离线渠道的电子表格。 而是要在选择列表框中输入信息，如下图所示。 通过单击 **[!UICONTROL Offline Channels]** 在 **[!UICONTROL Channels]** 部分。

![](assets/7-2.png)

>[!TIP]
>
>想要确定 _时间_ a [!DNL Salesforce] 营销活动类型被提取到 [!DNL Marketo Measure] 渠道映射？ 转到 **[!UICONTROL Setup]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Fields]** > **[!UICONTROL Type]**. 然后，您可以查看选择列表中包含哪些值以及哪些值处于非活动状态。 未激活的报表将不会在我们的“”中显示为可选类型[!UICONTROL Offline Channels]“ ”部分。 请注意，此过程可能需要几分钟到48小时的时间。

单击 **[!UICONTROL Save]** 当您完成并 [!DNL Marketo Measure] 将上传更改并重新处理数据。

>[!MORELIKETHIS]
>
>* [[!DNL Marketo Measure] 大学：映射离线渠道](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>* [[!DNL Marketo Measure] 大学：同步离线营销活动](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63286e34d9f0367662b78b)
>
>* [Marketo Engage程序集成](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping)
