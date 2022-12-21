---
unique-page-id: 37356030
description: 电子邮件跟踪参数 —  [!DNL Marketo Measure]  — 产品文档
title: 电子邮件跟踪参数
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 1%

---

# 电子邮件跟踪参数 {#email-tracking-parameter}

的 [!DNL Marketo Measure] 电子邮件跟踪参数允许营销人员将电子邮件点击视为表单提交，以便为这些操作生成接触点。 如果不使用电子邮件跟踪参数，则来自电子邮件的点进次数仅会被视为“Web访问”，直到用户通过表单提交或网络聊天实际参与网站为止。

## 用例  {#use-cases}

**网络研讨会注册**:营销团队通过单个按钮发出电子邮件邀请，以注册网络研讨会。 由于电子邮件已包含人员信息，因此单击将自动注册这些信息。 登陆页面包含电子邮件跟踪参数，因此当他们点进并登陆确认页面时， [!DNL Marketo Measure] 可以捕获电子邮件地址并将点进视为表单填充，这将生成一个接触点。

**内容下载**:内容营销团队希望推广他们最近发布的一本带有电子邮件直接下载链接的电子书。 构建电子邮件模板后，下载确认页面将包含电子邮件跟踪参数，以便它们点进时， [!DNL Marketo Measure] 可以捕获电子邮件地址。 无需在网站上填写表格， [!DNL Marketo Measure] 可以为通过电子邮件下载的内容生成一个接触点，因为它使用电子邮件跟踪参数将内容下载登陆确认页面。

## 工作原理 {#how-it-works}

当访客到达您的网站时， [!DNL Marketo Measure] 希望找到带有电子邮件地址或 [!DNL Salesforce] ID，以便我们能够将该访问与“表单提交”关联，并为该活动生成一个接触点。

作为客户，您将像往常一样构建电子邮件模板。 在需要为要跟踪的操作在登陆页面中添加内容后，您将需要确定营销自动化平台接受的令牌、变量标记或宏，以便动态显示每个人的值。

Marketo测量接受以下值：电子邮件地址、Salesforce潜在客户ID或Salesforce联系人ID。

## 标记示例 {#tag-examples}

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p>营销自动化</p></th> 
   <th><p>令牌/标记/宏 </p></th> 
   <th><p>示例</p></th> 
   <th><p>支持材料</p></th> 
  </tr> 
  <tr> 
   <td><p>Marketo</p></td> 
   <td><p>{{lead.email Address}} </p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}</p></td> 
   <td><p>https://docs.marketo.com/display/public/DOCS/Tokens+Overview#TokensOverview-PersonTokens</p></td> 
  </tr> 
  <tr> 
   <td><p>帕多</p></td> 
   <td><p>%%电子邮件%% </p><p>或</p><p>%%user_crm_id%</p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%</p></td> 
   <td><p>https://help.salesforce.com/articleView?id=pardot_variable_tags_reference.htm&amp;type=5</p></td> 
  </tr> 
  <tr> 
   <td><p>轮毂点</p></td> 
   <td><p>（通过编辑器插入）</p></td> 
   <td><p>不适用</p></td> 
   <td><p>https://knowledge.hubspot.com/cos-general/how-to-use-personalization-with-your-content</p></td> 
  </tr> 
  <tr> 
   <td><p>Act-On</p></td> 
   <td><p>（通过消息编辑器插入）</p></td> 
   <td><p>不适用</p></td> 
   <td><p>https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data</p></td> 
  </tr> 
 </tbody> 
</table>

最后，在 [!DNL Marketo Measure]，则需要指定跟踪参数，以便 [!DNL Marketo Measure] 可以找到电子邮件或ID值。 默认值为“mailId”，如上面的示例和下面的屏幕截图所示。 在的“设置”中输入值 [!DNL Marketo Measure]，然后单击 **[!UICONTROL Save]**.

![](assets/one.png)
