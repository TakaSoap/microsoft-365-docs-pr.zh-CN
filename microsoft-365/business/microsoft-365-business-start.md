---
title: Microsoft 365 商业版入门
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
description: 了解 Microsoft 365 商业版、如何设置它，以及如何准备用户的设备和电脑以确保它们受 Microsoft 365 商业版保护。
ms.openlocfilehash: 83bd2ff87683c1ad810d20658ba20f3229408968
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580086"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Microsoft 365 商业版入门

## <a name="what-is-microsoft-365-for-business"></a>什么是 Microsoft 365 商业版

Microsoft 365 商业版是一套全面的业务生产力和协作工具，如 Outlook、Word、Excel 和其他 Office 产品，始终保持最新。 可以使用易于管理的企业级安全性保护所有 iOS、Android 和 Windows 10 设备上的工作文件。

观看此视频，快速了解 Microsoft 365 商业版。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 商业版最多支持 300 个许可证。 如果需要更多许可证，请参阅 [Microsoft 365 企业版](../enterprise/index.yml)文档，以了解详细信息。 
  
## <a name="get-microsoft-365-for-business"></a>获取 Microsoft 365 商业版

- 如果你有合作伙伴，他们将获得 Microsoft 365 商业版：从 Microsoft 合作伙伴中心获取 [Microsoft 365 商业版](get-microsoft-365-business.md)。
    
- 如果你没有合作伙伴并且想要获取 Microsoft 365 商业版，可以 [在此处购买](https://www.microsoft.com/microsoft-365/business)。
    
## <a name="set-up-microsoft-365-for-business"></a>设置 Microsoft 365 商业版

 **Microsoft 365 商业版套件设置概述**
  
下图介绍了管理员如何设置 Microsoft 365 商业版。 它还介绍了为 Microsoft 365 商业版准备 Windows 电脑的步骤。 还可使用 [Windows AutoPilot](add-autopilot-devices-and-profile.md)在 Microsoft 365 管理中心添加新设备。 可以使用 AutoPilot 设置和预配置新设备，以便用户使用其 Microsoft 365 商业版凭据登录后即可将其用于高效使用。
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

观看此视频，了解 Microsoft 365 商业版设置概述。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1：设置 Microsoft 365 商业版 (管理员) 

使用全局管理员 [凭据登录到 Microsoft 365](https://portal.office.com/adminportal/home) 管理中心，并完成以下步骤以设置 Microsoft 365 商业版。 
  
1. [使用 Microsoft 365 商业版保护设备上数据的先决条件](pre-requisites-for-data-protection.md)
    
    首先阅读先决条件，确保你的设备已准备好使用 Microsoft 365 商业版。
    
2. [使用设置向导设置 Microsoft 365 商业版](set-up.md)
    
    如果你正在从本地 **Active Directory** 永久移动到云，可以转到 Microsoft 365 管理中心并使用设置向导手动添加用户，或者可以与 Azure AD Connect 进行一次同步。 可通过 2 种方法执行此操作： 
    
    - 如果还有 Exchange 2010、Exchange 2013 或 Exchange 2016 服务器，可以使用最小混合快速将 Exchange 邮箱迁移到[Microsoft 365。](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate) 最少混合步骤包括用户到 Azure AD 的一次同步，以及从本地到云的电子邮件迁移。 电子邮件迁移完成后，使用此方法时将自动关闭目录同步。
    
    - 使用目录同步向导将用户同步到云。 按照为 [Microsoft 365](../enterprise/set-up-directory-synchronization.md) 设置目录同步中的步骤完成此过程。 将用户同步到云后，必须关闭 [Microsoft 365 的目录同步](../enterprise/turn-off-directory-synchronization.md)。
    
    你还必须向通过此方式添加的每个用户授予 Microsoft 365 商业版许可证。 可以在安装向导中完成 [此操作](set-up.md) ，也可以向 [用户分配许可证](../admin/manage/assign-licenses-to-users.md)。
    
### <a name="2-prepare-mobile-devices"></a>2：准备移动设备

按照为 [Microsoft 365](set-up-mobile-devices.md) 商业版用户设置移动设备中的步骤在设备上安装 Office 应用，并确保它们受 Microsoft 365 商业版保护。 
  
### <a name="3-prepare-pcs"></a>3：准备电脑

管理员可以使用 [Windows AutoPilot](add-autopilot-devices-and-profile.md)预选择新 Windows 10 电脑的设置。 用户可以按照本主题中的步骤设置现有或新的 Windows 10 设备：为 Microsoft [365](set-up-windows-devices.md)商业版用户设置 Windows 电脑。 对于现有设备，用户可以 **选择**[将文件移动到 OneDrive for Business](move-files-to-onedrive.md)。 他们还可使用第三方工具将与 Windows 配置文件关联的文件移动到 OneDrive。
  
如果你的组织使用本地 Windows Server Active Directory，你可以设置 Microsoft 365 商业版来保护你的 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。 请按照允许 [Microsoft 365](manage-windows-devices.md) 商业版管理已加入域的 Windows 10 设备中的步骤进行设置。 此方法为首选，并且此状态中的设备称为加入混合 **Azure AD 的设备**。 
  
如果你保留包含一些本地资源 (例如文件共享和打印机) 的本地 Active Directory，你可以按照以下步骤向加入 Azure **AD** 的设备授予对这些资源的访问权限：从 [Microsoft 365](access-resources.md)商业版中加入 Azure AD 的设备访问本地资源。
  
  
## <a name="contact-support"></a>联系支持人员

 **如需联系支持人员：**
  
- 请与合作伙伴联系。
    
- 作为 Microsoft 365 商业版管理员，你可以访问我们的客户支持团队：联系商业版产品支持 **[人员 - 管理员帮助](../admin/contact-support-for-business-products.md)**
    
## <a name="see-also"></a>另请参阅

[Microsoft 365 商业版文档和资源](./index.yml)
  
[管理 Microsoft 365 商业版](manage.md)[迁移到 Microsoft 365 商业版](migrate-to-microsoft-365-business.md)

[Microsoft 365 商业版培训视频](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)