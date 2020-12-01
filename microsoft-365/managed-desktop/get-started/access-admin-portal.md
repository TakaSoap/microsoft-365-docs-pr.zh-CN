---
title: 访问管理门户
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: deeced350ad867a374a486967c2cbd278ba91710
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519325"
---
# <a name="access-the-admin-portal"></a>访问管理门户

你的 Microsoft 托管桌面服务的网关是 Microsoft [Azure 门户](https://portal.azure.com)。 有关通常情况下使用和自定义 Azure 门户体验的详细信息，请参阅 [azure 门户文档](https://docs.microsoft.com/azure/azure-portal/)。 在预览中，您还可以在 [Microsoft 终结点管理器](https://endpoint.microsoft.com/)中找到 Microsoft 托管桌面。 如果你不熟悉此门户的设备管理功能，请参阅 [Microsoft 终结点管理器文档](https://docs.microsoft.com/mem/)。

> [!NOTE]
> 不过，你可以选择在 microsoft [终结点管理器](https://endpoint.microsoft.com/) 或 [Azure 门户](https://portal.azure.com)中 accesss microsoft 托管桌面，以下浏览器受支持：
> - Microsoft Edge (最新版本) 
> - Microsoft Internet Explorer 11
> - Safari (最新版本，仅 Mac) 
> - Chrome (最新版本) 
> - Firefox (最新版本) 

您的管理帐户需要特定的权限才能访问 Azure 门户或 Microsoft 终结点管理器中的 Microsoft 托管桌面管理功能。 您可以通过使用基于角色的访问控制 (RBAC) 管理对组织内的这些功能的管理员访问。  (Azure AD) 管理员角色和内置自定义角色的多个 Azure Active Directory 可用于向 Microsoft 托管桌面管理门户中的不同功能提供更精细的控制。 有关 Azure Active Directory 角色的详细信息，请参阅 [Azure Active directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 与适用于各种 Microsoft 产品和服务的 Azure AD 管理员角色不同，自定义角色特定于 Microsoft 托管桌面，并将仅保证能够访问此服务的管理功能。 管理员可以将自定义角色单独或与 Azure AD 管理员角色结合使用，以向现有管理员帐户添加 Microsoft 托管桌面权限。

可以分配以下每个角色，以提供不同级别的访问权限：

|Azure AD 角色  |Microsoft 托管桌面权限  |
|---------|---------|
|全局管理员     | 具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中 **所有功能的读取和写入权限** 。         |
|全局读取者     | 具有此角色的管理员将对 Microsoft 托管桌面管理门户中的 **所有功能具有只读权限** 。         |
|Intune 服务管理员     |  具有此角色的管理员将具有对与 Microsoft 托管桌面管理门户中的 **安全性不相关的功能的读取和写入权限** 。       |
|服务支持管理员     | 具有此角色的管理员将对与安全性和写入权限 **不相关的功能** 具有对 Microsoft 托管桌面管理门户中 **管理支持请求** 的权限的只读权限。         |
|安全管理员 | 具有此角色的管理员对管理门户中的 Microsoft 托管桌面中的所有功能和对 **安全相关功能的写入权限** 都具有 **只读权限**。 |
|安全读取者 |具有此角色的管理员将对 Microsoft 托管桌面管理门户中的 **所有功能具有只读权限** 。|

> [!IMPORTANT]
> 只有全局管理员角色才具有在 Microsoft 托管桌面中 *注册* 组织所需的权限。 请注意，Azure Active Directory 角色将在各种 Microsoft 服务中提供用户帐户权限。 在 Microsoft 托管桌面完成注册后，应始终使用具有完成其他任务所需的 *最少* 权限的角色。

 
|自定义角色  |Microsoft 托管桌面权限  |
|---------|---------|
|Microsoft 托管桌面服务管理员  | 当分配给用户时，此角色将向管理员授予对与 Microsoft 托管桌面管理门户中的 **安全性不相关的功能的读取和写入权限** 。  |
|Microsoft 托管桌面服务读取器 | 当分配给用户时，此角色将向管理员授予对与 Microsoft 托管桌面管理门户中的 **安全性不相关的功能的只读权限** 。 |
|Microsoft 托管桌面安全管理器 |当分配给用户时，此角色会向管理员授予对 Microsoft 托管桌面管理门户中的 **安全相关功能的读取和写入权限** 。   |

> [!NOTE]
> 安全功能包括与安全性相关的通信、安全联系人的管理、与安全相关的支持请求的管理，以及对安全相关报告的访问。 

## <a name="assigning-roles-to-administrators"></a>向管理员分配角色

如果你需要有关分配 Azure Active Directory 角色的帮助，请参阅 [Azure Active directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。

为了便于管理内置角色，已为每个自定义角色创建安全组 (例如，"新式工作区角色–安全管理器" ) 。 若要将用户分配给其中一个安全组，请按照以下步骤操作：
1.  转到 Microsoft 终结点管理器门户
2.  选择左侧的 "组"。
3.  搜索新式工作区角色，然后选择与要分配的角色相关联的组。 
4.  选择左侧的 "成员"，然后在命令栏上选择 "+ 添加成员"。
5.  输入要添加的人员的电子邮件。 如果是外部用户，则必须先邀请它们，然后才能分配组。
6.  选择底部的 "选择"。

> [!NOTE]
> 目前不支持为角色分配嵌套安全组。 
