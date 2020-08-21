---
title: 在 EOP 中管理组
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
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: 独立 Exchange Online Protection (EOP) 中的管理员可了解如何在 Exchange 管理中心 (EAC 中以及独立 Exchange Online Protection (EOP) PowerShell 中创建) 、修改和删除通讯组和已启用邮件的安全组。
ms.openlocfilehash: e7b93b9d05fda7e4f5f8abea02fbe3f1c70a6c74
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826549"
---
# <a name="manage-groups-in-eop"></a>在 EOP 中管理组

在没有 Exchange Online 邮箱的 (EOP) 独立 Exchange Online Protection 组织中，可以创建、修改和删除以下类型的组：

- **通讯组**：邮件用户或其他通讯组的集合。 例如，在常见的兴趣区域，需要接收或发送电子邮件的团队或其他临时组。 通讯组专用于分发电子邮件，也不适用于安全主体 (他们无法为其分配) 。

- **启用邮件的安全组**：邮件用户以及需要具有管理员角色访问权限的其他安全组的集合。 例如，您可能想向特定组的用户授予管理员权限，使他们能够配置反垃圾邮件和反恶意软件设置。

    > [!NOTE]
    >
    > - 默认情况下，启用邮件的安全组拒绝来自未通过 (外部)  (的邮件。
    >
    > - 不要将通讯组添加到已启用邮件的安全组。

可以在 EAC 管理中心和独立 EOP PowerShell)  (Exchange 管理中心中的组。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 要打开 Exchange 管理中心，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 当您在独立 EOP PowerShell 中管理组时，您可能会遇到限制。 本主题中的 PowerShell 过程使用批处理方法，在显示命令结果之前，有几分钟的传播延迟。

- 必须先分配有权限，然后才能执行这些过程。 具体而说，需要有"通讯组"角色，默认情况下，该角色 (分配给 全局) 管理员角色和 RecipientManagement 角色组。 有关详细信息，请参阅独立[EOP 中的"权限](feature-permissions-in-eop.md)["和"使用 EAC 修改角色组中的成员列表"。](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 [Exchange Online 中 Exchange 管理中心的键盘快捷键](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 请在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 论坛中寻求帮助。

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>使用 Exchange 管理中心管理通讯组

### <a name="use-the-eac-to-create-groups"></a>使用 EAC 创建组

1. 在 EAC 中，转到"**收件人组** \> **"。**

2. 单击 **"新建** ![ " ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择以下选项之一：

   - **通讯组**

   - **启用邮件的安全组**

3. 在打开的新的组页中，配置以下设置。 标记有需要的 <sup>\*</sup> 设置。

   - <sup>\*</sup>**显示名称**：此名称将会出现在组织的通讯簿中、电子邮件中的"收件人："行中（电子邮件发送到该组时），以及 EAC **的"组** "列表中。 必须显示名称是唯一的，并且应当是用户友好的，以便用户可以识别其内容。

   - <sup>\*</sup>**别名**：使用此框键入组的别名。 别名不能超过 64 个字符，并且必须是唯一的。 当用户在电子邮件的"收件人"行中键入别名时，它将解析为该组的显示名称。

   - <sup>\*</sup>**电子邮件地址**：电子邮件地址由位于 (@) 符号左侧的别名和右侧的域。 默认情况下， **别名值将** 用于别名值，但您可以更改它。 对于域值，单击下拉列表，然后选择并接受组织中接受的域。

   - **Description：** 该描述出现在通讯簿和 EAC 的"详细信息"窗格中。

   - <sup>\*</sup>**所有者：** 组所有者可以管理组成员身份。 默认情况下，组创建者即为组所有者。 所有组都必须至少有一个所有者。

     若要添加所有者，请单击"**Add**添加 ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) "。 在出现的对话框中，找到并选择一个收件人或组，然后单击 **"添加 ->**。 根据需要重复执行此步骤（次数不限）。 完成后，单击"确定 **"。**

     若要删除所有者，请选择该所有者，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。

   - **成员**：添加和删除组成员。

     若要添加成员，请单击**Add**" ![ 添加"图标 ](../../media/ITPro-EAC-AddIcon.png) 。 在出现的对话框中，找到并选择一个收件人或组，然后单击 **"添加 ->**。 根据需要重复执行此步骤（次数不限）。 完成后，单击"确定 **"。**

     若要删除成员，请选择该成员，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。

4. 完成后，请单击 **"保存** "创建通讯组。

### <a name="use-the-eac-to-modify-distribution-groups"></a>使用 EAC 修改通讯组

1. 在 EAC 中，转到"**收件人组** \> **"。**

2. 在组列表中，选择要修改的通讯组或已启用邮件的安全组，然后单击"编辑 **"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。

3. 在打开的通讯组属性页面上，单击下列选项卡之一查看或更改属性。

   完成时，请单击“保存”****。

#### <a name="general"></a>常规

使用此选项卡可以查看或更改有关组的基本信息。

- **显示名称**：此名称将会出现在通讯簿中、电子邮件中的"收件人"行中（电子邮件发送到该组时）以及" **组"列表中**。 显示名称是必需的，并且应当是用户友好的，以便用户可以识别它。 显示名称在域中还必须是唯一的。

  如果您已实现了一个组命名策略，则显示名称必须符合此策略定义的命名格式。

- **别名**：这是电子邮件地址中 (@) 符号的部分。 如果更改别名，组的主 SMTP 地址也会更改，并包含新的别名。 同时，带有之前别名的电子邮件地址将作为该组的代理地址保留。

- **电子邮件地址**：电子邮件地址由位于 (@) 符号左侧的别名和右侧的域。 默认情况下， **别名值将** 用于别名值，但您可以更改它。 对于域值，单击下拉列表，然后选择并接受组织中接受的域。

- **Description：** 该描述出现在通讯簿和 EAC 的"详细信息"窗格中。

#### <a name="ownership"></a>Ownership

使用此选项卡分配组所有者。 组所有者可以管理组成员身份。 默认情况下，组创建者即为组所有者。 所有组都必须至少有一个所有者。

若要添加所有者，请单击"**Add**添加 ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) "。 在出现的对话框中，找到并选择收件人，然后单击"添加 - **显示>**。 根据需要重复执行此步骤（次数不限）。 完成后，单击"确定 **"。**

若要删除所有者，请选择该所有者，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。

#### <a name="membership"></a>成员身份

使用此选项卡可以添加或删除组成员。 组所有者无需是组的成员。

若要添加成员，请单击**Add**" ![ 添加"图标 ](../../media/ITPro-EAC-AddIcon.png) 。 在出现的对话框中，找到并选择一个收件人或组，然后单击 **"添加 ->**。 根据需要重复执行此步骤（次数不限）。 完成后，单击"确定 **"。**

若要删除成员，请选择该成员，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。

### <a name="use-the-eac-to-remove-groups"></a>使用 EAC 删除组

1. 在 EAC 中，转到"**收件人组** \> **"。**

2. 在组列表中，选择要删除的通讯组，然后单击 **"删除** ![ "图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-groups"></a>使用 PowerShell 管理组

### <a name="use-standalone-eop-powershell-to-view-groups"></a>使用独立 EOP PowerShell 查看组

若要返回独立 EOP PowerShell 中所有通讯组和已启用邮件的安全组的摘要列表，请运行以下命令：

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

若要返回组成员的列表，请 \<GroupIdentity\> 替换为组的名称、别名或电子邮件地址，并运行以下命令：

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

有关语法和参数的详细信息，请参阅 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) 和 [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)。

### <a name="use-standalone-eop-powershell-to-create-groups"></a>使用独立 EOP PowerShell 创建组

若要在独立 EOP PowerShell 中创建通讯组或已启用邮件的安全组，请使用以下语法：

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**注意**：

- _Name 参数_必需，最大长度为 64 个字符，并且必须是唯一的。 如果您不使用 _DisplayName_ 参数，_Name_ 参数的值可用于显示名称。

- 如果不使用 _Alias_ 参数， _则 Name_ 参数将用于别名值。 删除空格，并且不受支持的字符会被转换为问号 (？) 。

- 如果不使用 _PrimarySmtpAddress 参数_ ，则在 _PrimarySmtpAddress_ 参数中使用别名值。

- 如果不使用 _Type 参数_ ，则默认值为 Distribution。

本示例将创建具有指定属性的名为"IT Administrators"的通讯组。

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

有关语法和参数的详细信息，请参阅[New-EOPDistributionGroup。](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>使用独立 EOP PowerShell 修改组

若要修改独立 EOP PowerShell 中的组，请使用以下语法：

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

此示例使用将主 SMTP 地址类型 ("Seattle Employees"组) 也称为"答复地址"sea.employees@contoso.com。

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

此示例将"安全团队"组中当前成员替换为 Kitty Petersen 和 Tyson Fawcett。

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

本示例将名为"安全团队"的新用户（"Tyson Fawcettt"）添加到名为"安全团队"的组中，同时保留该组的当前成员。

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

有关语法和参数的详细信息，请参阅[Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)和[Update-EOPDistributionGroupMember。](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)

### <a name="remove-a-group-using-remote-windows-powershell"></a>使用远程用户删除Windows PowerShell

本示例使用了删除名为"IT 管理员"的通讯组。

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

有关语法和参数的详细信息，请参阅[Remove-EOPDistributionGroup。](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否已成功创建、修改或删除通讯组或已启用邮件的安全组，请执行以下任意步骤：

- 在 EAC 中，转到"**收件人组** \> **"。** 请验证组是否已 (列出或未列出) ，并验证组 **类型值** 。 选择该组并在"详细信息"窗格中查看信息，或单击"编辑 **"** ![ ](../../media/ITPro-EAC-AddIcon.png) 图标查看设置。

- 在独立 EOP PowerShell 中，运行以下命令来验证该组是否已 (或未列出) ：

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- 将 \<GroupIdentity\> 组的名称、别名或电子邮件地址替换，并运行以下命令来验证设置：

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- 若要查看组成员， \<GroupIdentity\> 请替换为该组的名称、别名或电子邮件地址，并运行以下命令：

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
