---
title: 使用基本权限访问Microsoft Defender 安全中心
description: 了解如何使用基本权限访问 Microsoft Defender for Endpoint 门户。
keywords: 分配用户角色， 分配读取和写入访问权限， 分配只读访问权限， 用户， 用户角色， 角色
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7c208998e436245c53b90905858b7cf7ebe91d6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290181"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>使用基本权限访问门户

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- Azure Active Directory
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

请参阅下面的说明以使用基本权限管理。

可以使用以下任一解决方案：
- Azure PowerShell
- Azure 门户

若要精细控制权限， [请切换到基于角色的访问控制](rbac.md)。

## <a name="assign-user-access-using-azure-powershell"></a>使用资源分配Azure PowerShell
您可以向用户分配以下权限级别之一：
- 可读写 (完全访问权限) 
- 只读访问

### <a name="before-you-begin"></a>开始之前

- 安装 Azure PowerShell。 有关详细信息，请参阅如何安装和配置[Azure PowerShell。](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)<br>

    > [!NOTE]
    > 需要在提升的命令行中运行 PowerShell cmdlet。

- 连接文件Azure Active Directory。 有关详细信息，请参阅[连接-MsolService](/powershell/module/msonline/connect-msolservice)。

**完全访问权限** <br>
具有完全访问权限的用户可以登录、查看所有系统信息并解决警报、提交文件进行深入分析以及下载载入程序包。
分配完全访问权限需要将用户添加到"安全管理员"或"全局管理员"AAD 内置角色。

**只读访问** <br>
具有只读访问权限的用户可以登录、查看所有警报和相关信息。
他们将不能更改警报状态、提交文件进行深入分析或执行任何状态更改操作。
分配只读访问权限需要将用户添加到"安全读者"Azure AD 内置角色。

使用以下步骤分配安全角色：

- 对于 **读取和写入** 权限，请通过使用以下命令将用户分配给安全管理员角色：

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- 对于 **只读访问权限** ，请通过使用以下命令将用户分配给安全读者角色：

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

有关详细信息，请参阅使用 Azure Active Directory 添加[或删除Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

## <a name="assign-user-access-using-the-azure-portal"></a>使用 Azure 门户分配用户访问权限

有关详细信息，请参阅 Assign [administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。

## <a name="related-topic"></a>相关主题

- [使用 RBAC 管理门户访问](rbac.md)
