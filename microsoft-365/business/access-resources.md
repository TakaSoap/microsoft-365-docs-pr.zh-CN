---
title: 在 Microsoft 365 商业版中从加入 Azure AD 的设备访问本地资源
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何从加入 Azure Active Directory 的 Windows 10 设备获取对本地资源（如业务线应用、文件共享和打印机）的访问权限。
ms.openlocfilehash: b78509d72cbd9b3c121039c4965625bf5c21c7e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913514"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>在 Microsoft 365 商业高级版中从加入 Azure AD 的设备访问本地资源

本文适用于 Microsoft 365 商业高级版。

加入 Azure Active Directory 的任何 Windows 10 设备都有权访问所有基于云的资源（如 Microsoft 365 应用）并受 Microsoft 365 商业高级版保护。 还可以允许访问本地资源，如业务线 (LOB) 应用、文件共享和打印机。 若要允许访问，请使用 [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) 将本地 Active Directory 与 Azure Active Directory 同步。 

若要了解更多信息，请参阅 [Azure Active Directory 中的设备管理简介](/azure/active-directory/device-management-introduction)。
以下各节还汇总了这些步骤。
 
## <a name="run-azure-ad-connect"></a>运行 Azure AD Connect

完成以下步骤，使已加入 Azure AD 的组织设备能够访问本地资源。
  
1. 若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory，请运行目录同步向导和 Azure AD Connect，如设置 [Office 365](../enterprise/set-up-directory-synchronization.md)的目录同步中所述。
    
2. 目录同步完成后，请确保组织的 Windows 10 设备已加入 Azure AD。 此步骤在每个 Windows 10 设备上单独完成。 有关详细信息 [，请参阅为 Microsoft 365 商业高级版用户](set-up-windows-devices.md) 设置 Windows 设备。 
    
3. Windows 10 设备加入 Azure AD 后，每个用户必须重新启动其设备，然后使用其 Microsoft 365 商业高级版凭据登录。 所有设备现在也有权访问本地资源。
    
无需执行其他步骤，就无需访问加入 Azure AD 的设备本地资源。 此功能内置于 Windows 10 中。 

如果你计划通过 WHFB 凭据登录登录到 AADJ 设备（如 PIN/Bio-metric）而不是密码方法，然后访问本地资源 (共享、打印机。等) ，请关注 https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
如果你的组织尚未准备好在上文所述的加入 Azure AD 的设备配置中部署，请考虑设置已加入 [Azure AD 的混合设备配置](manage-windows-devices.md)。
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>将 Windows 设备加入到 Azure AD 的注意事项

如果加入 Azure-AD 的 Windows 设备之前已加入域或工作组，请考虑以下限制：
  
- 当设备 Azure AD 加入时，它将创建一个新用户，而无需引用现有配置文件。 必须手动迁移配置文件。 用户配置文件包含收藏夹、本地文件、浏览器设置和"开始"菜单设置等信息。 最佳方法是查找第三方工具，将现有文件和设置映射到新配置文件。

- 如果设备使用组策略对象 (GPO) ，则某些 GPO 在 Intune 中可能[](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (配置服务提供程序) 相当。 运行 [MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520) 以查找现有 GPO 的可比较的 CSP。

- 用户可能无法对依赖于 Active Directory 身份验证的应用程序进行身份验证。 评估旧应用，并考虑更新到使用新式身份验证的应用（如果可能）。

- Active Directory 打印机发现将不起作用。 可以为所有用户提供直接打印机路径或使用 [通用打印](/universal-print/)。