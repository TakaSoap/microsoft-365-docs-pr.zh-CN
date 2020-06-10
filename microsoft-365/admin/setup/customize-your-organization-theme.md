---
title: 为你的组织自定义主题
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: '了解如何更改 Microsoft 365 的默认主题，并对其进行自定义以与公司徽标或颜色相匹配。 '
ms.openlocfilehash: 034e5cff726ea97397d5eee1592265ae3452209b
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678610"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>为你的组织自定义 Microsoft 365 主题

作为 Microsoft 365 for business 订阅的管理员，您可以更改组织中每个人的顶部导航栏中显示的默认主题： 

- 添加公司徽标。
- 更改颜色，使其与品牌的其余部分相匹配。 
- 当用户选择你的徽标时，请添加目标链接。 
  
## <a name="customize-your-theme-in-the-admin-center"></a>在管理中心中自定义您的主题

1. 在管理中心中，转到 "**设置** \> **组织设置**" 页，然后选择 "**组织配置文件**" 选项卡。

2. 在 "**组织配置文件**" 选项卡上，选择 "**自定义主题**"。

3. 在 "**海关主题**" 面板上，更改您的组织所需的主题元素：
    
    - **使用自定义徽标图像**：选择是使用 URL 中的图像还是上载图像。 如果您使用 URL，请确保该 URL 使用 HTTPS，并且该图像的格式为 200 x 30 像素（任意大小的任意格式）。 您可以在 10 KB 下上传一个徽标为 200 x 30 像素（JPG、PNG、GIF 或 SVG 格式）。

      > [!NOTE]
      > 若要在 SharePoint 移动应用程序中显示徽标，请仅使用 SVG 图像。 以任何其他格式上载的图像不会显示在应用程序中。 在 SharePoint 移动应用程序中，徽标不可单击。

    - **使徽标可单击**：您可以使用导航栏中的徽标作为指向任何公司资源的链接。 您可以在此处输入徽标的 URL，从 http://或 https://开始。 这是可选的。

    - **选择 "背景图像**"：选择图像，然后上传您自己的分辨率为 1366 x 50 像素的 JPG、PNG 或 GIF，不大于 15 KB。 背景图像将显示在每页的顶部导航栏中。

      > [!NOTE]
      > 包含文本的图像可能无法按预期显示。 显示在导航栏右侧和左侧的内置元素可能因服务而异，这些元素可能会遮住您的文本。 

    - **导航栏颜色**：选择要用于导航栏背景的颜色。 导航栏显示在每页的顶部。

    - **文本和图标**：选择要为顶部导航栏上的文本和图标使用的颜色。

    - **强调文字颜色**：选择用于导航栏按钮悬停颜色和页面强调元素（如按钮和特定应用程序上的文本）的颜色。

    - **阻止用户覆盖主题**：翻转此开关可阻止用户从主题选择中选择自己的主题。 这不会阻止用户设置高对比度主题。

    - **显示用户名**：选择是否在用户登录时，在页面右上角的 "客户" 的入口点显示用户的完整名称。 默认情况下，如果没有上载照片，用户将看到照片或其缩写。
    
4. 选择“**保存更改**”。
    
你可以立即在管理中心中看到你的新主题。 在短时间内，你可以在 Microsoft 365 中看到它，包括 Outlook 中的页面、SharePoint、 [sharepoint mobile 应用 For iOS](https://support.office.com/article/SharePoint-mobile-app-for-iOS-339402ce-16bb-4c97-9475-0c5375ccef7a)和[适用于 Android 的 SharePoint 移动应用](https://support.office.com/article/SharePoint-mobile-app-for-Android-d875654b-fb0a-4dbe-a17a-a676cf936284)。

可随时删除自定义图标或自定义颜色。 只需返回主题页面，然后选择 "**删除自定义主题**"。
  
## <a name="best-practices"></a>最佳做法

- **徽标图像**：使用 SVG 文件类型，以便你的徽标在所有屏幕和所有缩放级别上显示为高分辨率。

- **自定义颜色**：选择具有您选取的**徽标图像**的高对比度的**导航栏背景色**。 选择与**导航栏背景颜色**具有高对比度的**文本和图标**颜色，以便清楚显示所有文本和图标。

- **强调文字颜色**：在白色或浅色背景上选取一种显示效果。 强调文字颜色用于为显示在白色或浅色背景上的一些链接和按钮着色。 例如，在用户的收件箱和其 Office.com 门户页面上的元素中使用强调文字颜色。 
  
- **对比度**：文本、图标或按钮颜色与背景色之间的推荐对比度为4.5：1。
  
## <a name="related-articles"></a>相关文章

[向"我的应用"页面和应用启动器添加自定义磁贴](../manage/customize-the-app-launcher.md)
  
  
