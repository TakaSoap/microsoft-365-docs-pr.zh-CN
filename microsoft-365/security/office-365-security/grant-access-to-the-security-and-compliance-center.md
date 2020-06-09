---
title: 向用户授予对安全与合规中心的访问权限
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 用户需要在 Microsoft 365 安全 & 合规性中心中分配权限，才能管理其任何安全性或合规性功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfded9d3f75f57eca1097fec6f18dc55410b65fb
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616970"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>向用户授予对安全与合规中心的访问权限

用户需要在安全 & 合规性中心中分配权限，然后才能管理其任何安全性或合规性功能。 作为 Security & 合规中心中的 OrganizationManagement 角色组的全局管理员或成员，您可以向用户授予这些权限。 用户将只能管理你授权他们访问的安全或合规性功能。

有关您可以向安全 & 合规中心中的用户授予的不同权限的详细信息，请查看[安全 & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您必须是全局管理员，或者是 Security & 合规性中心中的 OrganizationManagement 角色组的成员，才能完成本文中的步骤。

- Security & 合规中心的角色组可能与 Exchange Online 中的角色组具有相似的名称，但它们不是相同的。

- 角色组成员身份不在 Exchange Online 与 Security & 合规性中心之间共享。

- 委派访问权限（分配）具有代表（AOBO）权限的管理的合作伙伴无法访问安全 & 合规中心。

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>使用管理中心向另一个用户授予对安全 & 合规中心的访问权限

1. [登录并转到管理中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)。

2. 在 Microsoft 365 管理中心，打开 "**管理中心**"，然后单击 "**安全 & 合规性**"。

3. 在安全 & 合规性中心中，转到 "**权限**"。

4. 从列表中，选择要向其添加用户的角色组，然后单击 "**编辑** ![ 编辑图标" ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。

5. 在 "**成员**" 下的角色组的 "属性" 页中，单击 "**添加**" "添加" ![ 图标， ](../../media/ITPro-EAC-AddIcon.gif) 然后选择要添加的一个或一组用户的名称。

6. 在选择了要添加到角色组的所有用户后，单击 "**添加 \> ** "，然后单击 **"确定"**。

7. 单击“保存”**** 以保存对角色组的更改。

### <a name="how-do-you-know-this-worked"></a>您如何知道操作成功？

1. 在安全 & 合规性中心中，转到 "**权限**"。

2. 从列表中选择要查看成员的角色组。

3. 在右侧的 "角色组详细信息" 中，您可以查看角色组的成员。

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>使用 PowerShell 授予另一个用户对安全 & 合规中心的访问权限

1. [连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. 使用 **Add-rolegroupmember** 命令将用户添加到组织管理角色，如以下示例中所示。

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **参数**：

   - _Identity_是要向其添加成员的角色组。

   - _Member_是要添加到角色组的邮箱、通用安全组（USG）或计算机。 每次只能指定一个成员。

有关语法和参数的详细信息，请参阅[外接程序 add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)。

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证您是否已授予用户对安全 & 合规中心的访问权限，请使用**add-rolegroupmember** Cmdlet 查看组织管理角色组中的成员，如以下示例所示。

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

有关语法和参数的详细信息，请参阅[add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)。
