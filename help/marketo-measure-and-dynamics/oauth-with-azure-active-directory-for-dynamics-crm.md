---
description: Dynamics CRM的OAuth与 [!DNL Azure Active Directory]  - [!DNL Marketo Measure]
title: 'Dynamics CRM的OAuth与 [!DNL Azure Active Directory] '
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
feature: Microsoft Dynamics
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 0%

---


# Dynamics CRM的OAuth与[!DNL Azure Active Directory] {#oauth-with-azure-active-directory-for-dynamics-crm}

## 受影响的人员 {#who-s-affected}

此设置适用于使用Dynamics CRM和[!DNL Marketo Measure] (AAD)帐户的新[!DNL Azure Active Directory]客户，或者适用于希望使用OAuth从其旧用户名和密码迁移到[!DNL Azure Active Directory]的客户。

>[!NOTE]
>对于这两种情况，此处都设置了AAD以便于在[!DNL Marketo Measure]中作为数据提供程序连接Dynamics实例。

## 设置新应用程序 {#set-up-new-application}

1. 登录到您的[Azure门户](https://portal.azure.com/#home)。

1. 单击页面右上角的帐户，然后单击“切换目录”导航，然后选择相应的租户，以选择Azure AD租户。 如果您的帐户下只有一个Azure AD租户，或者您已选择适当的Azure AD租户，请跳过此步骤。

   ![Azure门户租户选择下拉菜单](assets/setup-2.png)

1. 在搜索栏中搜索“[!DNL Azure Active Directory]”，然后单击要打开的名称。

   ![显示Azure Active Directory的Azure门户搜索结果](assets/setup-3.png)

1. 单击左侧菜单中的&#x200B;**[!UICONTROL App Registrations]**。

   带有应用程序注册的![Azure Active Directory导航菜单](assets/setup-4.png)

1. 单击顶部的&#x200B;**[!UICONTROL New Registration]**。

   ![包含“新注册”按钮的“应用程序注册”页面](assets/setup-5.png)

1. 按照提示创建应用程序。 它是Web应用程序还是公共客户端（移动和桌面）应用程序并不重要，但如果您想查看有关Web应用程序或公共客户端应用程序的特定示例，请查看[快速入门](https://learn.microsoft.com/en-us/azure/active-directory/develop/v2-overview)。\
   a. Name是应用程序名称，它向最终用户描述您的应用程序。\
   b.在“支持的帐户类型”下，选择任何组织目录中的帐户和个人Microsoft帐户。\
   c.提供重定向URI。 对于Web应用程序，这是用户可以登录的应用程序基本URL。 例如：`http://localhost:12345`。对于公共客户端（移动和桌面），Azure AD使用它返回令牌响应。 输入特定于您的应用程序的值。 例如：`http://MyFirstAADApp`。

1. 完成注册后，Azure AD将为应用程序分配唯一的客户端标识符（应用程序ID）。 您需要在下一节中使用此值，因此请从应用程序页面中复制此值。

1. 若要在Azure门户中找到您的应用程序，请单击&#x200B;**[!UICONTROL App Registrations]**，然后单击&#x200B;**[!UICONTROL All Applications]**。 打开新创建的应用程序

1. 单击左侧菜单中的&#x200B;**[!UICONTROL Authentication]**。

   ![突出显示身份验证选项的“应用程序”菜单](assets/setup-9.png)

1. 将[!DNL Marketo Measure]重定向URL： `https://apps.bizible.com/OAuth2`和`https://apps.bizible.com/OAuth2?identityOnly=true`添加到重定向URL列表中。

   ![身份验证设置显示Marketo Measure重定向URL](assets/setup-10.png)

1. 导航到API权限选项卡，并确保为应用程序分配了正确的权限。

   ![API权限选项卡显示分配的权限](assets/setup-10a.png)

1. 从此处，在搜索框中输入“[!UICONTROL enterprise]”，然后单击&#x200B;**[!UICONTROL Enterprise Applications]**。

   显示企业应用程序的![Azure门户搜索](assets/setup-11.png)

1. 再次从应用程序列表中查找并打开您的新应用程序。

1. 在“权限”选项卡中，单击&#x200B;**[!UICONTROL Grant Admin Consent for (instance name)]**。

   ![包含“授予管理员同意”按钮的“权限”选项卡](assets/setup-13a.png)

1. 单击 **[!UICONTROL Accept]**。

   ![带有“接受”按钮的管理员同意确认对话框](assets/setup-13b.png)

1. 在“[!UICONTROL Users and Groups]”选项卡中，确保将有效的“用户和组”分配给应用程序。

   ![显示已分配用户的“用户和组”选项卡](assets/setup-14.png)

## 创建应用程序用户 {#creating-an-application-user}

完成应用程序注册后，即可创建应用程序用户。

1. 导航到您的Common Data Service环境(`https://[org].crm.dynamics.com`)。

1. 导航到&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Users]**。

1. 在视图筛选器中选择&#x200B;**[!UICONTROL Application Users]**。

1. 选择&#x200B;**[!UICONTROL + New]**。

1. 在“应用程序用户”窗体中，输入所需的信息。

   >[!NOTE]
   > 用户名信息不能与[!DNL Azure Active Directory]中存在的用户匹配。
   > 在应用程序ID字段中，输入之前在Azure AD中注册的应用程序的应用程序ID。

1. 如果设置正确，则在选择&#x200B;**[!UICONTROL Save]**&#x200B;后，**[!UICONTROL Application ID URI]**&#x200B;和&#x200B;**[!UICONTROL Azure AD Object Id]**&#x200B;字段将自动填充正确的值。

1. 在退出用户表单之前，请选择&#x200B;**[!UICONTROL Manage Roles]**&#x200B;并为该应用程序用户分配安全角色，以便该应用程序用户能够访问所需的组织数据。

## 通过OAuth连接您的Dynamics实例 {#connecting-your-dynamics-instance-via-oAuth}

1. 首次设置Dynamics连接时，请按照[本文](/help/marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md)中“CRM as a Data Provider”部分的步骤1-5操作。

1. 在系统提示输入OAuth凭据时，填写上节中设置的客户端ID、客户端密钥和应用程序ID URI。

a.客户端ID是上一节中步骤#7中的ID。 如果您未记下该变量，则应用程序ID将显示在应用程序注册的设置中。

b.客户端密码是在Azure门户中为您的应用程序在“证书和密码”下创建的应用程序密码。

![显示客户端密钥值的“证书和密钥”页](assets/creating-2e.png)

c.应用程序ID URI是目标Web API（安全资源）的URL。 要查找应用程序ID URL，请在Azure Portal中，单击[!DNL Azure Active Directory]，单击应用程序注册，打开应用程序的“设置”页面，然后单击“属性”。 它也可以是外部资源，如`https://graph.microsoft.com`。 这通常是Dynamics实例的URL。

1. 单击&#x200B;**[!UICONTROL Submit]**&#x200B;后，系统将提示您使用[!DNL Azure Active Directory]登录。 身份验证成功后，你的Dynamics帐户将作为[!DNL Marketo Measure]中的数据提供程序进行连接。

## 重新验证您的Dynamics帐户 {#re-authenticating-your-dynamics-account}

1. 当您在[!DNL Marketo Measure]应用程序中时，转到&#x200B;**[!UICONTROL My Settings]** > **[!UICONTROL Settings]** > **[!UICONTROL Connections]**。

1. 单击Dynamics连接旁边CRM部分中的键图标。

1. 单击密钥后，会出现一个弹出窗口，提示您输入客户端ID、客户端密钥和应用程序ID URI，类似于注册流程。

   ![使用OAuth凭据字段重新身份验证对话框](assets/re-authenticating-3.png)

1. 单击&#x200B;**[!UICONTROL Submit]**&#x200B;后，系统将提示您使用[!DNL Azure Active Directory]登录。 身份验证成功后，您的Dynamics帐户将在[!DNL Marketo Measure]内重新获得授权。
