---
unique-page-id: 18874783
description: 不包括 [!DNL Marketo Measure] 来自特定Forms - [!DNL Marketo Measure]
title: 不包括 [!DNL Marketo Measure] 来自特定Forms
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 0%

---

# 不包括 [!DNL Marketo Measure] 来自特定Forms {#excluding-marketo-measure-from-specific-forms}

默认情况下， [!DNL Marketo Measure] 附加到您网站上的所有表单。 但是，并非所有表单提交都必然应该跟踪或包含在归因模型中。 这是因为并非所有表单填写都被认为是“好的”。 退订页面/表单即属于此情况。 此外，通常不会跟踪登录表单，因为这会稀释归因模型。

## 如何添加 [!DNL Marketo Measure]-exclude代码：  {#how-to-add-marketo-measure-exclude-code}

预防 [!DNL Marketo Measure] 只需在跟踪特定表单中添加“[!DNL Bizible-Exclude]”作为窗体上的“类”。 代码如下：

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
