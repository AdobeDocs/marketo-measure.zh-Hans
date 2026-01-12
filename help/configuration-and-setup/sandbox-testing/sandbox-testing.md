---
description: 测试Marketo Measure与Salesforce沙盒的集成 —  [!DNL Marketo Measure]
title: 测试Marketo Measure与Salesforce沙盒的集成
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 1%

---


# 测试Marketo Measure与Salesforce沙盒的集成 {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

[!DNL Marketo Measure]核心功能之一是，它能够通过网站上的操作跟踪您的数字营销工作，然后通过潜在客户和联系人将该数据推送到您的生产环境[!DNL Salesforce org]。 但是，通常，在沙盒集成中不会从您的网站创建入站潜在客户，因此对数据的关注将从纯粹离线角度进行。

以下是测试两个阶段中引用的两个源。 [步骤1-4](https://help.salesforce.com/s/articleView?id=lead_import_wizard.htm&language=en_US&type=5)和[步骤5-6](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)。 建议审查这些文件，因为它们在某些方面提供了更多细节。

1. 您需要在CSV中创建一些潜在客户，以便将其上传到Campaign。 这样做的方法是通过生产Salesforce中的报告导出一些潜在客户。 否则，您可以在Excel文件中手动创建潜在客户，然后将其保存为CSV以供导入。 你只需要大约20条记录。 该文件必须具有以下列：

   1. 电子邮件
   1. 公司
   1. 姓氏
   1. 名字（可选，但推荐）

1. 登录到您的Sandbox环境。
1. 创建测试营销活动。 使用活动类型，如事件或新闻稿。
1. 创建营销活动后，通过选择&#x200B;**[!UICONTROL Manage Members]** > **[!UICONTROL Add Members]** > **[!UICONTROL Import Files]**，将潜在客户上传为营销活动成员。
1. 完成该步骤后，返回活动页面布局，您将看到一个选择列表字段，即“启用买方接触点”。 选择值： **[!UICONTROL Include All Campaign Members]**。

完成此操作后，它将启动[!DNL Marketo Measure]和[!DNL Salesforce]之间的同步，并将接触点应用于Lead记录。 建议第二天通过在“报表”选项卡的[!UICONTROL Buyer Touchpoints Reports]文件夹中找到的名为“潜在客户的Buyer Touchpoint”的报表查看。 如果报告填充了每个Lead的接触点，则表示取得了成功。
