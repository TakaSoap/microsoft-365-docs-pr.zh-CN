---
title: 在 EOP 中管理组
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
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: 独立 Exchange Online Protection （EOP）组织中的管理员可以了解如何在 Exchange 管理中心（EAC）和独立 Exchange Online Protection （EOP） PowerShell 中创建、修改和删除通讯组和启用邮件的安全组。
ms.openlocfilehash: 42086b67e22df4725bf07bf227853c070f936f24
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616498"
---
# <a name="manage-groups-in-eop"></a>在 EOP 中管理组

在独立的 Exchange Online Protection （EOP）组织中，如果没有 Exchange Online 邮箱，您可以创建、修改和删除以下类型的组：

- **通讯组**：邮件用户或其他通讯组的集合。 例如，需要在感兴趣的公共领域接收或发送电子邮件的团队或其他临时组。 通讯组专门用于分发电子邮件，而不是安全主体（他们不能向其分配权限）。

- **启用邮件的安全组**：邮件用户和其他需要管理员角色访问权限的安全组的集合。 例如，您可能希望向特定用户组授予管理员权限，以便他们可以配置反垃圾邮件和反恶意软件设置。

    > [!NOTE]
    > <ul><li>默认情况下，启用邮件的新安全组拒绝来自外部（未经身份验证的）发件人的邮件。</li><li>不向启用邮件的安全组添加通讯组。</li></ul>.

您可以在 Exchange 管理中心（EAC）和独立 EOP PowerShell 中管理组。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开 Exchange 管理中心，请参阅[独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到独立的 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 当您在独立 EOP PowerShell 中管理组时，您可能会遇到限制。 本主题中的 PowerShell 过程使用一种批处理方法，该方法会导致在几分钟内发生传播延迟，然后才能看到命令的结果。

- 必须先分配有权限，然后才能执行这些过程。 具体来说，您需要 "通讯组" 角色，默认情况下该角色分配给 OrganizationManagement （全局管理员）和 RecipientManagement 角色组。 有关详细信息，请参阅[独立 EOP 中的权限](feature-permissions-in-eop.md)和[使用 EAC 修改角色组中的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>使用 Exchange 管理中心管理通讯组

### <a name="use-the-eac-to-create-groups"></a>使用 EAC 创建组

1. 在 EAC 中，转到 "**收件人** \> **组**"。

2. 单击 "**新建** ![ 新图标 ](../../media/ITPro-EAC-AddIcon.png) "，然后选择下列选项之一：

   - **通讯组**

   - **启用邮件的安全组**

3. 在打开的 "新建组" 页中，配置以下设置。 使用标记为的设置 <sup>\*</sup> 是必需的。

   - <sup>\*</sup>**显示名称**：此名称显示在组织的通讯簿中，在 "收件人：" 行中，电子邮件发送到此组，以及 EAC 的 "**组**" 列表中。 显示名称是必需的，必须是唯一的，并且应该是用户友好的，以便用户可以识别它。

   - <sup>\*</sup>**别名**：使用此框可以键入组的别名的名称。 别名不能超过64个字符，并且必须是唯一的。 当用户在电子邮件的 "To" 行中键入别名时，它将解析为组的显示名称。

   - <sup>\*</sup>**电子邮件地址**：电子邮件地址由 at （@）符号左侧的别名和右侧的域组成。 默认情况下，**别名**的值用于别名值，但您可以对其进行更改。 对于 "域" 值，请单击下拉，并在组织中选择并接受域。

   - **说明**：此说明出现在通讯簿和 EAC 的详细信息窗格中。

   - <sup>\*</sup>**所有者**：组所有者可以管理组成员身份。 默认情况下，组创建者即为组所有者。 所有组都必须至少有一个所有者。

     若要添加所有者，请单击 "**添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。 在出现的对话框中，查找并选择收件人或组，然后单击 "**加载项 >**"。 根据需要重复执行此步骤（次数不限）。 完成后，请单击 **"确定"**。

     若要删除所有者，请选择所有者，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。

   - **Members**：添加和删除组成员。

     若要添加成员，请单击 "**添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。 在出现的对话框中，查找并选择收件人或组，然后单击 "**加载项 >**"。 根据需要重复执行此步骤（次数不限）。 完成后，请单击 **"确定"**。

     若要删除某个成员，请选择该成员，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。

4. 完成后，请单击 "**保存**" 以创建通讯组。

### <a name="use-the-eac-to-modify-distribution-groups"></a>使用 EAC 修改通讯组

1. 在 EAC 中，转到 "**收件人** \> **组**"。

2. 在组列表中，选择要修改的通讯组或已启用邮件的安全组，然后单击 "**编辑** ![ 编辑图标" ](../../media/ITPro-EAC-AddIcon.png) 。

3. 在打开的 "通讯组属性" 页上，单击下列选项卡之一以查看或更改属性。

   完成时，请单击“保存”****。

#### <a name="general"></a>概要

使用此选项卡可以查看或更改有关组的基本信息。

- **显示名称**：此名称显示在通讯簿中、电子邮件发送到此组的 "收件人" 行和 "组"**列表**中。 显示名称是必需的，并且应当是用户友好的，以便用户可以识别它。 显示名称在域中还必须是唯一的。

  如果您已实现了一个组命名策略，则显示名称必须符合此策略定义的命名格式。

- **别名**：这是电子邮件地址中出现在（@）符号左侧的部分。 如果更改别名，组的主 SMTP 地址也会更改，并包含新的别名。 同时，带有之前别名的电子邮件地址将作为该组的代理地址保留。

- **电子邮件地址**：电子邮件地址由 at （@）符号左侧的别名和右侧的域组成。 默认情况下，**别名**的值用于别名值，但您可以对其进行更改。 对于 "域" 值，请单击下拉，并在组织中选择并接受域。

- **说明**：此说明出现在通讯簿和 EAC 的详细信息窗格中。

#### <a name="ownership"></a>Ownership

使用此选项卡可分配组所有者。 组所有者可以管理组成员身份。 默认情况下，组创建者即为组所有者。 所有组都必须至少有一个所有者。

若要添加所有者，请单击 "**添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。 在出现的对话框中，查找并选择收件人，然后单击 "**加载项 >**"。 根据需要重复执行此步骤（次数不限）。 完成后，请单击 **"确定"**。

若要删除所有者，请选择所有者，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。

#### <a name="membership"></a>成员身份

使用此选项卡可以添加或删除组成员。 组所有者不需要是组的成员。

若要添加成员，请单击 "**添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。 在出现的对话框中，查找并选择收件人或组，然后单击 "**加载项 >**"。 根据需要重复执行此步骤（次数不限）。 完成后，请单击 **"确定"**。

若要删除某个成员，请选择该成员，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。

### <a name="use-the-eac-to-remove-groups"></a>使用 EAC 删除组

1. 在 EAC 中，转到 "**收件人** \> **组**"。

2. 在组列表中，选择要删除的通讯组，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-groups"></a>使用 PowerShell 管理组

### <a name="use-standalone-eop-powershell-to-view-groups"></a>使用独立的 EOP PowerShell 查看组

若要在独立 EOP PowerShell 中返回所有通讯组和已启用邮件的安全组的摘要列表，请运行以下命令：

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

若要返回组成员的列表，请将 \<GroupIdentity\> 其替换为组的名称、别名或电子邮件地址，并运行以下命令：

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

有关语法和参数的详细信息，请参阅 "[获取-收件人](https://docs.microsoft.com/powershell/module/exchange/get-recipient)" 和 " [get-distributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)"。

### <a name="use-standalone-eop-powershell-to-create-groups"></a>使用独立的 EOP PowerShell 创建组

若要在独立 EOP PowerShell 中创建通讯组或启用邮件的安全组，请使用以下语法：

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**注意**：

- _Name_参数是必需的，最大长度为64个字符，并且必须是唯一的。 如果您不使用 _DisplayName_ 参数，_Name_ 参数的值可用于显示名称。

- 如果不使用_alias_参数，则_Name_参数将用于别名值。 删除空格并将不受支持的字符转换为问号（？）。

- 如果不使用_PrimarySmtpAddress_参数，则在_PrimarySmtpAddress_参数中使用别名值。

- 如果不使用_Type_参数，则默认值为分布。

本示例将创建一个名为 "IT 管理员" 的通讯组，其中包含指定的属性。

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

有关语法和参数的详细信息，请参阅[set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)。

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>使用独立的 EOP PowerShell 修改组

若要修改独立 EOP PowerShell 中的组，请使用以下语法：

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

本示例使用将 "西雅图员工" 组的主 SMTP 地址（也称为 "回复地址"）更改为 sea.employees@contoso.com。

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

此示例将安全团队组的当前成员替换为 Kitty Petersen 和 Tyson Fawcett。

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

本示例将名为 Tyson Fawcett 的新用户添加到名为安全团队的组，同时保留该组的当前成员。

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

有关语法和参数的详细信息，请参阅[set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)和[EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)。

### <a name="remove-a-group-using-remote-windows-powershell"></a>使用远程 Windows PowerShell 删除组

本示例使用删除名为 "IT 管理员" 的通讯组。

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

有关语法和参数的详细信息，请参阅[set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已成功创建、修改或删除了通讯组或已启用邮件的安全组，请执行以下任一步骤：

- 在 EAC 中，转到 "**收件人** \> **组**"。 验证组是否已列出（或未列出），并验证 "**组类型**" 值。 选择该组并查看详细信息窗格中的信息，或单击 "**编辑** ![ 编辑图标 ](../../media/ITPro-EAC-AddIcon.png) " 以查看设置。

- 在独立 EOP PowerShell 中，运行以下命令来验证组是否已列出（或未列出）：

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- \<GroupIdentity\>将替换为组的名称、别名或电子邮件地址，并运行以下命令来验证设置：

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- 若要查看组成员，请将 \<GroupIdentity\> 其替换为组的名称、别名或电子邮件地址，并运行以下命令：

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
