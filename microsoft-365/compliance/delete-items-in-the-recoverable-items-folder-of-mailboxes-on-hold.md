---
title: 删除保留的基于云的邮箱的 "可恢复的项目" 文件夹中的项目-管理员帮助
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: "对于管理员：删除中的项目 \n\nExchange Online 邮箱的 er 的 \"可恢复的项目\" 文件夹，即使该邮箱位于 \"合法保留\" 中也是如此。 这是一种删除意外溅入 Office 365 中的数据的有效方法。"
ms.openlocfilehash: 5c8614c0faf8ea0f807b09cb24ccd3409dd7facb
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409647"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>删除保留的基于云的邮箱的 "可恢复的项目" 文件夹中的项目-管理员帮助

Exchange Online 邮箱的 "可恢复的项目" 文件夹存在，以防止意外或恶意删除。 它还用于存储由 Office 365 合规性功能（如保留和电子数据展示搜索）保留和访问的项目。 但是，在某些情况下，组织可能会在必须删除的 "可恢复的项目" 文件夹中包含意外保留的数据。 例如，用户可能在不知情的情况下发送或转发包含敏感信息的电子邮件或可能有严重业务后果的信息。 即使邮件永久删除，它仍可能会无限期保留，因为邮箱中已设置了合法保留。 此方案称为数据外泄，因为数据被意外地溅入 Office 365 中。 在这些情况下，您可以删除 Exchange Online 邮箱的用户的 "可恢复的项目" 文件夹中的项目，即使该邮箱是使用 Office 365 中的一种不同的保留功能来保留的。 这些保留类型包括诉讼保留、就地保留、电子数据展示保留和 Office 365 保留策略（在 Office 365 或 Microsoft 365 的安全与合规中心中创建）。
  
 本文介绍如何从处于保留状态的基于云的邮箱的 "可恢复的项目" 文件夹中删除项目。 此过程涉及到禁用对邮箱的访问和禁用单个项目恢复，禁用托管文件夹助理处理邮箱，暂时删除保留，从 "可恢复的项目" 文件夹中删除项目，然后还原邮箱设置为其以前的配置。 过程如下： 
  
[步骤1：收集有关邮箱的信息](#step-1-collect-information-about-the-mailbox)

[步骤2：准备邮箱](#step-2-prepare-the-mailbox)

[步骤3：从邮箱中删除所有保留](#step-3-remove-all-holds-from-the-mailbox)

[步骤4：从邮箱中删除延迟保留](#step-4-remove-the-delay-hold-from-the-mailbox)

[步骤5：删除 "可恢复的项目" 文件夹中的项目](#step-5-delete-items-in-the-recoverable-items-folder)

[步骤6：将邮箱还原到其以前的状态](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> 本文中所述的过程将导致从 Exchange Online 邮箱永久删除（清除）的数据。 这意味着无法恢复从 "可恢复的项目" 文件夹中删除的邮件，也不会提供用于法律查询或其他合规性的邮件。 如果要从作为诉讼保留的一部分的邮箱中删除邮件，请在 "安全与合规中心" 中创建的 "就地保留"、"电子数据展示保留" 或 "Office 365 保留策略" 中，与您的记录管理或法律部门进行核实在删除保留之前。 您的组织可能有定义邮箱处于保留状态或 data 外泄事件是否优先的策略。 
  
## <a name="before-you-begin"></a>开始之前

- 若要创建并运行内容搜索，您必须是电子数据展示管理员角色组的成员，或者分配有“合规性搜索”管理角色。 若要删除邮件，您必须是组织管理角色组的成员或分配有“搜索并清除”管理角色。 有关将用户添加到角色组的信息，请参阅[分配安全与合规中心中的电子数据展示权限](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)。
    
- 非活动邮箱不支持本文中介绍的过程。 这是因为在删除保留（或 Office 365 保留策略）后，不能将其重新应用到非活动邮箱。 从非活动邮箱删除保留时，它会更改为标准软删除邮箱，并且在托管文件夹助理处理后，将从组织中永久删除。
    
- 您无法对已被分配到 Office 365 保留策略的邮箱执行此过程，该保留策略已通过保留锁定进行锁定。 这是因为保留锁可防止您从 Office 365 保留策略中删除或排除邮箱，也无法在邮箱上禁用托管文件夹助理。 有关锁定保留策略的详细信息，请参阅[锁定保留策略](retention-policies.md#locking-a-retention-policy)。
    
- 如果未将邮箱置于保留状态（或未启用单个项目恢复），则可以从 "可恢复的项目" 文件夹中删除这些项目。 有关如何执行此操作的详细信息，请参阅[在 Office 365 组织中搜索和删除电子邮件](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)。
  
## <a name="step-1-collect-information-about-the-mailbox"></a>步骤1：收集有关邮箱的信息

第一步是收集将影响此过程的目标邮箱中的所选属性。 请务必记下这些设置或将其保存到一个文本文件中，因为在从 "可恢复的项目" 文件夹中删除项目后，您将更改其中一些属性，然后再还原为第6步中的原始值。 下面列出了需要收集的邮箱属性。
  
-  *SingleItemRecoveryEnabled*和*RetainDeletedItemsFor* ;如有必要，您将禁用单个恢复并在步骤3中增加已删除项目的保留期。 
    
-  *LitigationHoldEnabled*和*InPlaceHolds* ;您需要确定邮箱上放置的所有保留，以便可以在步骤3中临时删除它们。 请参阅[详细信息](#more-information)部分，了解有关如何识别邮箱上可能放置的类型保留的提示。 
    
此外，您还需要获取邮箱客户端访问设置，以便您可以暂时禁用它们，以便所有者（或其他用户）在此过程中无法访问邮箱。 最后，您可以获取 "可恢复的项目" 文件夹中的当前大小和项目数。 在第5步中删除 "可恢复的项目" 文件夹中的项目后，您将使用此信息验证项目是否已删除。
  
1. [连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。 请务必对已在 Exchange Online 中为其分配了适当管理角色的管理员帐户使用用户名和密码。 
    
2. 运行以下命令以获取有关单个项目恢复和已删除项目保留期限的信息。

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   如果启用了单个项目恢复，则必须在第2步中禁用它。 如果已删除项目的保留期未设置为30天（Exchange Online 中的最大值），则可以在第2步中增加它。 
    
3. 运行以下命令以获取邮箱的邮箱访问设置。 
    
    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   您将在步骤2中禁用所有这些访问方法。
    
4. 运行以下命令以获取有关保留和适用于邮箱的 Office 365 保留策略的信息。
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > 如果*InPlaceHolds*属性中的值过多，并且不是全部显示，则可以运行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行中显示每个值。 
  
5. 运行以下命令以获取有关组织范围内的 Office 365 保留策略的信息。 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   如果您的组织具有任何组织范围的 Office 365 保留策略，则必须在步骤3中将邮箱排除在这些策略之外。

   > [!TIP]
    > 如果*InPlaceHolds*属性中的值过多，并且不是全部显示，则可以运行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行中显示每个值。 
  
6. 运行以下命令，获取用户主邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的当前大小和项目总数。 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   如果已启用用户的存档邮箱，请运行以下命令，以获取存档邮箱中 "可恢复的项目" 文件夹中的文件夹和子文件夹中的项目大小和总数。 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   删除步骤5中的项目时，可以选择删除或不删除用户的主存档邮箱中的 "可恢复的项目" 文件夹中的项目。 如果为邮箱启用了自动扩展存档，则不会删除辅助存档邮箱中的项目。
  
## <a name="step-2-prepare-the-mailbox"></a>步骤2：准备邮箱

收集并保存有关邮箱的信息后，下一步是通过执行以下任务来准备邮箱： 
  
- **禁用对邮箱的客户端访问**，以便邮箱所有者无法访问其邮箱，并在此过程中对邮箱数据进行任何更改。 
    
- 将**已删除项目的保留期增加**到30天（Exchange Online 中的最大值），以便从 "可恢复的项目" 文件夹中清除这些项目，然后才能在步骤5中将其删除。 
    
- **禁用单个项目恢复**，以便在从第5步中的 "可恢复的项目" 文件夹中删除项目后，将不会保留项目（在已删除项目的保留期内）。 
    
- **禁用托管文件夹助理**，使其不处理邮箱，并保留您在步骤5中删除的项目。 
    
在 Exchange Online PowerShell 中执行以下步骤。
  
1. 运行以下命令以禁用对邮箱的所有客户端访问。 命令语法假定已在邮箱上启用所有客户端访问方法。

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > 最长可能需要60分钟才能禁用邮箱的所有客户端访问方法。 请注意，禁用这些访问方法不会断开他们当前登录的邮箱所有者。 如果未登录到所有者，则在禁用这些访问方法后，他们将无法访问其邮箱。 
  
2. 运行以下命令，将已删除项目的保留期增加到最大30天。 这假定当前设置少于30天。 

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 运行以下命令以禁用单个项目恢复。
    
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > 可能需要长达60分钟才能禁用单个项目恢复。 在此期间之前，请勿删除 "可恢复的项目" 文件夹中的项目。 
  
4. 运行以下命令以阻止托管文件夹助理处理邮箱。 正如前面所述，仅当具有保留锁定的 Office 365 保留策略未应用于邮箱时，才可以禁用托管文件夹助理。 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>步骤3：从邮箱中删除所有保留

从 "可恢复的项目" 文件夹中删除项目之前的最后一步是删除邮箱上的所有保留（在第1步中标识）。 必须删除所有保留，以便在从 "可恢复的项目" 文件夹中删除项目后，不会保留这些项目。 以下各节包含有关删除邮箱的不同类型的保留的信息。 请参阅[详细信息](#more-information)部分，了解有关如何识别邮箱上可能放置的类型保留的提示。 有关详细信息，请参阅[如何识别 Exchange Online 邮箱上放置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)。
  
> [!CAUTION]
> 如前所述，在从邮箱中删除保留之前，请与您的记录管理或法律部门核实。 
  
 ### <a name="litigation-hold"></a>诉讼保留
  
在 Exchange Online PowerShell 中运行以下命令，以从邮箱中删除诉讼保留。

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> 类似于禁用客户端访问方法和单个项目恢复，可能需要长达60分钟的时间才能删除诉讼保留。 在此时间段过后，请勿从 "可恢复的项目" 文件夹中删除项目。 
  
 ### <a name="in-place-hold"></a>就地保留
  
在 Exchange Online PowerShell 中运行以下命令，以标识邮箱中放置的就地保留。 对您在步骤1中标识的就地保留使用 GUID。 

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

在确定就地保留之后，可以使用 Exchange 管理中心（EAC）或 Exchange Online PowerShell 将邮箱从保留中删除。 有关详细信息，请参阅[创建或删除就地保留](https://go.microsoft.com/fwlink/?linkid=852668)。
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>应用于特定邮箱的 Office 365 保留策略
  
在[Security & 合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以确定应用于邮箱的 Office 365 保留策略。 对您在步骤1中标识`mbx`的`skp`保留策略使用 GUID （不包括或前缀）。 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

在确定保留策略后，请转到安全 & 合规性中心中的 "**信息管理** \> "**保留**页，编辑在上一步中标识的保留策略，然后从保留策略中包含的收件人列表中删除邮箱。 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>组织范围内的 Office 365 保留策略
  
组织范围和 Exchange 范围的 Office 365 保留策略应用于组织中的每个邮箱。 它们在组织级别（而不是邮箱级别）应用，并在您在步骤1中运行**set-organizationconfig** cmdlet 时返回。 在[Security & 合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以确定组织范围内的 Office 365 保留策略。 对您在步骤1中确定`mbx`的组织范围的保留策略使用 GUID （不包括前缀）。 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

在确定组织范围内的 Office 365 保留策略后，请转到安全 & 合规性中心中的 "**信息管理** \> "**保留**页，编辑在上一步中标识的每个组织范围的保留策略，并将邮箱添加到排除的收件人列表中。 执行此操作会将用户的邮箱从保留策略中删除。 

### <a name="office-365-retention-labels"></a>Office 365 保留标签

每当用户应用配置为保留内容或保留内容，然后将内容删除到其邮箱中的任何文件夹或项目的标签时， *ComplianceTagHoldApplied*邮箱属性将设置为**True**。 发生这种情况时，邮箱被视为处于保留状态，就像将其置于诉讼保留状态或分配到 Office 365 保留策略一样。

若要查看*ComplianceTagHoldApplied*属性的值，请在 Exchange Online PowerShell 中运行以下命令：

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

确定邮箱处于保留状态，因为保留标签应用于文件夹或项目，您可以使用 "安全和合规中心" 中的 "内容搜索" 工具来搜索带标签的项目，方法是使用 New-compliancetag 搜索条件。 有关详细信息，请参阅关键字查询中的 "搜索条件" 部分[和内容搜索的搜索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)。

有关标签的详细信息，请参阅[Office 365 概述标签](labels.md)。

 ### <a name="ediscovery-case-holds"></a>电子数据展示事例保留
  
在[Security & 合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以确定与应用于邮箱的电子数据展示事例关联的保留。 使用您在步骤1中确定`UniH`的电子数据展示保留的 GUID （不包括前缀）。 第二个命令显示与保留相关联的电子数据展示事例的名称;第三个命令显示保留的名称。 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

确定电子数据展示事例的名称和保留后，请转到合规中心中的**电子数据** \>展示**电子数据**展示页面，打开事例，并将邮箱从保留中删除。 有关详细信息，请参阅[电子数据展示事例](ediscovery-cases.md)。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>步骤4：从邮箱中删除延迟保留

从邮箱中删除了任何类型的保留后， *DelayHoldApplied*或*DelayReleaseHoldApplied*邮箱属性的值将设置为**True**。 在下次托管文件夹助理处理邮箱并检测已删除保留时，会发生这种情况。 这称为*延迟保留*，意味着实际删除保留的延迟时间为30天，以防止永久删除邮箱中的数据。 （延迟保留的目的是使管理员有机会搜索或恢复在删除保留后将清除的邮箱项目。） 将延迟保留放在邮箱上时，该邮箱仍被视为无限持续时间处于保留状态，就像该邮箱处于诉讼保留状态一样。 30天后，延迟保留过期，Office 365 将自动尝试删除延迟保留（通过将*DelayHoldApplied*或*DelayReleaseHoldApplied*属性设置为**False**），以便删除保留。 有关延迟保留的详细信息，请参阅[如何识别 Exchange Online 邮箱上的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)一节中的 "管理延迟挂起的邮箱" 一节。

在您可以删除步骤5中的项目之前，必须从邮箱中删除延迟保留。 首先，通过在 Exchange Online PowerShell 中运行以下命令来确定是否对邮箱应用延迟保留：

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

如果将*DelayHoldApplied*或*DelayReleaseHoldApplied*属性的值设置为**False**，则不会在邮箱上放置延迟保留。 您可以转到步骤5并删除 "可恢复的项目" 文件夹中的项目。

如果*DelayHoldApplied*或*DelayReleaseHoldApplied*属性的值设置为**True**，则运行以下命令之一以删除延迟保留：

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

或

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

您必须在 Exchange Online 中向您分配 "合法保留" 角色，才能使用*RemoveDelayHoldApplied*或*RemoveDelayReleaseHoldApplied*参数。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>步骤5：删除 "可恢复的项目" 文件夹中的项目

现在，您已准备好在 "可恢复的项目" 文件夹中实际删除项目，方法是使用 Security & 合规性中心中的[new-compliancesearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)和[new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction) cmdlet。 

若要执行此操作，请参阅[搜索和删除电子邮件](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)。

### <a name="verify-that-items-were-deleted"></a>验证项目是否已被删除

若要验证是否已成功删除邮箱的 "可恢复的项目" 文件夹中的项目，请使用 Exchange Online PowerShell 中的**get-mailboxfolderstatistics** cmdlet 检查 "可恢复的项目" 文件夹中的邮件大小和数量。 您可以将这些统计信息与您在步骤1中收集的统计信息进行比较。 
  
在中运行以下命令，以获取用户主邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的当前大小和项目总数。 
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

运行以下命令以获取用户存档邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的项目大小和总数。 

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>步骤6：将邮箱还原到其以前的状态

最后一步是将邮箱还原回其以前的配置。 这意味着重置您在步骤2中更改的属性，并重新应用您在步骤3中删除的保留。 这包括：
  
- 将已删除项目的保留期更改回其以前的值。 或者，您可以仅将此设置保留为30天，即 Exchange Online 中的最大值。
    
- 重新启用单个项目恢复。
    
- 重新启用客户端访问方法，以便所有者可以访问其邮箱。
    
- 重新应用已删除的保留策略和 Office 365 保留策略。
    
- 重新启用托管文件夹助理以处理邮箱。
    
> [!IMPORTANT]
> 建议您在重新启用托管文件夹助理以处理邮箱之前，等待24小时后再365应用保留策略（并验证是否已就绪）。 
  
在 Exchange Online PowerShell 中执行以下步骤（按指定的顺序）。
  
1. 运行以下命令，将已删除项目的保留期更改回其原始值。 这假定上一个设置的时间不到30天;例如，14天。 
    
    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. 运行以下命令以重新启用单个项目恢复。
   
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 运行以下命令，将所有客户端访问方法重新启用到邮箱。
    
    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. 重新应用您在步骤3中删除的保留。 根据保留的类型，使用以下过程之一。
    
    **诉讼保留**
    
    运行以下命令以重新启用邮箱的诉讼保留。
    
    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**
    
    使用 EAC （或 Exchange Online PowerShell）将邮箱重新添加到就地保留。 
    
    **应用于特定邮箱的 Office 365 保留策略**
    
    使用安全 & 合规性中心将邮箱重新添加到保留策略。 转到 "安全性 & 合规性中心" 中的 "**信息管理** \> "**保留**页，编辑保留策略，并将邮箱重新添加到应用保留策略的收件人列表中。 
    
    **组织范围内的 Office 365 保留策略**
    
    如果通过从策略中排除组织范围或 Exchange 范围内的保留策略，则使用安全 & 合规性中心将邮箱从排除的用户列表中删除。 转到 "安全性 & 合规性中心" 中的 "**信息管理** \> "**保留**页，编辑组织范围的保留策略，然后从排除的收件人列表中删除邮箱。 执行此操作将把保留策略重新应用到用户的邮箱。 
    
    **电子数据展示事例保留**
    
    使用安全 & 合规性中心将邮箱重新添加到与电子数据展示事例相关联的保留。 转到 "**电子数据展示** \> **电子数据**展示" 页，打开事例，并将邮箱重新添加到保留。 
    
5. 运行以下命令，以允许托管文件夹助理再次处理邮箱。 如前所述，在重新启用托管文件夹助理之前，我们建议您等待24小时后再重新应用365保留策略（并验证是否已就绪）。 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. 若要验证是否已将邮箱还原回其以前的配置，可以运行以下命令，然后将设置与您在步骤1中收集的设置进行比较。

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>更多信息

下面的表格介绍了在运行 Set-organizationconfig **cmdlet 或** **** cmdlet 时，如何根据*InPlaceHolds*属性中的值标识不同类型的保留。 有关更多详细信息，请参阅[如何识别 Exchange Online 邮箱上放置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)。

如前所述，在成功删除 "可恢复的项目" 文件夹中的项目之前，必须从邮箱中删除所有保留和 Office 365 保留策略。 
  
|**保留类型**|**示例值**|**如何识别保留**|
|:-----|:-----|:-----|
|诉讼保留  <br/> | `True` <br/> |*LitigationHoldEnabled*属性设置为`True`。  <br/> |
|就地保留  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds*属性包含邮箱中放置的就地保留的 GUID。 您可以指示这是就地保留，因为 GUID 不以前缀开头。  <br/> 您可以使用 Exchange `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Online PowerShell 中的命令来获取有关邮箱的就地保留的信息。  <br/> |
| 在应用于特定邮箱的安全性 & 合规性中心中的 Office 365 保留策略  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> 或  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |当您运行**邮箱获取**cmdlet 时， *InPlaceHolds*属性还包含应用于邮箱的 Office 365 保留策略的 guid。 您可以确定保留策略，因为 GUID 以`mbx`前缀开头。 如果保留策略的 GUID 以`skp`前缀开头，则表示该保留策略应用于 Skype for business 会话。  <br/> 若要标识应用于邮箱的 Office 365 保留策略，请在 Security & 合规性中心 PowerShell 中运行以下命令： <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>运行此命令时， `mbx`请`skp`务必删除或前缀。  <br/> |
|安全 & 合规中心中的组织范围内的 Office 365 保留策略  <br/> |无值  <br/> 或  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`（指示邮箱已从组织范围的策略中排除）  <br/> |即使在运行**邮箱**cmdlet 时， *InPlaceHolds*属性为空，仍可能会将一个或多个组织范围内的 Office 365 保留策略应用于邮箱。  <br/> 若要验证这一点，可以在`Get-OrganizationConfig | FL InPlaceHolds` Exchange Online PowerShell 中运行命令，以获取组织范围内的 Office 365 保留策略的 guid 列表。 应用于 Exchange 邮箱的组织范围的保留策略的 GUID 以`mbx`前缀开头;例如， `mbxa3056bb15562480fadb46ce523ff7b02`。  <br/> 若要标识应用于邮箱的组织范围内的 Office 365 保留策略，请在 Security & 合规性中心 PowerShell 中运行以下命令： <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>如果从组织范围内的 Office 365 保留策略中排除了邮箱，则在运行 "**获取邮箱**" cmdlet 时，保留策略的 GUID 将显示在用户邮箱的*InPlaceHolds*属性中。它是由前缀`-mbx`标识的;例如，`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|安全 & 合规中心中的电子数据展示案例保留  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds*属性还包含与可能位于邮箱上的安全性 & 合规性中心中的电子数据展示事例相关的任何保留的 GUID。 你可以告诉这是电子数据展示事例保留，因为 GUID 以`UniH`前缀开头。  <br/> 您可以使用 Security `Get-CaseHoldPolicy` & 合规性中心 PowerShell 中的 cmdlet 来获取有关邮箱中的保留与邮箱关联的电子数据展示事例的信息。 例如，您可以运行命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`以显示邮箱上的事例保留的名称。 运行此命令时， `UniH`请务必删除前缀。  <br/><br/> 若要标识与邮箱的保留内容相关联的电子数据展示事例，请运行以下命令：<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


