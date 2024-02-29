---
unique-page-id: 18874781
description: 通过归因配置Doubleclick Campaign Manager视图 —  [!DNL Marketo Measure]
title: 通过归因配置Doubleclick Campaign管理器视图
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
feature: Attribution
source-git-commit: 518a984b0d8d640290bd9b637221fcdc0948e5b9
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# 通过归因配置Doubleclick Campaign管理器视图 {#configuring-doubleclick-campaign-manager-view-through-attribution}

## 通过归因测量视图 {#measuring-view-through-attribution}

>[!NOTE]
>
>如果您使用 [!DNL Marketo Measure] 和 [!DNL DoubleClick Campaign Manager] 集成，我们需要 [API连接](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) 因此，我们可以下载促销活动的详细信息和创意内容以解决广告。

开始通过从视图到跟踪获得更精细的见解 [!DNL Doubleclick Campaign Manager]，则需要配置我们的跟踪像素。

欲知关于 [!DNL Marketo Measure] 通过归因功能查看，请参阅 [Marketo Measure通过归因常见问题解答进行查看](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md).

[!DNL Marketo Measure] 被视为回头支点标记，因为它是通过DCM广告标记进行的第三方调用。 背带标记不适用于图像标记，只能用于iframe或javascript标记。 根据DCM支持部门的说法，这种情况最近没有变化，而且一直如此。 标准标记已于2017年10月2日弃用，但不会影响 [!DNL Marketo Measure] 以跟踪展示。

如果您在DCM中使用父级和子级层次结构，则需要将我们的标记应用于所有级别的展示跟踪。

## 如何添加图像标记 {#how-to-add-the-image-tag}

将标记添加到“广告商”设置下的Doubleclick中，并创建“展示事件”标记。

1. 添加以下代码作为1x1图像像素。

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. 添加后，请确认分隔符的映射如下所示。 在应用标记后，此操作应该自动完成：

   v = %eadv！ [!DNL Expand] 广告商ID\
   a = %eaid！ 展开广告Id\
   c = %ecid！ 展开创作Id\
   s = %esid！ 展开站点ID\
   p = %epid！ 展开版面Id\
   m = %m匹配代码宏\
   n = %n随机数宏

   ![](assets/1.png)

## 常见问题 {#faq}

**问：图像标记是否安全？**

答：是的。 它不是JavaScript标记，而是图像标记。

**问：连接的用户需要哪些权限？**

答：dfatrafficking、dfareporting、userinfo.email

**问：导入支出数据需要多长时间？**

答：最长6小时

**问：导入广告数据需要多长时间？**

答：最长6小时
