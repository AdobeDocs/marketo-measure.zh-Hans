---
unique-page-id: 18874600
description: 同步离线营销活动 —  [!DNL Marketo Measure]
title: 同步离线营销活动
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
feature: Channels
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 0%

---

# 同步离线营销活动 {#syncing-offline-campaigns}

可能很难准确地跟踪离线营销活动，并且很难了解它们与您的数字营销工作的对比情况。 [!DNL Marketo Measure] 允许您在中跟踪接触点并将其归因于离线营销活动 [!DNL Salesforce]，即使在 [!DNL Salesforce] 直到事件后几周才会创建营销活动。

>[!NOTE]
>
>本文介绍了一个过时的流程。 我们鼓励用户使用 [新的、改进的应用程序内流程](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

## 同步之前 {#before-you-sync}

以下是有关高效同步过程的一些提示：

* 离线营销活动是指不在线发生的营销互动。 其中包括营销渠道，如活动、网络研讨会和商展。 仅包括离线营销活动。
* 如果您希望包含在安装之前跟踪在线活动的营销活动 [!DNL Marketo Measure]，请确保将接触点结束日期设置为在您的网站上部署JavaScript的日期。
* 保留 [!DNL Marketo Measure] 在离线渠道页面上打开应用程序，以便轻松识别不同的促销活动类型，以及接触点将存储到的营销渠道。

* 在点击&#39;&#39;之前仔细检查所有内容[!UICONTROL Save]”按钮！

## 批量更新接触点日期 {#bulk-update-touchpoint-date}

在 [!DNL Salesforce]，促销活动成员对象上的创建日期字段会记下将促销活动成员添加到促销活动的日期。 为了使同步流程顺利进行，请确保“采购员接触点日期字段”中的日期与“Salesforce促销活动成员对象”中的日期相同。 此步骤使用&#39;&#39;执行[!UICONTROL Bulk Update Touchpoint Date button]，” _早于_ 您选择 [!UICONTROL picklist] 选项。

为什么这很重要？ 想象一下，你的公司在1月份的一次会议上赞助了一个展位。 会上，100个人对您的产品表现出兴趣，并提供了他们的联系信息以接收电子邮件更新。 三周后，您终于在中创建了一个营销活动 [!DNL Salesforce] 追踪会议结果。

您的上传日期将晚于会议日期三周。 为了弥补这一差异， [!UICONTROL Bulk Update Touchpoint Date] 按钮可用于设置适当的日期。 下图显示了按钮。

![](assets/1-3.png)

在这种情况下，它将回填上传日期3周。 应在设置&#39;&#39;之前执行此步骤[!UICONTROL Enable Buyer Touchpoints]”字段。

总之，如果您使用 [!UICONTROL Bulk Update Touchpoint Date] 按钮并将接触点日期更改为事件的日期， [!DNL Marketo Measure] 将生成事件实际日期（而非上传日期）的接触点。

您还可以更新现有营销活动上所有营销活动成员的日期。 执行此操作时，请确保接触点的日期是成员交互的日期。 单击批量更新购买者接触点日期，根据情况筛选营销活动成员列表，并在»[!UICONTROL Select Date]”选项位于营销活动成员列表上方，添加与事件发生日期相同的日期。

>[!CAUTION]
>
>确保更新接触点日期 _早于_ 您可以为所有营销活动成员启用接触点。

![](assets/2-3.png)

## 如何创建营销活动并同步购买者接触点 {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

在中创建营销活动 [!DNL Salesforce]，导航到 [!UICONTROL Campaigns] 选项卡并选择&#39;[!UICONTROL New]&#39;如下图所示。 根据您的 [!DNL Salesforce] 设置，您可能需要通过单击加号(+)图标将Campaigns添加到顶部栏。

![](assets/3-3.png)

创建此营销策划时，单击“[!UICONTROL Enable Buyer Touchpoints]”字段，并从选取列表中选择以下选项之一：

![](assets/4-3.png)

* **包括所有营销活动成员**
   * 此选项启用 [!DNL Marketo Measure] 将接触点归因于每个营销活动成员。

* **包括“已响应”营销活动成员。**
   * 此选项会将接触点应用于具有“已响应”状态的营销活动成员。

* **排除所有营销活动成员。**
   * 此选项不会将接触点归因于营销活动中的任何成员，并充当刻意从中排除营销活动的标志 [!DNL Marketo Measure]. 如果您曾经在意外情况下将促销活动与购买者接触点同步，则可以将状态更改为“排除所有促销活动成员”，并且接触点将被删除。

一旦选择了其中一项， [!DNL Marketo Measure] 会为每个营销活动成员分配一个接触点（如果适用）。 添加到营销活动的潜在客户或联系人 _必须_ 具有与记录关联的电子邮件地址，以便 [!DNL Marketo Measure] 以创建接触点。 如果没有电子邮件地址， [!DNL Marketo Measure] 不会向营销活动成员分配接触点。

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Tutorials：映射离线渠道](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
>
>[[!DNL Marketo Measure] Tutorials：Campaign对象字段](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/campaign-object-fields){target="_blank"}
