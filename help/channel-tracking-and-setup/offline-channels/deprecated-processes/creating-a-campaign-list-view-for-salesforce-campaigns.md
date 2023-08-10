---
unique-page-id: 18874718
description: 创建营销活动列表视图 [!DNL Salesforce Campaigns] - [!DNL Marketo Measure]  — 产品文档
title: 创建营销活动列表视图 [!DNL Salesforce] 营销活动
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
feature: Channels
source-git-commit: e01738222e8845112892c0258cb084a4f0ebb257
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# 创建营销活动列表视图 [!DNL Salesforce] 营销活动 {#creating-a-campaign-list-view-for-salesforce-campaigns}

了解如何为那些要与买方接触点同步的营销活动创建列表视图。

>[!NOTE]
>
>本文介绍了一个过时的流程。 我们鼓励用户使用 [新的、改进的应用程序内进程](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

通过可创建的Campaign列表视图，您可以有一个“转至”位置，用于查看和管理“类型”和“启用买方接触点”字段，以确保 [!DNL Salesforce] 已正确设置通知离线营销渠道的营销活动。

1. 中的“转至营销活动”选项卡 [!DNL Salesforce] 并创建新列表视图
1. 将视图命名为“要与之同步的促销活动” [!DNL Marketo Measure]“
1. 我们希望此列表仅显示要与之同步的营销活动 [!DNL Marketo Measure] 因此我们需要几个过滤器：

   * **类型** [等于] &#39;我们已映射到您的离线渠道的所有Campaign类型&#39;。 请参阅您的实施计划或中的“离线渠道”选项卡 [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} ->我的帐户 — >设置 — >脱机渠道)。 您可以通过放大镜图标选择所需的类型（映射到离线营销渠道的类型）。

      * 为每个过滤器选择3种最大类型。 过滤器字段中可包含的字符数存在限制。 从每个过滤器3个类型开始，并根据需要添加更多“类型”过滤器行。

   * **创建日期** [大于或等于] 您的 [!DNL Marketo Measure] 开始日期。 您可以在ROI仪表板的 [!DNL Marketo Measure] 应用程序。 只需在短划线的日期范围内选择“自创建日期起”，它将显示您的开始日期。
   * **&#42;记录类型&#42;**  — 要在“列表视图”中进行编辑，您需要为“记录类型”添加过滤器。 您可能需要编辑的每个营销活动记录都需要使用相同的记录类型。

1. 编辑要在列表视图中显示的选定字段。 列表视图的完整设置应类似于以下示例：

   通过此视图，您可以查看营销策划，并根据需要编辑“类型”和“启用买方接触点”字段。 在创建应与之同步的新营销活动时 [!DNL Marketo Measure]中，它们将显示在此视图中，您可以直接从列表中管理这些营销活动的所有设置。

   要从列表视图进行内联编辑，您需要确保您的中的以下内容也成立 [!DNL Salesforce] 设置：

   * **[!UICONTROL Setup]** > **[!UICONTROL User Interface]** > **[!UICONTROL Enable Inline Editing]**
   * 还需要选中增强列表（位于用于内联编辑的框下）
   * 确保对字段具有权限

>[!MORELIKETHIS]
>
>[列表视图内联编辑的常见问题疑难解答](http://help.salesforce.com/articleView?id=000003911&amp;language=en_US&amp;type=1){target="_blank"}
