---
title: 访问管理门户
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
description: 如何查找和使用管理门户，包括控制对管理门户的访问。
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 09427d163b8b5e47911b6df26e5acf0fcd1f3524
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841347"
---
# <a name="access-the-admin-portal"></a>访问管理门户

Microsoft 托管桌面服务的网关是 Microsoft [Azure 门户](https://portal.azure.com)。 有关通常使用和自定义 Azure 门户体验的更多信息，请参阅 [Azure 门户文档](https://docs.microsoft.com/azure/azure-portal/)。 现在可在预览版中查看，还可以在 Microsoft Endpoint Manager 中查找 [Microsoft 托管桌面](https://endpoint.microsoft.com/)。 如果你不熟悉此门户的设备管理功能，请参阅 [Microsoft Endpoint Manager 文档](https://docs.microsoft.com/mem/)。

> [!NOTE]
> 但是，选择在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 或 [Azure](https://portal.azure.com)门户中访问 Microsoft 托管桌面，支持以下浏览器：
> - Microsoft Edge (最新版本) 
> - Microsoft Internet Explorer 11
> - Safari (最新版本，仅 Mac) 
> - Chrome (最新版本) 
> - Firefox (最新版本) 

管理帐户需要特定权限才能访问 Azure 门户或 Microsoft Endpoint Manager 中的 Microsoft 托管桌面管理功能。 您可以使用基于角色的访问控制或 RBAC (管理对组织中这些功能的管理员) 。 多个 Azure Active Directory (Azure AD) 管理员角色和内置自定义角色可用于为 Microsoft 托管桌面管理门户中的不同功能提供更精细的控制。 有关 Azure Active Directory 角色详细信息，请参阅 [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 与应用于各种 Microsoft 产品和服务的 Azure AD 管理员角色不同，自定义角色特定于 Microsoft 托管桌面，并且仅保证访问此服务的管理员功能。 管理员可以单独或结合 Azure AD 管理员角色向用户分配自定义角色，以向现有管理员帐户添加 Microsoft 托管桌面权限。

可以分配以下每个角色以提供不同级别的访问：

|Azure AD 角色  |Microsoft 托管桌面权限  |
|---------|---------|
|全局管理员     | 具有此角色的 **管理员将拥有** 对 Microsoft 托管桌面管理门户中所有功能的读取和写入权限。         |
|全局读取者     | 具有此角色的 **管理员将具有** 对 Microsoft 托管桌面管理门户中所有功能的只读权限。         |
|Intune 服务管理员     |  具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中与安全不相关的功能的读取和写入权限。       |
|服务支持管理员     | 具有此角色的管理员将具有对与安全不相关的功能的只读权限，并且具有在Microsoft 托管桌面管理门户中管理支持请求的写入权限。         |
|安全管理员 | 具有此角色的管理员将拥有针对所有功能的只读权限，并且对管理门户中的 Microsoft 托管桌面中的与安全相关的功能具有写入权限。 |
|安全读取者 |具有此角色的 **管理员将具有** 对 Microsoft 托管桌面管理门户中所有功能的只读权限。|

> [!IMPORTANT]
> 只有全局管理员角色才具有在 Microsoft 托管桌面中注册组织所需的权限。 请注意，Azure Active Directory 角色将为用户帐户提供跨各种 Microsoft 服务的权限。 完成 Microsoft 托管桌面的注册后，应始终使用具有完成其他任务所需的最低权限的角色。

 
|自定义角色  |Microsoft 托管桌面权限  |
|---------|---------|
|Microsoft 托管桌面服务管理员  | 分配给用户时，此角色授予管理员对 Microsoft托管桌面管理门户中与安全不相关的功能的读取和写入权限。  |
|Microsoft Managed Desktop Service Reader | 分配给用户时，此角色授予管理员对 Microsoft托管桌面管理门户中与安全不相关的功能的只读权限。 |
|Microsoft 托管桌面安全管理器 |分配给用户时，此角色仅授予管理员对 Microsoft托管桌面管理门户中与安全相关的功能的读取和写入权限。   |

> [!NOTE]
> 安全功能包括与安全相关的通信、安全联系人的管理、安全相关支持请求的管理以及安全相关报告的访问权限。 

## <a name="assigning-roles-to-administrators"></a>向管理员分配角色

如果需要有关分配 Azure Active Directory 角色的帮助，请参阅 [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。

为了便于管理内置角色，每个自定义角色都有一个安全组 (例如，"新式工作区角色 – 安全管理器") 。 若要将用户分配到其中一个安全组，请按照以下步骤操作：
1.  转到 Microsoft Endpoint Manager 门户。
2.  选择 **左侧** 的组。
3.  搜索 **新式工作区角色**，然后选择与要分配的角色关联的组。 
4.  选择 **左侧** 的成员，然后选择 **命令栏上的 +** 添加成员。
5.  输入要添加的人的电子邮件。 如果他们是来宾，必须先邀请他们，然后才能分配组。
6.  选择 **底部的** "选择"。

> [!NOTE]
> 当前不支持嵌套角色分配组。 
