---
description: 实施的最佳实践 [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure]
title: 实施的最佳实践 [!DNL Marketo Measure] JavaScript
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# 实施的最佳实践 [!DNL Marketo Measure] JavaScript {#best-practices-for-implementing-marketo-measure-javascript}

## 概述 {#overview}

此 [!DNL Marketo Measure] JavaScript可跟踪Web访客的数字营销互动，并且是 [!DNL Marketo Measure] 能够创建在线接触点数据。 拥有 [!DNL Marketo Measure] 在整个站点中正确、全面部署的JavaScript将确保收集的会话数据能够生成准确的接触点数据。

部署中的不一致 [!DNL Marketo Measure] JavaScript将导致会话数据中断，这可能导致以下情况：

* 不正确的渠道/子渠道归因
* 源数据丢失
* 高水平的错误直接流量
* 报告不一致

[!DNL Marketo Measure] JavaScript是您的 [!DNL Marketo Measure] 帐户和密钥助您取得成功！

## 最佳实践 {#best-practice}

实施和管理您的 [!DNL Marketo Measure] JavaScript，请记住以下最佳实践。

* 确认您的所有域都列在中 [!DNL Marketo Measure] 帐户
   * 如果您对您的域有任何疑虑，请联系支持人员
* 在所有页面中部署JavaScript。
   * 仅将JavaScript放在某些页面上会导致会话数据中断，从而导致不正确 [!DNL Marketo Measure] 数据
* 对于您网站上不想从中创建接触点的表单，请确保添加 [!DNL Marketo Measure] 排除脚本
   * 此排除项脚本将确保 [!DNL Marketo Measure] 会话数据不会中断，并且源数据将保持不变
      * 要隐藏的常见表单示例包括：
         * 客户登录
         * 忘记密码表单
         * 取消订阅表单
         * 职业申请表
* 查看添加中的“其他注意事项”和“Forms要特别注意”部分 [!DNL Marketo Measure] 下面列出的脚本资源，用于检查可能需要特殊处理的任何场景

## 维护的最佳实践 {#best-practice-for-maintenance}

而设置 [!DNL Marketo Measure] 在初始实施期间涵盖JavaScript，对您的网站或管理该网站的团队进行的更改可能会导致中出现中断 [!DNL Marketo Measure] 跟踪。 我们建议您确认 [!DNL Marketo Measure] JavaScript每年可正确全面部署一次。 此外，如果贵组织拥有该网站的任何类型的更改协议文档，请确保有一部分对此进行说明 [!DNL Marketo Measure] JavaScript应保留/添加到所有新页面。

可能触发审查JavaScript设置的其他原因包括……

* 您的营销团队中的人员调整
* 网站结构的更改和更新
* 站点迁移
* 对域所做的更改
* 收购其他公司及其网络资产
