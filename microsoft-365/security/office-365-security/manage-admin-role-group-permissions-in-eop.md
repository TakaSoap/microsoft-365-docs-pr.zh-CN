---
title: 管理 EOP 中的角色组
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 管理员可以了解如何在 Exchange Online Protection 中分配或删除 Exchange 管理中心（EAC）中的权限。
ms.openlocfilehash: 3555d3bd7fa4c53802eb214747735223cccc21e5
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616510"
---
# <a name="manage-role-groups-in-standalone-eop"></a>在独立 EOP 中管理角色组

在独立的 Exchange Online Protection （EOP）组织中，如果没有 Exchange Online 邮箱，您可以使用 Exchange 管理中心（EAC）将用户添加到角色组。 向角色组添加用户将向用户授予执行特定管理任务的权限。 您还可以从角色组中删除用户。

有关角色和角色组的详细信息，请参阅[独立 EOP 中的权限](feature-permissions-in-eop.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开 Exchange 管理中心（EAC），请参阅[独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要打开独立的 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 必须先分配有权限，然后才能执行这些过程。 具体来说，您需要角色管理角色，默认情况下该角色分配给 OrganizationManagement （全局管理员）角色组。 有关详细信息，请参阅[独立 EOP 中的权限](feature-permissions-in-eop.md)和[使用 EAC 修改角色组中的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。

## <a name="use-the-eac-to-manage-role-groups"></a>使用 EAC 管理角色组

### <a name="use-the-eac-to-view-role-groups"></a>使用 EAC 查看角色组

1. 在 EAC 中，转到 "**权限**" " \> **管理员角色**"。 这里列出了你组织中的所有角色组。

2. 选择一个角色组。 "详细信息" 窗格显示**名称**、**说明**、**分配的角色**，并由角色组**进行管理**。 您也可以通过单击 "**编辑**编辑图标" 查看此信息 ![ ](../../media/ITPro-EAC-EditIcon.png) 。

### <a name="use-the-eac-to-create-role-groups"></a>使用 EAC 创建角色组

创建新角色组时，您可以自己配置所有设置（在组创建期间或之后）。 或者，您可以复制现有角色组并对其进行修改。

1. 在 EAC 中，转到 "**权限** \> " "**管理员角色**"，然后执行下列步骤之一：

   - **手动创建新的角色组**：单击 "**添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。

   - **复制现有角色组**：选择要复制的角色组，然后单击 "**复制** ![ 副本" 图标 ](../../media/ITPro-EAC-CopyIcon.png) 。

2. 在出现的 "**新建角色组**" 窗口中，配置以下设置：

    - **名称**：输入角色组的唯一名称。

    - **说明**：输入角色组的可选描述。

    - **角色**：单击 "**添加**" "添加" ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 或**删除** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) "ITPro-EAC-RemoveIcon" 以选择或修改分配给角色组的角色。

    - **Members**：单击 "**添加**" "添加" ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 或**删除** ![ ITPro-EAC-RemoveIcon ](../../media/ITPro-EAC-RemoveIcon.gif) 以修改角色组成员身份。

3. 完成后，请单击 "**保存**" 以创建角色组。

### <a name="use-the-eac-to-modify-role-groups"></a>使用 EAC 修改角色组

在 EAC 中，转到 "**权限** \> " "**管理员角色**"，选择要修改的角色组，然后单击 "**编辑** ![ 编辑图标" ](../../media/ITPro-EAC-EditIcon.png) 。

当您在创建角色组时修改角色组时，可以使用相同的选项。 可执行下列操作：

- 更改名称和说明。

- 添加和删除管理角色（创建或删除角色分配）。

- 添加和删除成员。

**注意**：某些角色组（例如，"组织管理"）限制了可以从组中删除的角色。

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>使用 EAC 修改角色组中的成员列表

1. 在 EAC 中，转到 "**权限** \> " "**管理员角色**"，选择要修改的角色组，然后单击 "**编辑** ![ 编辑图标" ](../../media/ITPro-EAC-EditIcon.png) 。

2. 在打开的角色组属性页的 " **Memebers** " 部分中，执行下列步骤之一：

   - 单击 "**添加**" "添加" ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。 在出现的页面中，找到 wou 要添加的用户，然后单击 "**加载项 >**"。 选择 "用户"，并根据需要多次单击 "**添加->** "。 完成后，请单击 **"确定"**。

   - 选择要删除的用户，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。

3. 完成时，请单击“保存”****。

   > [!NOTE]
   > 在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。

### <a name="use-the-eac-to-remove-role-groups"></a>使用 EAC 删除角色组

无法删除内置角色组，但可以删除已创建的自定义角色组。

1. 在 EAC 中，转到 "**权限**" " \> **管理员角色**"。

2. 选择要删除的角色组，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-DeleteIcon.png) 。

3. 在出现的确认窗口中，单击 **"是"** 。

## <a name="use-powershell-to-manage-role-groups"></a>使用 PowerShell 管理角色组

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>使用独立的 EOP PowerShell 查看角色组

若要查看角色组，请使用以下语法：

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

本示例返回所有角色组的摘要列表。

```PowerShell
Get-RoleGroup
```

此示例返回名为 "收件人管理员" 的角色组的详细信息。

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

此示例返回用户 Julia 所属的所有角色组。 您需要使用 Julia 的 DistinguishedName （DN）值，可以通过运行以下命令找到它： `Get-User -Identity Julia | Format-List DistinguishedName` 。

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

有关详细的语法和参数信息，请参阅 [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)。

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>使用独立的 EOP PowerShell 创建角色组

创建新角色组时，可以手动配置所有设置（在组创建期间或之后）。 或者，您可以复制现有角色组并对其进行修改。

- 若要手动创建新的角色组，请使用以下语法：

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - _Roles_参数通过使用以下语法指定要分配给角色组的管理角色 `"Role1","Role1",..."RoleN"` 。 您可以通过使用**get-managementrole** cmdlet 来查看可用的角色。

  - _Members_参数通过使用以下语法指定角色组的成员： `"Member1","Member2",..."MemberN"` 。 您可以指定用户、已启用邮件的通用安全组（Usg）或其他角色组（安全主体）。

  此示例使用以下设置创建名为 "受限收件人管理" 的新角色组：

  - 将为角色组分配 Mail Recipients 角色。

  - 将用户 Kim 和圣马丁添加为成员。

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- 若要复制现有角色组，请执行以下步骤：

  1. 请使用以下语法将想要复制的角色组存储在变量中：

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. 使用以下语法创建新角色组：

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     _Members_参数通过使用以下语法指定角色组的成员： `"Member1","Member2",..."MemberN"` 。 您可以指定用户、已启用邮件的通用安全组（Usg）或其他角色组（安全主体）。

     此示例将组织管理角色组复制到名为 "受限的组织管理" 的新角色组。 角色组成员是 Isabelle、Carter 和 Lukas。

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

有关语法和参数的详细信息， [new-rolegroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)。

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>使用独立 EOP PowerShell 修改角色组中的成员列表

- **Add-rolegroupmember**和**add-rolegroupmember** cmdlet 在一次添加或删除单个成员。 **Add-rolegroupmember** cmdlet 可以替换或修改现有的成员列表。

- 角色组的成员可以是用户、已启用邮件的通用安全组（Usg）或其他角色组（安全主体）。

若要修改角色组的成员，请使用以下语法：

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- 若要将现有的成员列表_替换_为您指定的值，请使用以下语法： `"Member1","Member2",..."MemberN"` 。

- 若要_有选择地修改_现有的成员列表，请使用以下语法： `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 。

本示例将帮助台角色组的所有当前成员替换为指定的用户。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

本示例将 Daigoro Akai 添加到 "帮助台" 角色组中的成员列表中，并从列表中删除 Valeria Barrio。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

有关语法和参数的详细信息，请参阅[add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)。

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>使用独立 EOP PowerShell 删除角色组

无法删除内置角色组，但可以删除已创建的自定义角色组。

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

若要验证是否已成功复制角色组，请执行以下步骤之一：

- 在 EAC 中，转到 "**权限** \> " "**管理员角色**"，然后验证角色组是否已列出（或未列出）。 选择角色组，并验证详细信息窗格中的设置，或单击 "**编辑** ![ 编辑图标 ](../../media/ITPro-EAC-EditIcon.png) " 以验证设置。

- 在 Exchange Online PowerShell 中，将替换 \<Role Group Name\> 为角色组的名称，然后运行以下命令来验证角色组是否存在（或不存在）并验证设置：

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
