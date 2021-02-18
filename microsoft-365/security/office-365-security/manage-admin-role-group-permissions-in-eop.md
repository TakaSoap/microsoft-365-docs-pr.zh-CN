---
title: 在 EOP 中管理角色组
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 管理员可以了解如何在 Exchange Online Protection 中的 Exchange 管理中心 (EAC) 权限。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce272985f195f44c57848e6861cefb64431698b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289921"
---
# <a name="manage-role-groups-in-standalone-eop"></a>在独立 EOP 中管理角色组

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
-  [独立 Exchange Online Protection](exchange-online-protection-overview.md)

在独立 Exchange Online Protection (EOP) 组织中，可以使用 Exchange 管理中心 (EAC) 将用户添加到角色组。 向角色组添加用户会授予用户执行特定管理任务的权限。 还可以从角色组中删除用户。

有关角色和角色组的信息，请参阅独立 [EOP 中的权限](feature-permissions-in-eop.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开 Exchange 管理中心 (EAC) ，请参阅独立 [EOP](exchange-admin-center-in-exchange-online-protection-eop.md)中的 Exchange 管理中心。

- 若要打开独立 EOP PowerShell，请参阅["连接到 Exchange Online Protection PowerShell"。](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

- 您需要在 Exchange Online Protection 中分配权限，然后才能执行本文中的过程。 具体而言，您需要角色 **管理** 角色，默认情况下，角色管理角色分配给 **组织管理** 角色组。 有关详细信息，请参阅独立 [EOP 中](feature-permissions-in-eop.md) 的权限和使用 [EAC 修改角色组的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅 Exchange Online 中 [Exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 请在 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 论坛中寻求帮助。

## <a name="use-the-eac-to-manage-role-groups"></a>使用 EAC 管理角色组

### <a name="use-the-eac-to-view-role-groups"></a>使用 EAC 查看角色组

1. 在 EAC 中，转到 **"权限** \> **管理员"角色**。 这里列出了你组织中的所有角色组。

2. 选择角色组。 "详细信息"窗格显示 **角色组的名称**、说明、分配的角色和管理。  您还可以通过单击"编辑编辑" **图标来查看** ![ 此信息 ](../../media/ITPro-EAC-EditIcon.png) 。

### <a name="use-the-eac-to-create-role-groups"></a>使用 EAC 创建角色组

创建新的角色组时，可以在组创建期间或 (配置所有设置) 。 或者，您可以复制并修改现有角色组。

1. 在 EAC 中，转到 **"权限** \> **管理员**"角色，然后执行以下步骤之一：

   - **手动创建新角色组**：单击 **"添加"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。

   - **复制现有角色组**：选择要复制的角色组，然后单击"复制 **复制"** ![ 图标 ](../../media/ITPro-EAC-CopyIcon.png) 。

2. 在 **出现的"新建角色组** "窗口中，配置以下设置：

    - **名称**：输入角色组的唯一名称。

    - **说明**：输入角色组的可选说明。

    - **角色**：单击 **"添加** ![ "图标或"删除删除"图标以选择或修改分配给角色 ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 组的角色。

    - **成员**：单击 **"** ![ 添加" ](../../media/ITPro-EAC-AddIcon.png) 图标 **或"** 删除 ![ 删除"图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 以修改角色组成员身份。

3. 完成后，单击"保存"以创建角色组。

### <a name="use-the-eac-to-modify-role-groups"></a>使用 EAC 修改角色组

在 EAC 中，转到 **"权限** 管理员角色"，选择要修改的角色组， \> 然后单击"编辑 **编辑"** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。

修改角色组时可用的选项与创建角色组时相同。 可执行下列操作：

- 更改名称和说明。

- 添加和删除管理 (角色分配) 。

- 添加和删除成员。

**注意**：某些角色 (例如，组织) 限制可以从组中删除的角色。

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>使用 EAC 修改角色组的成员列表

1. 在 EAC 中，转到 **"权限** 管理员角色"，选择要修改的角色组， \> 然后单击"编辑 ![ 编辑"图标 ](../../media/ITPro-EAC-EditIcon.png) 。

2. 在打开的角色组属性页的 **"成员** "部分中，执行下列任一步骤：

   - 单击 **"添加** ![ "图标 ](../../media/ITPro-EAC-AddIcon.png) 。 在出现的页面中，找到要添加的用户，然后单击"添加 **>。** 选择 **用户并根据需要** >多次添加 ->。 完成后，单击"确定 **"。**

   - 选择要删除的用户，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。

3. 完成时，请单击“保存”。

   > [!NOTE]
   > 在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。

### <a name="use-the-eac-to-remove-role-groups"></a>使用 EAC 删除角色组

不能删除内置角色组，但可以删除已创建的自定义角色组。

1. 在 EAC 中，转到 **"权限** \> **管理员"角色**。

2. 选择要删除的角色组，然后单击" **删除"** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。

3. 在 **出现的** 确认窗口中单击"是"。

## <a name="use-powershell-to-manage-role-groups"></a>使用 PowerShell 管理角色组

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>使用独立 EOP PowerShell 查看角色组

若要查看角色组，请使用以下语法：

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

此示例返回所有角色组的摘要列表。

```PowerShell
Get-RoleGroup
```

此示例返回名为"收件人管理员"的角色组的详细信息。

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

本示例返回用户 Julia 是成员的所有角色组。 需要为 Julia 使用 DistinguishedName (DN) 值，可通过运行以下命令找到该值 `Get-User -Identity Julia | Format-List DistinguishedName` ：

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

有关详细的语法和参数信息，请参阅 [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)。

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>使用独立 EOP PowerShell 创建角色组

创建新的角色组时，可以在组创建期间或 (配置所有设置) 。 或者，您可以复制并修改现有角色组。

- 若要手动创建新角色组，请使用以下语法：

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - _Roles_ 参数通过以下语法指定要分配给角色组的管理角色 `"Role1","Role1",..."RoleN"` 。 可以使用 **Get-ManagementRole** cmdlet 查看可用角色。

  - _Members_ 参数使用以下语法指定角色组 `"Member1","Member2",..."MemberN"` 的成员： 可以指定用户、启用邮件的通用安全组 (USG) 或其他角色组 (安全) 。

  此示例创建一个名为"有限收件人管理"的新角色组，该角色组具有以下设置：

  - 将为角色组分配 Mail Recipients 角色。

  - 用户 Kim 和 Martin 将添加为成员。

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- 若要复制现有角色组，请执行以下步骤：

  1. 请使用以下语法将想要复制的角色组存储在变量中：

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. 使用以下语法创建新的角色组：

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     _Members_ 参数使用以下语法指定角色组 `"Member1","Member2",..."MemberN"` 的成员： 可以指定用户、启用邮件的通用安全组 (USG) 或其他角色组 (安全) 。

     本示例将组织管理角色组复制到名为"Limited Organization Management"的新角色组。 角色组的成员是 Isab、Carter 和 Lukas。

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

有关语法和参数的详细信息，[请参阅 New-RoleGroup。](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>使用独立的 EOP PowerShell 修改角色组的成员列表

- **Add-RoleGroupMember** 和 **Remove-RoleGroupMember** cmdlet 一次添加或删除一个成员。 **Update-RoleGroupMember** cmdlet 可以替换或修改现有成员列表。

- 角色组的成员可以是用户、启用邮件的通用安全组 (USG) 或其他角色组 (安全) 。

若要修改角色组的成员，请使用以下语法：

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- 若要 _将_ 现有的成员列表替换为您指定的值，请使用以下 `"Member1","Member2",..."MemberN"` 语法：

- 若要 _有选择地修改_ 现有成员列表，请使用以下 `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 语法：

本示例将技术支持角色组的所有当前成员替换为指定的用户。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

此示例将添加一个一代，并从 Help Desk 角色组的成员列表中删除一个。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

有关语法和参数的详细信息，请参阅 [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)。

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>使用独立 EOP PowerShell 删除角色组

不能删除内置角色组，但可以删除已创建的自定义角色组。

若要删除自定义角色组，请使用以下语法：

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

本示例将删除 Training Administrators 角色组。

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

有关语法和参数的详细信息，请参阅 [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)。

### <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否成功复制了角色组，请执行下列任一步骤：

- 在 EAC 中，转到 **"权限** 管理员"角色，并验证角色组是否 (\> 列出) 。 选择角色组，然后验证"详细信息"窗格中的设置 **或单击"** 编辑编辑"图标 ![ ](../../media/ITPro-EAC-EditIcon.png) 以验证设置。

- 在 Exchange Online PowerShell 中，替换为角色组的名称，并运行以下命令来验证角色组是否存在 (或不存在) 验证 \<Role Group Name\> 设置：

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
