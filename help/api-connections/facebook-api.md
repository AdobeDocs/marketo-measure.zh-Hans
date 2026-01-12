---
description: '[!DNL Facebook] API - [!DNL Marketo Measure]'
title: '[!DNL Facebook] API'
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
feature: APIs, Integration, UTM Parameters
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---


# [!DNL Facebook] API {#facebook-api}

## 简介 {#introduction}

与我们的AdWords和[!DNL Bing Ads]集成类似，我们的[!DNL Facebook]集成执行两项基本操作：

* 使用[!DNL Facebook]参数(_bf)自动标记所有[!DNL Marketo Measure]广告
* 下载所有有效Facebook广告的广告成本信息

## 如何配置[!DNL Facebook]集成 {#how-to-configure-the-facebook-integration}

至于设置，[!DNL Marketo Measure]应用程序中有七个步骤需要完成。

1. 导航到[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}并登录。
1. 在“我的帐户”下，选择&#x200B;**[!UICONTROL Settings]**。
1. 在集成下，选择&#x200B;**[!UICONTROL Connections]**。
1. 选择&#x200B;**[!UICONTROL Set Up New Ads Connection]**，此时将出现一个弹出窗口。 选择&#x200B;**[!UICONTROL Facebook]**&#x200B;并使用您的Facebook凭据登录。

   >[!NOTE]
   >连接[!DNL Facebook Ads]帐户的人员必须是[!DNL Facebook Ads]帐户中的管理员。

1. 将[!DNL Marketo Measure]连接到您的Facebook帐户后，单击该帐户旁边的铅笔图标。
1. 在此视图中，移动“自动标记？” 切换到“是”。 然后，选中[!UICONTROL Learn More]部分中的复选框以同意条款和条件。 确保[!UICONTROL Auto-tagging]切换仍设置为“[!UICONTROL Yes]”。

## 连接帐户 {#connecting-the-account}

![在Marketo Measure中设置新的Facebook广告连接](assets/1.gif)

## 启用自动标记 {#enabling-autotagging}

>[!NOTE]
>如果启用自动标记，我们将重置所标记的所有广告的转化历史记录和社交证明。 我们强烈建议您在启用自动标记之前[将此数据导出为CSV](https://www.facebook.com/business/help/205067636197240)。

![ 2](assets/2-2.png)

启用集成后，[!DNL Marketo Measure]将开始将广告级别成本下载到[!DNL Marketo Measure Marketing ROI]仪表板。

为使集成正常工作，必须在[!DNL Facebook]帐户上启用自动标记。 这将允许我们的系统在所有广告链接上添加_bf参数。 此进程将在您已添加到[!DNL Facebook]广告的任何其他跟踪参数之上添加新参数。

![在Facebook连接设置中启用自动标记](assets/3.gif)

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
   <td><p>[[!DNL Facebook]营销活动ID]</p></td>
  </tr>
  <tr>
   <td><p>广告营销活动名称 </p></td>
   <td><p>[[!DNL Facebook]营销活动名称]，或[utm_campaign]（如果提供）</p></td>
  </tr>
  <tr>
   <td><p>广告组ID</p></td>
   <td><p>[[!DNL Facebook]广告集Id]</p></td>
  </tr>
  <tr>
   <td><p>广告组名称</p></td>
   <td><p>[[!DNL Facebook]广告集名称]</p></td>
  </tr>
  <tr>
   <td><p>接触点Source</p></td>
   <td><p>"[!DNL Facebook]"或[utm_source]（如果提供）</p></td>
  </tr>
  <tr>
   <td><p>媒介</p></td>
   <td><p>"Social"，或者[utm_medium]（如果提供）</p></td>
  </tr>
  <tr>
   <td><p>广告Id或Creative_Unique_Id (Data Warehouse)</p></td>
   <td><p>[从utm_content生成的自定义ID]</p></td>
  </tr>
  <tr>
   <td><p>广告内容或Creative_Name (Data Warehouse)</p></td>
   <td><p>[utm_content]（如果提供）</p></td>
  </tr>
  <tr>
   <td><p>关键字文本或Keyword_Name (Data Warehouse)</p></td>
   <td><p>[utm_term]（如果提供）</p></td>
  </tr>
  <tr>
   <td><p>Ad_Unique_Id (Data Warehouse)</p></td>
   <td><p>[[!DNL Facebook]广告Id]</p></td>
  </tr>
  <tr>
   <td><p>Ad_Name (Data Warehouse)</p></td>
   <td><p>[[!DNL Facebook]广告名称]</p></td>
  </tr>
  <tr>
   <td><p>Keyword_Unique_Id (Data Warehouse)</p></td>
   <td><p>[从utm_term生成的自定义ID]</p></td>
  </tr>
  <tr>
   <td><p>Ad_Provider (Data Warehouse)</p></td>
   <td><p>"[!DNL Facebook]"</p></td>
  </tr>
  <tr>
   <td><p>Account_Unique_ID (Data Warehouse)</p></td>
   <td><p>[[!DNL Facebook]帐户号]</p></td>
  </tr>
  <tr>
   <td><p>Account_Name (Data Warehouse)</p></td>
   <td><p>[[!DNL Facebook]帐户名称]</p></td>
  </tr>
 </tbody>
</table>

## 常见问题解答 {#faq}

**问：[!DNL Facebook]支持哪些[!DNL Marketo Measure]广告？**

答：轮播，单个图像。 当前不是视频、幻灯片或收藏集。

**问：什么是社交校对？**

答：社交验证是可见的参与，例如点击、点击、评论和分享。

**问：[!DNL Marketo Measure]标记广告后会出现什么情况？**

答： [!DNL Facebook]不允许编辑广告，因此[!DNL Marketo Measure]需要删除包含目标URL的创意，然后使用新参数重新创建广告。

**问：为什么[!DNL Marketo Measure]更新所有[!DNL Facebook]广告？**

答：[!DNL Marketo Measure]进程将标记所有广告，以防它们被重新激活。

**问：连接的用户需要什么权限？**

答：ads_management，电子邮件

**问：导入支出数据需要多长时间？**

A：1小时

**问：导入广告数据需要多长时间？**

答：4小时
