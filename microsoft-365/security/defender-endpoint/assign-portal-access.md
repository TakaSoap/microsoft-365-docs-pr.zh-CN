---
title: 向用户分配Microsoft Defender 安全中心
description: 分配对 Microsoft Defender 终结点门户的读取和写入或只读访问权限。
keywords: 分配用户角色， 分配读取和写入访问权限， 分配只读访问权限， 用户， 用户角色， 角色
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 7ea8fd8a87e15291f0f65e6f21bb452efe72383c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207099"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>向用户分配Microsoft Defender 安全中心

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- Azure Active Directory
- Office 365
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

Defender for Endpoint 支持两种权限管理方法：

- **基本权限管理**：将权限设置为完全访问或只读。
- 基于角色的访问控制 **(RBAC) ：** 通过定义角色、将 Azure AD 用户组分配给角色并授予用户组对设备组的访问权限来设置粒度权限。 有关 RBAC 详细信息，请参阅使用基于角色的访问控制管理 [门户访问](rbac.md)。

> [!NOTE]
> 如果已分配基本权限，可以随时切换到 RBAC。 进行切换之前，请考虑以下事项：
>
> - 具有完全访问权限 (Azure AD) 中分配了全局管理员或安全管理员目录角色的用户将自动分配有默认 Defender for Endpoint 管理员角色，该角色也具有完全访问权限。 切换到 RBAC 后，可以将其他 Azure AD 用户组分配给 Defender for Endpoint 管理员角色。 只有分配到 Defender for Endpoint 管理员角色的用户才能使用 RBAC 管理权限。 
> - 具有只读访问权限的用户 (安全读者) 分配角色之前，将失去对门户的访问权限。 请注意，在 RBAC 下只能为 Azure AD 用户组分配角色。
> - 切换到 RBAC 后，将无法切换回使用基本权限管理。

## <a name="related-topics"></a>相关主题

- [使用基本权限访问门户](basic-permissions.md)
- [使用 RBAC 管理门户访问](rbac.md)
