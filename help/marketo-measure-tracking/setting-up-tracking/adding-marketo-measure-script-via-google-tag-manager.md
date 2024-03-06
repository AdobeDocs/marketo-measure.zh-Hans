---
unique-page-id: 18874797
description: 正在添加 [!DNL Marketo Measure] 脚本方式 [!DNL Google Tag Manager] - [!DNL Marketo Measure]
title: 正在添加 [!DNL Marketo Measure] 脚本方式 [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# 正在添加 [!DNL Marketo Measure] 脚本方式 [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

安装时 [!DNL Marketo Measure] JavaScript，建议您 [对脚本进行硬编码](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} 直接进入站点。 如果不可能，您还可以使用 [!DNL Google Tag Manager] (GTM)以加载 [!DNL Marketo Measure] JS. 请注意 [!DNL Marketo Measure] 通过GTM加载的JS容易出现延迟。 滞后会导致脚本加载时间延迟，这可能会导致所有表单提交丢失约3-5%。

如果您决定通过GTM添加脚本，请将 [!DNL Marketo Measure] 脚本触发顺序中的最高优先级，并确保前面没有同步脚本 [!DNL Marketo Measure] 标记以减少GTM延迟产生的任何影响。

>[!NOTE]
>
>使用此 [Google的支持文章](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"} 了解更多信息。

## 如何添加 [!DNL Marketo Measure] JS，通过 [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. 打开GTM并添加 [!DNL Marketo Measure] 网站容器上的脚本。 确保选择 **[!UICONTROL Custom HTML tag]**.

1. 使用 [!DNL Marketo Measure] 编写下面的脚本并将其合并到容器中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 单击 **[!UICONTROL Add a Firing Rule]** 以便您指示Google加载我们的代码片段 *所有页面*.

1. 转到左侧的容器草稿概述部分。 单击按钮可创建容器的版本并发布更改。
