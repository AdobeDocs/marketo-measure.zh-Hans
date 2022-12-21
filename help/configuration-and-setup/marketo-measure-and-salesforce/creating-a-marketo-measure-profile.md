---
unique-page-id: 18874698
description: 创建 [!DNL Marketo Measure] 用户档案 —  [!DNL Marketo Measure]  — 产品文档
title: 创建 [!DNL Marketo Measure] 用户档案
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# 创建 [!DNL Marketo Measure] 用户档案 {#creating-a-marketo-measure-profile}

了解如何创建 [!DNL Marketo Measure] 配置文件。 创建 [!DNL Marketo Measure] 配置文件可确保在将数据推送到您的CRM时不会遇到验证错误。

1. 创建特定 [!DNL Marketo Measure] 用户档案：

   * 分配 [!DNL Marketo Measure] 管理员权限集
   * 启用查看和编辑已转换的潜在客户的权限

   >[!NOTE]
   >
   >此配置文件可以是 [!DNL System Admin] 个人资料

1. 创建专用 [!DNL Marketo Measure] 用户：

   * 分配新 [!DNL Marketo Measure] 向该用户提供用户档案
   * 启用“营销用户”作为用户级别权限

1. 从所有触发器、工作流和流程中排除此用户档案。
1. 登录到 [!DNL Marketo Measure] 帐户并重新授权 [!DNL Salesforce] 与新用户的连接：

   * 转到 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}并使用新用户生产Salesforce凭据登录
   * 选择“[!UICONTROL Settings]“ ”[!UICONTROL My Account]“ ”下拉列表
   * 选择“[!UICONTROL Connections]“ ”[!UICONTROL Integrations]“分组”
   * 单击当前连接对象右侧的键图标 [!DNL Salesforce] 连接，然后选择“使用生产重新授权”。 如果出现提示，则再次使用新用户凭据登录

   完成!

   如果您对创建专用 [!DNL Marketo Measure] 用户档案，请联系您的客户成功经理或 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}。
