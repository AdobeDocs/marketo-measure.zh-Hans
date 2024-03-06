---
unique-page-id: 18874572
description: 复制记录和 [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: 复制记录和 [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# 复制记录和 [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>您可能会看到说明“[!DNL Marketo Measure]”，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

[!DNL Marketo Measure] 将数据与CRM中的相关潜在客户或联系人匹配时，使用电子邮件地址作为唯一标识符。 时间 [!DNL Marketo Measure] 查找具有相同电子邮件地址的多个潜在客户或联系人，我们会在所有记录中显示相同的数据。 当您报告以下潜在客户或联系人时，就会产生这种影响： [!DNL Marketo Measure] 并且可能会错误地夸大具有买方接触点的独特人员的数量。

这是什么样的 [!DNL Marketo Measure] 报告？

_示例报告： [!DNL Marketo Measure] 具有买方接触点的人员。_

![](assets/1-1.png)

您可以看到的 [!DNL Marketo Measure] kelsey@adobe.com的人员ID，表明存在使用该电子邮件地址的销售线索和联系人。 在此报表中，报告了2次首次接触、2次商机创建接触和2次PostLC交互。 这些重复记录共享接触点日期和接触点信息，这可能会导致以下结论：尽管他们是同一个人，但他们是两个不同的人。

**推荐**

* 为了最大化报表的回报，我们建议在CRM中使用重复数据删除工具，以确保仅创建新的唯一记录。 您可以使用营销自动化工具或CRM中安装的单独软件来完成此操作。 [!DNL Marketo Measure] 不会自动删除重复记录，也不会通过我们的软件提供此服务。
* 另一种选择是在标识重复项时手动合并记录。 这个过程可能既费时又繁琐，但准确报告的输出值得投入时间。
