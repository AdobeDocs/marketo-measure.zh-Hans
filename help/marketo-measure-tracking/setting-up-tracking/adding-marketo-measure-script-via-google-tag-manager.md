---
unique-page-id: 18874797
description: 正在通过 [!DNL Marketo Measure] - [!DNL Google Tag Manager] 添加 [!DNL Marketo Measure]脚本
title: 正在通过 [!DNL Marketo Measure] 添加 [!DNL Google Tag Manager]脚本
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# 通过[!DNL Marketo Measure]添加[!DNL Google Tag Manager]脚本 {#adding-marketo-measure-script-via-google-tag-manager}

安装[!DNL Marketo Measure] JavaScript时，建议您[将脚本](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"}直接硬编码到站点中。 如果无法这样做，您还可以使用[!DNL Google Tag Manager] (GTM)来加载[!DNL Marketo Measure] JS。 请注意，通过GTM加载的[!DNL Marketo Measure] JS容易出现延迟。 滞后会导致脚本加载时间延迟，这可能会导致所有表单提交丢失约3-5%。

如果您决定通过GTM添加脚本，请将[!DNL Marketo Measure]脚本设置为触发顺序中的最高优先级，并确保[!DNL Marketo Measure]标记前面没有同步脚本，以减少GTM延迟产生的任何影响。

>[!NOTE]
>
>使用Google[发表的此](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"}支持文章了解更多信息。

## 如何通过[!DNL Marketo Measure]添加[!DNL Google Tag Manager] JS {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. 打开GTM并在您的网站容器上添加[!DNL Marketo Measure]脚本。 确保选择&#x200B;**[!UICONTROL Custom HTML tag]**。

1. 使用下面的[!DNL Marketo Measure]脚本并将其合并到容器中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 单击&#x200B;**[!UICONTROL Add a Firing Rule]**，以便您可以指示Google在&#x200B;*所有页面*&#x200B;上加载我们的代码片段。

1. 转到左侧的容器草稿概述部分。 单击按钮可创建容器的版本并发布更改。
