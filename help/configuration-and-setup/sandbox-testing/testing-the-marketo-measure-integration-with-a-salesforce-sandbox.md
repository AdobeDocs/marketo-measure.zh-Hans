---
unique-page-id: 18874765
description: 测试Marketo Measure与Salesforce沙盒的集成 —  [!DNL Marketo Measure]  — 产品文档
title: 测试Marketo Measure与Salesforce沙盒的集成
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 1%

---

# 测试Marketo Measure与Salesforce沙盒的集成 {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>您可能会看到指定“[!DNL Marketo Measure]“ ”，但仍会在您的CRM中看到“Bizible”。 我们正在努力更新该版本，并且该品牌重命名将很快地反映在您的CRM中。

其中一个 [!DNL Marketo Measure] 核心功能是，通过在网站上采取操作来跟踪您的数字营销工作，然后将该数据推送到您的生产环境 [!DNL Salesforce org] 通过潜在客户和联系人。 但是，在沙盒集成中，通常不会从您的网站创建入站Lead，因此将仅从离线的角度来关注数据。

以下是两个测试阶段引用的两个源。 [步骤1-4](https://help.salesforce.com/apex/HTViewHelpDoc?id=lead_import_wizard.htm&amp;language=en_US) 和 [步骤5-6](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md). 我们建议您查看这些文档，因为它们在某些方面提供了更详细的信息。

1. 您需要以CSV格式创建一些潜在客户，以便将他们上传到营销活动。 要执行此操作，请在生产Salesforce中通过报表导出一些潜在客户。 否则，您可以在Excel文件中手动创建潜在客户，然后将其另存为CSV以进行导入。 你只需要20张唱片。 文件需要具有以下列：

   1. 电子邮件
   1. 公司
   1. 姓氏
   1. 名字（可选，但推荐）

1. 登录到沙盒环境。
1. 您首先将创建一个测试营销活动。 我们建议使用促销活动类型，如事件或新闻稿。
1. 创建营销活动后，您将通过选择 **[!UICONTROL Manage Members]** > **[!UICONTROL Add Members]** > **[!UICONTROL Import Files]**.
1. 完成后，返回至Campaign页面布局，您将“启用买方接触点”（即选取列表字段）。 选择值： **[!UICONTROL Include All Campaign Members]**.

完成此操作后，将在 [!DNL Marketo Measure] 和 [!DNL Salesforce] 并将接触点应用于潜在客户记录。 建议第二天通过名为：在 [!UICONTROL Buyer Touchpoints Reports] 文件夹。 如果报表为每个潜在客户填充接触点，则表示成功。
