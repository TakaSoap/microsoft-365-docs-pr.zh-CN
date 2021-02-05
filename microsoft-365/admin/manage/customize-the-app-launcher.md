---
title: 向应用启动器添加自定义磁贴
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
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
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: '通过向应用启动器添加自定义磁贴，创建指向电子邮件、文档、应用程序、SharePoint 网站、外部网站和其他资源的快速链接。 '
ms.openlocfilehash: 96d059b252b63e48e20edb29861cf8233e220e34
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114185"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>向应用启动器添加自定义磁贴

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。

::: moniker-end

在 Microsoft 365 中，可以使用应用启动器快速轻松地访问电子邮件、日历、文档和应用， ([了解) 。](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) 这些是使用 Microsoft 365 获取的应用，以及从 [SharePoint 商店](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) 或 [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)添加的自定义应用程序。
  
可将自己的自定义磁贴添加到应用启动器，这些磁贴指向 SharePoint 网站、外部网站、旧版应用等。自定义磁贴显示在应用启动器的" **全部**"应用下，可将其固定到" **主页**"应用，并指示用户执行相同操作。这样做便于查找相关网站、应用和资源来完成工作。 在以下示例中，名为"Contoso 门户"的自定义磁贴用于访问组织的主要 SharePoint 网站。 
  
![应用启动器](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>向应用启动器添加自定义磁贴

1. 以全局管理员模式登录管理中心，转到"设置组织设置"，然后选择"  >  组织 **配置文件"** 选项卡。
    
2. 在" **组织配置文件"** 选项卡上，选择 **"自定义应用启动器"磁贴**。
  
3. 选择 **"添加自定义磁贴"。** 
  
4. 为新磁贴输入" **磁贴名称**"。 该名称将显示在磁贴中。 
    
5. 输入 **磁贴的网站** URL。 这是你想要用户在应用启动器上选择磁贴时转到的位置。 在 URL 中使用 HTTPS。<br/>提示：如果要为 SharePoint 网站创建磁贴，请导航到该网站，复制 URL 并将其粘贴到此处。 默认团队网站的 URL 如下所示： `https://<company_name>.sharepoint.com` 
  
6. 输入 **磁贴的图像 URL。** 此图像显示在"我的应用"页面上和应用启动器中。<br/>提示：图像应为 60x60 像素，并且无需身份验证即可供组织所有人使用。

7. 为磁贴输入" **说明**"。 当你在"我的应用"页面上选择磁贴并选择应用详细信息时，你将 **看到此内容**。 
  
8. 选择 **"保存更改** "以创建自定义磁贴。 
    
自定义磁贴现显示在应用启动器中的" **全部**"选项卡上。 
  
## <a name="promote-the-tile-to-app-launcher"></a>将磁贴提升为应用启动器

1. 选择应用启动器图标，然后选择 **"所有应用"。** 
    
2. 找到你的应用的新磁贴，选择省略号，然后选择"固定 **到启动器"。**
  
    > [!NOTE]
    > 如果看不到先前步骤中创建的自定义磁贴，请确保你已分配有 Exchange Online 邮箱，且至少有一次成功登录到邮箱中。 这些步骤对于 Microsoft 365 中的自定义磁贴是必需的。 
  
> [!IMPORTANT]
> 你和你的用户需要执行这些步骤，才能将"我的应用"页面中的自定义磁贴提升到应用启动器。 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. 在管理中心，转到"**设置**  >  **组织设置组织**  >  **配置文件"** </a> 选项卡。
    
2. 在"**组织配置文件**"页上的"为组织添加 **自定义磁贴**"旁边，选择"**编辑"。**

3. 更新自定义磁贴的" **磁贴名称**"、" **URL**"、" **说明**"或" **图像 URL**"（请参阅 [向应用启动器添加自定义磁贴](#add-a-custom-tile-to-the-app-launcher)）。
    
4. 选择 **"更新** \> **关闭"。** 
    
若要删除自定义磁贴，请从"自定义磁贴"窗口中选择该磁贴，选择 **"删除磁贴**  >  **删除"。** 
  
## <a name="whats-next"></a>下一步做什么？

除了将磁贴添加到应用启动器之外，还可以将应用启动器磁贴添加到导航栏 ([了解) 。](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985) 若要自定义 Microsoft 365 的外观以匹配组织的品牌，请参阅" [自定义 Microsoft 365"主题](../setup/customize-your-organization-theme.md)。
  
