---
description: 通过Marketo Measure用户的归因指南配置Doubleclick Campaign Manager视图
title: 通过归因配置Doubleclick Campaign管理器视图
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
feature: Attribution
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# 通过归因配置Doubleclick Campaign管理器视图 {#configuring-doubleclick-campaign-manager-view-through-attribution}

## 通过归因测量视图 {#measuring-view-through-attribution}

>[!IMPORTANT]
>
>出于隐私考虑，第三方Cookie即将退出。 Google Chrome在2024年第3季度宣布弃用第三方Cookie，这实际上标志着这种跟踪形式的结束。 因此，Adobe将弃用依赖第三方Cookie的Marketo Measure功能；特别是跨域跟踪和浏览归因，后者使用Google/DoubleClick展示次数Cookie。 任何其他Marketo Measure功能都不会受到影响。 第一方Cookie的使用也不受影响。 按照Google的时间表，预计上述两个功能的弃用日期为2024年6月1日。 在此日期之前收集的相关数据仍可供Adobe客户使用。

>[!NOTE]
>
>如果您使用[!DNL Marketo Measure]和[!DNL DoubleClick Campaign Manager]集成，我们需要[API连接](/help/api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms)，以便我们可以下载促销活动和创意的详细信息以解决广告。

要使用[!DNL Doubleclick Campaign Manager]开始从查看到跟踪获取更精细的insight，需要配置我们的跟踪像素。

有关[!DNL Marketo Measure]通过归因功能查看的详细信息，请参阅[Marketo Measure通过归因常见问题解答](/help/advanced-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md)。

[!DNL Marketo Measure]被视为一个随身携带标记，因为它是通过DCM广告标记进行的第三方调用。 背带标记不适用于图像标记，只能用于iframe或javascript标记。 根据DCM支持部门的说法，这种情况最近没有变化，而且一直如此。 标准标记已于2017年10月2日弃用，但不会影响[!DNL Marketo Measure]跟踪展示次数的能力。

如果您在DCM中使用父级和子级层次结构，则需要将我们的标记应用于所有级别的展示跟踪。

## 如何添加图像标记 {#how-to-add-the-image-tag}

将标记添加到“广告商”设置下的Doubleclick中，并创建“展示事件”标记。

1. 添加以下代码作为1x1图像像素。

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. 添加后，请确认分隔符的映射如下所示。 在应用标记后，此操作应该自动完成：

   v = %eadv！ [!DNL Expand]广告商ID\
   a = %eaid！ 展开广告Id\
   c = %ecid！ 展开Creative Id\
   s = %esid！ 展开站点ID\
   p = %epid！ 展开版面Id\
   m = %m匹配代码宏\
   n = %n随机数宏

   ![](assets/view-attribution-1.png)

## 常见问题解答 {#faq}

**问：图像标记是否安全？**

答：是的。 它不是JavaScript标记，而是图像标记。

**问：连接的用户需要哪些权限？**

答：dfatrafficking、dfareporting、userinfo.email

**问：导入支出数据需要多长时间？**

答：最长6小时

**问：导入广告数据需要多长时间？**

答：最长6小时
