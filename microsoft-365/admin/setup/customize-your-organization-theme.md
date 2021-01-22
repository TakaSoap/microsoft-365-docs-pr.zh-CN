---
title: 为组织自定义主题
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: '了解如何更改 Microsoft 365 的默认主题，并对其进行自定义以匹配你的公司徽标或颜色。 '
ms.openlocfilehash: 9d17ac800fb0fe38627fcb7842ed5555d2ac28ae
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926878"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>为组织自定义 Microsoft 365 主题

作为 Microsoft 365 商业版订阅的管理员，可以更改显示在组织顶部导航栏中的默认主题：

- 添加公司徽标。
- 更改颜色以匹配品牌的其余部分。
- 添加用户在选择徽标时转到的目标链接。
  
## <a name="customize-your-theme-in-the-admin-center"></a>在管理中心自定义主题

1. 在管理中心，转到"设置 \> **组织** 设置"页，然后选择"组织 **配置文件"** 选项卡。

2. 在"**组织配置文件"** 选项卡上，选择 **"自定义主题"。**

3. 在 **"Customs"主题** 面板上，更改组织需要的主题元素：

    - **使用自定义徽标图像**：选择是使用 URL 中的图像还是上载图像。 如果使用 URL，请确保 URL 使用 HTTPS，并且图像是 200 x 30 像素（任意大小的任何格式）。 你可以上传 10 KB 以下的徽标，该徽标采用 JPG、PNG、GIF 或 SVG 格式，大小为 200 x 30 像素。

      > [!NOTE]
      > 若要在 SharePoint 移动应用中显示徽标，请仅使用 SVG 图像。 以任何其他格式上载的图像不会显示在应用中。 徽标在 SharePoint 移动应用中不可单击。

    - **使徽标可单击**：可以将导航栏中的徽标用作指向任何公司资源的链接。 你可以在此处输入徽标的 URL，从http://或https://。 这是可选的。

    - **选择背景图像**：选择图像并上传你自己的分辨率为 1366 x 50 像素（不超过 15 KB）的 JPG、PNG 或 GIF。 背景图像将显示在每页的顶部导航栏中。

      > [!NOTE]
      > 包含文本的图像可能不会如预期显示。 显示在导航栏的右侧和左侧的内置元素可能因服务而异，并且您的文本可能会被这些元素遮盖。

    - **导航栏颜色**：选择要用于导航栏背景的颜色。 导航栏显示在每页的顶部。

    - **文本和图标**：选择要为顶部导航栏上的文本和图标使用的颜色。

    - **主题色**：选择要用于导航栏按钮悬停颜色和页面重音（如按钮和特定应用程序上的文本）的颜色。

    - **阻止用户替代主题**：翻转此切换以阻止用户从主题选择中选择自己的主题。 这不会阻止用户设置高对比度主题。

    - **显示用户名**：选择在用户登录时是否在页面右上方的入口点向帐户经理显示用户的全名。 默认情况下，如果未上载照片，则用户会看到其照片或缩写。

4. 选择“**保存更改**”。

你可马上在管理中心看到新主题。 在短暂延迟后，您可以在 Microsoft 365 中查看它，包括 Outlook、SharePoint、 [适用于 iOS](https://support.microsoft.com/office/339402ce-16bb-4c97-9475-0c5375ccef7a)的 SharePoint 移动应用和适用于 Android 的 [SharePoint 移动应用中的页面](https://support.microsoft.com/office/d875654b-fb0a-4dbe-a17a-a676cf936284)。

可随时删除自定义图标或自定义颜色。 只需返回到主题页面，然后选择 **"删除自定义主题设置"。**
  
## <a name="best-practices"></a>最佳做法

- **徽标图像**：使用 SVG 文件类型，以便徽标在所有屏幕和所有缩放级别以高分辨率显示。

- **自定义颜色**：选择具有高对比度 **的** 导航栏背景色和你选取的 **徽标** 图像。 选择 **具有与** 导航栏背景色的高对比度的文本和图标颜色，以便所有文本和图标都清晰可见。

- **主题色**：选择一个在白色或浅色背景上显示良好的颜色。 主题色用于为在白色或浅色背景上显示的链接和按钮设置颜色。 例如，主题色用于为用户收件箱中的元素及其主题门户Office.com颜色。
  
- **对比率：** 建议的文本、图标或按钮颜色和背景色之间的对比度比率为 4.5：1。
  
## <a name="related-articles"></a>相关文章

[向"我的应用"页面和应用启动器添加自定义磁贴](../manage/customize-the-app-launcher.md)