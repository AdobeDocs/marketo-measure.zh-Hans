---
description: JavaScript收集的数据 —  [!DNL Marketo Measure]
title: JavaScript收集的数据
feature: Tracking
exl-id: 83814168-9d3e-45ac-b514-df58f0b2e90b
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 11%

---

# JavaScript收集的数据 {#data-collected-by-javascript}

了解Marketo Measure JavaScript在部署时收集的数据。

**示例请求：**

```
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure会为所有类型的请求收集以下常用数据：

<table>
<thead>
  <tr>
    <th>来源</th>
    <th>名称</th>
    <th>数据类型</th>
    <th>用途</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>请求标头</td>
    <td>IP地址</td>
    <td>字符串</td>
    <td>通过GeoIP查找推断用户的位置。 此数据是临时的，不会永久存储。</td>
  </tr>
  <tr>
    <td>请求标头</td>
    <td>用户代理字符串</td>
    <td>字符串</td>
    <td>确定用户使用的设备。</td>
  </tr>
  <tr>
    <td>查询参数</td>
    <td>_biz_u</td>
    <td>字符串</td>
    <td>Bizible Cookie ID。</td>
  </tr>
  <tr>
    <td>查询参数</td>
    <td>_biz_l</td>
    <td>字符串</td>
    <td>当前页面URL。</td>
  </tr>
  <tr>
    <td>查询参数</td>
    <td>_biz_t</td>
    <td>长</td>
    <td>活动时间戳。</td>
  </tr>
  <tr>
    <td>查询参数</td>
    <td>_biz_i</td>
    <td>字符串</td>
    <td>当前页面标题。</td>
  </tr>
</tbody>
</table>

除了上述常见数据之外，bizible.js还根据下面指定的请求类型附加其他数据：

<table>
<thead>
  <tr>
    <th>请求类型</th>
    <th>请求路径</th>
    <th>其他查询参数</th>
    <th>数据类型</th>
    <th>用途</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>页面查看</td>
    <td>/ipv</td>
    <td>_biz_r</td>
    <td>字符串</td>
    <td>反向链接页面URL。</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_h</td>
    <td>字符串</td>
    <td>经过哈希处理的客户端屏幕分辨率。</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_c</td>
    <td>字符串</td>
    <td>可选参数。 如果此参数存在，则表示租户将bizible.js配置为等待用户同意后再跟踪，并且bizible.js已收到用户同意进行跟踪。</td>
  </tr>
  <tr>
    <td>表单提交</td>
    <td>/frm</td>
    <td>电子邮件</td>
    <td>字符串</td>
    <td>纯文本电子邮件地址。</td>
  </tr>
  <tr>
    <td>用户ID映射</td>
    <td>/u</td>
    <td>mapType</td>
    <td>枚举</td>
    <td>检测到哪种用户id映射bizible.js(Marketo Munchkin id和Adobe ECID)</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>映射值</td>
    <td>字符串</td>
    <td>上述集成的实际第三方Cookie ID值。</td>
  </tr>
</tbody>
</table>

>[!NOTE]
>
>Bizible是Marketo Measure的前称。
