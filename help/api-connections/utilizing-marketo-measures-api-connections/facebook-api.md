---
unique-page-id: 18874680
description: '"[!DNL Facebook] API - [!DNL Marketo Measure]  — 产品文档”'
title: "[!DNL Facebook] API"
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
feature: APIs, Integration, UTM Parameters
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 1%

---

# [!DNL Facebook] API {#facebook-api}

## 介绍 {#introduction}

类似于我们的AdWords &amp; [!DNL Bing Ads] 集成，我们的 [!DNL Facebook] 集成执行两项基本操作：

* 全部自动标记 [!DNL Facebook] 带有的广告 [!DNL Marketo Measure] 参数(_bf)
* 下载所有有效Facebook广告的广告成本信息

## 如何配置 [!DNL Facebook] 集成 {#how-to-configure-the-facebook-integration}

在设置方面，您需要在 [!DNL Marketo Measure] 应用程序。

1. 导航到 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 并登录。
1. 在我的帐户下，选择 **[!UICONTROL Settings]**.
1. 在集成下，选择 **[!UICONTROL Connections]**.
1. 选择 **[!UICONTROL Set Up New Ads Connection]** 此时将出现一个弹出窗口。 选择 **[!UICONTROL Facebook]** 并使用您的Facebook凭据登录。

   >[!NOTE]
   >
   >连接 [!DNL Facebook Ads] 帐户必须是内的管理员 [!DNL Facebook Ads] 帐户。

1. 一次 [!DNL Marketo Measure] 已连接到您的Facebook帐户，请单击帐户旁边的铅笔图标。
1. 在此视图中，移动“自动标记？” 切换到“是”。 然后，选中中显示的复选框 [!UICONTROL Learn More] 部分同意条款和条件。 确保 [!UICONTROL Auto-tagging] 切换仍设置为&#39;[!UICONTROL Yes]’。

## 连接帐户 {#connecting-the-account}

![](assets/1.gif)

## 启用自动标记 {#enabling-autotagging}

>[!NOTE]
>
>如果启用自动标记，我们将重置所标记的所有广告的转化历史记录和社交证明。 我们强烈建议 [将此数据导出为CSV](https://www.facebook.com/business/help/205067636197240) 然后再启用自动标记。

![](assets/2-2.png)

启用集成后， [!DNL Marketo Measure] 将开始将广告级别的成本下载到 [!DNL Marketo Measure Marketing ROI] 仪表板。

为使集成正常工作，您需要在页面上 [!DNL Facebook] 帐户。 这将允许我们的系统在所有广告链接上添加_bf参数。 此进程将在您已经添加到的任何其他跟踪参数之上添加新参数 [!DNL Facebook] 广告。

![](assets/3.gif)

## 字段映射 {#field-mapping}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>接触点字段</strong></p></th> 
   <th><p><strong>值</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>广告营销活动ID</p></td> 
   <td><p>[[!DNL Facebook] 营销活动ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>广告营销活动名称 </p></td> 
   <td><p>[[!DNL Facebook] Campaign Name]或[utm_campaign]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>广告组ID</p></td> 
   <td><p>[[!DNL Facebook] 广告集Id</p></td> 
  </tr> 
  <tr> 
   <td><p>广告组名称</p></td> 
   <td><p>[[!DNL Facebook] 广告集名称]</p></td> 
  </tr> 
  <tr> 
   <td><p>接触点源</p></td> 
   <td><p>"[!DNL Facebook]"，或者[utm_source]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>中</p></td> 
   <td><p>"Social"，或者[utm_medium]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>广告Id或Creative_Unique_Id(Data warehouse)</p></td> 
   <td><p>[从utm_content生成的自定义ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad Content或Creative_Name(Data warehouse)</p></td> 
   <td><p>[utm_content]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>Keyword Text或Keyword_Name(Data warehouse)</p></td> 
   <td><p>[utm_term]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Unique_Id(Data warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 广告ID</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Name(Data warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 广告名称]</p></td> 
  </tr> 
  <tr> 
   <td><p>Keyword_Unique_Id(Data warehouse)</p></td> 
   <td><p>[从utm_term生成的自定义ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Provider(Data warehouse)</p></td> 
   <td><p>"[!DNL Facebook]"</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Unique_ID(Data warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 帐户 #]</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Name(Data warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 帐户名称]</p></td> 
  </tr> 
 </tbody> 
</table>

## 常见问题解答 {#faq}

**问：什么 [!DNL Facebook] 支持广告 [!DNL Marketo Measure]？**

答：轮播，单个图像。 当前不是视频、幻灯片或收藏集。

**问：什么是社交证据？**

答：社交验证是可见的参与，例如点击、点击、评论和分享。

**问：出现以下情况时会出现什么情况 [!DNL Marketo Measure] 为广告添加标签？**

答： [!DNL Facebook] 不允许编辑广告，因此 [!DNL Marketo Measure] 需要删除包含目标URL的创意，然后使用新参数重新创建广告。

**问：为什么会 [!DNL Marketo Measure] 全部更新 [!DNL Facebook] 广告？**

答： [!DNL Marketo Measure] 流程是标记所有广告，以防它们被重新激活。

**问：连接的用户需要什么权限？**

答：ads_management，电子邮件

**问：导入支出数据需要多长时间？**

A：1小时

**问：导入广告数据需要多长时间？**

答：4小时
