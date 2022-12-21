---
unique-page-id: 18874680
description: '"[!DNL Facebook] API - [!DNL Marketo Measure]  — 产品文档”'
title: "[!DNL Facebook] API"
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 1%

---

# [!DNL Facebook] API {#facebook-api}

## 简介 {#introduction}

与我们的AdWords和 [!DNL Bing Ads] 集成，我们 [!DNL Facebook] 集成可执行两项基本操作：

* 自动标记全部 [!DNL Facebook] 带有 [!DNL Marketo Measure] 参数(_bf)
* 下载所有活动的Facebook广告中的广告成本信息

## 如何配置 [!DNL Facebook] 集成 {#how-to-configure-the-facebook-integration}

至于设置，在 [!DNL Marketo Measure] 应用程序。

1. 导航到 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}并登录。
1. 在我的帐户下，选择 **[!UICONTROL Settings]**.
1. 在集成下，选择 **[!UICONTROL Connections]**.
1. 选择 **[!UICONTROL Set Up New Ads Connection]** 随即会出现一个弹出窗口。 选择 **[!UICONTROL Facebook]** 和使用您的Facebook凭据登录。

   >[!NOTE]
   >
   >连接 [!DNL Facebook Ads] 帐户需要是 [!DNL Facebook Ads] 帐户。

1. 一次 [!DNL Marketo Measure] 已连接到您的Facebook帐户，请单击该帐户旁边的铅笔图标。
1. 在此视图中，移动“自动标记？” 切换为“是”。 然后，选中 [!UICONTROL Learn More] 部分以同意条款和条件。 确保 [!UICONTROL Auto-tagging] 切换仍设置为“[!UICONTROL Yes]&#39;。

## 连接帐户 {#connecting-the-account}

![](assets/1.gif)

## 启用自动标记 {#enabling-autotagging}

>[!NOTE]
>
>如果启用自动标记，我们将重置我们标记的所有广告的转化历史记录和社交验证。 我们强烈建议 [将此数据导出为CSV](https://www.facebook.com/business/help/205067636197240) ，然后再启用自动标记。

![](assets/2-2.png)

启用集成后， [!DNL Marketo Measure] 将开始将广告级别成本下载到 [!DNL Marketo Measure Marketing ROI] 功能板。

为使集成正常工作，您需要在 [!DNL Facebook] 帐户。 这将允许我们的系统在所有广告链接中添加_bf参数。 此过程将在您已添加到的任何其他跟踪参数之上添加新参数 [!DNL Facebook] 广告。

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
   <td><p>广告促销活动Id</p></td> 
   <td><p>[[!DNL Facebook] 促销活动Id]</p></td> 
  </tr> 
  <tr> 
   <td><p>广告促销活动名称 </p></td> 
   <td><p>[[!DNL Facebook] 促销活动名称]，或[utm_campaign]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>广告组ID</p></td> 
   <td><p>[[!DNL Facebook] 广告集Id]</p></td> 
  </tr> 
  <tr> 
   <td><p>广告组名称</p></td> 
   <td><p>[[!DNL Facebook] 广告集名称]</p></td> 
  </tr> 
  <tr> 
   <td><p>接触点源</p></td> 
   <td><p>"[!DNL Facebook]“，或[utm_source]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>中</p></td> 
   <td><p>"Social"或[utm_medium]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>广告ID或Creative_Unique_Id(Data warehouse)</p></td> 
   <td><p>[从utm_content生成的自定义ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>广告内容或Creative_Name(Data warehouse)</p></td> 
   <td><p>[utm_content]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>关键词文本或关键词名称(Data warehouse)</p></td> 
   <td><p>[utm_term]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Unique_Id(Data warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 广告Id]</p></td> 
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

**问：什么 [!DNL Facebook] 广告受 [!DNL Marketo Measure]?**

答：轮播，单幅图像。 当前不是视频、幻灯片或收藏集。

**问：什么是社交证据？**

答：社交验证是可见的参与，如称赞、点击、评论和共享。

**问：当 [!DNL Marketo Measure] 标记广告？**

答： [!DNL Facebook] 不允许编辑广告 [!DNL Marketo Measure] 需要删除包含目标URL的创作元素，然后使用新参数重新创建广告。

**问：为什么 [!DNL Marketo Measure] 更新全部 [!DNL Facebook] 广告？**

答：的 [!DNL Marketo Measure] 流程是在所有广告重新激活时标记它们。

**问：连接的用户需要什么权限？**

答：ads_management，电子邮件

**问：导入支出数据需要多长时间？**

答：1小时

**问：导入广告数据需要多长时间？**

答：4小时
