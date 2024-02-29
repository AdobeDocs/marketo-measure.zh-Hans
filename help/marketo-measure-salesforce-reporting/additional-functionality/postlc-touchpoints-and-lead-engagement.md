---
unique-page-id: 18874562
description: PostLC接触点和潜在客户参与 — Marketo Measure — 产品文档
title: PostLC接触点和潜在客户参与
exl-id: 3ee5c571-195e-46c7-b150-fedcbc3614cb
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 0%

---

# PostLC接触点和潜在客户参与 {#postlc-touchpoints-and-lead-engagement}

[!DNL Marketo Measure] 商机后创建(PostLC)接触点可供使用多点接触归因模型（W-Shape及更高版本）的客户使用。 当潜在客户或联系人返回您的网站并继续填写表单时，这些表单提交将注册为PostLC接触点。 这些接触点允许您查看是什么内容在促使潜在客户在首次转化后很长时间继续参与您的网站。 PostLC接触点与Opportunity中的所有中间接触点共享归因点数；将10%的归因点数分配给中间接触点，并在所有接触之间平均分配。

![](assets/1.png)

您可以调整将在以下位置显示的PostLC接触点数量： [!DNL SFDC]. 通常，我们建议最多推送五个PostLC接触点；每个接触点占用1 KB的空间 [!DNL SFDC].

>[!NOTE]
>
>有关如何调整PostLC接触点设置的说明，请参阅本文末尾。

PostLC接触点是动态的。 作为潜在客户或联系人继续提交PostLC表单， [!DNL Marketo Measure] 将更新您CRM中的PostLC接触点，以显示他们提交的最新表单。 具体来说，如果您设置了5个PostLC接触点的限制， [!DNL Marketo Measure] 总是推5号 _最近_ CRM的接触点。  在此示例中，此帐户已将其PostLC限制设置为四个接触点。 此潜在客户已达到其在您的CRM中可以包含的最大PostLC接触点数。 最近一次PostLC接触是在2018年2月6日。 如果这个人第二天要填写另一个表格， [!DNL Marketo Measure] 将从2017年9月11日删除第一个PostLC接触点，以添加从2018年7月2日起的最新接触点。

![](assets/2.png)

>[!NOTE]
>
>[!DNL Marketo Measure] 将仅更新Lead或Contact上的PostLC接触点，不会更新Opportunity上的PostLC归因接触点。 Contact的所有相关PostLC接触点都将包含在Opportunity中。

## 如何更改PostLC接触点设置 {#how-to-change-postlc-touchpoint-settings}

要调整潜在客户或联系人的PostLC接触点设置，请按照以下说明操作。

**潜在客户**

1. 登录 [!DNL Marketo Measure] 帐户位置 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 并转到 [!UICONTROL Settings].

1. 在CRM下，选择 **[!UICONTROL Leads]**.

1. 输入您要推送至潜在客户的postLC接触点数量，然后单击 **[!UICONTROL Save]**.

   ![](assets/3.png)

**联系人**

1. 登录 [!DNL Marketo Measure] 帐户位置 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 并转到 [!UICONTROL Settings].

1. 在CRM下，选择 **[!UICONTROL Contacts]**.

1. 输入要推送到联系人的postLC接触点数，然后单击 **[!UICONTROL Save]**.

   ![](assets/4.png)
