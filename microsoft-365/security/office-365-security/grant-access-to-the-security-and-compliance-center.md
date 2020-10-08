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
description: 用户需要在 Microsoft 365 安全 & 合规性中心中分配权限，才能管理其任何安全性或合规性功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d586684d44545f7aea94c30f5474b1fe5fa4651
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202803"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>向用户授予对安全与合规中心的访问权限

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


用户需要在安全 & 合规性中心中分配权限，然后才能管理其任何安全性或合规性功能。 作为 Security & 合规中心中的 OrganizationManagement 角色组的全局管理员或成员，您可以向用户授予这些权限。 用户将只能管理你授权他们访问的安全或合规性功能。

有关您可以向安全 & 合规中心中的用户授予的不同权限的详细信息，请查看 [安全 & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您必须是全局管理员，或者是 Security & 合规性中心中的 OrganizationManagement 角色组的成员，才能完成本文中的步骤。

- Security & 合规中心的角色组可能与 Exchange Online 中的角色组具有相似的名称，但它们不是相同的。

- 角色组成员身份不在 Exchange Online 与 Security & 合规性中心之间共享。

- 委派访问权限 (通过代表 (AOBO 的管理) 合作伙伴。) 权限无法访问安全 & 合规性中心。

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>使用安全 & 合规性中心向另一个用户授予对安全 & 合规性中心的访问权限

1. 在上打开 "安全 & 合规中心" <https://protection.office.com> ，然后转到 " **权限**"。 若要直接转到 " **权限** " 选项卡，请打开 <https://protection.office.com/permissions> 。

2. 从角色组列表中，选择角色组，然后单击 " **编辑** ![ 编辑图标" ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。

3. 在 "**成员**" 下的角色组的 "属性" 页中，单击 "**添加**" "添加 ![ " 图标， ](../../media/ITPro-EAC-AddIcon.gif) 然后选择要添加的用户的名称 (或用户) 。

4. 在选择了要添加到角色组的所有用户后，单击 "**添加 \> ** "，然后单击 **"确定"**。

5. 完成时，请单击“保存”****。

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>使用安全 & 合规性中心 PowerShell 向另一个用户授予对安全 & 合规性中心的访问权限

1. [连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. 使用以下语法：

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

有关语法和参数的详细信息，请参阅 [外接程序 add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>如何知道操作成功？

若要验证是否已成功授予对安全 & 合规中心的访问权限，请执行以下步骤之一：

- 在安全 & 合规性中心中，转到 " **权限** "，然后选择角色组。 在打开的 "详细信息" 浮出控件中，验证角色组的成员。 

- 在安全 & 合规性中心 PowerShell 中，将替换 \<RoleGroupName\> 为角色组的名称，然后运行以下命令：

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  有关语法和参数的详细信息，请参阅 [add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)。
