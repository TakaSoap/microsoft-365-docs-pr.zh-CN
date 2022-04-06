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
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 用户需要在安全与合规Microsoft 365中心&权限，然后才能管理其任何安全或合规性功能。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5af3d045b174c4405dc2060fea1db22b3b4066ac
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680678"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>向用户授予对安全与合规中心的访问权限

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

用户需要在安全与合规&分配权限，然后才能管理其任何安全或合规性功能。 作为安全与合规中心中的全局管理员或 OrganizationManagement 角色组&，你可以向用户授予这些权限。 用户将只能管理你授权他们访问的安全或合规性功能。

有关可以在安全与合规中心向用户授予&权限详细信息，请参阅安全与合规中心& [权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 你需要是全局管理员或安全与合规中心内 OrganizationManagement 角色组&才能完成本文中的步骤。

- 安全与合规&的角色组的名称可能与 Exchange Online 中的角色组的名称相似，但名称不同。

- 角色组成员身份不会在安全与Exchange Online安全中心&共享。

- 委派访问权限 (DAP) 具有代表 (AOBO) 管理的合作伙伴无法访问安全与&中心。

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>使用安全&中心向其他用户授予对安全与合规&的访问权限

1. 打开安全&合规中心， <https://protection.office.com> 然后转到 **"权限"**。 若要直接转到" **权限"选项卡** ，请打开 <https://protection.office.com/permissions>。

2. 从角色组列表中，选择角色组，然后单击"编辑 **编辑**![图标"](../../media/O365-MDM-CreatePolicy-EditIcon.gif)。

3. 在角色组的属性页的"成员 **"** 下，单击" **添加**![添加图标"。](../../media/ITPro-EAC-AddIcon.gif) ，然后选择要添加 (的用户) 或用户的名称。

4. 选择要添加到角色组的所有用户后，单击" **添加\>** "，然后单击"确定 **"**。

5. 完成后，单击“**保存**”。

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>使用安全&合规中心 PowerShell 向其他用户授予对安全与合规&的访问权限

1. [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

2. 使用以下语法:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

有关语法和参数的详细信息，请参阅 [Add-RoleGroupMember](/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

要验证您是否已成功授予对安全与合规&访问权限，请执行以下步骤之一：

- 在安全&中心，转到" **权限** "并选择角色组。 在打开的详细信息飞出中，验证角色组的成员。

- 在安全&合规中心 PowerShell 中，将 替换为 \<RoleGroupName\> 角色组的名称，然后运行以下命令：

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  有关语法和参数的详细信息，请参阅 [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember)。