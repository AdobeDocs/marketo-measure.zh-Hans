---
description: 重复记录和 [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: 重复记录和 [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---


# 重复记录和[!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

将数据与CRM中的相关潜在客户或联系人匹配时，[!DNL Marketo Measure]使用电子邮件地址作为唯一标识符。 当[!DNL Marketo Measure]找到多个电子邮件地址相同的潜在客户或联系人时，我们会在所有记录中显示相同的数据。 当您报告具有[!DNL Marketo Measure]的潜在客户或联系人时，这会造成影响，并且可能会错误地夸大具有买方接触点的独特人数。

[!DNL Marketo Measure]报表中该内容是什么样的？

_示例报告：[!DNL Marketo Measure]具有购买者接触点的人员。_

![&#x200B; 1](assets/1-1.png)

对于kelsey@adobe.com的[!DNL Marketo Measure]人员ID，您可以看到存在使用该电子邮件地址的销售线索和联系人。 在此报表中，报告了2次首次接触、2次商机创建接触和2次PostLC交互。 这些重复记录共享接触点日期和接触点信息，这可能会导致以下结论：尽管他们是同一个人，但他们是两个不同的人。

**推荐**

* 为了最大化报表的回报，我们建议在CRM中使用重复数据删除工具，以确保仅创建新的唯一记录。 您可以使用营销自动化工具或CRM中安装的单独软件来完成此操作。 [!DNL Marketo Measure]不会自动删除重复记录，也不会通过我们的软件提供此服务。
* 另一种选择是在标识重复项时手动合并记录。 这个过程可能既费时又繁琐，但准确报告的输出值得投入时间。
