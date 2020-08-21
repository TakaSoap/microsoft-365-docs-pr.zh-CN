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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 管理员可以了解在 Exchange Online Protection 中，管理员可以在 Exchange Online Protection 中 (或) Exchange 管理中心内的权限。
ms.openlocfilehash: 8d452eb85d59bbe82cc6685d652617bc857c1ddf
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825685"
---
# <a name="manage-role-groups-in-standalone-eop"></a>在独立 EOP 中管理角色组

在没有 Exchange Online 邮箱 (EOP) 组织中的独立 Exchange Online Protection 中，您可以使用 Exchange 管理中心 (EAC) 将用户添加到角色组。 向角色组添加用户将授予用户执行特定管理任务的权限。 您还可以从角色组中删除用户。

有关角色和角色组的详细信息，请参阅["独立 EOP 中的权限"。](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 要打开 Exchange 管理中心 (EAC，) ，请参阅 [在独立 EOP 中部署 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 要打开独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell。](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

- 必须先分配有权限，然后才能执行这些过程。 具体而说，需要 Role Management 角色，默认情况下该角色分配给 OrganizationManagement (全局) 管理员角色。 有关详细信息，请参阅独立[EOP 中的"权限](feature-permissions-in-eop.md)["和"使用 EAC 修改角色组中的成员列表"。](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 [Exchange Online 中 Exchange 管理中心的键盘快捷键](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 请在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 论坛中寻求帮助。

## <a name="use-the-eac-to-manage-role-groups"></a>使用 EAC 管理角色组

### <a name="use-the-eac-to-view-role-groups"></a>使用 EAC 查看角色组

1. 在 EAC 中，转到" **权限** \> **管理员"角色**。 这里列出了你组织中的所有角色组。

2. 选择角色组。 "详细信息"窗格显示**该****角色组的名称****、说明**、**分配角色**和管理者。 还可通过单击编辑图标查看 **此** ![ 信息 ](../../media/ITPro-EAC-EditIcon.png) 。

### <a name="use-the-eac-to-create-role-groups"></a>使用 EAC 创建角色组

当您创建新角色组时，可以在组创建过程中或 (配置所有) 设置。 或者，您可以复制现有角色组并对其进行修改。

1. 在 EAC 中，**Permissions**转到" \> **权限管理员"** 角色，然后执行下列步骤之一：

   - **手动创建新角色组：单击**"添加 **"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。

   - **复制现有角色组：** 选择您想要复制的角色组，然后单击"复制 **"** ![ 图标 ](../../media/ITPro-EAC-CopyIcon.png) 。

2. 在 **出现的"新建** 角色组"窗口中，配置下列设置：

    - **名称**：输入角色组的唯一名称。

    - **描述**：输入角色组的可选描述。

    - **角色**：**单击** ![ "添加 ](../../media/ITPro-EAC-AddIcon.png) **Remove** ![ "图标ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) 选择或修改分配给角色组的角色。

    - **成员**：单击 **"** ![ 添加" ](../../media/ITPro-EAC-AddIcon.png) 图标 **或** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) 删除邮件，以修改角色组成员身份。

3. 完成后，请单击" **保存** "创建角色组。

### <a name="use-the-eac-to-modify-role-groups"></a>使用 EAC 修改角色组

在 EAC 中，转到" **权限** \> **管理员角色**"，选择要修改的角色组，然后单击"编辑 **"** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。

修改角色组时可用的选项与创建角色组时相同。 可执行下列操作：

- 更改名称和说明。

- 添加和删除管理角色 (或从角色组) 。

- 添加和删除成员。

**注意**：某些 (例如，组织) 来限制可以从组中删除的角色。

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>使用 EAC 修改角色组中成员的列表

1. 在 EAC 中，转到" **权限** \> **管理员角色**"，选择要修改的角色组，然后单击"编辑 **"** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。

2. 在打开的角色组属性页的" **成员"部分** ，执行以下步骤之一：

   - 单击 **"添加** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) "。 在出现的页面中，找到要添加的小部件用户，然后单击" **添加 ->**"。 选择用户，并 **根据需要>添加 -- ** 个值。 完成后，单击"确定 **"。**

   - 选择要删除的用户，然后单击" **删除"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。

3. 完成时，请单击“保存”****。

   > [!NOTE]
   > 在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。

### <a name="use-the-eac-to-remove-role-groups"></a>使用 EAC 删除角色组

您不能删除内置角色组，但可以删除已创建的自定义角色组。

1. 在 EAC 中，转到" **权限** \> **管理员"角色**。

2. 选择要删除的角色组，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。

3. 在 **出现** 的确认窗口中，单击"是"。

## <a name="use-powershell-to-manage-role-groups"></a>使用 PowerShell 管理角色组

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>使用独立 EOP PowerShell 查看角色组

若要查看角色组，请使用以下语法：

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

本示例返回所有角色组的摘要列表。

```PowerShell
Get-RoleGroup
```

本示例返回名为 Recipient Administrators 的角色组的详细信息。

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

本示例返回用户 Julia 为成员的所有角色组。 必须使用 DistinguishedName (Julia 的) DN 值，你可以通过运行以下命令查找这些值 `Get-User -Identity Julia | Format-List DistinguishedName` 。

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

有关详细的语法和参数信息，请参阅 [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)。

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>使用独立 EOP PowerShell 创建角色组

当您创建新角色组时，可以在 (创建组或期间手动配置所有) 。 或者，您可以复制现有角色组并对其进行修改。

- 若要手动创建新角色组，请使用以下语法：

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - _Roles_参数指定要使用以下语法分配给该角色组的管理角色 `"Role1","Role1",..."RoleN"` 。 可以通过使用 **Get-ManagementRole** cmdlet 查看可用角色。

  - _Members_参数通过使用以下语法指定角色 `"Member1","Member2",..."MemberN"` 组的成员： 可以为 USG 或其他角色组或其他安全主体 (用户、) 启用 (邮件) 。

  本示例将使用下列设置创建名为"受限收件人管理"的新角色组：

  - 将为角色组分配 Mail Recipients 角色。

  - 用户 Kim 和 Martin 被添加为成员。

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- 要复制现有角色组，请执行下列步骤：

  1. 请使用以下语法将想要复制的角色组存储在变量中：

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. 请使用以下语法创建新角色组：

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     _Members_参数通过使用以下语法指定角色 `"Member1","Member2",..."MemberN"` 组的成员： 可以为 USG 或其他角色组或其他安全主体 (用户、) 启用 (邮件) 。

     此示例将 组织管理 角色组复制到名为"Limited Organization Management"的新角色组。 角色组成员是 Isabelle、Carter 和 Lukas。

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

有关语法和参数的详细信息[，New-RoleGroup。](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>使用独立 EOP PowerShell 修改角色组中成员的列表

- **Add-RoleGroupMember**和**Remove-RoleGroupMember** cmdlet 每次添加或删除单个成员。 **Update-RoleGroupMember** cmdlet 可以替换或修改现有成员列表。

- 角色组的成员可以是用户、已启用邮件的通用安全 (USG) 或其他基于安全主体 (角色组) 。

若要修改角色组的成员，请使用以下语法：

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- 若要 _将_ 现有的成员列表替换为您指定的值，请使用以下语法 `"Member1","Member2",..."MemberN"` ：

- 若要 _有选择地_ 修改现有成员列表，请使用以下语法 `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` ：

此示例将帮助支持角色组的所有现有成员替换为指定的用户。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

本示例添加 Daigoro Akai 并从 Help Desk 角色组成员列表中删除 Valeria Barrio。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

有关语法和参数的详细信息，请参阅[Update-RoleGroupMember。](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>使用独立 EOP PowerShell 删除角色组

您不能删除内置角色组，但可以删除已创建的自定义角色组。

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

若要验证是否已成功复制了角色组，请执行以下步骤之一：

- 在 EAC 中，转到" **权限** \> **管理员"** 角色，并验证角色组是否未 (未) 。 选择角色组，然后验证"详细信息"窗格中的设置，或单击"编辑 **"** ![ ](../../media/ITPro-EAC-EditIcon.png) 图标验证设置。

- 在 Exchange Online PowerShell 中 \<Role Group Name\> ，将角色组名称替换为角色组名称，并运行以下命令，验证角色组是否存在 (或不存在) 并验证设置：

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
