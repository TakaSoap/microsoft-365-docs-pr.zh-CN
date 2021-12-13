---
title: 删除云邮箱保留的"可恢复的项目"文件夹中的项目
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 了解管理员如何删除某个邮箱的用户"可恢复的项目"文件夹中Exchange Online，即使该邮箱已置于法定保留状态。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: 89022e39aef17609774c90696e7bab54e66a95e0
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421650"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>删除保留状态云邮箱的“可恢复的项目”文件夹中的项目

存在邮箱的"可恢复Exchange Online文件夹，防止意外或恶意删除。 它还用于存储合规性功能（如保留项和电子数据展示搜索）保留和访问的项目。 但是，在某些情况下，组织可能有无意中保留在"可恢复的项目"文件夹中必须删除的数据。 例如，用户可能会无意中发送或转发一封电子邮件，其中包含可能导致严重业务后果的敏感信息或信息。 即使邮件被永久删除，它也可能无限期保留，因为邮箱已被置于法定保留状态。 此方案称为 *数据泄漏，* 因为数据无意中溢出到Office 365。  在这些情况下，您可以删除 Exchange Online 邮箱的用户"可恢复的项目"文件夹中的项目，即使该邮箱已使用 Office 365 中的一个不同保留功能置于保留状态。 这些类型的保留包括诉讼保留、In-Place保留、电子数据展示保留和在 Office 365 或 Microsoft 365 安全与合规中心创建的保留策略。

本文介绍了管理员如何从保留的基于云的邮箱的"可恢复的项目"文件夹中删除项目。 此过程包括禁用对邮箱的访问和禁用单个项目恢复、禁用托管文件夹助理处理邮箱、临时删除保留、从"可恢复的项目"文件夹中删除项目，然后将邮箱还原到其以前的配置。 过程如下：
  
[步骤 1：收集有关邮箱的信息](#step-1-collect-information-about-the-mailbox)

[步骤 2：准备邮箱](#step-2-prepare-the-mailbox)

[步骤 3：从邮箱中删除所有保留](#step-3-remove-all-holds-from-the-mailbox)

[步骤 4：从邮箱中删除延迟保留](#step-4-remove-the-delay-hold-from-the-mailbox)

[步骤 5：删除"可恢复的项目"文件夹中的项目](#step-5-delete-items-in-the-recoverable-items-folder)

[步骤 6：将邮箱还原到以前的状态](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> 本文中概述的过程将导致数据被永久删除， (从) 中Exchange Online数据。 这意味着从"可恢复的项目"文件夹中删除的邮件无法恢复，并且不能用于法律发现或其他合规性目的。 如果要从作为诉讼保留、In-Place 保留、电子数据展示保留或 Microsoft 365 合规中心 中创建的保留策略的一部分置于保留的邮箱中删除邮件，请在删除保留之前，与记录管理或法律部门核实。 您的组织可能拥有一个策略，用于定义邮箱是置于保留状态还是数据泄漏事件优先。
  
## <a name="before-you-delete-items"></a>删除项目之前

- 若要创建并运行内容搜索，您必须是电子数据展示管理员角色组的成员，或者分配有“合规性搜索”管理角色。 若要删除邮件，您必须是组织管理角色组的成员或分配有“搜索并清除”管理角色。 有关向角色组添加用户的信息，请参阅分配 [电子数据展示权限](./assign-ediscovery-permissions.md)。

- 如果将邮箱分配给组织范围的保留策略，则您必须从策略中排除该邮箱，然后才能从"可恢复的项目"文件夹中删除项目。 同步策略更改以及从策略中删除邮箱可能需要 24 小时。 有关详细信息，请参阅本文从邮箱中删除所有保留部分中的"组织范围的[](#organization-wide-retention-policies)保留策略"。

- 对于已使用保留锁定锁定的保留策略分配保留设置的邮箱，无法执行此过程。 这是因为此锁定可防止您从策略中删除或排除邮箱，并阻止禁用邮箱上的托管文件夹助理。 有关锁定保留策略详细信息，请参阅使用保留锁定来限制对保留策略 [和保留标签策略的更改](retention-preservation-lock.md)。

- 非活动邮箱不支持本文中描述的过程。 这是因为在删除非活动邮箱 (无法将保留策略) 或保留策略重新应用至非活动邮箱。 从非活动邮箱删除保留时，该保留将更改为正常的软删除邮箱，并且将在托管文件夹助理处理后从组织永久删除。

- 如果邮箱未处于保留状态 (或未启用单个项目恢复) ，可以从"可恢复的项目"文件夹中删除项目。 若要详细了解如何操作，请参阅在组织中搜索和 [删除电子邮件](./search-for-and-delete-messages-in-your-organization.md)。

## <a name="step-1-collect-information-about-the-mailbox"></a>步骤 1：收集有关邮箱的信息

第一步是从将影响此过程的目标邮箱中收集所选属性。 请务必记下这些设置或将它们保存到文本文件中，因为您将更改其中一些属性，然后在从"可恢复的项目"文件夹中删除项目后，恢复步骤 6 中的原始值。 以下是需要收集的邮箱属性的列表。
  
- *SingleItemRecoveryEnabled*  和  *RetainDeletedItemsFor*。 如有必要，您将在步骤 3 中禁用单个恢复并增加已删除项目的保留期。

- *LitigationHoldEnabled*  和  *InPlaceHolds*。 您需要标识邮箱上设置的所有保留，以便可以在步骤 3 中暂时删除它们。 有关如何 [标识邮箱](#more-information) 上可能设置的类型保留的提示，请参阅详细信息部分。

此外，您需要获取邮箱客户端访问设置，以便您可以暂时禁用这些设置，以便所有者 (或其他) 用户无法在此过程中访问邮箱。 最后，你可以获取"可恢复的项目"文件夹中的当前大小和项目数。 在步骤 5 中删除"可恢复的项目"文件夹中的项目后，您将使用此信息验证项目已删除。
  
1. [连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 请确保为管理员帐户使用用户名和密码，该帐户在 Exchange Online 中分配了适当的管理角色。

2. 运行以下命令，获取有关单个项目恢复和已删除邮件保留期的信息。

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   如果启用单个项目恢复，您必须在步骤 2 中禁用它。 如果已删除项目的保留期未设置为 (中最大值的 30 Exchange Online) ，可以在步骤 2 中增加该值。

3. 运行以下命令获取邮箱的邮箱访问设置。

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   您将在步骤 2 中禁用所有这些访问方法。

4. 运行以下命令，获取有关应用于邮箱的保留和保留策略的信息。

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

    > [!TIP]
    > 如果  *InPlaceHolds*  属性中的值太多，并且并非所有值都显示，可以运行命令以在单独的行上  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 显示每个值。
  
5. 运行以下命令，获取有关任何组织范围内的保留策略的信息。 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   如果您的组织具有任何组织范围的保留策略，您必须在步骤 3 中将邮箱从这些策略中排除。 可能需要 24 小时才能复制更改。

    > [!TIP]
    > 如果  *InPlaceHolds*  属性中的值太多，并且并非所有值都显示，可以运行命令以在单独的行上  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 显示每个值。 
  
6. 运行以下命令，确定是否对邮箱应用了延迟保留。

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   如果 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 属性的值设置为 **True，** 则延迟保留将应用于邮箱，并且必须删除。 有关延迟保留详细信息，请参阅步骤 [4：从邮箱中删除延迟保留](#step-4-remove-the-delay-hold-from-the-mailbox)。

   如果任一属性的值都设置为 **False，** 则延迟保留不会应用于邮箱，您可以跳过步骤 4。

7. 运行以下命令，获取用户主邮箱中"可恢复的项目"文件夹中文件夹和子文件夹中的当前大小和项目总数。

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   如果用户的存档邮箱已启用，请运行以下命令，获取存档邮箱中"可恢复的项目"文件夹的文件夹和子文件夹中的项目的大小和总数。 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   在步骤 5 中删除项目时，可以选择删除或不删除用户主存档邮箱中"可恢复的项目"文件夹中的项目。 如果为邮箱启用自动扩展存档，将不会删除辅助存档邮箱中的项目。
  
## <a name="step-2-prepare-the-mailbox"></a>步骤 2：准备邮箱

收集和保存有关邮箱的信息后，下一步是通过执行以下任务来准备邮箱：
  
- **禁用客户端对邮箱的访问** ，以便邮箱所有者在此过程中无法访问其邮箱并更改邮箱数据。

- **将已删除邮件** 的保留期增加至 30 天 (Exchange Online) 以便项目不会从"可恢复的项目"文件夹中清除，然后才能在步骤 5 中删除它们。

- 禁用 **单个项目** 恢复，以便从步骤 5 中的"可恢复的项目"文件夹中删除 (在已删除邮件保留期) 内不会保留这些项目。

- **禁用托管文件夹助理** ，以便它不会处理邮箱并保留在步骤 5 中删除的项目。

在 PowerShell 中Exchange Online步骤。
  
1. 运行以下命令以禁用对邮箱的所有客户端访问。 命令语法假定邮箱上已启用所有客户端访问方法。

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

    > [!NOTE]
    > 可能需要 60 分钟才能禁用邮箱的所有客户端访问方法。 请注意，禁用这些访问方法不会断开邮箱所有者（如果他们当前已登录）断开连接。 如果所有者未登录，则禁用这些访问方法后，他们无法访问其邮箱。
  
2. 运行以下命令，将已删除项目的保留期最长增加 30 天。 这假定当前设置小于 30 天。

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 运行以下命令以禁用单个项目恢复。

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

    > [!NOTE]
    > 禁用单个项目恢复可能需要 240 分钟。 不要删除"可恢复的项目"文件夹中的项目，直到此期限结束。
  
4. 运行以下命令以防止托管文件夹助理处理邮箱。 如前所述，只有当具有保留锁定的保留策略未应用于邮箱时，才能禁用托管文件夹助理。

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>步骤 3：从邮箱中删除所有保留

从"可恢复的项目"文件夹中删除项目之前的最后一步是删除在步骤 1 (对邮箱) 标识的所有保留。 必须删除所有保留，以便从"可恢复的项目"文件夹中删除项目后不会保留这些项目。 以下各节包含有关删除邮箱上不同类型的保留的信息。 有关如何 [标识邮箱](#more-information) 上可能设置的类型保留的提示，请参阅详细信息部分。 有关详细信息，请参阅如何标识邮箱[中置于Exchange Online的类型](identify-a-hold-on-an-exchange-online-mailbox.md)。
  
> [!CAUTION]
> 如前所述，在从邮箱中删除保留之前，请与记录管理或法律部门核实。
  
### <a name="litigation-hold"></a>诉讼保留
  
在 PowerShell Exchange Online以下命令以从邮箱中删除诉讼保留。

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> 与禁用单个项目恢复类似，可能需要 240 分钟才能删除诉讼保留。 不要从"可恢复的项目"文件夹中删除项目，直到此期限结束。
  
### <a name="in-place-hold"></a>就地保留
  
在 PowerShell Exchange Online以下命令，In-Place置于邮箱上的保留状态。 使用在步骤 1 In-Place标识的保留的 GUID。

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

确定保留In-Place后，可以使用 Exchange 管理中心 (<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">EAC</a>) 或 Exchange Online PowerShell 从保留中删除邮箱。 有关详细信息，请参阅创建[或删除In-Place保留。](/exchange/security-and-compliance/create-or-remove-in-place-holds)
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>应用于特定邮箱的保留策略
  
在安全与合规& [PowerShell 中](/powershell/exchange/connect-to-scc-powershell) 运行以下命令，以标识应用于邮箱的保留策略。 此命令还将返回应用于Teams保留策略的任何邮件。 使用 GUID (步骤 1 中) 标识的保留策略的 或 前缀 `mbx` `skp` 。

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

确定保留策略后，请转到 Microsoft 365 合规中心 中的"信息治理""保留"页，编辑在上一步中确定的保留策略，并从保留策略中包含的收件人列表中删除  >  邮箱。
  
### <a name="organization-wide-retention-policies"></a>组织范围内的保留策略
  
组织范围内、Exchange和Teams保留策略将应用于组织的每一个邮箱。 它们在组织级别应用， (邮箱级别应用) 在步骤 1 中运行 **Get-OrganizationConfig** cmdlet 时返回。 在安全与合规& [PowerShell 中](/powershell/exchange/exchange-online-powershell) 运行以下命令，以标识组织范围内的保留策略。 使用 GUID (步骤 1 中) 确定的组织范围的保留策略的前缀  `mbx` 值。

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

确定组织范围的保留策略后，请转到  >  Microsoft 365 合规中心 中的"信息治理""保留"页，编辑在上一步中确定的每个组织范围内的保留策略，将邮箱添加到已排除收件人列表中。 执行此操作将删除保留策略中的用户邮箱。

> [!IMPORTANT]
> 从组织范围的保留策略中排除邮箱后，可能需要 24 小时才能同步此更改并从策略中删除邮箱。

### <a name="retention-labels"></a>保留标签

每当用户应用配置为保留内容或保留内容的标签，然后删除其邮箱中任何文件夹或项目的内容时 *，ComplianceTagHoldApplied* 邮箱属性都设置为 **True**。 发生这种情况时，邮箱被视为处于保留状态，就像将其置于诉讼保留或分配给保留策略一样。

若要查看 *ComplianceTagHoldApplied* 属性的值，在 PowerShell 中运行Exchange Online命令：

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

确定邮箱因保留标签应用于文件夹或项目而置于保留状态后，可以使用 Microsoft 365 合规中心 中的内容搜索工具，使用"保留标签"条件搜索 **已标记项目**。 有关更多信息，请参阅：

- 了解保留策略和保留标签中的"使用内容搜索查找具有特定保留标签的所有 [内容"部分](retention.md#using-content-search-to-find-all-content-with-a-specific-retention-label)

- 内容搜索的关键字 [查询和搜索条件中的"搜索条件"部分](keyword-queries-and-search-conditions.md#conditions-for-common-properties)。

有关标签详细信息，请参阅 [了解保留策略和保留标签](retention.md)。

### <a name="ediscovery-holds"></a>电子数据展示保留
  
在安全与&合规中心 [PowerShell](/powershell/exchange/connect-to-scc-powershell) 中运行以下命令，以标识与电子数据展示 ("电子数据展示"保留) 应用于邮箱 *的* 保留。 使用 GUID (步骤 1 中) 标识的电子数据展示保留的前缀  `UniH` 和前缀。 第二个命令显示与保留关联的电子数据展示案例的名称;第三个命令显示保留的名称。
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

确定电子数据展示案例的名称和保留后，请转到合规性中心中的电子数据展示 \> **电子数据** 展示页面，打开该案例，然后从保留中删除邮箱。 有关标识电子数据展示保留项详细信息，请参阅如何标识邮箱中保留的保留类型中的"电子数据展示保留Exchange Online[部分](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>步骤 4：从邮箱中删除延迟保留

从邮箱中删除任何类型的保留后 *，DelayHoldApplied* 或 *DelayReleaseHoldApplied* 邮箱属性的值将设置为 **True**。 这发生在托管文件夹助理下次处理邮箱并检测已删除保留时。 这称为 *延迟保留* ，意味着保留的实际删除延迟 30 天，以防止从邮箱中永久删除数据。  (延迟保留的目的是使管理员有机会搜索或恢复将在删除保留后清除的邮箱项目。) 在邮箱上设置延迟保留时，该邮箱仍被视为处于无限期保留状态，就像邮箱处于诉讼保留状态一样。 30 天后，延迟保留过期，Microsoft 365 将自动尝试删除延迟保留 (，将 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 属性设置为 **False**) 以便删除该保留。 有关延迟保留详细信息，请参阅如何标识邮箱上置于的保留类型中的"管理处于延迟保留状态Exchange Online[部分](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。

如果 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 属性的值设置为 **True，** 请运行以下命令之一来删除延迟保留：

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

或

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

您必须获得法定保留角色Exchange Online *RemoveDelayHoldApplied* 或 *RemoveDelayReleaseHoldApplied* 参数。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>步骤 5：删除"可恢复的项目"文件夹中的项目

现在，可以使用安全与合规中心 PowerShell 中的 [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) 和 [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) cmdlet 实际删除"可恢复的项目"文件夹中&项。

若要搜索位于"可恢复的项目"文件夹中的项目，我们建议您执行目标 *集合*。 这意味着您仅将搜索范围缩小到"可恢复的项目"文件夹中的项目。 为此，可以运行使用目标集合的内容 [搜索文章中的脚本](use-content-search-for-targeted-collections.md) 。 此脚本返回目标"可恢复的项目"文件夹中所有子文件夹的文件夹 ID 属性的值。 然后，在搜索查询中使用该文件夹 ID 返回位于该文件夹中的项目。

以下是搜索和删除用户的"可恢复的项目"文件夹中的项目的过程概述：

1. 运行目标集合脚本，该脚本返回目标用户邮箱中所有文件夹的文件夹 ID。 脚本连接到同Exchange Online PowerShell 会话中& PowerShell 和安全与安全与合规 PowerShell。 有关详细信息，请参阅 [运行脚本获取邮箱的文件夹列表](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)。

2. 复制"可恢复的项目"文件夹中所有子文件夹的文件夹 ID。 或者，可以将脚本的输出重定向到文本文件。

   以下是"可恢复的项目"文件夹中的子文件夹的列表和说明，可以从中搜索和删除项目：

   - **删除**：包含已删除项目的保留期尚未到期的软删除项目。 用户可以使用 Outlook 中的"恢复已删除邮件"工具从此子文件夹恢复软删除Outlook。

   - **清除**：包含已删除项目的保留期已到期的硬删除项目。 用户还可以从"可恢复的项目"文件夹中清除项目来硬删除项目。 如果邮箱置于保留状态，则保留硬删除的项目。 此子文件夹对最终用户不可见。

   - **DiscoveryHolds：** 包含已由电子数据展示保留或保留策略保留的硬删除项目。 此子文件夹对最终用户不可见。

   - **SubstrateHolds：** 包含来自Teams保留策略或另一类保留项保留的其他基于云的应用中的硬删除项目。 此子文件夹对最终用户不可见。

3. 使用安全 & 合规中心 PowerShell) 中的 **New-ComplianceSearch** cmdlet (或使用合规性中心中的内容搜索工具创建从目标用户的"可恢复的项目"文件夹中返回项目的内容搜索。 为此，可以在要搜索的所有子文件夹的搜索查询中包括 FolderId。 例如，以下查询返回"清除"和"eDiscoveryHolds"子文件夹内的所有邮件：

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   有关运行使用文件夹 ID 属性的内容搜索详细信息和示例，请参阅使用文件夹 [ID 或执行目标集合](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)。

   > [!NOTE]
   > 如果使用 **New-ComplianceSearch** cmdlet 搜索"可恢复的项目"文件夹，请务必使用 **Start-ComplianceSearch** cmdlet 运行搜索。

4. 创建内容搜索并验证它返回要删除的项目后，使用安全 & 合规中心 PowerShell) 中的命令 (永久删除在上一步中创建的内容搜索返回的项目。 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 例如，可以运行类似于以下命令的命令：

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. 运行上一个命令时，每个邮箱最多删除 10 个项目。 这意味着您可能必须多次运行该命令，以删除要删除的"可恢复的项目"文件夹中 `New-ComplianceSearchAction -Purge` 的所有项目。 若要删除其他项目，首先必须删除以前的合规性搜索清除操作。 通过运行 `Remove-ComplianceSearchAction` cmdlet 可完成此操作。 例如，若要删除在上一步中运行的清除操作，请运行以下命令：

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   完成此操作后，可以创建新的合规性搜索清除操作以删除更多项目。 在创建新的清除操作之前，必须删除每个清除操作。

   若要获取合规性搜索操作的列表，可以运行 `Get-ComplianceSearchAction` cmdlet。 清除操作通过附加到 `_Purge` 搜索名称进行标识。

### <a name="verify-that-items-were-deleted"></a>验证项目已删除

若要验证您是否已成功从邮箱的"可恢复的项目"文件夹中删除项目，请使用 Exchange Online PowerShell 中的 **Get-MailboxFolderStatistics** cmdlet 检查"可恢复的项目"文件夹中的项目大小和数量。 可以将这些统计信息与在步骤 1 中收集的统计信息进行比较。
  
在 中运行以下命令，获取用户主邮箱中"可恢复的项目"文件夹的文件夹和子文件夹中的当前大小和项目总数。
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

运行以下命令，获取用户存档邮箱中"可恢复的项目"文件夹的文件夹和子文件夹中的项目大小和总数。

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>步骤 6：将邮箱还原到以前的状态

最后一步是将邮箱恢复为以前的配置。 这意味着重置在步骤 2 中更改的属性，并重新应用在步骤 3 中删除的保留项。 这包括：
  
- 将已删除项目的保留期更改回其以前的值。 或者，你可以仅将此值保留为 30 天，即 Exchange Online。

- 重新启用单个项目恢复。

- 重新启用客户端访问方法，以便所有者可以访问其邮箱。

- 重新应用已删除的保留和保留策略。

- 重新启用托管文件夹助理以处理邮箱。

> [!IMPORTANT]
> 建议在重新应用保留或保留策略 (并验证其是否已在) 之后等待 24 小时，然后再重新启用托管文件夹助理处理邮箱。
  
在 PowerShell (按指定顺序) 执行Exchange Online步骤。
  
1. 运行以下命令，将已删除项目的保留期更改回其原始值。 这假定上一个设置少于 30 天;例如，14 天。

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. 运行以下命令以重新启用单个项目恢复。

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 运行以下命令以重新启用邮箱的所有客户端访问方法。

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. 重新应用在步骤 3 中删除的保留项。 根据保留类型，请使用以下过程之一。

    **诉讼保留**

    运行以下命令以重新启用邮箱的诉讼保留。

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **就地保留**

    使用 EAC (或 Exchange Online PowerShell) 将邮箱添加回"In-Place保留"。

    **应用于特定邮箱的保留策略**

    使用 Microsoft 365 合规中心将邮箱添加回保留策略。 转到合规 **中心的"信息** 治理""保留"页面，编辑保留策略，将邮箱添加回应用了保留  >  策略的收件人列表。

    **组织范围内的保留策略**

    如果通过从策略中Exchange组织范围的保留策略或组织范围的保留策略，则使用 Microsoft 365 合规中心 从已排除用户列表中删除邮箱。 转到合规 **中心的"信息** 治理""保留"页面，编辑组织范围的保留策略，并从已排除  >  收件人列表中删除邮箱。 执行此操作后，保留策略将重新应用至用户邮箱。

    **电子数据展示案例保留**

    使用Microsoft 365 合规中心将邮箱添加回与电子数据展示案例关联的保留。 转到"**电子数据展示**  >  **核心**"页面，打开案例，将邮箱添加回保留。 

5. 运行以下命令以允许托管文件夹助理再次处理邮箱。 如前所述，建议在重新应用保留策略 (并验证其是否已在) 之后等待 24 小时，然后再重新启用托管文件夹助理。

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. 若要验证邮箱已恢复为以前的配置，可以运行以下命令，然后将设置与在步骤 1 中收集的设置进行比较。

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>更多信息

下表介绍了在运行 **Get-Mailbox** 或 **Get-OrganizationConfig** cmdlet 时，如何根据 *InPlaceHolds* 属性的值标识不同类型的保留。 有关更多详细信息，请参阅如何标识邮箱中置于Exchange Online[的类型](identify-a-hold-on-an-exchange-online-mailbox.md)。

如前所述，您必须从邮箱中删除所有保留和保留策略，然后才能成功删除"可恢复的项目"文件夹中的项目。
  
| 保留类型 | 示例值 | 如何识别保留 |
|:-----|:-----|:-----|
|诉讼保留  <br/> | `True` <br/> |*LitigationHoldEnabled* 属性设置为 `True` 。  <br/> |
|就地保留  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds* 属性包含邮箱上In-Place保留的 GUID。 你可以判断这是一个In-Place保留，因为 GUID 不以前缀开头。  <br/> 可以在 `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` PowerShell Exchange Online 命令获取有关邮箱In-Place保留的信息。  <br/> |
| 应用于特定Microsoft 365 合规中心保留策略  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> 或  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |运行 **Get-Mailbox** cmdlet 时  *，InPlaceHolds*  属性还包含应用于邮箱的保留策略的 GUID。 您可以标识保留策略，因为 GUID 以前缀  `mbx` 开头。 如果保留策略的 GUID 以前缀开头，则表明保留策略 `skp` 应用于Skype for Business对话。  <br/> 若要标识应用于邮箱的保留策略，请运行安全与合规中心 PowerShell &命令： <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>运行此命令时，  `mbx` 请务必删除 或  `skp` 前缀。  <br/> |
|组织中组织的保留策略Microsoft 365 合规中心  <br/> |无值  <br/> 或  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (表示邮箱从组织范围内的策略中)   <br/> |即使运行 **Get-Mailbox** cmdlet 时 *InPlaceHolds* 属性为空，也可能有一个或多个组织范围的保留策略应用于邮箱。  <br/> 若要验证这一点，可以在 Exchange Online PowerShell 中运行命令，获取组织范围内的保留策略 `Get-OrganizationConfig | FL InPlaceHolds` 的 GUID 列表。 应用于邮箱的组织范围的保留策略的 GUID Exchange前缀开头; `mbx` 例如， `mbxa3056bb15562480fadb46ce523ff7b02` 。  <br/> 若要标识应用于邮箱的组织范围的保留策略，请运行安全与合规中心 PowerShell &命令： <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>如果从组织范围的保留策略中排除邮箱，则在您运行 **Get-Mailbox** cmdlet 时，保留策略的 GUID 将显示在用户邮箱的 *InPlaceHolds* 属性中;它由 前缀标识 `-mbx` ;例如，`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|电子数据展示服务中的Microsoft 365 合规中心  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds* 属性还包含与邮箱上可能放置的邮箱中的电子数据展示Microsoft 365 合规中心关联的任何保留的 GUID。 你可以判断这是电子数据展示案例保留，因为 GUID 以前缀  `UniH` 开头。  <br/> 您可以使用安全与合规& PowerShell 中的 cmdlet 获取有关邮箱上的保留相关联的电子数据展示  `Get-CaseHoldPolicy` 案例的信息。 例如，可以运行命令来显示邮箱上案例  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 保留的名称。 运行此命令时  `UniH` ，请务必删除前缀。  <br/><br/> 若要标识与邮箱上的保留相关联的电子数据展示案例，请运行以下命令：<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
