---
title: 从已加入 Azure AD 的设备访问 Microsoft 365 业务中的本地资源
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.localizationpriority: medium
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何从已加入 Azure Active Directory 设备获取对本地资源（如业务线应用、文件共享和打印机Windows 10的访问权限。
ms.openlocfilehash: 311f49b340a6a66af22729c0ebe11bb9adb264a6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195121"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>从已加入 Azure AD 的设备访问本地Microsoft 365 商业高级版

本文适用于Microsoft 365 商业高级版。

已Windows 10设备Azure Active Directory所有基于云的资源（如 Microsoft 365 应用）的访问权限，并且受 Microsoft 365 商业高级版 保护。 还可以允许访问本地资源，如业务线 (LOB) 应用、文件共享和打印机。 若要允许访问，请使用[Azure AD 连接](/azure/active-directory/connect/active-directory-aadconnect)将本地 Active Directory 与 Azure Active Directory。

若要了解更多信息，请参阅 Azure Active Directory[中的设备管理简介](/azure/active-directory/device-management-introduction)。
以下各节还汇总了这些步骤。

## <a name="run-azure-ad-connect"></a>运行 Azure AD 连接

完成以下步骤，使已加入 Azure AD 的组织设备能够访问本地资源。

1. 若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory，请运行目录同步向导和 Azure AD 连接如为 Office 365[设置目录同步中所述](../../enterprise/set-up-directory-synchronization.md)。

2. 目录同步完成后，请确保组织的 Windows 10设备已加入 Azure AD。 此步骤在每个设备上单独Windows 10完成。 有关详细信息[，Windows为Microsoft 365 商业高级版设置设备](set-up-windows-devices.md)。

3. 加入 Windows 10设备后，每个用户必须重新启动其设备，然后使用其 Microsoft 365 商业高级版 凭据登录。 所有设备现在也有权访问本地资源。

无需执行其他步骤，就无需访问加入 Azure AD 的设备本地资源。 此功能内置于Windows 10。

如果你计划通过 WHFB 凭据登录登录到 AADJ 设备（如 PIN/Bio-metric），然后访问本地资源 (共享、打印机等 ) ，请按照本文 [操作](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)。

如果你的组织尚未准备好在上文所述的加入 Azure AD 的设备配置中部署，请考虑设置已加入 [Azure AD 的混合设备配置](manage-windows-devices.md)。

### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>将设备加入 Windows Azure AD 的注意事项

如果你Windows Azure-AD 加入的设备之前已加入域或工作组中，请考虑以下限制：

- 当设备 Azure AD 加入时，它将创建一个新用户，而无需引用现有配置文件。 必须手动迁移配置文件。 用户配置文件包含收藏夹、本地文件、浏览器设置和浏览器"开始"菜单设置。 最佳方法是查找将现有文件和设置映射到新配置文件的第三方工具。

- 如果设备使用组策略对象 (GPO) ，则某些 GPO 在 Intune 中可能没有[](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (配置) 提供程序。 运行 [MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520) 以查找现有 GPO 的可比较的 CSP。

- 用户可能无法对依赖于 Active Directory 身份验证的应用程序进行身份验证。 评估旧应用，并考虑更新到使用新式身份验证的应用（如果可能）。

- Active Directory 打印机发现将不起作用。 您可以为所有用户提供直接打印机路径或使用 [通用打印](/universal-print/)。

### <a name="related-articles"></a>相关文章

[Azure AD 连接](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
