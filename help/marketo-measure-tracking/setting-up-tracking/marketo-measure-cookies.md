---
unique-page-id: 18874590
description: "[!DNL Marketo Measure] Cookie - [!DNL Marketo Measure]"
title: '"[!DNL Marketo Measure] Cookies”'
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 4%

---

# Marketo Measure Cookies {#marketo-measure-cookies}

了解各种 [!DNL Marketo Measure] 在您应用时加载到您网站上的Cookie [!DNL Marketo Measure] 将JavaScript添加到登陆页面。 这些信息在实施过程中可能会对Web开发团队非常有用。

>[!IMPORTANT]
>
>出于隐私考虑，第三方Cookie即将退出。 Google Chrome宣布在2024年第3季度弃用第三方Cookie，这实际上标志着这种跟踪形式的结束。 因此，Adobe将弃用依赖第三方Cookie的Marketo Measure功能，特别是跨域跟踪和浏览归因，后者使用Google/DoubleClick展示次数Cookie。 任何其他Marketo Measure功能都不会受到影响。 第一方Cookie的使用也不受影响。 按照Google的时间表，预计上述两个功能的弃用日期为2024年6月1日。 Adobe客户仍可使用此日期之前收集的相关数据。

<table>
<thead>
  <tr>
    <th>Cookie名称</th>
    <th>Cookie类型</th>
    <th>用途</th>
    <th>到期</th>
    <th>是否已设置安全标志？<br></th>
    <th>是否设置了HTTP Only标志？</th>
    <th>Cookie Setter</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>_biz_uid</td>
    <td>第一方</td>
    <td>唯一标识当前域上的用户。</td>
    <td>1年</td>
    <td>否</td>
    <td>否</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_nA</td>
    <td>第一方</td>
    <td>Marketo Measure包含用于所有内部诊断请求的序列号。</td>
    <td>1年</td>
    <td>否</td>
    <td>否</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_flagsA</td>
    <td>第一方</td>
    <td>用于存储各种用户信息（如表单提交、跨域迁移、显示到达像素、跟踪选择退出状态等）的Cookie。</td>
    <td>1年</td>
    <td>否</td>
    <td>否</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_pendingA</td>
    <td>第一方</td>
    <td>临时存储Analytics数据，直到成功发送到Marketo Measure服务器。</td>
    <td>1年</td>
    <td>否</td>
    <td>否</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_ABTestA</td>
    <td>第一方</td>
    <td>Optimizly和Visual Web Optimizer ABTests中已报告的校验和列表，阻止bizible.js重新发送收集的数据。</td>
    <td>1年</td>
    <td>否</td>
    <td>否</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_EventA</td>
    <td>第一方</td>
    <td>Bizible事件为防止bizible.js重新发送收集的数据而报告的校验和列表。</td>
    <td>1年</td>
    <td>否</td>
    <td>否</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_su</td>
    <td>第一方</td>
    <td>跨多个域标识用户的通用用户ID，仅适用于具有绕过ITP限制集成的租户。</td>
    <td>1年</td>
    <td>是</td>
    <td>否</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>第三方，域=。<a href="http://bizible.com/">bizible.com</a></td>
    <td>跨多个域标识用户的通用用户ID。</td>
    <td>1年</td>
    <td>是</td>
    <td>否</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>第三方，域=。<a href="http://bizibly.com/">bizibly.com</a></td>
    <td>租户域上的Marketo Measure Cookie ID与其Doubleclick展示Cookie ID之间的映射。</td>
    <td>1年</td>
    <td>是</td>
    <td>否</td>
    <td>Edgecast</td>
  </tr>
</tbody>
</table>

如果在JavaScript设置期间触发了Web应用程序防火墙(WAF)警告，则用户可以禁用该WAF规则或将Cookie列入允许列表，如下例所示：

![](assets/marketo-measure-cookies-1.png)
