---
unique-page-id: 18874572
description: 复制记录和 [!DNL Marketo Measure] - [!DNL Marketo Measure]  — 产品文档
title: 复制记录和 [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# 复制记录和 [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>您可能会看到指定“[!DNL Marketo Measure]“ ”，但仍会在您的CRM中看到“Bizible”。 我们正在努力更新该版本，并且该品牌重命名将很快地反映在您的CRM中。

[!DNL Marketo Measure] 在CRM中将数据与相关潜在客户或联系人匹配时，会利用电子邮件地址作为我们的唯一标识符。 When [!DNL Marketo Measure] 查找具有相同电子邮件地址的多个潜在客户或联系人，我们将在所有记录中显示相同的数据。 当您报告的潜在客户或联系人与 [!DNL Marketo Measure] 并且可能会错误地夸大具有买方接触点的独特人员数量。

这在里面是什么样子 [!DNL Marketo Measure] 报告？

_示例报表： [!DNL Marketo Measure] 具有买方接触点的人员。_

![](assets/1-1.png)

您可以在 [!DNL Marketo Measure] 人员ID为kelsey@adobe.com，表示该电子邮件地址同时存在潜在客户和联系人。 您会发现，在此报表中，报告了2次首次接触、2次潜在客户创建接触和2次PostLC交互。 这些重复记录共享相同的接触点日期和接触点信息，这可能导致他们是2个不同的人，尽管他们是同一个人。

**推荐**

* 为了在您的报表中获得最大回报，我们建议在您的CRM中利用一个去重复工具，以确保您仅创建新的唯一记录。 这可以通过您的营销自动化工具或CRM中安装的单独软件来完成。 [!DNL Marketo Measure] 不会自动删除重复数据记录，也不会通过我们的软件提供此服务。
* 另一种选择是在您识别重复项时手动合并记录。 此过程既费时又繁琐，但准确报告的输出值得投入时间。
