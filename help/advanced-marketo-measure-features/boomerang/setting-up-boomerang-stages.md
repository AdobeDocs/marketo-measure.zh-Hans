---
unique-page-id: 18874767
description: 设置回音廊阶段 —  [!DNL Marketo Measure]
title: 设置回访单阶段
exl-id: 00dd2826-27a3-462e-a70e-4cec90d07f92
feature: Boomerang
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# 设置回访单阶段 {#setting-up-boomerang-stages}

>[!AVAILABILITY]
>
>Boomerang功能仅对第3层客户启用。 要申请更高的客户层，请联系Adobe客户团队（您的客户经理）。

要启用 [!UICONTROL Boomerang] 暂存帐户，您必须是帐户管理员。 或者，可以通过联系来启用该功能 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}. 启用该功能后，请按照以下说明进行设置。

## 回旋镖阶段设置 {#boomerang-stage-setup}

1. 转到 [!UICONTROL Stage Mapping]. 在标题为&#39;&#39;的列下[!UICONTROL Boomerang]，”选中要跟踪的阶段旁边的框。

   ![](assets/1-2.png)

1. 转到 [!UICONTROL Attribution Settings] 制表符并输入您希望看到的每个阶段的接触点数量。 最多允许10个。 缺省设置为1。

   ![](assets/2-2.png)

1. 单击 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >根据这些更改，允许24-48小时重新处理您的数据。

## 使用自定义模型归因设置回音廊阶段 {#boomerang-stage-setup-with-custom-model-attribution}

1. 转到 [!UICONTROL Stage Mapping]. 在标题为&#39;&#39;的列下[!UICONTROL Boomerang]，”选中要跟踪的阶段旁边的框。

   ![](assets/3-1.png)

1. 如果您还希望将这些Boomerang阶段包含在自定义模型中并获取归因点数，请务必选中“[!UICONTROL Custom Model]“ ”列。

   ![](assets/4-1.png)

1. 转到 [!UICONTROL Attribution Settings] 选项卡。 确定您希望如何为自转站阶段归因赋权。 选项包括在第一次发生次数、最后一次发生次数上对归因进行加权，或者将归因平均拆分到所有发生次数。

   ![](assets/5-1.png)

1. 输入您希望查看的每个阶段的发生次数。 最多允许10个。 缺省设置为1。

   ![](assets/6-1.png)

1. 设置要分配给自定义模型中包含的Boomerang阶段的归因百分比。 确保所有阶段的总归因合计为100%。 单击 **[!UICONTROL Save and Process]**.

   ![](assets/7-1.png)

   >[!NOTE]
   >
   >根据这些更改，允许24-48小时重新处理您的数据。
