---
description: 实施 [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure]的最佳实践
title: 实施 [!DNL Marketo Measure] JavaScript的最佳实践
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---


# 实施[!DNL Marketo Measure] JavaScript的最佳实践 {#best-practices-for-implementing-marketo-measure-javascript}

## 概述 {#overview}

[!DNL Marketo Measure] JavaScript跟踪Web访客的数字营销交互，并且是[!DNL Marketo Measure]创建在线接触点数据的能力的关键。 在整个站点上正确、全面地部署[!DNL Marketo Measure] JavaScript将确保收集的会话数据能够生成准确的接触点数据。

部署[!DNL Marketo Measure] JavaScript时出现不一致，这会导致会话数据中断，进而导致以下情况：

* 不正确的渠道/子渠道归因
* 源数据丢失
* 高水平的错误直接流量
* 报告不一致

[!DNL Marketo Measure] JavaScript是[!DNL Marketo Measure]帐户的基础部分，是您成功的关键！

## 最佳实践 {#best-practice}

在实施和管理[!DNL Marketo Measure] JavaScript时，请牢记以下最佳实践。

* 确认您的[!DNL Marketo Measure]帐户中列出了您的所有域
   * 如果您对您的域有任何疑虑，请联系支持人员
* 在所有页面中部署JavaScript 。
   * 仅在某些页面上放置JavaScript会导致会话数据中断，从而导致[!DNL Marketo Measure]数据不正确
* 对于您网站上不想在其中创建接触点的表单，请确保添加[!DNL Marketo Measure]排除脚本
   * 此排除项脚本将确保[!DNL Marketo Measure]会话数据不会被中断，并且源数据保持不变
      * 要隐藏的常见表单示例包括：
         * 客户登录
         * 忘记密码表单
         * 取消订阅表单
         * 职业申请表
* 查看下面列出的添加[!DNL Marketo Measure]脚本资源的“其他注意事项”和“Forms要特别注意”部分，以检查可能需要特殊处理的任何方案

## 维护的最佳实践 {#best-practice-for-maintenance}

虽然初始实施期间涵盖[!DNL Marketo Measure] JavaScript的设置，但更改您的网站或管理该网站的团队可能会导致[!DNL Marketo Measure]跟踪中断。 我们建议您确认已正确全面部署[!DNL Marketo Measure] JavaScript，每年一次。 此外，如果贵组织拥有该网站的任何类型的更改协议文档，请确保有一部分说明[!DNL Marketo Measure] JavaScript应保留/添加到所有新页面。

可能触发审查JavaScript设置的其他原因包括……

* 您的营销团队中的人员调整
* 网站结构的更改和更新
* 站点迁移
* 对域所做的更改
* 收购其他公司及其网络资产
