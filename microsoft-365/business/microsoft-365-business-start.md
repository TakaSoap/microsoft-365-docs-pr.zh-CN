---
title: Microsoft 365 Business 入门
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 了解如何设置 Microsoft 365 企业版。
ms.openlocfilehash: 1c4adc64f62f7d4ae5038603804aa10e48d8a6e1
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866041"
---
# <a name="get-started-with-microsoft-365-business"></a>Microsoft 365 Business 入门

## <a name="what-is-microsoft-365-business"></a>什么是 Microsoft 365 Business

Microsoft 365 Business 是一套功能全面的业务生产和协作工具，如 Outlook、Word、Excel 和始终不断优化的其他 Office 产品。可通过易于管理的企业级安全性保护所有 iOS、Android 和 Windows 10 设备上的工作文件。
  
如果您需要更多许可证，Microsoft 365 业务旨在最多 300 许可证，请参阅[Microsoft 365 企业版](https://go.microsoft.com/fwlink/p/?linkid=860986)的详细信息的文档。 
  
## <a name="get-microsoft-365-business"></a>获取 Microsoft 365 商业版

- 如果有合作伙伴，他们将获取 Microsoft 365 商业版：[从 Microsoft 合作伙伴中心获取 Microsoft 365 商业版](get-microsoft-365-business.md)。
    
- 如果您不具有合作伙伴并希望获取 Microsoft 365 企业版，则可以[购买此处](https://www.microsoft.com/en-us/microsoft-365/business)。
    
## <a name="set-up-microsoft-365-business"></a>设置 Microsoft 365 商业版

 **Microsoft 365 业务套件设置概述**
  
下图描述了管理员如何设置 Microsoft 365 企业版。该参数还描述为 Microsoft 365 业务准备 Windows Pc 的步骤。此外可以在 Microsoft 365 业务管理中心与[Windows 自动执行某些操作](add-autopilot-devices-and-profile.md)添加到新设备。您可以使用自动执行某些操作设置和预配置新的设备，只要用户使用使用其 Microsoft 365 业务凭据供使用效率获取。
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1： 设置 Microsoft 365 企业版 （管理员）

使用全局管理员凭据登录 [Microsoft 365 商业版管理中心](https://portal.office.com/adminportal/home)，并完成以下步骤设置 Microsoft 365 商业版。 
  
1. [通过 Microsoft 365 商业版保护设备上的数据的先决条件](pre-requisites-for-data-protection.md)
    
    请先阅读先决条件以确保设备已为 Microsoft 365 商业版 做好准备。
    
2. [使用安装向导安装 Microsoft 365 Business](set-up.md)
    
    如果您是**从云到本地 Active Directory 永久移动**，您可以添加用户手动在 Microsoft 365 业务管理中心使用安装向导中，或者您可以与 Azure AD 连接一次性同步。有两种方法来执行此操作： 
    
  - 如果您还具有 Exchange 2010、 Exchange 2013 或 Exchange 2016 服务器，您还可以[使用最少混合快速迁移到 Office 365 的 Exchange 邮箱](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef)。最简单的混合步骤包括用户迁移到 Azure AD 的一次性同步以及电子邮件从内部部署迁移到云中。在电子邮件迁移完成后，使用此方法时自动关闭目录同步。
    
  - 使用 Office 365 目录同步向导将用户同步到云。请按照[设置 Office 365 目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)中的步骤来完成此过程。将用户同步到云后，需要[关闭目录同步](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d)。
    
    您还需要为每个用户添加到 Microsoft 365 企业版许可证这种方式。在[安装向导](set-up.md)中，或[分配给为企业的 Office 365 中的用户的许可证](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC)，您可以这样做。
    
### <a name="2-prepare-mobile-devices"></a>2： 准备移动设备

按照[设置适用于 Microsoft 365 业务用户的移动设备](set-up-mobile-devices.md)在设备和确保受 Microsoft 365 企业版上安装 Office 应用程序中的步骤。 
  
### <a name="3-prepare-pcs"></a>3： 准备 Pc

管理员可以使用[Windows 自动执行某些操作](add-autopilot-devices-and-profile.md)前选择新设备 Windows 10 Pc 的设置。用户可以设置其现有或新 Windows 10 设备按照本主题中的步骤：[设置为 Microsoft 365 业务用户的 Windows Pc](set-up-windows-devices.md)。现有的设备用户还可以**选择**[移动到 OneDrive for Business 的文件](move-files-to-onedrive.md)。他们还可以使用第三方工具移动到 OneDrive Windows 配置文件相关联的文件。
  
如果您的组织使用 Windows Server Active Directory 部署，您可以设置 Microsoft 365 业务保护 Windows 10 设备，同时保持需要本地身份验证的本地资源的访问权限。按照中[启用 Windows 10 加入域的设备由 Microsoft 365 业务管理](manage-windows-devices.md)此设置的步骤。这是首选的方法，在此状态的设备称为**混合 Azure AD 加入设备**。 
  
如果保持本地 Active Directory，其中包含一些部署资源 （如文件共享和打印机），您可以按照下面的步骤移交给这些资源**Azure AD 加入设备**访问：[访问内部部署中的资源Microsoft 365 企业版中的 azure AD 加入设备](access-resources.md)。
  
您已设置 Windows 10 Pc 后，您可以对设备[自动安装 Office](auto-install-or-uninstall-office.md) 。 
  
## <a name="contact-support"></a>联系支持人员

 **如需联系支持人员：**
  
- 请与合作伙伴联系。
    
- 作为 Microsoft 365 企业版管理员必须对我们的客户支持团队，**[业务产品-管理员技术支持联系人](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)的访问**
    
## <a name="related-topics"></a>相关主题
[Microsoft 365 Business documentation and resources](https://go.microsoft.com/fwlink/p/?linkid=853701)（Microsoft 365 Business 文档和资源）
  
[管理 Microsoft 365 业务](manage.md)[迁移到 Microsoft 365 业务](migrate-to-microsoft-365-business.md)
  

