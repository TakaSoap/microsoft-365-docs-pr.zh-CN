---
title: 如何识别为 Exchange Online 邮箱设置的保留类型
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: 了解如何确定可置于邮箱中邮箱中Exchange Online不同类型的Microsoft 365。
ms.openlocfilehash: 708d6e18428d090a6ba5291aea95e1a690dac556
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61422527"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>如何识别为 Exchange Online 邮箱设置的保留类型

本文介绍如何识别邮箱中Exchange Online邮箱Microsoft 365。

Microsoft 365提供了几种防止邮箱内容被永久删除的方法。 这样，贵组织可以保留内容以满足合规性法规，或在法律和其他类型的调查期间保留内容。 下面是一个保留功能列表， (*在*) 保留Office 365：

- **[诉讼保留](create-a-litigation-hold.md)：** 应用于用户邮箱的保留Exchange Online。

- **[电子数据展示保留](create-ediscovery-holds.md)：** 与安全与合规中心中的核心电子数据展示案例相关联的保留项。 电子数据展示保留可应用于用户邮箱以及用户组和用户Microsoft 365邮箱Microsoft Teams。

- **[就地保留](/Exchange/security-and-compliance/create-or-remove-in-place-holds)**：通过使用 Exchange Online 中 Exchange 管理中心中的 In-Place 电子数据展示 & 保留工具应用于用户邮箱的保留。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank"></a> 

   > [!NOTE]
   > In-Place保留已停用，并且您无法再创建In-Place保留或将其应用于邮箱。 但是，In-Place保留可能仍应用于您组织的邮箱，这就是本文包含它们的原因。 有关详细信息，请参阅 [停用旧版电子数据展示工具](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center)。

- **[Microsoft 365保留](retention.md)** 策略：可以配置为保留 (或保留) 内容，然后删除 Exchange Online 中用户邮箱中的) 内容，以及 Microsoft 365 组和 Microsoft Teams 的相应邮箱中的内容。 您还可以创建保留策略，以保留Skype for Business用户邮箱中存储的对话。

  有两种类型的Microsoft 365可分配给邮箱的保留策略。

    - **特定位置保留策略：** 这些是分配给特定用户的内容位置的策略。 使用 PowerShell **中的 Get-Mailbox** cmdlet Exchange Online获取有关分配给特定邮箱的保留策略的信息。 有关此类型的保留策略详细信息，请参阅保留策略文档中具有特定包含 [或排除项](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions) 的策略一节。

    - **组织范围的保留策略：** 这些是分配给组织中所有内容位置的策略。 在 PowerShell **中使用 Get-OrganizationConfig** cmdlet Exchange Online获取有关组织范围的保留策略的信息。 有关此类型的保留策略详细信息，请参阅保留策略文档中适用于整个 [位置的策略](retention-settings.md#a-policy-that-applies-to-entire-locations) 一节。

- **[Microsoft 365保留标签：](retention.md)** 如果用户应用 Microsoft 365 保留标签 (该标签配置为保留内容或保留内容，然后将内容) 删除到其邮箱中的任意文件夹或项目，则邮箱将置于保留状态，就像邮箱被置于诉讼保留或分配给 Microsoft 365 保留策略一样。 有关详细信息，请参阅本文中的标识保留邮箱，因为保留标签已应用于文件夹 [或](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) 项目部分。

若要管理处于保留状态邮箱，可能需要确定邮箱上所放置的保留类型，以便执行以下任务：更改保留期、临时或永久删除保留，或者从 Microsoft 365 保留策略中排除邮箱。 在这些情况下，第一步是标识置于邮箱上的保留类型。 由于多个保留 (和不同类型的) 可以置于单个邮箱上，因此如果要删除或更改保留，必须标识邮箱上设置的所有保留。

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>步骤 1：获取邮箱上保留的 GUID

可以在 PowerShell 中运行Exchange Online cmdlet，获取邮箱上保留项的 GUID。 获取 GUID 后，可以使用它标识步骤 2 中的特定保留。 诉讼保留不是由 GUID 标识的。 为邮箱启用或禁用诉讼保留。

- **Get-Mailbox：** 使用此 cmdlet 可确定是否为邮箱启用诉讼保留，并获取专门分配给邮箱的电子数据展示保留、In-Place 保留和 Microsoft 365 保留策略的 GUID。 此 cmdlet 的输出还将指示邮箱是否已被明确从组织范围的保留策略中排除。

- **Get-OrganizationConfig：** 使用此 cmdlet 可获取组织范围内的保留策略的 GUID。

若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

### <a name="get-mailbox"></a>Get-Mailbox

运行以下命令，获取有关应用于邮箱的保留Microsoft 365保留策略的信息。

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中的值太多，并且并非所有值都显示出来，可以运行命令以在单独的行上显示每个 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` GUID。

下表介绍了在运行 **Get-Mailbox** cmdlet 时，如何根据 *InPlaceHolds* 属性的值标识不同类型的保留。

| 保留类型                                                          | 示例值                                                                                  | 如何识别保留                                                                                                                                                                                                                                                                                                                     |
| ------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 诉讼保留                                                    | `True`                                                                                         | *LitigationHoldEnabled* 属性设置为 时，为邮箱启用诉讼保留 `True` 。                                                                                                                                                                                                                                         |
| 电子数据展示保留                                                    | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`                                                     | *InPlaceHolds 属性* 包含与安全与合规中心中的电子数据展示案例关联的任何保留的 GUID。 您可以判断这是电子数据展示保留，因为 GUID 以前缀 (表示统一保留 `UniH`) 。                                                                                   |
| 就地保留                                                      | `c0ba3ce811b6432a8751430937152491` <br/> 或 <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`        | *InPlaceHolds* 属性包含邮箱上In-Place保留的 GUID。 你可以判断这是一个In-Place保留，因为 GUID 不是以前缀开头，就是以前缀 `cld` 开头。                                                                                                               |
| Microsoft 365专门应用于邮箱的保留策略 | `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> 或 <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3` | InPlaceHolds 属性包含应用于邮箱的任一特定位置保留策略的 GUID。 您可以标识保留策略，因为 GUID 以 `mbx` 或 `skp` 前缀开头。 前缀 `skp` 指示保留策略应用于Skype for Business邮箱中的会话。 |
| 从组织范围内的保留策略Microsoft 365排除  | `-mbxe9b52bf7ab3b46a286308ecb29624696`                                                         | 如果从组织范围的 Microsoft 365 保留策略中排除邮箱，则从中排除邮箱的保留策略的 GUID 将显示在 InPlaceHolds 属性中，并且由前缀标识。 `-mbx`                                                                                                     |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
如果运行 **Get-Mailbox** cmdlet 时 *InPlaceHolds* 属性为空，则可能仍有一个或多个组织范围内的保留策略Microsoft 365应用于邮箱。 在 PowerShell Exchange Online运行以下命令，获取组织范围内保留策略的 GUID Microsoft 365列表。

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中的值太多，并且并非所有值都显示出来，可以运行命令以在单独的行上显示每个 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` GUID。

下表介绍了不同类型的组织范围内的保留项，以及如何在运行 **Get-OrganizationConfig** cmdlet 时根据 *InPlaceHolds* 属性中包含的 GUID 标识每种类型。

| 保留类型                                                                                                | 示例值                           | 说明                                                                                                                                                                                                                                                            |
| -------------------------------------------------------------------------------------------------------- | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Microsoft 365邮箱、Exchange公用文件夹Exchange聊天应用的保留Teams策略 | `mbx7cfb30345d454ac0a989ab3041051209:2` | Microsoft Teams 中应用于 Exchange 邮箱、Exchange 公用文件夹和 1xN 聊天的组织范围的保留策略由以前缀开头的 GUID `mbx` 标识。 注意 1xN 聊天存储在单个聊天参与者的邮箱中。  |
| Microsoft 365组和频道消息Microsoft 365保留Teams策略                | `grp1a0a132ee8944501a4bb6a452ec31171:3` | 应用于组织中组和频道消息Microsoft 365组织范围的保留策略Microsoft Teams以前缀开头的 GUID `grp` 进行标识。 注意 频道消息存储在与 Microsoft 团队关联的组邮箱中。 |

有关应用于保留策略Microsoft Teams，请参阅了解适用于 Microsoft Teams 的[保留Microsoft Teams。](retention-policies-teams.md)

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>了解保留策略的 InPlaceHolds 值的格式

除了将 InPlaceHolds 属性中的项目标识为 Microsoft 365 保留策略的前缀 (mbx、skp 或 grp) 之外，值还包含一个后缀，用于标识为策略配置的保留操作类型。 例如，在下面的示例中，操作后缀以粗体突出显示：

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

下表定义了三种可能的保留操作：

| 值 | 说明                                                                                                                          |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **1** | 指示保留策略配置为删除项目。 策略不保留项目。                                  |
| **2** | 指示保留策略配置为保留项目。 保留期到期后，策略不会删除项目。 |
| **3** | 指示保留策略配置为保留项目，然后在保留期到期后删除这些项目。             |

有关保留操作详细信息，请参阅保留特定时间段 [的内容部分](retention-settings.md#retaining-content-for-a-specific-period-of-time) 。
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>步骤 2：使用 GUID 标识保留

获取应用于邮箱的保留的 GUID 后，下一步是使用该 GUID 标识该保留。 以下各节显示如何使用保留 GUID 标识 (和其他) 信息的名称。

### <a name="ediscovery-holds"></a>电子数据展示保留

在安全与合规& PowerShell 中运行以下命令，以标识应用于邮箱的电子数据展示保留。 使用 GUID (步骤 1 中) 标识的电子数据展示保留的 UniH 前缀值。 

若要连接到安全&中心 PowerShell，请参阅连接安全&[中心 PowerShell。](/powershell/exchange/connect-to-scc-powershell)

第一个命令创建一个包含有关保留信息的变量。 此变量用于其他命令。 第二个命令显示与保留关联的电子数据展示案例的名称。 第三个命令显示保留的名称以及应用保留的邮箱列表。

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

### <a name="in-place-holds"></a>就地保留

在 PowerShell Exchange Online以下命令，In-Place应用于邮箱的保留。 使用在步骤 1 In-Place标识的保留的 GUID。 该命令显示保留的名称和应用于保留的邮箱列表。

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

如果保留的 GUID In-Place前缀开头，请确保在运行上一个命令时包含 `cld` 前缀。

> [!IMPORTANT]
> 由于我们将继续以不同方式投资来保留邮箱内容，我们宣布停用 Exchange 管理中心中的 In-Place 保留 (EAC) 。 从 2020 年 7 月 1 日开始，将无法在 Exchange Online 中创建新的 In-Place 保留。 但你仍然可以在 EAC 中In-Place或通过使用 PowerShell 中的 **Set-MailboxSearch** cmdlet 管理Exchange Online保留。 但是，从 2020 年 10 月 1 日起，你将无法管理In-Place保留。 您将仅在 EAC 中或通过使用 **Remove-MailboxSearch** cmdlet 删除它们。 有关停用保留In-Place，请参阅 [停用旧版电子数据展示工具](legacy-ediscovery-retirement.md)。

### <a name="microsoft-365-retention-policies"></a>Microsoft 365保留策略

在安全与合规& PowerShell 中运行以下命令，以标识Microsoft 365邮箱 (组织范围或) 位置的保留策略。 使用 GUID (不包含在步骤 1 中标识的 mbx、skp 或 grp 前缀) 操作后缀。

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>标识保留邮箱，因为保留标签已应用于文件夹或项目

每当用户应用配置为保留内容或保留内容，然后删除其邮箱中任何文件夹或项目的保留标签时 *，ComplianceTagHoldApplied* 邮箱属性都设置为 **True**。 发生这种情况时，邮箱被视为处于保留状态，就像将其置于诉讼保留或分配给保留Microsoft 365一样。 当 *ComplianceTagHoldApplied* 属性设置为 **True** 时，可能会发生以下情况：

- 如果邮箱或用户的用户帐户被删除，则邮箱将成为非 [活动邮箱](inactive-mailboxes-in-office-365.md)。
- 如果已启用主邮箱或存档 (，将无法禁用邮箱) 。
- 邮箱中的项目保留时间可能会超过预期。 这是因为邮箱已置于保留状态，因此不会在清除邮件 (永久) 。

若要查看 *ComplianceTagHoldApplied* 属性的值，在 PowerShell 中运行Exchange Online命令：

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

有关保留标签详细信息，请参阅保留 [标签](retention.md#retention-labels)。

## <a name="managing-mailboxes-on-delay-hold"></a>管理延迟保留的邮箱

从邮箱中删除任何类型的保留后，将 *应用延迟* 保留。 这意味着保留的实际删除延迟 30 天，以防止数据在从邮箱中 () 永久删除。 这使管理员有机会搜索或恢复将在删除保留后清除的邮箱项目。 托管文件夹助理下次处理邮箱并检测到已删除保留时，邮箱将设置延迟保留。 具体来说，当托管文件夹助理将下列邮箱属性之一设置为 True 时，将延迟保留应用于 **邮箱**：

- **DelayHoldApplied：** 此属性适用于用户邮箱 (邮箱Outlook Outlook 网页版) 用户邮箱中生成的电子邮件相关内容。

- **DelayReleaseHoldApplied：** 此属性 (适用于非 Outlook 应用（如 Microsoft Teams、Microsoft Forms 和 Microsoft Yammer) ）生成的基于云的内容Yammer) 存储在用户邮箱中。 Microsoft 应用生成的云数据通常存储在用户邮箱的隐藏文件夹中。

当对邮箱设置延迟保留 (当之前的属性中的任一属性设置为 **True**) 时，该邮箱仍被视为处于无限期保留状态，就像邮箱处于诉讼保留一样。 30 天后，延迟保留过期，Microsoft 365 将自动尝试删除延迟保留 (，将 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **False**) 以便删除该保留。 在将其中任一属性设置为 **False** 后，将在托管文件夹助理下次处理邮箱时清除标记为删除的相应项目。

若要查看邮箱的 DelayHoldApplied 和 DelayReleaseHoldApplied 属性的值，请运行 PowerShell 中的以下Exchange Online命令。

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

若要在延迟保留过期之前删除延迟保留，可以在 (PowerShell 中运行) 或同时运行以下Exchange Online，具体取决于要更改的属性：

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

或

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

您必须获得法定保留角色Exchange Online *RemoveDelayHoldApplied* 或 *RemoveDelayReleaseHoldApplied* 参数。 

若要删除非活动邮箱的延迟保留，请运行 PowerShell 中的以下Exchange Online之一：

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

或

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> 在上一个命令中指定非活动邮箱的最佳方法就是使用其可分辨名称或Exchange GUID 值。 使用下列值之一有助于避免意外指定错误的邮箱。 

有关使用这些参数管理延迟保留状态的信息，请参阅 [Set-Mailbox](/powershell/module/exchange/set-mailbox)。

在管理延迟保留邮箱时，请记住以下事项：

- 如果 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **True，** 并删除邮箱 (或相应的用户帐户) ，则邮箱将成为非活动邮箱。 这是因为如果任一属性设置为 **True，** 则认为邮箱处于保留状态，删除处于保留状态的邮箱会导致邮箱处于非活动状态。 若要删除邮箱，使其不变为非活动邮箱，您必须将两个属性都设置为 **False**。

- 如前文所说明，如果 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 True ，则认为邮箱将置于无限期保留 **状态**。 但是，这并不意味着保留 *邮箱* 中所有内容。 它取决于设置为每个属性的值。 例如，假设这两个属性都设置为 **True，** 因为保留将从邮箱中删除。 然后，使用 *RemoveDelayReleaseHoldApplied* 参数删除仅应用于Outlook云 (应用的延迟保留) 。 下次托管文件夹助理处理邮箱时，将清除Outlook删除的非邮箱项目。 任何Outlook标记为删除的项目将不会清除，因为 DelayHoldApplied 属性仍设置为 **True**。 相反，同样为 true：如果 DelayHoldApplied 设置为False，DelayReleaseHoldApplied 设置为 **True，** 则Outlook删除的项将被清除。

## <a name="how-to-confirm-that-an-organization-wide-retention-policy-is-applied-to-a-mailbox"></a>如何确认组织范围的保留策略已应用于邮箱

将组织范围的保留策略应用于或删除邮箱时，导出邮箱诊断日志可以帮助您确定 Exchange Online已实际将保留策略应用或删除到邮箱。 若要查看此信息，首先需要使用 Powershell 验证Exchange Online[一些内容](/powershell/exchange/connect-to-exchange-online-powershell)。

### <a name="obtain-the-guids-for-any-retention-policies-explicitly-applied-to-a-mailbox"></a>获取显式应用于邮箱的任何保留策略的 GUID

```powershell
Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds
```

### <a name="obtain-the-guids-for-any-organization-wide-retention-policies-appled-to-mailboxes"></a>获取所有组织范围内的保留策略的 GUID（小程序到邮箱）

```powershell
Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds
```

### <a name="get-the-mailbox-diagnostics-for-holdtracking"></a>获取 HoldTracking 的邮箱诊断

保留跟踪邮箱诊断日志维护应用于用户邮箱的保留的历史记录。

```powershell
$ht = Export-MailboxDiagnosticLogs <username> -ComponentName HoldTracking
$ht.MailboxLog | Convertfrom-Json
```

### <a name="review-the-results-of-the-mailbox-diagnostics-logs"></a>查看邮箱诊断日志的结果

如果从上一步收集数据，则生成的数据可能如下所示：

> **ed** `  : 0001-01-01T00:00:00.0000000` 
>  ` : mbx7cfb30345d454ac0a989ab3041051209:1` hid 
> **ht** `  : 4` 
> **lsd** ` : 2020-03-23T18:24:37.1884606Z` 
> **osd**` : 2020-03-23T18:24:37.1884606Z`

使用下表可帮助您了解诊断日志中列出的每个以前的值。

| 值   | 说明 |
|:------- |:----------- |
| **ed**  | 指示"结束日期"，即禁用保留策略的日期。 MinValue 表示策略仍分配给邮箱。 |
| **hid** | 指示保留策略的 GUID。 此值与为分配给邮箱的显式保留策略或组织范围内的保留策略收集的 GUID 相关。|
| **lsd** | 指示"上次开始日期"，即将保留策略分配给邮箱的日期。|
| **osd** | 指示原始开始日期，即首次Exchange保留策略信息的日期。 |
|||

当保留策略不再应用于邮箱时，我们将临时延迟保留用户，以防止清除内容。 可以通过运行命令禁用延迟 `Set-Mailbox -RemoveDelayHoldApplied` 保留。

## <a name="next-steps"></a>后续步骤

确定应用于邮箱的保留后，可以执行任务，例如更改保留期、临时或永久删除保留，或者从 Microsoft 365 保留策略中排除非活动邮箱。 有关执行与保留项相关的任务的信息，请参阅下列主题之一：

- 在 &安全与合规中心 PowerShell 中运行[Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationException \<user mailbox> ](/powershell/module/exchange/set-retentioncompliancepolicy)命令，从组织范围内的邮箱保留策略中Microsoft 365邮箱。 此命令只能用于 *ExchangeLocation* 属性的值等于 的保留策略 `All` 。

- [更改非活动邮箱的保留期](change-the-hold-duration-for-an-inactive-mailbox.md)

- [删除非活动邮箱](delete-an-inactive-mailbox.md)

- [删除保留状态云邮箱的“可恢复的项目”文件夹中的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
