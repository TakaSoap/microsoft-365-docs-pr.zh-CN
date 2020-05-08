---
title: 从 Microsoft 365 商业版中的 Azure AD 加入设备访问本地资源
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何从加入 Windows 10 设备的 Azure Active Directory 中获取本地资源（如业务线应用、文件共享和打印机）的访问权限。
ms.openlocfilehash: 980efbf09349cc0203ac50ae5e028c008d5694ca
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165893"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>从 Microsoft 365 商业高级版中的 Azure AD 加入设备访问本地资源

任何已加入 Azure Active Directory 的 Windows 10 设备都有权访问所有基于云的资源（如 Microsoft 365 应用），并且可以通过 Microsoft 365 商业高级版进行保护。 您还可以允许访问本地资源，如业务线（LOB）应用程序、文件共享和打印机。 若要允许访问，请使用[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)将本地 Active Directory 与 Azure active directory 同步。 

若要了解详细信息，请参阅[Azure Active Directory 中的设备管理简介](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。
以下各节也汇总了这些步骤。

> [!IMPORTANT]
> 此过程仅适用于 OAuth 和 NTLM。 Kerberos 不受支持。
 
## <a name="run-azure-ad-connect"></a>运行 Azure AD Connect

完成以下步骤，使组织的 Azure AD 加入设备能够访问本地资源。
  
1. 若要将您的用户、组和联系人从本地 Active Directory 同步到 Azure Active Directory，请运行目录同步向导和 Azure AD Connect，如[设置 Office 365 的目录同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)中所述。
    
2. 目录同步完成后，请确保你的组织的 Windows 10 设备已加入 Azure AD。 此步骤是在每个 Windows 10 设备上单独执行的。 有关详细信息，请参阅为[Microsoft 365 商业高级版用户设置 Windows 设备](set-up-windows-devices.md)。 
    
3. 一旦 Windows 10 设备加入了 Azure AD，每个用户都必须重新启动其设备，并使用其 Microsoft 365 商业高级凭据登录。 现在，所有设备都有权访问本地资源。
    
无需执行任何其他步骤即可访问 Azure AD 加入的设备的本地资源。 此功能内置在 Windows 10 中。 

如果您计划登录到 AADJ 设备而不是 password 方法（如通过 WHFB 凭据登录的 PIN/Bio 指标），然后访问本地资源（共享、打印机）。等），请按照https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
如果你的组织未准备好在上面所述的 Azure AD 联接的设备配置中进行部署，请考虑设置[混合 AZURE ad 已加入设备配置](manage-windows-devices.md)。
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>将 Windows 设备加入 Azure AD 时的注意事项

如果你的 Azure 加入的 Windows 设备之前已加入域或在工作组中，请考虑以下限制：
  
- 设备 Azure AD 加入时，它会在不引用现有配置文件的情况下创建新用户。 必须手动迁移配置文件。 用户配置文件包含收藏夹、本地文件、浏览器设置和「开始」菜单设置等信息。 最佳方法是查找第三方工具以将现有文件和设置映射到新的配置文件。

- 如果设备使用的是组策略对象（GPO），则某些 Gpo 在 Intune 中可能没有可比较的[配置服务提供程序](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)（CSP）。 运行[MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520)以查找现有 gpo 的可比较 csp。

- 用户将无法对依赖 Active Directory 身份验证的应用程序进行身份验证。 评估旧版应用程序，并考虑更新到使用新式身份验证的应用（如果可能）。

- Active Directory 打印机发现将不起作用。 您可以为所有用户提供直接打印机路径，也可以使用[混合云打印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。
