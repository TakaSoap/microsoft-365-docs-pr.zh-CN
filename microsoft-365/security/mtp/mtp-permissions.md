---
title: 在 Microsoft 365 安全中心管理对 Microsoft 365 Defender 数据的访问权限
description: 了解如何在 Microsoft 365 Defender 中管理对数据的权限
keywords: 访问, 权限, MTP, Microsoft 威胁防护, M365, 安全性, MCAS, MDATP, Cloud App Security, Microsoft Defender 高级威胁防护, 范围, 范围, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55b7b8c5755b773a4d53c95017a0a17a85495dee
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847244"
---
# <a name="manage-access-to-microsoft-365-defender"></a>管理对 Microsoft 365 Defender 的访问

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

分配了以下 Azure Active Directory (AD) 角色的帐户可以访问 Microsoft 365 Defender 功能和数据：
- 全局管理员
- 安全管理员
- 安全操作员
- 全局读取者
- 安全读取者

若要查看具有这些角色的帐户，请[在 Microsoft 365 安全中心中查看权限](https://security.microsoft.com/permissions)。

## <a name="access-to-functionality"></a>对功能的访问权限
对特定功能的访问权限由 [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)确定。 如果需要访问要求你或你的用户组分配有新角色的特定功能，请联系全局管理员。

### <a name="approve-pending-automated-tasks"></a>批准挂起的自动化任务
[自动调查和修复](mtp-autoir-actions.md)可以针对电子邮件、转发规则、文件、持久性机制和调查过程中找到的其他项目执行操作。 若要批准或拒绝需要显式审批的挂起操作，必须在 Microsoft 365 中分配特定角色。 若要了解详细信息，请参阅[操作中心权限](mtp-action-center.md#required-permissions-for-action-center-tasks)。

## <a name="access-to-data"></a>对数据的访问
可以使用为 Microsoft Defender 中的用户组分配的作用域来控制对 Microsoft 365 Defender 数据的访问权限， (RBAC) 。 如果你的访问未限定为 Defender for Endpoint 中的一组特定设备，你将拥有对 Microsoft 365 Defender 中的数据的完全访问权限。 但是，在限定帐户范围后，你将只看到有关范围内的设备的数据。

例如，如果您仅属于一个具有 Microsoft Defender for Endpoint 角色的用户组，并且该用户组已被授予仅对销售设备的访问权限，则你将仅在 Microsoft 365 Defender 中看到有关销售设备的数据。 [了解有关 Microsoft Defender for Endpoint 中的 RBAC 设置的详细信息](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security 访问控制
在预览过程中，Microsoft 365 Defender 不会强制实施基于云应用安全设置的访问控制。 这些设置不会影响对 Microsoft 365 Defender 数据的访问。

## <a name="related-topics"></a>相关主题

- [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender for Endpoint RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security 角色](https://docs.microsoft.com/cloud-app-security/manage-admins)
