---
unique-page-id: 37357059
description: OAuth替换为 [!DNL Azure Active Directory] 对于Dynamics CRM - [!DNL Marketo Measure]
title: OAuth替换为 [!DNL Azure Active Directory] 适用于Dynamics CRM的
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
feature: Microsoft Dynamics
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 0%

---

# OAuth替换为 [!DNL Azure Active Directory] 适用于Dynamics CRM的 {#oauth-with-azure-active-directory-for-dynamics-crm}

## 受影响的人员 {#who-s-affected}

此设置适用于新用户 [!DNL Marketo Measure] 客户结合使用Dynamics CRM [!DNL Azure Active Directory] (AAD)帐户或适用于要从旧版用户名和密码迁移到的客户 [!DNL Azure Active Directory] 使用OAuth。

>[!NOTE]
>
>对于这两种情况，此处都设置了AAD以便于在中连接您的Dynamics实例 [!DNL Marketo Measure] 作为数据提供程序。

## 设置新应用程序 {#set-up-new-application}

1. 登录到您的 [Azure门户](https://portal.azure.com/#home).

1. 单击页面右上角的帐户，然后单击“切换目录”导航，然后选择相应的租户，以选择Azure AD租户。 如果您的帐户下只有一个Azure AD租户，或者您已选择适当的Azure AD租户，请跳过此步骤。

   ![](assets/setup-2.png)

1. 搜索&quot;[!DNL Azure Active Directory]”并单击名称以打开。

   ![](assets/setup-3.png)

1. 单击 **[!UICONTROL App Registrations]** 在左侧菜单中。

   ![](assets/setup-4.png)

1. 单击 **[!UICONTROL New Registration]** 在顶端。

   ![](assets/setup-5.png)

1. 按照提示创建应用程序。 这无论是Web应用程序还是公共客户端（移动设备和桌面）应用程序，但是如果您想查看Web应用程序或公共客户端应用程序的特定示例，请查看 [快速启动](https://learn.microsoft.com/en-us/azure/active-directory/develop/v2-overview).\
   a. Name是应用程序名称，它向最终用户描述您的应用程序。\
   b.在“支持的帐户类型”下，选择任何组织目录中的帐户和个人Microsoft帐户。\
   c.提供重定向URI。 对于Web应用程序，这是用户可以登录的应用程序基本URL。 例如， `http://localhost:12345`. 对于公共客户端（移动和桌面），Azure AD使用它返回令牌响应。 输入特定于您的应用程序的值。 例如， `http://MyFirstAADApp`.

1. 完成注册后，Azure AD将为应用程序分配唯一的客户端标识符（应用程序ID）。 您需要在下一节中使用此值，因此请从应用程序页面中复制此值。

1. 要在Azure门户中找到您的应用程序，请单击 **[!UICONTROL App Registrations]**，然后单击 **[!UICONTROL All Applications]**. 打开新创建的应用程序

1. 单击 **[!UICONTROL Authentication]** 在左侧菜单中。

   ![](assets/setup-9.png)

1. 添加 [!DNL Marketo Measure] 重定向URL： `https://apps.bizible.com/OAuth2` 和 `https://apps.bizible.com/OAuth2?identityOnly=true` 到重定向URL列表。

   ![](assets/setup-10.png)

1. 导航到API权限选项卡，并确保为应用程序分配了正确的权限。

   ![](assets/setup-10a.png)

1. 从此处输入&quot;[!UICONTROL enterprise]”并单击 **[!UICONTROL Enterprise Applications]**.

   ![](assets/setup-11.png)

1. 再次从应用程序列表中查找并打开您的新应用程序。

1. 在“权限”选项卡中，单击 **[!UICONTROL Grant Admin Consent for (instance name)]**.

   ![](assets/setup-13a.png)

1. 单击 **[!UICONTROL Accept]**.

   ![](assets/setup-13b.png)

1. 从&quot;[!UICONTROL Users and Groups]”选项卡，确保将有效的“用户和组”分配给应用程序。

   ![](assets/setup-14.png)

## 创建应用程序用户 {#creating-an-application-user}

完成应用程序注册后，即可创建应用程序用户。

1. 导航到您的Common Data Service环境(`https://[org].crm.dynamics.com`)。

1. 导航到 **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Users]**.

1. 选择 **[!UICONTROL Application Users]** 在视图筛选器中。

1. 选择 **[!UICONTROL + New]**.

1. 在“应用程序用户”窗体中，输入所需的信息。

   >[!NOTE]
   >
   >* 用户名信息不得与中存在的用户匹配 [!DNL Azure Active Directory].
   >
   >* 在应用程序ID字段中，输入之前在Azure AD中注册的应用程序的应用程序ID。

1. 如果设置正确，则在选择 **[!UICONTROL Save]**， **[!UICONTROL Application ID URI]** 和 **[!UICONTROL Azure AD Object Id]** 字段将自动填充正确的值。

1. 退出用户表单前，选择 **[!UICONTROL Manage Roles]** 并为该应用程序用户分配安全角色，以便该应用程序用户能够访问所需的组织数据。

## 通过OAuth连接您的Dynamics实例 {#connecting-your-dynamics-instance-via-oAuth}

1. 首次设置Dynamics连接时，请按照中的“CRM as a Data Provider”部分的步骤1-5操作。 [本文](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

1. 在系统提示输入OAuth凭据时，填写上节中设置的客户端ID、客户端密钥和应用程序ID URI。

a.客户端ID是上一节中步骤#7中的ID。 如果您未记下该变量，则应用程序ID将显示在应用程序注册的设置中。

b.客户端密码是在Azure门户中为您的应用程序在“证书和密码”下创建的应用程序密码。

![](assets/creating-2e.png)

c.应用程序ID URI是目标Web API（安全资源）的URL。 要查找应用程序ID URL，请在Azure Portal中单击 [!DNL Azure Active Directory]，单击应用程序注册，打开应用程序的设置页面，然后单击属性。 它也可以是类似于的外部资源 `https://graph.microsoft.com`. 这通常是Dynamics实例的URL。

1. 单击之后 **[!UICONTROL Submit]**，系统将提示您使用 [!DNL Azure Active Directory]. 身份验证成功后，您的Dynamics帐户将作为数据提供程序连接到 [!DNL Marketo Measure].

## 重新验证您的Dynamics帐户 {#re-authenticating-your-dynamics-account}

1. 当您在 [!DNL Marketo Measure] 应用程序，转到 **[!UICONTROL My Settings]** > **[!UICONTROL Settings]** > **[!UICONTROL Connections]**.

1. 单击Dynamics连接旁边CRM部分中的键图标。

1. 单击密钥后，会出现一个弹出窗口，提示您输入客户端ID、客户端密钥和应用程序ID URI，类似于注册流程。

   ![](assets/re-authenticating-3.png)

1. 单击之后 **[!UICONTROL Submit]**，系统将提示您使用 [!DNL Azure Active Directory]. 身份验证成功后，您的Dynamics帐户将在 [!DNL Marketo Measure].
