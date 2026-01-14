---
description: 面向Marketo Measure用户的电子邮件跟踪参数指南
title: 电子邮件跟踪参数
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 2%

---

# 电子邮件跟踪参数 {#email-tracking-parameter}

[!DNL Marketo Measure]电子邮件跟踪参数允许营销人员将电子邮件点击视为表单提交，以便生成这些操作的接触点。 在不使用电子邮件跟踪参数的情况下，电子邮件中的点进次数仅被视为“Web访问”，直到用户通过表单提交或Web聊天实际参与网站活动为止。

## 用例  {#use-cases}

**网络研讨会注册**：营销团队发送电子邮件邀请函，只需按一下按钮即可注册网络研讨会。 由于电子邮件已包含用户信息，因此一键单击会自动注册这些信息。 登陆页面包含电子邮件跟踪参数，因此当登陆用户点进并登陆确认页面时，[!DNL Marketo Measure]可以捕获电子邮件地址，并将点进视为表单填充，这将生成接触点。

**内容下载**：内容营销团队希望通过电子邮件中的直接下载链接来推广他们最近发布的电子书。 生成电子邮件模板后，下载确认页面包含电子邮件跟踪参数，以便用户点进时，[!DNL Marketo Measure]可以捕获电子邮件地址。 无需填写网站上的表单，[!DNL Marketo Measure]可以为内容下载生成接触点。 这是因为电子邮件使用电子邮件跟踪参数将它们定位到确认页面。

## 工作原理 {#how-it-works}

当访客访问您的网站时，[!DNL Marketo Measure]期望找到具有电子邮件地址或[!DNL Salesforce] ID的登陆页面，以便我们可以将该访问与“表单提交”关联并为该活动生成接触点。

作为客户，您可以像往常一样构建电子邮件模板。 在需要为要跟踪的操作添加登陆页面后，您必须确定令牌、变量标记或宏，营销自动化平台可以接受这些标记或宏以动态显示每个人的值。

Marketo Measure接受以下值：电子邮件地址、Salesforce潜在客户Id或Salesforce联系人Id。

## 标记示例 {#tag-examples}

| 营销自动化 | 令牌/标记/宏 | 示例 | 支持材料 |
| --- | --- | --- | --- |
| Marketo | {{lead.Email Address}} | <https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}> | [令牌概述](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/personalizing-landing-pages/tokens-overview.html?lang=zh-Hans) |
| 帕尔多 | %%email%%或%%user_crm_id%% | <https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%> | [Pardot变量标记引用](https://help.salesforce.com/s/articleView?language=en_US&id=pardot_variable_tags_reference.htm&type=5) |
| Hubspot | （通过编辑器插入） | 不适用 | [HubSpot个性化内容](https://knowledge.hubspot.com/website-pages/personalize-your-content) |
| 操作 | （通过消息编辑器插入） | 不适用 | [实际操作个性化电子邮件内容](https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data) |

最后，在[!DNL Marketo Measure]中，必须指定跟踪参数，以便[!DNL Marketo Measure]能够找到电子邮件或ID值。 默认值为“mailId”，如上面的示例和下面的屏幕快照所示。 在[!DNL Marketo Measure]的设置中输入值，然后单击&#x200B;**[!UICONTROL Save]**。

![](assets/one-one-1.png)
