---
description: 实施最佳实践 [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure]  — 产品文档
title: 实施最佳实践 [!DNL Marketo Measure] JavaScript
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
source-git-commit: cf144eb4bc9282ae6a260acd3735f24644292a19
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# 实施最佳实践 [!DNL Marketo Measure] JavaScript {#best-practices-for-implementing-marketo-measure-javascript}

## 概述 {#overview}

的 [!DNL Marketo Measure] JavaScript可跟踪您的Web访客的数字营销互动，并且对 [!DNL Marketo Measure] 能够创建在线接触点数据。 拥有 [!DNL Marketo Measure] 在您的整个站点中正确、全面地部署JavaScript将确保收集的会话数据生成准确的接触点数据。

部署中不一致 [!DNL Marketo Measure] JavaScript将导致会话数据中断，这可能导致以下结果：

* 渠道/子渠道属性不正确
* 源数据丢失
* 错误的直接流量的高级别
* 报表不一致

[!DNL Marketo Measure] JavaScript是 [!DNL Marketo Measure] 帐户和成功的关键！

## 最佳实践 {#best-practice}

在实施和管理 [!DNL Marketo Measure] JavaScript中，请牢记以下最佳实践。

* 确认您的所有域都列在 [!DNL Marketo Measure] 帐户
   * 如果您对您的域有任何疑问，请联系支持人员
* 在所有页面中部署JavaScript。
   * 仅将JavaScript放置在某些页面上会导致会话数据中断，从而导致错误 [!DNL Marketo Measure] 数据
* 对于您网站上不希望从中创建接触点的表单，请确保添加 [!DNL Marketo Measure] 排除脚本
   * 此排除脚本将确保 [!DNL Marketo Measure] 会话数据不会中断，源数据会保留到位
      * 要禁止的常见表单示例包括：
         * 客户登录
         * 忘记密码表单
         * 取消订阅表单
         * 职业申请表
* 查看添加 [!DNL Marketo Measure] 下面列出的脚本资源，用于检查是否存在可能需要特殊处理的任何方案

## 维护最佳实践 {#best-practice-for-maintenance}

而 [!DNL Marketo Measure] JavaScript在初始实施期间涵盖，对您的网站或管理该网站的团队所做的更改可能会导致 [!DNL Marketo Measure] 跟踪。 我们建议您确认 [!DNL Marketo Measure] JavaScript每年正确、全面部署一次。 此外，如果贵组织拥有任何类型的网站更改协议文档，请确保有一部分说明 [!DNL Marketo Measure] JavaScript应保留/添加到所有新页面。

这可能会触发对JavaScript设置的审核的其他原因……

* 营销团队的营业额
* 更改和更新网站结构
* 站点迁移
* 对域所做的更改
* 其他公司的收购及其Web属性
