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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: '通过将自定义磁贴添加到应用启动器中，创建指向您的电子邮件、文档、应用程序、SharePoint 网站、外部网站和其他资源的快速链接。 '
ms.openlocfilehash: 7220f0be8ad6605b7ad6d30000fde6411948c996
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780129"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>向应用启动器添加自定义磁贴

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

在 Microsoft 365 中，可以使用应用启动器快速轻松地访问您的电子邮件、日历、文档和应用程序（[了解详细信息](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)）。 这些是使用 Microsoft 365 获取的应用以及从[SharePoint 应用商店](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43)或[Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)添加的自定义应用程序。
  
You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site. 
  
![应用启动器](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>向应用启动器添加自定义磁贴

1. 在管理中心中，转到 "**设置**  >  **组织设置**"，然后选择 "**组织配置文件**" 选项卡。
    
2. 在 "**组织配置文件**" 选项卡上，选择 "**自定义应用启动器" 磁贴**。
  
3. 选择 "**添加自定义磁贴**"。 
  
4. 为新磁贴输入" **磁贴名称**"。 该名称将显示在磁贴中。 
    
5. 为磁贴输入**网站的 URL** 。 这是您希望用户在应用启动器上选择磁贴时要转到的位置。 在 URL 中使用 HTTPS。<br/>提示：如果要为 SharePoint 网站创建磁贴，请导航到该网站，复制该 URL，然后将其粘贴到此处。 默认团队网站的 URL 如下所示：`https://<company_name>.sharepoint.com` 
  
6. 输入图块的**图像的 URL** 。 此图像显示在"我的应用"页面上和应用启动器中。<br/>提示：图像应为60x60 像素，并且可供组织中的所有人使用，而无需进行身份验证。

7. 为磁贴输入" **说明**"。 当您在 "我的应用程序" 页上选择磁贴并选择 "**应用程序详细信息**" 时，会看到此 
  
8. 选择 "**保存更改**" 以创建自定义磁贴。 
    
自定义磁贴现显示在应用启动器中的" **全部**"选项卡上。 
  
## <a name="promote-the-tile-to-app-launcher"></a>将磁贴升级到应用启动器

1. 选择应用启动器图标并选择 "**所有应用**"。 
    
2. 找到您的应用程序的新磁贴，选择省略号，然后选择 "**固定到启动器**"。
  
    > [!NOTE]
    > 如果看不到先前步骤中创建的自定义磁贴，请确保你已分配有 Exchange Online 邮箱，且至少有一次成功登录到邮箱中。 这些步骤是 Microsoft 365 中的自定义磁贴所必需的。 
  
> [!IMPORTANT]
> 你和你的用户需要执行这些步骤，才能将"我的应用"页面中的自定义磁贴提升到应用启动器。 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. 在管理中心中，转到 "**设置**组织设置" "  >  **Org Settings**  >  **组织配置文件** </a> " 选项卡。
    
2. 在 "**组织配置文件**" 页上的 "为**您的组织添加自定义磁贴**" 旁边，选择 "**编辑**"。

3. 更新自定义磁贴的" **磁贴名称**"、" **URL**"、" **说明**"或" **图像 URL**"（请参阅[向应用启动器添加自定义磁贴](#add-a-custom-tile-to-the-app-launcher)）。
    
4. 选择 "**更新** \> **关闭**"。 
    
若要删除自定义磁贴，请从 "**自定义磁贴**" 窗口中选择该图块，选择 "**删除磁贴**  >  **删除**"。 
  
## <a name="whats-next"></a>下一步做什么？

除了将磁贴添加到应用启动器之外，还可以将应用启动器磁贴添加到导航栏中（[了解详细信息](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)）。 若要自定义 Microsoft 365 的外观以与您的组织的品牌相匹配，请参阅[自定义 microsoft 365 主题](../setup/customize-your-organization-theme.md)。
  

