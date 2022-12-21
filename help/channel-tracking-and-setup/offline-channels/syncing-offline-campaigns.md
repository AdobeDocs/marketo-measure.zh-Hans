---
unique-page-id: 18874600
description: 正在同步离线营销活动 —  [!DNL Marketo Measure]  — 产品文档
title: 正在同步离线营销活动
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 0%

---

# 正在同步离线营销活动 {#syncing-offline-campaigns}

很难准确跟踪离线促销活动并了解它们与您的数字营销工作相比。 [!DNL Marketo Measure] 允许您跟踪触点并将其归因于 [!DNL Salesforce]，即使在 [!DNL Salesforce] 活动要到活动后几周后才能创建营销活动。

## 同步之前 {#before-you-sync}

以下是有关高效同步过程的一些提示：

* 离线营销活动是指不在线发生的营销互动。 这些渠道包括活动、网络研讨会和贸易展等营销渠道。 仅包括离线营销活动。
* 如果要在安装之前包含跟踪在线活动的营销活动，请 [!DNL Marketo Measure]，请确保将接触点结束日期设置为在您的网站上部署JavaScript的日期。
* 将 [!DNL Marketo Measure] 应用程序会在“离线渠道”页面上打开，以便轻松识别不同的促销活动类型，以及接触点将被分段到的营销渠道。

* 在点击“[!UICONTROL Save]&quot;按钮！

## 批量更新接触点日期 {#bulk-update-touchpoint-date}

在 [!DNL Salesforce]，营销活动成员对象上的创建日期字段会注意营销活动成员添加到营销活动的日期。 为了顺利进行同步过程，请确保“采购员接触点日期”字段与Salesforce促销活动成员对象上的日期相同。 使用“[!UICONTROL Bulk Update Touchpoint Date button]，” _之前_ 选择 [!UICONTROL picklist] 选项启用采购员接触点字段。

为什么这很重要？ 想象一下，你的公司在1月份的一个会议上赞助了一个展位。 在会议上，100人对您的产品表示了兴趣，并提供了联系信息以接收电子邮件更新。 三周后，您终于在 [!DNL Salesforce] 跟踪会议结果。

您的上传日期将比会议日期晚三周。 要解决此差异，请 [!UICONTROL Bulk Update Touchpoint Date] 按钮来设置相应的日期。 下图显示了按钮。

![](assets/1-3.png)

在这种情况下，会将上传日期回填三周。 此步骤应在设置“[!UICONTROL Enable Buyer Touchpoints]“ ”字段。

总之，如果您使用 [!UICONTROL Bulk Update Touchpoint Date] 按钮，并将接触点日期更改为事件日期， [!DNL Marketo Measure] 将为事件的实际日期（而非上传日期）生成接触点。

您还可以更新现有营销活动中所有营销活动成员的日期。 执行此操作时，请确保接触点的日期是成员交互的日期。 只需单击批量更新采购员接触点日期，根据需要筛选促销活动成员列表，并在“[!UICONTROL Select Date]“ ”选项，添加与事件发生日期相同的日期。

>[!CAUTION]
>
>确保更新接触点日期 _之前_ 为所有营销活动成员启用接触点。

![](assets/2-3.png)

## 如何创建促销活动和同步购买者接触点 {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

在中创建营销活动 [!DNL Salesforce]，导航到 [!UICONTROL Campaigns] 选项卡，选择&#39;[!UICONTROL New]“ ”，如下图所示。 根据您的 [!DNL Salesforce] 设置后，您可能需要通过单击加号(+)图标，将营销活动添加到顶部栏。

![](assets/3-3.png)

创建此营销活动时，请单击[!UICONTROL Enable Buyer Touchpoints]“ ”字段，然后从选取列表中选择以下选项之一：

![](assets/4-3.png)

* **包括所有营销活动成员**
   * 此选项将启用 [!DNL Marketo Measure] 将接触点归因到每个营销活动成员。

* **包括“已响应”营销活动成员。**
   * 此选项将接触点应用于具有“已响应”状态的营销活动成员。

* **排除所有营销活动成员。**
   * 此选项不将接触点归因于营销活动中的任何成员，并充当营销活动被有意排除在外的标记 [!DNL Marketo Measure]. 如果您在意外时将营销活动与买方接触点同步，则可以将状态更改为“排除所有营销活动成员”，接触点将被删除。

选择其中一个选项后， [!DNL Marketo Measure] 将为每个营销活动成员分配一个接触点（如果适用）。 添加到营销活动的潜在客户或联系人 _必须_ 具有与其记录关联的电子邮件地址，以便 [!DNL Marketo Measure] 创建接触点。 没有电子邮件地址， [!DNL Marketo Measure] 不会为营销活动成员分配接触点。

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 大学：映射离线渠道](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>[[!DNL Marketo Measure] 大学：促销活动对象字段](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
