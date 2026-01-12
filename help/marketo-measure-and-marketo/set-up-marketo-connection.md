---
description: 设置Marketo连接 —  [!DNL Marketo Measure]
title: 设置Marketo连接
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 1%

---


# 设置Marketo连接 {#set-up-marketo-connection}

下面是如何设置与Marketo的连接。

>[!PREREQUISITES]
>
>[为](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html){target="_blank"}/Marketo Engage连接创建仅API用户角色[!DNL Marketo Measure]。

1. 在[!DNL Marketo Measure]中，单击&#x200B;**[!UICONTROL My Account]**&#x200B;下拉菜单并选择&#x200B;**[!UICONTROL Settings]**。

   ![Marketo Measure我的帐户下拉列表，带有设置选项](assets/set-up-marketo-connection-1.png)

1. 在[!UICONTROL Integrations]下，单击&#x200B;**[!UICONTROL Connections]**。

   ![带有“连接”选项的“集成”菜单](assets/set-up-marketo-connection-2.png)

1. 单击 **[!UICONTROL Set Up New CRM Connection]**。

   ![设置新CRM连接按钮](assets/set-up-marketo-connection-3.png)

1. 单击Marketo旁边的&#x200B;**[!UICONTROL Connect]**&#x200B;按钮。

   Marketo集成选项旁边的![连接按钮](assets/set-up-marketo-connection-4.png)

1. 在新选项卡中，登录到您的Marketo Engage帐户。 转到&#x200B;**管理员** > **Web服务**。 向下滚动到REST API。 突出显示并保存端点和Identity服务URL。 您需要在以下步骤中使用它们。

   ![显示REST API端点和标识URL的Marketo Web服务页面](assets/set-up-marketo-connection-5.png)

1. 仍在Marketo Engage中，在左侧的树中选择&#x200B;**LaunchPoint**。 查找要连接到Marketo Measure的自定义服务，然后单击&#x200B;**查看详细信息**。

   带有自定义服务和查看详细信息选项的![LaunchPoint菜单](assets/set-up-marketo-connection-6.png)

1. 突出显示并保存客户端ID和客户端密码。 单击&#x200B;**关闭**。

   ![LaunchPoint服务详细信息显示客户端ID和客户端密钥](assets/set-up-marketo-connection-7.png)

1. 返回[!DNL Marketo Measure]，使用您收集的数据填充这些字段。

   ![带有终结点和凭据字段的Marketo连接表单](assets/set-up-marketo-connection-8.png)

1. 输入值后，单击&#x200B;**[!UICONTROL Authenticate]**。 您的Marketo Engage帐户已连接到[!DNL Marketo Measure]。

   ![成功的Marketo连接确认消息](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >[!DNL Marketo Measure]代表您调用Marketo API而不占用任何Marketo API限制，因此无需担心上限和与其他集成的信用分配。
