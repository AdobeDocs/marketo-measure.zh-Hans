---
unique-page-id: 18874783
description: 正在从特定Forms中排除 [!DNL Marketo Measure]  - [!DNL Marketo Measure]
title: '正在从特定Forms中排除 [!DNL Marketo Measure] '
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 0%

---

# 从特定Forms中排除[!DNL Marketo Measure] {#excluding-marketo-measure-from-specific-forms}

默认情况下，[!DNL Marketo Measure]会附加到您网站上的所有表单。 但是，并非所有表单提交都必然会被跟踪或包含在归因模型中。 这是因为并非所有表单填写都被认为是“好的”。 退订页面/表单即属于此情况。 此外，通常不会跟踪登录表单，因为这会稀释归因模型。

## 如何添加[!DNL Marketo Measure] — 排除代码：  {#how-to-add-marketo-measure-exclude-code}

要阻止[!DNL Marketo Measure]跟踪特定表单，只需在表单上添加“[!DNL Bizible-Exclude]”作为“类”即可。 代码如下：

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
