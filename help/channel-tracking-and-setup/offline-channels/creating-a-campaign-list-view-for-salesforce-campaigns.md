---
unique-page-id: 18874718
description: 为创建营销活动列表视图 [!DNL Salesforce Campaigns] - [!DNL Marketo Measure]  — 产品文档
title: 为创建营销活动列表视图 [!DNL Salesforce] 促销活动
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# 为创建营销活动列表视图 [!DNL Salesforce] 促销活动 {#creating-a-campaign-list-view-for-salesforce-campaigns}

了解如何为要与买方接触点同步的营销活动创建列表视图。

通过可创建的促销活动列表视图，您可以拥有一个“入门”位置来查看和管理“类型”和“启用买方接触点”字段，以确保您的 [!DNL Salesforce] 已正确设置可通知离线营销渠道的营销活动。

1. 中的“营销活动标题”选项卡 [!DNL Salesforce] 并创建新列表视图
1. 将视图命名为“要与同步的营销活动” [!DNL Marketo Measure].&quot;
1. 我们希望此列表仅显示要与同步的营销活动 [!DNL Marketo Measure] 因此，我们需要几个过滤器：

   * **类型** [等于] “我们映射到离线渠道的所有营销活动类型”。 请参阅实施计划或 [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} ->我的帐户 — >设置 — >脱机渠道)。 您可以通过放大镜图标选择所需的类型（那些已映射到离线营销渠道的类型）。

      * 每个过滤器最多选择3种类型。 过滤器字段中可以包含字符数限制。 从每个过滤器3种类型开始，并根据需要添加额外的“类型”过滤器行。
   * **创建日期** [大于或等于] 您的 [!DNL Marketo Measure] 开始日期。 您可以在 [!DNL Marketo Measure] 应用程序。 只需在短划线的日期范围中选择“自创建日期起”，即可显示开始日期。
   * **&#42;记录类型&#42;**  — 要在列表视图中进行编辑，您需要为记录类型添加过滤器。 您可能需要编辑的每个营销活动记录都需要是相同的记录类型。


1. 编辑要在列表视图中显示的选定字段。 列表视图的完整设置应类似于以下示例：

   此视图允许您查看营销活动，并根据需要编辑“类型”和“启用买方接触点”字段。 在您创建新的营销活动时，应与 [!DNL Marketo Measure]，它们将显示在此视图中，您可以从列表中直接管理这些营销活动的所有设置。

   要从列表视图进行内联编辑，您需要确保在 [!DNL Salesforce] 设置：

   * **[!UICONTROL Setup]** > **[!UICONTROL User Interface]** > **[!UICONTROL Enable Inline Editing]**
   * 还需要选中启用增强列表（就在用于内联编辑的框下方）
   * 确保拥有字段的权限

>[!MORELIKETHIS]
>
>[对列表视图内联编辑的常见问题进行故障诊断](http://help.salesforce.com/articleView?id=000003911&amp;language=en_US&amp;type=1){target="_blank"}
