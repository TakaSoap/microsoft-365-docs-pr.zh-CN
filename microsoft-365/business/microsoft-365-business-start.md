---
title: Microsoft 365 Business 入门
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 了解如何设置 Microsoft 365 商业版。
ms.openlocfilehash: 5986e3fb7786ebb3fa7bcf42b34345be98af44a2
ms.sourcegitcommit: 9a057e70637dcfe06d4f729a96c02be989cf9e25
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38633421"
---
# <a name="get-started-with-microsoft-365-business"></a>Microsoft 365 Business 入门

## <a name="what-is-microsoft-365-business"></a>什么是 Microsoft 365 业务

Microsoft 365 商业版是一组全面的业务效率和协作工具，如 Outlook、Word、Excel 和其他 Office 产品，它们始终处于最新状态。 您可以使用易于管理的企业级安全性来保护所有 iOS、Android 和 Windows 10 设备上的工作文件。
  
Microsoft 365 商业版适用于最高300的许可证。 如果你需要更多许可证，请参阅[Microsoft 365 企业版](https://go.microsoft.com/fwlink/p/?linkid=860986)文档以了解详细信息。 
  
## <a name="get-microsoft-365-business"></a>获取 Microsoft 365 商业版

- 如果你有合作伙伴，他们将获得 Microsoft 365 商业版：[从 Microsoft 合作伙伴中心获取 microsoft 365 商业](get-microsoft-365-business.md)版。
    
- 如果你没有合作伙伴并且想要获取 Microsoft 365 商业版，你可以在[此处购买它](https://www.microsoft.com/microsoft-365/business)。
    
## <a name="set-up-microsoft-365-business"></a>设置 Microsoft 365 商业版

 **Microsoft 365 业务套件设置概述**
  
下图介绍了管理员如何设置 Microsoft 365 商业版。 还介绍为 Microsoft 365 商业版 准备 Windows 电脑的步骤。 您还可以使用[Windows AutoPilot](add-autopilot-devices-and-profile.md)在 Microsoft 365 商业版管理中心添加新设备。 您可以使用 AutoPilot 设置和预配置新设备，以便用户可以在用户使用其 Microsoft 365 业务凭据登录后立即进行生产。
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1：设置 Microsoft 365 商业版（管理员）

使用全局管理员凭据登录[Microsoft 365 商业版管理中心](https://portal.office.com/adminportal/home)，并完成以下步骤以设置 Microsoft 365 商业版。 
  
1. [使用 Microsoft 365 Business 保护设备上的数据的先决条件](pre-requisites-for-data-protection.md)
    
    先阅读先决条件，以确保你的设备已准备好安装 Microsoft 365 商业版。
    
2. [使用安装向导设置 Microsoft 365 商业版](set-up.md)
    
    如果要将**本地 Active Directory 永久移动到云**，可以转到 Microsoft 365 Business 管理中心，并使用安装向导手动添加用户，也可以执行与 Azure AD Connect 的一次性同步。 可通过 2 种方法执行此操作： 
    
    - 如果你还具有 Exchange 2010、Exchange 2013 或 Exchange 2016 服务器，则可以[使用最少混合将 Exchange 邮箱快速迁移到 Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef)。 最小混合步骤包括将用户一次性同步到 Azure AD，并将电子邮件从本地迁移到云。 电子邮件迁移完成后，使用此方法时，目录同步将自动关闭。
    
    - 使用 Office 365 目录同步向导将您的用户与云同步。 请按照[设置 Office 365 目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)中的步骤来完成此过程。 将用户同步到云后，必须[关闭 Office 365 的目录同步](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d)。
    
    此外，还必须为以这种方式添加的每个用户提供 Microsoft 365 商业版的许可证。 可以在 "[安装向导](set-up.md)" 中执行此操作，也可以在[Office 365 for business 中向用户分配许可证](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC)。
    
### <a name="2-prepare-mobile-devices"></a>2：准备移动设备

按照[为 microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)中的步骤，在设备上安装 Office 应用，并确保它们受 Microsoft 365 商业版的保护。 
  
### <a name="3-prepare-pcs"></a>3：准备电脑

管理员可以使用[Windows AutoPilot](add-autopilot-devices-and-profile.md)为新的 Windows 10 电脑预选择设置。 用户可以按照本主题中的步骤设置其现有的或新的 Windows 10 设备：[为 Microsoft 365 商业版用户设置 Windows 电脑](set-up-windows-devices.md)。 对于现有设备，用户可以**选择**[将文件移动到 OneDrive for](move-files-to-onedrive.md)business。 他们还可以使用第三方工具将与 Windows 配置文件关联的文件移动到 OneDrive。
  
如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。 按照 Microsoft 365 商业版中的 "[启用加入域的 Windows 10 设备](manage-windows-devices.md)" 中的步骤进行操作，以便对此进行设置。 此方法是首选方法，在此状态的设备称为**混合 AZURE AD 加入的设备**。 
  
如果保留包含某些本地资源（如文件共享和打印机）的本地 Active Directory，则可以通过以下步骤向**AZURE ad 联接设备**授予对这些资源的访问权限：[从 Microsoft 365 商业版中的 Azure AD 加入设备访问本地资源](access-resources.md)。
  
设置 Windows 10 电脑后，可以将[Office 自动安装](auto-install-or-uninstall-office.md)到设备上。 
  
## <a name="contact-support"></a>联系支持人员

 **如需联系支持人员：**
  
- 请与合作伙伴联系。
    
- 作为 Microsoft 365 商业版管理员，你可以访问我们的客户支持团队： **[联系商业版产品支持人员-管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>相关主题
[Microsoft 365 Business documentation and resources](https://go.microsoft.com/fwlink/p/?linkid=853701)（Microsoft 365 Business 文档和资源）
  
[管理 microsoft 365 业务](manage.md)[迁移到 microsoft 365 业务](migrate-to-microsoft-365-business.md)
  

