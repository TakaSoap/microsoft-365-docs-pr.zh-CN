---
title: 访问本地资源从 Microsoft 365 企业版中的 Azure AD 加入设备
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何获取的本地资源的访问权限，如业务线应用程序、 文件共享和 Azure Active Directory 中的打印机加入 Windows 10 设备。
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865426"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>访问本地资源从 Microsoft 365 企业版中的 Azure AD 加入设备

Azure Active Directory 加入任何 Windows 10 设备将可以访问所有的基于云的资源，例如您的 Office 365 应用程序，并可以受 Microsoft 365 企业版。此外允许访问本地资源，例如业务线 (LOB) 应用程序、 文件共享和打印机，您必须使用[Azure AD 连接](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)与 Azure Active Directory 同步您的本地 Active Directory。请参阅[在 Azure Active Directory 中的设备管理的简介](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction)了解详细信息。 
  
## <a name="run-azure-ad-connect"></a>运行 Azure AD 连接

完成以下步骤来启用组织的 Azure AD 加入设备访问的本地资源。
  
1. 若要将您的用户、 组和联系人从本地 Active Directory 同步到 Azure Active Directory 中，运行目录同步向导，并[设置 Office 365 的目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)中所述为 Azure AD 连接。
    
2. 完成目录同步后，确保您的组织的 Windows 10 设备都加入的 Azure AD。每个 Windows 10 设备上单独完成此步骤。有关详细信息，请参阅[设置 Microsoft 365 业务用户的 Windows 设备](set-up-windows-devices.md)。 
    
3. 加入的 Azure AD 的 Windows 10 设备后，每个用户应重新启动其设备和使用其 Microsoft 365 业务凭据登录。现在，所有设备将都可以访问以及本地资源。
    
无需其他步骤所需获取访问内部的 Azure AD 资源加入设备。这是 Windows 10 中可用的内置功能。 
  
如果贵组织尚未准备好在 Azure AD 加入设备上述配置中部署，请考虑[混合 Azure AD 加入设备配置](manage-windows-devices.md)的设置。
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>加入到 Azure AD 的 Windows 设备时的注意事项

如果您是加入先前已加入域的 Windows 设备的 Azure AD 或工作组中，您需要考虑以下限制：
  
- 当设备 Azure AD 加入时，它没有引用现有配置文件创建一个新用户。若要解决此问题，需要手动迁移配置文件。用户配置文件包含类似收藏夹、 本地文件、 浏览器设置、 开始菜单设置等信息。最佳做法是找到用于将现有文件和设置映射到新的配置文件的第三方工具
    
- 如果设备正在使用组策略对象 (GPO)，某些 Gpo 可能没有相当[配置服务提供程序](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)(CSP) Intune 中。运行[MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520)以查找现有的 Gpo 相当 Csp。 
    
- 用户不能对应用程序依赖于 Active Directory 身份验证进行身份验证。处理此评估使用旧应用程序，并考虑更新到尽可能使用现代身份验证应用程序。
    
- Active Directory 打印机发现不起作用。若要解决此问题，为所有用户提供直接打印机路径或利用[混合云打印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。
    

