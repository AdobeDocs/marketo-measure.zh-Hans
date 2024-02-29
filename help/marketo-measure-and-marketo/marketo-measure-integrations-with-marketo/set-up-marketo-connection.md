---
unique-page-id: 42762762
description: 设置Marketo连接 —  [!DNL Marketo Measure]
title: 设置Marketo连接
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 1%

---

# 设置Marketo连接 {#set-up-marketo-connection}

下面是如何设置与Marketo的连接。

>[!PREREQUISITES]
>
>[创建仅API用户角色](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html) 对于 [!DNL Marketo Measure]/Marketo Engage连接。

1. 在 [!DNL Marketo Measure]，单击 **[!UICONTROL My Account]** 下拉并选择 **[!UICONTROL Settings]**.

   ![](assets/set-up-marketo-connection-1.png)

1. 下 [!UICONTROL Integrations]，单击 **[!UICONTROL Connections]**.

   ![](assets/set-up-marketo-connection-2.png)

1. 单击 **[!UICONTROL Set Up New CRM Connection]**.

   ![](assets/set-up-marketo-connection-3.png)

1. 单击 **[!UICONTROL Connect]** Marketo按钮。

   ![](assets/set-up-marketo-connection-4.png)

1. 在新选项卡中，登录到您的Marketo Engage帐户。 转到 **管理员** > **Web服务**. 向下滚动到REST API。 突出显示并保存端点和Identity服务URL。 你马上就需要。

   ![](assets/set-up-marketo-connection-5.png)

1. 仍在Marketo Engage中，选择 **启动点** 在左边的树上。 找到要连接到Marketo Measure的自定义服务，然后单击 **查看详细信息**.

   ![](assets/set-up-marketo-connection-6.png)

1. 突出显示并保存客户端ID和客户端密码。 单击&#x200B;**关闭**。

   ![](assets/set-up-marketo-connection-7.png)

1. 返回 [!DNL Marketo Measure]，使用您刚刚收集的数据填充字段。

   ![](assets/set-up-marketo-connection-8.png)

1. 输入值后，单击 **[!UICONTROL Authenticate]**. 然后，您的Marketo Engage帐户将连接到 [!DNL Marketo Measure].

   ![](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] 将代表您调用Marketo API，而不使用任何Marketo API限制，因此无需担心与其他集成的大小和信用分配。
