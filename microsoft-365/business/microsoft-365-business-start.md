---
title: 企业Microsoft 365入门
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 了解Microsoft 365，如何设置，以及如何准备用户的设备和电脑，以确保它们受到适用于Microsoft 365保护。
ms.openlocfilehash: 3ac8ec3c831d14cfa6d0018340458b2b494b2dd746a7f2bd61d2eba0b4eaf0a1
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53837877"
---
# <a name="get-started-with-microsoft-365-for-business"></a>企业Microsoft 365入门

## <a name="what-is-microsoft-365-for-business"></a>业务Microsoft 365是什么

Microsoft 365是一套全面的业务生产力和协作工具，例如 Outlook、Word、Excel 以及其他始终保持最新的 Office 产品。 可以使用易于管理的企业级安全性在所有 iOS、Android 和 Windows 10设备上保护工作文件。

## <a name="watch-what-is-microsoft-365-business-premium"></a>观看：什么是 Microsoft 365 商业高级版

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365企业版最多需要 300 个许可证。 如果需要更多许可证，请参阅 [Microsoft 365 企业版](../enterprise/index.yml)文档，以了解详细信息。 
  
## <a name="get-microsoft-365-for-business"></a>获取Microsoft 365企业信息

- 如果你有合作伙伴，他们将获得适用于Microsoft 365服务：从 Microsoft 合作伙伴Microsoft 365[获取适用于企业的产品](get-microsoft-365-business.md)。
    
- 如果你没有合作伙伴，并且想要获取适用于Microsoft 365，可以[在此处购买](https://www.microsoft.com/microsoft-365/business)。
    
## <a name="set-up-microsoft-365-for-business"></a>设置 Microsoft 365 商业版

 **企业Microsoft 365套件设置概述**
  
下图介绍了管理员如何设置适用于Microsoft 365服务。 此外，还介绍了准备Windows电脑以用于Microsoft 365的步骤。 还可以在[AutoPilot](add-autopilot-devices-and-profile.md)中Microsoft 365 管理中心Windows设备。 可以使用 AutoPilot 设置和预配置新设备，以便用户使用适用于企业凭据的 Microsoft 365 登录后即可将其用于高效使用。
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

## <a name="watch-set-up-microsoft-365-business"></a>观看：设置 Microsoft 365 Business

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](../business-video/index.yml)。

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1：设置Microsoft 365商业 (管理员) 

Sign in to [Microsoft 365 管理中心](https://admin.microsoft.com/adminportal/home)with your global admin credentials， and complete the following steps to set up Microsoft 365 for business. 
  
1. [使用适用于企业的设备保护Microsoft 365的先决条件](pre-requisites-for-data-protection.md)
    
    首先阅读先决条件，确保你的设备可供Microsoft 365使用。
    
2. [使用安装向导设置Microsoft 365企业](set-up.md)
    
    如果你正在从本地 **Active Directory** 永久移动到云，你可以转到 Microsoft 365 管理中心并使用设置向导手动添加用户，或者你可以与 Azure AD 连接 进行一次同步。 可以通过两种方式来执行此操作： 
    
    - 如果还有 Exchange 2010、Exchange 2013 或 Exchange 2016 服务器，可以使用最小混合快速将 Exchange 邮箱迁移到[Microsoft 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)。 最少混合步骤包括用户到 Azure AD 的一次同步，以及从本地到云的电子邮件迁移。 电子邮件迁移完成后，使用此方法时将自动关闭目录同步。
    
    - 使用目录同步向导将用户同步到云。 按照为用户[设置目录同步Microsoft 365](../enterprise/set-up-directory-synchronization.md)中的步骤完成此过程。 将用户同步到云后，必须关闭云[Microsoft 365。](../enterprise/turn-off-directory-synchronization.md)
    
    您还必须向通过此方式添加的每个用户提供一个许可证Microsoft 365企业版。 可以在安装向导中完成 [此操作](set-up.md) ，也可以向 [用户分配许可证](../admin/manage/assign-licenses-to-users.md)。
    
### <a name="2-prepare-mobile-devices"></a>2：准备移动设备

按照为[企业用户设置](set-up-mobile-devices.md)Microsoft 365移动设备中的步骤在设备上安装 Office 应用，并确保它们受适用于Microsoft 365保护。 
  
### <a name="3-prepare-pcs"></a>3：准备电脑

管理员可以使用[AutoPilot](add-autopilot-devices-and-profile.md)为新的Windows 10电脑预Windows设置。 用户可以按照本主题中的步骤Windows 10设置现有或新的 Windows 10 设备：为商业用户设置 Windows 电脑[Microsoft 365。](set-up-windows-devices.md) 对于现有设备，用户可以 **选择**[将文件移动到OneDrive for Business。](move-files-to-onedrive.md) 他们还可使用第三方工具将与配置文件Windows文件OneDrive。
  
如果你的组织在本地使用 Windows Server Active Directory，你可以设置 Microsoft 365 for Business 来保护 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。 按照启用要[由企业Windows 10加入域](manage-windows-devices.md)的设备中的Microsoft 365设置此操作。 此方法为首选，并且此状态中的设备称为加入混合 **Azure AD 的设备**。 
  
如果你保留包含一些本地资源 (（如文件共享和打印机) ）的本地 Active Directory，你可以按照下面的步骤向加入 Azure **AD** 的设备授予对这些资源的访问权限：从 Microsoft 365 for business 中加入 [Azure AD](access-resources.md)的设备访问本地资源。
  
  
## <a name="contact-support"></a>联系技术支持部门

 **如需联系支持人员：**
  
- 请与合作伙伴联系。
    
- 作为Microsoft 365管理员，你可以访问我们的客户支持团队：联系商业产品支持人员 -**[管理员帮助](../business-video/get-help-support.md)**
    
## <a name="related-content"></a>相关内容

[Microsoft 365链接页 (](./index.yml)文档和资源) \
[管理Microsoft 365企业 (](manage.md)文章) \
[迁移到 Microsoft 365 for business (](migrate-to-microsoft-365-business.md)文章) \
[Microsoft 365 商业版培训视频](../business-video/index.yml)(链接页面)