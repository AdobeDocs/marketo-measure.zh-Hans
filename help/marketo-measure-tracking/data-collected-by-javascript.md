---
description: JavaScript针对Marketo Measure用户的指南收集的数据
title: JavaScript收集的数据
feature: Tracking
exl-id: 83814168-9d3e-45ac-b514-df58f0b2e90b
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 11%

---

# JavaScript收集的数据 {#data-collected-by-javascript}

了解Marketo Measure JavaScript在部署时收集的数据。

**示例请求：**

```text
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure会为所有类型的请求收集以下常用数据：

| 来源 | 名称 | 数据类型 | 用途 |
| --- | --- | --- | --- |
| 请求标头 | IP地址 | 字符串 | 通过GeoIP查找推断用户的位置。 此数据是临时的，不会永久存储。 |
| 请求标头 | 用户代理字符串 | 字符串 | 确定用户使用的设备。 |
| 查询参数 | `_biz_u` | 字符串 | Bizible Cookie ID。 |
| 查询参数 | `_biz_l` | 字符串 | 当前页面URL。 |
| 查询参数 | `_biz_t` | 长 | 活动时间戳。 |
| 查询参数 | `_biz_i` | 字符串 | 当前页面标题。 |

除了上述常见数据之外，bizible.js还根据下面指定的请求类型附加其他数据：

| 请求类型 | 请求路径 | 其他查询参数 | 数据类型 | 用途 |
| --- | --- | --- | --- | --- |
| 页面查看 | `/ipv` | `_biz_r` | 字符串 | 反向链接页面URL。 |
|  |  | `_biz_h` | 字符串 | 经过哈希处理的客户端屏幕分辨率。 |
|  |  | `_biz_c` | 字符串 | 可选参数。 如果此参数存在，则表示租户将`bizible.js`配置为在跟踪前等待用户同意，并且`bizible.js`已收到要跟踪的用户同意。 |
| 表单提交 | `/frm` | `eMail` | 字符串 | 纯文本电子邮件地址。 |
| 用户ID映射 | `/u` | `mapType` | 枚举 | 检测到`bizible.js`的用户标识映射(Marketo Munchkin ID和Adobe ECID) |
|  |  | `mapValue` | 字符串 | 上述集成的实际第三方Cookie ID值。 |

>[!NOTE]
>
>Bizible是Marketo Measure的前称。
