---
unique-page-id: 18874572
description: 复制记录和 [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: 复制记录和 [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# 复制记录和 [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>您可能会看到说明“[!DNL Marketo Measure]”，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

[!DNL Marketo Measure] 在将数据与CRM中的相关潜在客户或联系人匹配时，使用电子邮件地址作为我们的唯一标识符。 时间 [!DNL Marketo Measure] 查找具有相同电子邮件地址的多个Lead或Contact，我们将在所有记录中显示相同的数据。 当您报告以下潜在客户或联系人时，就会产生这种影响： [!DNL Marketo Measure] 并且可能会错误地夸大具有买方接触点的独特人员的数量。

这是什么样的 [!DNL Marketo Measure] 报告？

_示例报告： [!DNL Marketo Measure] 具有买方接触点的人员。_

![](assets/1-1.png)

您可以看到的 [!DNL Marketo Measure] kelsey@adobe.com的人员ID，表明存在使用该电子邮件地址的销售线索和联系人。 您会发现，在此报表中报告了2次首次接触、2次潜在客户创建接触和2次PostLC交互。 这些重复记录共享相同的接触点日期和接触点信息，这可能会导致得出结论：尽管他们是同一个人，但他们是2个不同的人。

**推荐**

* 为了最大限度地提高报表的回报，我们建议在CRM中利用重复数据删除工具，以确保您仅创建新的唯一记录。 您可以使用营销自动化工具或CRM中安装的单独软件来完成此操作。 [!DNL Marketo Measure] 不会自动删除重复记录，也不会通过我们的软件提供此服务。
* 另一种选择是在标识重复项时手动合并记录。 这个过程可能既费时又繁琐，但输出准确的报表是值得的时间投入。
