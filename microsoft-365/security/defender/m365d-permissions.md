---
title: 在 Microsoft 365 安全中心管理对 Microsoft 365 Defender 数据的访问权限
description: 了解如何在 Microsoft 365 Defender 中管理对数据的权限
keywords: 访问, 权限, MTP, Microsoft 威胁防护, M365, 安全性, MCAS, MDATP, Cloud App Security, Microsoft Defender 高级威胁防护, 范围, 范围, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e1be2cf4d5510b2a31a61f848d7d99d6a6704d49
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056546"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>使用 Azure Active Directory 全局角色管理对 Microsoft 365 Defender 的访问权限

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

有两种方法可以管理对 Microsoft 365 Defender 的访问权限
- **全局 Azure Active Directory (AD) 角色**
- **自定义角色访问**

分配了以下全局 **Azure Active Directory (AD) 的帐户** 可以访问 Microsoft 365 Defender 功能和数据：
- 全局管理员
- 安全管理员
- 安全操作员
- 全局读取者
- 安全读取者

若要查看具有这些角色的帐户，请[在 Microsoft 365 安全中心中查看权限](https://security.microsoft.com/permissions)。

**自定义角色** 访问是 Microsoft 365 Defender 中的一项新功能，允许你管理对 Microsoft Defender 365 中特定数据、任务和功能的访问权限。 自定义角色提供比全局 Azure AD 角色更多的控制，从而仅为用户提供所需的访问权限以及所需的最小权限角色。  除了全局 Azure AD 角色之外，还可以创建自定义角色。 [详细了解自定义角色](custom-roles.md)。

> ![注意]本文仅适用于管理全局 Azure Active Directory 角色。 有关使用基于自定义角色的访问控制的信息，请参阅基于 [角色的访问控制的自定义角色](custom-roles.md)

## <a name="access-to-functionality"></a>对功能的访问权限
对特定功能的访问权限由 [Azure AD 角色](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)确定。 如果需要访问要求你或你的用户组分配有新角色的特定功能，请联系全局管理员。

### <a name="approve-pending-automated-tasks"></a>批准挂起的自动化任务
[自动调查和修复](m365d-autoir-actions.md)可以针对电子邮件、转发规则、文件、持久性机制和调查过程中找到的其他项目执行操作。 若要批准或拒绝需要显式审批的挂起操作，必须在 Microsoft 365 中分配特定角色。 若要了解详细信息，请参阅[操作中心权限](m365d-action-center.md#required-permissions-for-action-center-tasks)。

## <a name="access-to-data"></a>对数据的访问
可以使用在 Microsoft Defender 中为基于终结点角色的访问控制分配至用户组的范围控制对 Microsoft 365 Defender 数据 (RBAC) 。 如果你的访问范围尚未确定为 Defender for Endpoint 中的一组特定设备，你将具有对 Microsoft 365 Defender 中数据的完全访问权限。 但是，在限定帐户范围后，你将只看到有关范围内的设备的数据。

例如，如果你仅属于具有 Microsoft Defender for Endpoint 角色的一个用户组，并且该用户组只获得对销售设备的访问权限，你将只看到有关 Microsoft 365 Defender 中销售设备的数据。 [详细了解 Microsoft Defender for Endpoint 中的 RBAC 设置](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security 访问控制
在预览版中，Microsoft 365 Defender 不会基于 Cloud App Security 设置强制执行访问控制。 这些设置不会影响对 Microsoft 365 Defender 数据的访问。

## <a name="related-topics"></a>相关主题
- [Microsoft 365 Defender 基于角色的访问控制中的自定义角色](custom-roles.md)
- [Azure AD 角色](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [适用于终结点 RBAC 的 Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security 角色](/cloud-app-security/manage-admins)