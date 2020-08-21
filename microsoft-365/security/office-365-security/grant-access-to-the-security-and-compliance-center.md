---
title: 向用户授予对安全与合规中心的访问权限
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 用户必须先在 Microsoft 365 安全 & 合规中心内分配权限，然后才能管理其任何安全或合规性功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21fef9458c02bd09d6d5ce2129b95571e0f8371
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826597"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>向用户授予对安全与合规中心的访问权限

用户必须先在安全 & 合规中心内分配权限，然后才能管理其任何安全或合规性功能。 作为安全与合规中心内的 OrganizationManagement 角色组的成员 &，你可以向用户授予这些权限。 用户将只能管理你授权他们访问的安全或合规性功能。

有关您可以在安全 & 合规中心向用户授予的不同权限的详细信息，请在安全与合规[中心&查看" 权限"。](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要完成本文中的步骤，需要是全局管理员，或是安全 & 合规中心中的 OrganizationManagement 角色组的成员。

- 安全与合规中心&可能与 Exchange Online 中的角色组名称类似，区分不同。

- Exchange Online 和安全合规性中心之间不共享&成员身份。

- 具有"代表 (的"管理) 的 DAP (和 DAP) 委派访问权限无法访问安全与&合规中心。

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>使用管理中心授予其他用户对安全合规中心&访问权限

1. [登录并转到管理中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)。

2. 在 Microsoft 365 管理中心内，**打开管理中心，然后单击**"安全与 **&合规"。**

3. 在安全与合 &规中心内，转到"权限 **"。**

4. 从列表中，选择您想要向其添加用户的角色组，然后单击"编辑 **"** ![ 图标 ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。

5. 在"成员"下面的角色组**属性页的****"添加** ![ 图标 ](../../media/ITPro-EAC-AddIcon.gif) "下，单击"添加图标"， (或要) 的用户的名称。

6. 当已选中所有想要添加到角色组的用户时，请单击"**添加"， \> **然后单击"确定 **"。**

7. 单击“保存”**** 以保存对角色组的更改。

### <a name="how-do-you-know-this-worked"></a>您如何知道操作成功？

1. 在安全与合 &规中心内，转到"权限 **"。**

2. 从列表中，选择要查看成员的角色组。

3. 在右侧的角色组详细信息中，可以查看角色组的成员。

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>使用 PowerShell 授予另一个用户对安全与&访问权限

1. [连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. 使用 **Add-rolegroupmember** 命令将用户添加到组织管理角色，如以下示例中所示。

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **参数**：

   - _标识_ 是要向其添加成员的角色组。

   - _成员_ 是要添加到角色组 (，) 通用安全组"权限或计算机。 每次只能指定一个成员。

有关语法和参数的详细信息，请参阅[Add-RoleGroupMember。](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证您已授予用户对安全 & 合规中心的访问权限，请使用 **Get-RoleGroupMember** cmdlet 查看组织管理角色组中的成员，如以下示例中所示。

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

有关语法和参数的详细信息，请参阅 [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)。
