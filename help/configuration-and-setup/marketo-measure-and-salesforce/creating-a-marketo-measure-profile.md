---
unique-page-id: 18874698
description: 创建 [!DNL Marketo Measure] 个人资料 —  [!DNL Marketo Measure]
title: 创建 [!DNL Marketo Measure] 个人资料
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# 创建 [!DNL Marketo Measure] 个人资料 {#creating-a-marketo-measure-profile}

了解如何创建 [!DNL Marketo Measure] 个人资料。 创建 [!DNL Marketo Measure] 配置文件可确保我们在将数据推送到您的CRM时不会遇到验证错误。

1. 创建特定 [!DNL Marketo Measure] 个人资料：

   * 分配 [!DNL Marketo Measure] 管理员权限集
   * 启用查看和编辑已转化商机的权限

   >[!NOTE]
   >
   >此配置文件可以是 [!DNL System Admin] 个人资料

1. 已创建专用 [!DNL Marketo Measure] 用户：

   * 分配新的 [!DNL Marketo Measure] 该用户的配置文件
   * 启用“营销用户”作为用户级别权限

1. 从所有触发器、工作流和流程中排除此配置文件。
1. 登录 [!DNL Marketo Measure] 帐户并重新授权 [!DNL Salesforce] 与新用户的连接：

   * 转到 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 并使用新的用户生产Salesforce凭据登录
   * 选择“[!UICONTROL Settings]“（在“”中）[!UICONTROL My Account]”下拉列表
   * 选择“[!UICONTROL Connections]“（在“”中）[!UICONTROL Integrations]”分组
   * 单击当前连接的右侧的键图标 [!DNL Salesforce] 连接，然后选择使用生产环境重新授权。 然后，如果出现提示，使用新用户凭据再次登录

   完成！

   如果您对创建专用报表有任何疑问， [!DNL Marketo Measure] 配置文件，联系Adobe客户团队（您的客户经理）或 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
