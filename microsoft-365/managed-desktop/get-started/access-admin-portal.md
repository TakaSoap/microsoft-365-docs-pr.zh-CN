---
title: 访问管理门户
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 420cdaabb607eacf0d7a7109827fe5437e2f999c
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530219"
---
# <a name="access-the-admin-portal"></a>访问管理门户

你的 Microsoft 托管桌面服务的网关是 Microsoft [Azure 门户](https://portal.azure.com)。 有关通常情况下使用和自定义 Azure 门户体验的详细信息，请参阅[azure 门户文档](https://docs.microsoft.com/azure/azure-portal/)。 在预览中，您还可以在[Microsoft 终结点管理器](https://endpoint.microsoft.com/)中找到 Microsoft 托管桌面。 如果你不熟悉此门户的设备管理功能，请参阅[Microsoft 终结点管理器文档](https://docs.microsoft.com/mem/)。

您的管理帐户需要特定的权限才能访问 Microsoft 托管桌面管理门户。 通过使用基于角色的访问控制（RBAC），可以管理对组织中这些功能的管理员访问。 有关 Azure Active Directory 角色的详细信息，请参阅[Azure Active directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。

为您的管理员用户帐户分配以下任何角色以确保访问：

|Azure AD 角色  |Microsoft 托管桌面权限  |
|---------|---------|
|全局管理员     | 具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中所有功能的**读取和写入权限**。         |
|全局读取者     | 具有此角色的管理员将对 Microsoft 托管桌面管理门户中的所有功能具有**只读权限**。         |
|Intune 服务管理员     |  具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中所有功能的**读取和写入权限**。       |
|服务支持管理员     | 具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中所有功能的**读取和写入权限**。         |

> [!IMPORTANT]
> 只有全局管理员角色才具有在 Microsoft 托管桌面中*注册*组织所需的权限。 请注意，Azure Active Directory 角色将在各种 Microsoft 服务中提供用户帐户权限。 在 Microsoft 托管桌面完成注册后，应始终使用具有完成其他任务所需的*最少*权限的角色。

## <a name="assigning-roles-to-administrators"></a>向管理员分配角色

如果你需要有关分配 Azure Active Directory 角色的帮助，请参阅[Azure Active directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。
