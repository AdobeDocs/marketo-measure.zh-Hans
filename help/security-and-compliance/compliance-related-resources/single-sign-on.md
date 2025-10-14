---
unique-page-id: 18874761
description: 单点登录 —  [!DNL Marketo Measure]
title: 单点登录
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '1257'
ht-degree: 0%

---

# 单点登录 {#single-sign-on}

SSO（单点登录）的SAML（安全断言标记语言）允许用户在登录到[!DNL Marketo Measure]应用程序时通过公司的身份提供程序进行身份验证。 SSO允许用户进行一次身份验证，而无需单独验证应用程序。 企业客户必须使用SAML，因为并非所有用户在其组织内都有[!DNL Salesforce]或[!DNL Google]帐户。 为了扩展，[!DNL Marketo Measure]开发了一个可以支持公司身份提供商的SAML解决方案。

>[!CAUTION]
>
>本文概述了单点登录(SSO)和高级CRM用户管理。 如果您的帐户是在2020年9月10日&#x200B;**之后配置的**，请忽略本文，因为将在[Adobe Admin Console中为您的 [!DNL Marketo Measure] 集成](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md)设置SSO和Identity Management。

>[!NOTE]
>
>公司可能使用不同的身份提供程序（例如，Ping Identity、Okta）。 以下设置说明和UI中使用的术语可能与您的身份提供程序使用的术语不直接匹配。

## 要求 {#requirements}

* 在[!DNL Marketo Measure]应用程序中具有AccountAdmin权限的用户
* 对客户的身份提供程序具有管理访问权限的用户

## 快速入门 {#getting-started}

要开始操作，请在[!DNL Marketo Measure]应用程序中导航到“设置”>“安全”>“身份验证”页面。 然后将登录类型切换到自定义SSO以查看配置选项。 在您测试身份验证并单击页面底部的&#x200B;**[!UICONTROL Save]**&#x200B;按钮之前，更改将不会生效。

![](assets/single-sign-on-1.png)

## 进程 {#process}

[!DNL Marketo Measure]单点登录需要通过一系列步骤来配置您的身份验证设置，这样您就不会有被锁定在[!DNL Marketo Measure]帐户之外的风险。

在身份提供程序中设置[!DNL Marketo Measure]应用程序。 有关演练，请参阅下面列出的外部文档。

    a。当提示输入单点登录URL或收件人URL或目标URL、SAML Assertion Customer Service (ACS) URL时，请使用[https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest](https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)
    
    b。当提示输入受众限制URL或应用程序定义的唯一标识符时，请使用[https://BizibleLPM](https://biziblelpm/)

在[!DNL Marketo Measure]应用程序中切换到自定义SSO

    a。为您的帐户启用计费组后，您现在可以导航到[!UICONTROL Settings] >>[!UICONTROL Security] >> [!UICONTROL Authentication]
    
    b。默认情况下，您的登录类型将设置为“CRM用户”。
    
    c。将登录类型切换为“自定义SSO”以开始配置过程。

填写身份提供程序配置的连接设置

    a。您的身份提供程序可能会提供IdP元数据.xml文档，该文档将提取所需的配置字段。 加载到.xml文档的内容中，或从身份提供程序配置过程中获得的输出中填写以下三个字段。 **您不需要同时完成这两项。**
    
    i。IdP URL： [!DNL Marketo Measure] 需要指向的URL以向 [!DNL Marketo Measure] 应用程序验证您的用户。 有时称为“重定向URL”。
    ii。 IdP颁发者：身份提供程序的唯一标识符。 有时称为“外部密钥”。
    iii。 IdP证书：一个公钥，它允许 [!DNL Marketo Measure] 验证和验证所有身份提供程序响应的签名。

设置用户的令牌过期时间（分钟）。

    a. [!DNL Marketo Measure] 允许1到1440分钟的整数。 超过用户的会话时间后，用户一旦导航到新页面，将被注销。

设置用户属性设置并将其映射到各自的名字、姓氏和电子邮件地址。

    a。通过输入SAML属性， [!DNL Marketo Measure] 将能够通过传递的信息识别您的用户。
    
    i。电子邮件属性：提供您的身份提供方用于用户电子邮件地址的属性名称。
    ii。 名字属性：提供您的身份提供方用于用户名字的属性名称。
    iii。 姓氏属性：提供您的身份提供方用于用户姓氏的属性名称。
    
    b。提示：如果您现在测试您的SAML配置，我们将解析可用于此节的电子邮件、名字和姓氏属性。

![](assets/single-sign-on-2.png)

设置用户角色设置，并将其映射到从IdP分类的各个角色或组。

    a。客户可以选择根据在其身份提供程序中定义的组分配 [!DNL Marketo Measure] 用户角色。 通过输入SAML属性， [!DNL Marketo Measure] 能够将用户的角色和组映射到 [!DNL Marketo Measure] 用户权限。 我们强烈建议您设置这些角色，以便 [!DNL Marketo Measure] 管理员有足够的权限来更新您的帐户。
    
    b。如果未映射任何角色或组，则默认设置是身份提供者中的所有员工都将具有标准用户访问权限。
    
    i. [!DNL Marketo Measure] 标准用户：为应该对 [!DNL Marketo Measure] 应用程序具有只读访问权限的用户提供角色或组值（来自您的SSO提供商）。
    ii。 [!DNL Marketo Measure] 帐户管理员用户：为应具有 [!DNL Marketo Measure] 应用程序管理访问权限的用户提供角色或组值（来自您的SSO提供商）。 这意味着该角色有权更改与您的帐户相关的配置和设置。
    iii。 您在IdP中必须具有一个属性，该属性具有用于“Bizible Standard User”或“Bizible Account Admin User”属性中放置值的确切名称“groups”。
    
    c。如果应将多个角色或组映射到某个角色，请输入用逗号分隔的每个值。

![](assets/single-sign-on-3.png)

测试单点登录配置

    a。在点击“保存”之前，您需要单击[!UICONTROL Test SAML Authentication]按钮以验证您的设置是否已正确配置。
    
    b。如果您看到“失败”错误，请按照消息操作并重试。

![](assets/single-sign-on-4.png)

保存您的设置并指示您的同事将[!UICONTROL Single Sign On]与新的自定义登录URL一起使用。

    a。重要信息：保存新的身份验证设置后，由于您已禁用CRM用户的登录并启用自定义SSO，因此在导航到新页面后，会话可能会结束。

![](assets/single-sign-on-5.png)

试试看！

    a。使用新的自定义登录URL，并尝试使用您的身份提供程序凭据重新登录到 [!DNL Marketo Measure] 应用程序。
    
    b。格式将类似于“https://apps.adobe.com/business/[accountName]”
    
    c。恭喜！ 您已成功为帐户设置 [!DNL Marketo Measure] 应用程序的单点登录！

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>配置SSO后，您将不再需要在[!DNL Marketo Measure]应用程序中添加用户。 应直接在身份提供程序中处理用户设置。

## CRM用户（高级设置） {#crm-users-advanced-setup}

默认情况下，所有帐户都可以使用其CRM凭据访问[!DNL Marketo Measure]应用程序。 有时，帐户所有者需要限制对某些角色的访问，而不是将其开放给具有活动CRM许可证的所有用户。 高级设置允许您将CRM角色和组映射到[!DNL Marketo Measure]用户权限。

如果未映射任何角色或组，则默认设置是CRM中的所有活动许可证都具有“标准”用户访问权限。

* [!DNL Marketo Measure]标准用户：为应该对[!DNL Marketo Measure]应用程序具有只读访问权限的用户提供角色或组值。
* [!DNL Marketo Measure]帐户管理员用户：为应具有对[!DNL Marketo Measure]应用程序的管理访问权限的用户提供角色或组值。 这意味着该角色有权更改与您的帐户相关的配置和设置。

如果应将多个角色或组映射到某个角色，请输入用逗号分隔的每个值。

**Salesforce角色**

对于[!DNL Salesforce]角色，请使用每个角色的名称。 可在[!UICONTROL Setup] >[!UICONTROL Manage Users] >[!UICONTROL Roles]菜单下找到所有角色。

![](assets/6.png)

**动态角色**

对于[!DNL Dynamics]角色，请使用每个安全角色的名称。 可在[!UICONTROL Settings] >[!UICONTROL Security] >[!UICONTROL Security Roles]菜单下找到所有安全角色。

![](assets/7.png)

![](assets/8.png)

**Google用户**

设置自定义SSO后，[!UICONTROL Users]页面将更新，以仅显示已添加了Google登录的外部用户。 由于所有具有访问权限的用户都是通过SSO配置定义的，因此此处列出了其他外部用户。

![](assets/9.png)

只能添加有效的[!DNL Google]帐户，并且必须定义用户角色。

## 外部链接 {#external-links}

* [Okta](https://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Ping身份](https://docs.pingidentity.com:443/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](https://onelogin.service-now.com/support?id=kb_article&sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
