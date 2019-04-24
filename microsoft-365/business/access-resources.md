---
title: 从 Microsoft 365 商业版中的 Azure AD 加入设备访问本地资源
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何从加入 Windows 10 设备的 Azure Active Directory 中获取本地资源 (如业务线应用、文件共享和打印机) 的访问权限。
ms.openlocfilehash: 212685bc229f519152e69b09d0a745bfac7a38cd
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276873"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>从 Microsoft 365 商业版中的 Azure AD 加入设备访问本地资源

任何已加入 Azure Active Directory 的 Windows 10 设备都将有权访问所有基于云的资源 (如 Office 365 应用程序), 并可通过 Microsoft 365 商业版进行保护。 若要同时允许访问本地资源 (如业务线 (LOB) 应用程序、文件共享和打印机), 您必须使用[azure AD Connect 将](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)本地 Active directory 与 azure active directory 同步。 若要了解详细信息, 请参阅[Azure Active Directory 中的设备管理简介](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction)。 
  
## <a name="run-azure-ad-connect"></a>运行 Azure AD Connect

完成以下步骤, 使组织的 Azure AD 加入设备能够访问本地资源。
  
1. 若要将您的用户、组和联系人从本地 Active directory 同步到 Azure Active directory, 请运行目录同步向导和 Azure AD Connect, 如[设置 Office 365 的 "设置目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)" 中所述。
    
2. 目录同步完成后, 请确保你的组织的 Windows 10 设备已加入 Azure AD。 此步骤是在每个 Windows 10 设备上单独执行的。 有关详细信息, 请参阅为[Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)。 
    
3. 一旦 Windows 10 设备加入了 Azure AD, 每个用户都应重新启动其设备并使用其 Microsoft 365 商业版凭据登录。 所有设备现在都可以访问本地资源。
    
无需执行任何其他步骤即可访问 Azure AD 加入设备的本地资源。 这是 Windows 10 中提供的内置功能。 
  
如果你的组织未准备好在上述 Azure ad 联接的设备配置中进行部署, 请考虑设置[混合 Azure ad 已加入设备配置](manage-windows-devices.md)。
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>将 Windows 设备加入 Azure AD 时的注意事项

如果 Azure AD 加入之前已加入域或在工作组中的 Windows 设备, 则需要考虑以下限制:
  
- 设备 Azure AD 加入时, 它会在不引用现有配置文件的情况下创建新用户。 若要解决此问题, 需要手动迁移配置文件。 用户配置文件包含诸如收藏夹、本地文件、浏览器设置、"开始" 菜单设置等信息。一种最佳方法是查找第三方工具以将现有文件和设置映射到新的配置文件
    
- 如果设备使用的是组策略对象 (GPO), 则某些 gpo 在 Intune 中可能没有可比较的[配置服务提供程序](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)(CSP)。 运行[MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520)以查找现有 gpo 的可比较 csp。 
    
- 用户将无法对依赖 Active Directory 身份验证的应用程序进行身份验证。 若要处理此评估, 请使用旧版应用程序, 并考虑更新到使用新式身份验证的应用 (如果可能)。
    
- Active Directory 打印机发现将不起作用。 若要解决此问题, 请为所有用户提供直接打印机路径, 或利用[混合云打印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。
    

