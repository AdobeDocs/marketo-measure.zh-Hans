---
description: 集成权限概述 —  [!DNL Marketo Measure]  — 产品文档
title: 集成权限概述
hide: true
hidefromtoc: true
feature: APIs, Integration
source-git-commit: 95bdfe7c95111b6c6430e2de2b5eef050183fb0b
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 1%

---

# 集成权限概述 {#integration-permissions-overview}

本指南概述了与Marketo Measure无缝集成所需的权限，确保每个集成有效运行且没有问题。

<table>
<thead>
  <tr>
    <th style="width:10%">集成</th>
    <th style="width:25%">数据类型
    <li>Web交互数据</li>
    <li>B2B系统数据</li>
    <li>广告平台数据</li></th>
    <th style="width:25%">我们跟踪的内容</th>
    <th style="width:40%">权限要求</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Salesforce</td>
    <td>B2B系统数据    
</td>
    <td>Marketo Measure正在跟踪：
    <p>
    <li>帐户</li>
    <li>Campaign</li>
    <li>CampaignMember</li>
    <li>联系人</li>
    <li>CurrentconversionRange</li>
    <li>货币状态</li>
    <li>事件</li>
    <li>FieldHistory （Lead 、 Contact和Opportunity ）</li>
    <li>商机</li>
    <li>机会</li>
    <li>Opportuncontactrole</li>
    <li>机会历史记录</li>
    <li>任务</li>
<p>
创建的接触点和其他数据将写入Account、Campaign、CampaignMember、Case、Contact、Lead和Opportunity上的自定义bizible字段中。</td>
    <td><b>Salesforce已连接用户权限（必需）</b>
    <p>
    <b>为专用用户设置的Marketo Measure管理员权限：</b> 允许SFDC管理员对Marketo度量对象执行CRUD操作。
    <br>
    <b>查看和编辑转化后的潜在客户权限集：</b> 这允许Marketo Measure在潜在客户转换为联系人后对其进行装饰。
    <br>
    <b>Salesforce营销用户复选框：</b> 通过营销用户复选框，用户可创建营销活动并使用Campaign导入向导。
    <br>
    <b>Marketo Measure Standard用户：</b> 允许用户从Marketo Measure对象中读取记录。
    <p>
    <b>Salesforce标准字段权限</b>
    <br>
    <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce标准对象和访问</a>
    <p>
    <b>Salesforce自定义字段权限</b>
    <br>
    我们提供一些功能设置，用于保存客户可以使用的自定义Salesforce字段。 如果定义了这些功能设置，则我们需要对功能设置中保存的每个salesforce字段的“读取”访问权限(例如，如果CustomLeadSourceField设置值等于“LeadSource__c”，则我们需要对此字段的“读取”访问权限)。
    </td>
  </tr>
  <tr>
    <td>动态</td>
    <td>B2B系统数据</td>
    <td>Marketo Measure正在跟踪：
    <p>
    <li>帐户
<li>活动方
<li>活动指针
<li>Campaign
<li>CampaignItem（系统中的CampaignList）
<li>CampaignResponse（系统中的CampaignMember）
<li>联系人
<li>商机
<li>列表（系统中的营销列表）
<li>ListMember（系统中的MarketingListMember）
<li>机会
<li>组织
<li>TransactionCurrency （我们系统中的CurrencyConversionRange和CurrencyStatus）
<li>约会， CampaignActivity，电子邮件，传真， IncidentResolution，事件解决，信件， PhoneCall， RecurringAppointmentMaster， ServiceAppointment，任务
<li>bizible2_bizible_abtest
<li>bizible2_bizible_attribution_touchpoint
<li>bizible2_bizible_event
<li>bizible2_bizible_history
<li>bizible2_bizible_touchpoint
<p>
创建的接触点和其他数据将写入Account、Campaign、CampaignResponse、Contact、Lead、List、Opportunity和PhoneCall上的自定义bizible字段中</td>
    <td><b>Marketo Measure用户权限</b>
<br>
我们建议在Dynamics中创建专门的Marketo Measure用户，以便我们通过来导出和导入数据，从而避免您的CRM中的其他用户出现任何问题。 记下用户名和密码以及端点URL，因为创建Marketo Measure帐户时将使用此选项。
<p>
<b>安全角色</b>
<br>
如果您的组织使用Dynamics安全角色，请确保连接的用户或专用的Marketo Measure用户具有所需实体的足够读/写权限。
<br>
安全角色位于此处：设置&gt;安全&gt;安全角色
<br>
对于Marketo Measure自定义实体，我们需要所有实体的完全权限。
<p>
<b>Dynamics Standard字段权限</b>
<br>
<a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Marketo Measure Dynamics架构</a>
<p>
<b>Dynamics自定义字段权限</b>
<br>
我们需要“读取”权限，才能访问客户希望用于自定义禁止/删除接触点设置规则的Lead或Contact实体中的任何字段。
<br>
我们需要Lead或Opportunity实体上任何字段的READ访问权限，客户希望将这些字段用于区段规则或阶段映射。
<br>
我们需要对Campaign、CampaignResponse和List实体上客户希望用于同步Campaign/MarketingList成员的任何字段具有“读取”访问权限。
</td>
  </tr>
  <tr>
    <td>Facebook</td>
    <td>广告平台数据</td>
    <td>我们与Facebook集成以：
<p>
<li>导入客户广告数据</li>
<li>导入客户广告成本数据</li>
<li>通过附加url参数更新客户端的广告</li>
<p>
Marketo Measure正在跟踪帐户、促销活动、广告组、广告、过滤器ID和URL。</td>
    <td><li>创建营销活动、管理广告或获取广告量度需要ads_management权限。</li>
<li>需要电子邮件权限才能允许用户登录其Facebook电子邮件。</li>
<p>
<b>范围</b>
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/ads_management/">ads_management</a>
<br>
<li>以编程方式创建营销活动、管理广告和获取量度。</li>
<li>构建广告管理工具，为广告商提供创新解决方案和独特的价值。</li>
<br>
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/email">电子邮件</a>
<br>
<li>与用户通信，并允许他们使用与其Facebook个人资料关联的电子邮件地址登录到您的应用程序。</li></td>
  </tr>
  <tr>
    <td>LinkedIn</td>
    <td>广告平台数据
    <p>
    B2B系统数据（Lead Gen Form Data，包括表单和提交内容，分类为CRM活动）。</td>
    <td>Marketo Measure正在跟踪LinkedIn广告促销活动、创意和成本数据，以及潜在客户Forms和回应。 根据导入的数据，我们可以生成LinkedIn接触点并将潜在客户表单响应与客户关联起来。</td>
    <td><li>Marketo Measure需要营销活动经理或客户经理角色才能下载成本数据。 （范围行1）</li>
    <br>
    <li>Marketo Measure需要超级管理员（页面管理员角色，范围第2行）或潜在客户Forms经理（付费媒体管理员角色，范围第3行）来访问潜在客户表单数据</li>
    <br>
    <li>Marketo Measure需要超级管理员（页面管理员角色，范围第2行）或赞助的内容海报（付费媒体管理员角色，范围第3行）才能处理自动标记</li>
    <p>
    <b>范围</b>
    <br>
    <a href="https://www.linkedin.com/campaignmanager/accounts">在门户中设置用户角色(需要登录到LinkedIn帐户)</a> - <a href="https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager">用户角色概述</a>：用户角色，查看和管理用户权限，分配帐户经理或营销活动经理等角色
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en">设置页面管理员角色 —  <a href="https://www.linkedin.com/help/linkedin/answer/a541981/linkedin-page-admin-roles-overview">页面管理员角色定义</a>：页面管理员角色，在所需的管理员页面上
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en">设置付费媒体管理员角色（查找付费媒体管理员） —  <a href="https://www.linkedin.com/help/linkedin/answer/a554540">付费媒体管理员定义</a>：付费媒体管理员角色</td>
  </tr>
  <tr>
    <td>Doubleclick</td>
    <td>广告平台数据</td>
    <td>Marketo Measure正在跟踪帐户、广告商、促销活动、（自定义）登陆页面、广告、创意、投放和网站。</td>
    <td><li>需要用户的主要Google帐户电子邮件地址</li>
<li>访问Campaign Manager 360帐户所需的Campaign Manager权限</li>
<ul>
<li>查看和管理DoubleClick广告商报告</li>
<li>查看和管理DoubleClick Campaign经理显示广告营销活动</li>
<p>
    <b>范围</b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email">https://www.googleapis.com/auth/userinfo.email</a>：查看您的主要Google帐户电子邮件地址
    <p>
     <a href="https://www.googleapis.com/auth/dfareporting">https://www.googleapis.com/auth/dfareporting</a>：查看并管理广告商的DoubleClick报表
    <p>
     <a href="https://www.googleapis.com/auth/dfatrafficking">https://www.googleapis.com/auth/dfatrafficking</a>：查看和管理DoubleClick Campaign Manager (DCM)的显示广告营销活动</td>
  </tr>
  <tr>
    <td>AdWords</td>
    <td>广告平台数据</td>
    <td>我们与AdWords集成以：
<p>
<li>导入客户广告数据</li>
<li>导入客户广告成本数据</li>
<li>通过附加url参数/更新URL跟踪模板来更新客户端的广告</li>
<p>
Marketo Measure正在跟踪促销活动、广告组、创意内容、网站链接和关键字。</td>
    <td><li>需要用户的主要Google帐户电子邮件地址</li>
<p>
    <b>范围</b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email">https://www.googleapis.com/auth/userinfo.email</a>：查看您的主要Google帐户电子邮件地址</td>
  </tr>
  <tr>
    <td>Bing</td>
    <td>广告平台数据</td>
    <td>Marketo Measure正在跟踪帐户、营销活动、广告组、创意和关键字。</td>
    <td><li>用户必须通过其Microsoft帐户授予“离线访问权限”(这可以授予Marketo Measure对最终用户的UserInfo的访问权限，即使未登录也是如此)。 请参阅 <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access">Microsoft的页面</a> 如何操作。</li>
<p>
    <b>范围</b>
    <br>
    <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access">https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access</a>：维护对您已授予其权限的数据的访问权限。</td>
  </tr>
  <tr>
    <td>Marketo Engage</td>
    <td>B2B系统数据</td>
    <td>Marketo集成使Marketo Measure能够收集Marketo活动、人员、项目和项目成员资格。 此外，Marketo Measure还跟踪Marketo Cookie (Munchkin ID)，以便将Marketo Web活动关联到Marketo Measure潜在接触点， <a href="/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#cookie-mapping">如此处所述</a>：
    <p>
    <i>作为Marketo Measure与Marketo集成的结果，Marketo Measure Cookie ID现在也已映射并与Marketo Munchkin ID同步。 这有助于弥合将匿名首次接触归因于Web会话的差距，而不是将FT和LC接触都归因于Marketo活动。</i>
    </td>
    <td>客户必须创建一个专用的Marketo EngageAPI用户，并向Marketo Measure提供凭据。 无需其他权限配置。 <a href="/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/set-up-marketo-connection.md#configuring-the-integration">了解详情</a>.</td>
  </tr>
  <tr>
    <td>Adobe Analytics</td>
    <td>B2B系统数据</td>
    <td>通过B2B客户属性集成，Marketo Measure和Adobe Analytics的共同用户可以使用源自Marketo Measure归因引擎的有价值元数据扩充其Adobe Analytics用户配置文件，并通过其与CRM(Microsoft Dynamics和Salesforce)的同步功能扩充这些用户配置文件。 <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">了解详情</a>.</td>
    <td>客户必须向Marketo Measure提供别名ID和FTP服务器凭据，以便将数据上传到其Analytics实例的位置。
    <p>
    请注意以下信息，因为在此过程中的某些后续步骤中您将需要这些信息：
    <p>
    <li>别名ID，可以是您希望它成为的任何值。 我们建议使用“marketomeasure_id”</li>
    <li>FTP服务器主机名和凭据（用户名和密码）</li>
    <p>
    <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md#configuring-the-integration">了解更多</a></td>
  </tr>
  <tr>
    <td>Bizible Javascript</td>
    <td></td>
    <td><a href="/help/marketo-measure-tracking/setting-up-tracking/data-collected-by-javascript.md">bizible.js收集哪些数据</a>.</td>
    <td></td>
  </tr>
</tbody>
</table>
