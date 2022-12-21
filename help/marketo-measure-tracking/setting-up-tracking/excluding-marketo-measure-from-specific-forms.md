---
unique-page-id: 18874783
description: 排除 [!DNL Marketo Measure] 从特定Forms - [!DNL Marketo Measure]  — 产品文档
title: 排除 [!DNL Marketo Measure] 从特定Forms
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 0%

---

# 排除 [!DNL Marketo Measure] 从特定Forms {#excluding-marketo-measure-from-specific-forms}

默认情况下， [!DNL Marketo Measure] 附加到您网站上的所有表单。 但是，并非所有表单提交都必须被跟踪或包含在归因模型中。 这是因为并非所有表单填充都被视为“好”。 例如，取消订阅页面/表单。 此外，通常不会跟踪登录表单，因为它会稀释归因模型。

## 如何添加 [!DNL Marketo Measure]-exclude代码：  {#how-to-add-marketo-measure-exclude-code}

防止 [!DNL Marketo Measure] 从跟踪特定表单，只需添加“[!DNL Bizible-Exclude]”作为表单上的“类”。 代码如下：

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
