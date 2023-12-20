---
description: 集成权限概述 —  [!DNL Marketo Measure]  — 产品文档
title: 集成权限概述
hide: true
hidefromtoc: true
feature: APIs, Integration
source-git-commit: 4953d6c51a87669ced0a13e2a54810d14976585c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 3%

---

# 集成权限概述 {#integration-permissions-overview}

本指南概述了与Marketo Measure无缝集成所需的权限，确保每个集成有效运行且没有问题。

<table>
<thead>
  <tr>
    <th>集成</th>
    <th>数据类型
    <li>Web交互数据</li>
    <li>B2B系统数据</li>
    <li>广告平台数据</li></th>
    <th>我们跟踪的内容</th>
    <th>权限要求</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Salesforce</td>
    <td>B2B系统数据    
</td>
    <td>Marketo Measure正在跟踪：
    <br>
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
<br>
创建的接触点和其他数据将写入Account、Campaign、CampaignMember、Case、Contact、Lead和Opportunity上的自定义bizible字段中。</td>
    <td><b>Salesforce连接的用户权限（必需）</b>
    <br>
    <b>为专用用户设置的Marketo Measure管理员权限：</b> 允许SFDC管理员对Marketo度量对象执行CRUD操作。
    <br>
    <b>查看和编辑转化后的潜在客户权限集：</b> 这允许Marketo Measure在潜在客户转换为联系人后对其进行装饰。
    <br>
    <b>Salesforce营销用户复选框：</b> 通过营销用户复选框，用户可创建营销活动并使用Campaign导入向导。
    <br>
    <b>Marketo Measure Standard用户：</b> 允许用户从Marketo Measure对象中读取记录。
    <p>
    <b>Salesforce标准字段权限</b>
    <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce标准对象和访问</a>
    <p>
    <b>Salesforce自定义字段权限</b>
    <br>
    我们提供一些功能设置，用于保存客户可以使用的自定义Salesforce字段。 如果定义了这些功能设置，则我们需要对功能设置中保存的每个salesforce字段的“读取”访问权限(例如，如果CustomLeadSourceField设置值等于“LeadSource__c”，则我们需要对此字段的“读取”访问权限)。
    </td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</tbody>
</table>
