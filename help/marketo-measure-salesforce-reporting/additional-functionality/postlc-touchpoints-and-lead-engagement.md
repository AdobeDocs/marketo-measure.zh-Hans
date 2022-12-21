---
unique-page-id: 18874562
description: LC后接触点和潜在客户参与 — Marketo测量 — 产品文档
title: LC后接触点和潜在客户参与
exl-id: 3ee5c571-195e-46c7-b150-fedcbc3614cb
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# LC后接触点和潜在客户参与 {#postlc-touchpoints-and-lead-engagement}

[!DNL Marketo Measure] 潜在客户创建后(PostLC)接触点适用于使用多接触归因模型（W形及更高版本）的客户。 当潜在客户或联系人返回您的网站并继续填写表单时，这些表单提交将注册为PostLC接触点。 这些接触点允许您查看哪些内容促使潜在客户在首次转化后很久便继续与您的网站互动。 PostLC触点与Opportunity中的所有中间接触点共享归因信用；10%的归因点数分配给中间接触点，并在所有接触点之间平均分配。

![](assets/1.png)

您可以调整将在中显示的PostLC接触点数 [!DNL SFDC]. 通常，我们建议最多推送5个PostLC接触点；每个接触点占用1KB [!DNL SFDC].

>[!NOTE]
>
>有关如何调整PostLC接触点设置的说明，请参阅本文的末尾。

PostLC触点是动态的。 由于潜在客户或联系人继续提交PostLC表单， [!DNL Marketo Measure] 将更新CRM中的PostLC接触点，以向您显示他们最近提交的表单。 具体而言，如果已将PostLC接触点限制为5, [!DNL Marketo Measure] 总是推5 _最近_ 接触点。  在本例中，此帐户已将其PostLC限制设置为四个接触点。 此潜在客户已达到在您的CRM中可以拥有的PostLC接触点的最大数量。 PostLC最近一次联系是2/6/2018。 如果第二天这个人要填另一张表格， [!DNL Marketo Measure] 将从11/9/2017中删除第一个PostLC接触点，以从2/7/2018中添加最新接触点。

![](assets/2.png)

>[!NOTE]
>
>[!DNL Marketo Measure] 将只更新潜在客户或联系人上的PostLC接触点，而不会更新Opportunity上的PostLC归因接触点。 Contact上所有相关的PostLC接触点都将包含在Opportunity中。

## 如何更改PostLC接触点设置 {#how-to-change-postlc-touchpoint-settings}

要调整潜在客户或联系人的PostLC接触点设置，请按照以下说明操作。

**潜在客户**

1. 登录到 [!DNL Marketo Measure] 帐户 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}，转到 [!UICONTROL Settings].

1. 在CRM下，选择 **[!UICONTROL Leads]**.

1. 输入要推送到潜在客户的postLC接触点数量，然后单击 **[!UICONTROL Save]**.

   ![](assets/3.png)

**联系人**

1. 登录到 [!DNL Marketo Measure] 帐户 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}，转到 [!UICONTROL Settings].

1. 在CRM下，选择 **[!UICONTROL Contacts]**.

1. 输入要推送到联系人的postLC接触点数，然后单击 **[!UICONTROL Save]**.

   ![](assets/4.png)
