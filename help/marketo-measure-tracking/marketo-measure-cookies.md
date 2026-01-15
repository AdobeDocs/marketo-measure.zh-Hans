---
description: '[!DNL Marketo Measure] Cookie - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Cookie'
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 10%

---

# Marketo Measure Cookies {#marketo-measure-cookies}

了解将[!DNL Marketo Measure] JavaScript应用于登陆页面时加载到您网站的各种[!DNL Marketo Measure] Cookie。 这些信息在实施过程中可能会对Web开发团队非常有用。

>[!IMPORTANT]
>
>出于隐私考虑，第三方Cookie即将退出。 Google Chrome在2024年第3季度宣布弃用第三方Cookie，这实际上标志着这种跟踪形式的结束。 因此，Adobe将弃用依赖第三方Cookie的Marketo Measure功能；特别是跨域跟踪和浏览归因，后者使用Google/DoubleClick展示次数Cookie。 任何其他Marketo Measure功能都不会受到影响。 第一方Cookie的使用也不受影响。 按照Google的时间表，预计上述两个功能的弃用日期为2024年6月1日。 在此日期之前收集的相关数据仍可供Adobe客户使用。

| Cookie 名称 | Cookie类型 | 用途 | 过期 | 是否已设置安全标志？ | 是否设置了HTTP Only标志？ | Cookie Setter |
| --- | --- | --- | --- | --- | --- | --- |
| `_biz_uid` | 第一方 | 唯一标识当前域上的用户。 | 1 年 | 否 | 否 | `bizible.js` |
| `_biz_nA` | 第一方 | Marketo Measure包含用于所有内部诊断请求的序列号。 | 1 年 | 否 | 否 | `bizible.js` |
| `_biz_flagsA` | 第一方 | 用于存储各种用户信息（如表单提交、跨域迁移、显示到达像素、跟踪选择退出状态等）的Cookie。 | 1 年 | 否 | 否 | `bizible.js` |
| `_biz_pendingA` | 第一方 | 临时存储Analytics数据，直到成功发送到Marketo Measure服务器。 | 1 年 | 否 | 否 | `bizible.js` |
| `_biz_ABTestA` | 第一方 | 来自Optimizly和Visual Web Optimizer ABTests已报告数据的校验和列表，导致`bizible.js`无法重新发送收集的数据。 | 1 年 | 否 | 否 | `bizible.js` |
| `_biz_EventA` | 第一方 | Bizible事件报告的校验和列表，用于阻止`bizible.js`重新发送收集的数据。 | 1 年 | 否 | 否 | `bizible.js` |
| `_biz_su` | 第一方 | 跨多个域标识用户的通用用户ID，仅适用于具有绕过ITP限制集成的租户。 | 1 年 | 是 | 否 | Edgecast |
| `_BUID` | 第三方，域=.bizible.com | 跨多个域标识用户的通用用户ID。 | 1 年 | 是 | 否 | Edgecast |
| `_BUID` | 第三方，域=.bizibly.com | 租户域上的Marketo Measure Cookie ID与其Doubleclick展示Cookie ID之间的映射。 | 1 年 | 是 | 否 | Edgecast |

如果在JavaScript设置期间触发了Web应用程序防火墙(WAF)警告，则用户可以禁用该WAF规则或允许列表Cookie，如下例所示：

![如果在JavaScript期间触发了Web应用程序防火墙(WAF)警告](assets/adding-script-1.png)
