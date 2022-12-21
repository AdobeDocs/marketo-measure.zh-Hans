---
unique-page-id: 18874761
description: 单点登录 —  [!DNL Marketo Measure]  — 产品文档
title: 单点登录
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 0%

---

# 单点登录 {#single-sign-on}

SSO（单点登录）的SAML（安全断言标记语言）使用户在登录到 [!DNL Marketo Measure] 应用程序。 SSO允许用户仅进行一次身份验证，而无需对单独的应用程序进行身份验证。 SAML是企业客户的必需工具，因为并非所有用户都具有 [!DNL Salesforce] 或 [!DNL Google] 帐户。 为了扩展， [!DNL Marketo Measure] 开发了可支持公司标识提供程序的SAML解决方案。

>[!CAUTION]
>
>本文概述了单点登录(SSO)和高级CRM用户管理。 如果您的帐户已配置 **之后9/10/2020**，请忽略本文，因为SSO和Identity Management将在 [Adobe Admin Console [!DNL Marketo Measure] 集成](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md).

>[!NOTE]
>
>公司可能使用不同的身份提供程序（例如Ping Identity、Okta）。 以下设置说明和UI中使用的术语可能与身份提供者使用的术语不匹配。

## 要求 {#requirements}

* 在 [!DNL Marketo Measure] 应用程序
* 具有客户身份提供者管理访问权限的用户

## 快速入门 {#getting-started}

要开始配置，请导航至 [!DNL Marketo Measure] 应用程序。 然后，将登录类型切换为自定义SSO以查看配置选项。 所做的更改在您测试身份验证并单击 **[!UICONTROL Save]** 按钮。

![](assets/single-sign-on-1.png)

## 进程 {#process}

[!DNL Marketo Measure] 单点登录需要通过一系列非常重要的步骤来配置身份验证设置，这样您就不会面临被锁定在外部的风险 [!DNL Marketo Measure] 帐户。

设置 [!DNL Marketo Measure] 身份提供程序中的应用程序。 请参阅下面列出的外部文档，以了解演练。

    a.当提示输入单点登录URL、收件人URL或目标URL、SAML断言客户服务(ACS)URL时，请使用[https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest](https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)
    
    b.在提示输入受众限制URL或应用程序定义的唯一标识符时，请使用[https://BizibleLPM](https://biziblelpm/)

在 [!DNL Marketo Measure] 应用程序

    a.为您的帐户启用账单组后，您现在可以导航到 [!UICONTROL Settings] >>[!UICONTROL Security] >> [!UICONTROL Authentication]
    
    b.默认情况下，您的登录类型将设置为“CRM用户”。
    
    c.将登录类型切换为“自定义SSO”以开始配置过程。

填写身份提供程序配置的连接设置

    a.您的身份提供程序可能会提供一个IdP元数据.xml文档，该文档将提取所需的配置字段。 在.xml文档的内容中加载，或从在身份提供程序配置过程中获得的输出中填写以下三个字段。 **您无需同时完成这两项操作。**
    
    i.IdP URL:URL [!DNL Marketo Measure] 需要指向，以便在 [!DNL Marketo Measure] 应用程序。 有时称为“重定向URL”。
    ii. IdP颁发者：身份提供程序的唯一标识符。 有时称为“外部密钥”。
    三。 IdP证书：允许 [!DNL Marketo Measure] 来验证和验证所有身份提供程序响应的签名。

在几分钟内为用户设置令牌过期时间。

    a. [!DNL Marketo Measure] 允许1到1440分钟之间的整数。 超过用户的会话时间后，用户在导航到新页面后将被注销。

设置用户属性设置并将其映射到相应的名字、姓氏和电子邮件地址。

    a.通过输入SAML属性， [!DNL Marketo Measure] 将能够通过传递的信息识别您的用户。
    
    i.电子邮件属性：提供身份提供者用于用户电子邮件地址的属性名称。
    ii. 名字属性：提供身份提供者用作用户名字的属性名称。
    三。 姓氏属性：提供身份提供者用作用户姓氏的属性名称。
    
    b.提示：如果您现在测试SAML配置，我们将解析可用于此部分的电子邮件、名字和姓氏属性。

![](assets/single-sign-on-2.png)

设置“用户角色”设置并将其映射到从您的IdP中分类的各个角色或组。

    a.客户可以选择分配 [!DNL Marketo Measure] 用户角色基于其身份提供程序中定义的组。 通过输入SAML属性， [!DNL Marketo Measure] 将能够将用户的角色和群组映射到 [!DNL Marketo Measure] 用户权限。 我们强烈建议您设置这些角色，以便 [!DNL Marketo Measure] 管理员拥有足够的权限来更新您的帐户。
    
    b.如果未映射角色或组，则默认设置是标识提供程序中的所有员工都将具有标准用户访问权限。
    
    i. [!DNL Marketo Measure] 标准用户：为应具有只读访问权限的用户提供角色或组值（来自您的SSO提供程序） [!DNL Marketo Measure] 应用程序。
    ii. [!DNL Marketo Measure] 帐户管理员用户：为应具有管理访问权限的用户提供角色或组值（来自您的SSO提供商） [!DNL Marketo Measure] 应用程序。 这意味着该角色有权更改与您的帐户相关的配置和设置。
    三。 您的IdP中必须具有一个具有“组”确切名称的属性，该属性将存储您放置在“Bizible Standard用户”或“Bizible帐户管理员用户”属性中的值。
    
    c.如果应将多个角色或组映射到某个角色，请输入以逗号分隔的每个值。

![](assets/single-sign-on-3.png)

测试单点登录配置

    a.在点击保存之前，您需要单击 [!UICONTROL Test SAML Authentication] 按钮来验证设置是否配置正确。
    
    b.如果看到“失败”错误，请按照该消息操作，然后再次尝试。

![](assets/single-sign-on-4.png)

保存设置并指示您的同事使用 [!UICONTROL Single Sign On] 使用您的新自定义登录URL。

    a.重要信息：保存新的身份验证设置后，在导航到新页面后，您的会话可能会结束，因为您已禁用CRM用户登录并启用了自定义单点登录。

![](assets/single-sign-on-5.png)

试试看！

    a.使用您新的自定义登录URL并尝试重新登录到 [!DNL Marketo Measure] 具有您的身份提供者凭据的应用程序。
    
    b.格式将类似于“https://apps.adobe.com/business/[accountName]”
    
    c.恭喜！ 您已成功在 [!DNL Marketo Measure] 您帐户的申请！

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>配置SSO后，您将不再需要在 [!DNL Marketo Measure] 应用程序。 用户配置应直接在您的身份提供程序中处理。

## CRM用户（高级设置） {#crm-users-advanced-setup}

默认情况下，所有帐户都可以访问 [!DNL Marketo Measure] 应用程序。 有时，帐户所有者需要限制对特定角色的访问，而不是使用活动CRM许可证将其打开给所有用户。 利用高级设置，可将CRM角色和群组映射到 [!DNL Marketo Measure] 用户权限。

如果未映射角色或组，则默认设置是CRM中所有活动的许可证都将具有标准用户访问权限。

* [!DNL Marketo Measure] 标准用户：为应具有只读访问权限的用户提供角色或组值 [!DNL Marketo Measure] 应用程序。
* [!DNL Marketo Measure] 帐户管理员用户：为应具有管理访问权限的用户提供角色或组值 [!DNL Marketo Measure] 应用程序。 这意味着该角色有权更改与您的帐户相关的配置和设置。

如果应将多个角色或组映射到某个角色，请输入以逗号分隔的每个值。

**Salesforce角色**

对于 [!DNL Salesforce] 角色，请使用每个角色的名称。 所有角色都可在 [!UICONTROL Setup] >[!UICONTROL Manage Users] >[!UICONTROL Roles] 菜单。

![](assets/6.png)

**Dynamics角色**

对于 [!DNL Dynamics] 角色，使用每个安全角色的名称。 所有安全角色都可在 [!UICONTROL Settings] >[!UICONTROL Security] >[!UICONTROL Security Roles] 菜单。

![](assets/7.png)

![](assets/8.png)

**Google用户**

设置自定义单点登录(SSO)后， [!UICONTROL Users] 页面将进行更新，以仅显示已添加了Google登录的外部用户。 由于所有具有访问权限的用户都通过SSO配置进行定义，因此此处列出了其他外部用户。

![](assets/9.png)

仅有效 [!DNL Google] 帐户可以添加，且必须定义用户角色。

## 外部链接 {#external-links}

* [奥克塔](http://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Ping标识](http://docs.pingidentity.com/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](http://onelogin.service-now.com/support?id=kb_article&amp;sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](http://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
