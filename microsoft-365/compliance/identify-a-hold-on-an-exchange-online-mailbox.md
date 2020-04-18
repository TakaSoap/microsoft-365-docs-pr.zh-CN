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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: 了解如何识别可在 Office 365 邮箱中放置的不同类型的保留。 这些保留类型包括诉讼保留、电子数据展示保留和 Office 365 保留策略。 您还可以确定是否已从组织范围的保留策略中排除了用户
ms.openlocfilehash: 4063128e368b19b156fbf42173fb2d4725c3e7ab
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551133"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>如何识别为 Exchange Online 邮箱设置的保留类型

本文介绍如何确定在 Office 365 的 Exchange Online 邮箱中放置的保留。

Office 365 提供了多种方法，使您的组织可以阻止邮箱内容被永久删除。 这使您的组织可以保留内容以满足合规性管理法规或在法律和其他类型的调查过程中。 下面列出了 Office 365 中的保留功能（也称为 "*保留*"）：

- **[诉讼保留](create-a-litigation-hold.md)：** 应用于 Exchange Online 中的用户邮箱的保留。

- **[电子数据展示保留](create-ediscovery-holds.md)：** 与安全与合规中心中的电子数据展示事例相关联的保留项。 电子数据展示保留可应用于用户邮箱以及 Office 365 组和 Microsoft 团队对应的邮箱。

- **[就地保留](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds)：** 使用 exchange Online 中 Exchange 管理中心的就地电子数据展示 & 保留工具对用户邮箱应用的保留。

- ** [Office 365 保留策略](retention-policies.md)：** 可以配置为保留（或保留并删除） Exchange Online 中的用户邮箱中的内容，以及 Office 365 组和 Microsoft 团队对应的邮箱中的内容。 您还可以创建保留策略以保留 Skype for Business 对话，这些会话存储在用户邮箱中。

  有两种类型的 Office 365 保留策略可分配给邮箱。

    - **特定位置保留策略：** 这些是分配给特定用户的内容位置的策略。 您可以使用 Exchange Online PowerShell 中的**邮箱获取**cmdlet 获取有关分配给特定邮箱的保留策略的信息。

    - **组织范围内的保留策略：** 这些是分配给组织中的所有内容位置的策略。 您可以使用 Exchange Online PowerShell 中的**set-organizationconfig** cmdlet 来获取有关组织范围的保留策略的信息。
  有关详细信息，请参阅[Office 365 保留策略概述](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)中的 "将保留策略应用于整个组织或特定位置" 部分。

- **[Office 365 保留标签](labels.md)：** 如果用户将 office 365 保留标签（配置为保留内容或保留，然后删除内容）应用到其邮箱中的*任何*文件夹或项目中，则会在邮箱上放置保留，就像邮箱被置于诉讼保留或分配到 Office 365 保留策略。 有关详细信息，请参阅[保留邮箱处于保留状态，因为已将保留标签应用于本文中的文件夹或项目](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)部分。

若要管理处于保留状态的邮箱，您可能需要确定邮箱中放置的保留类型，以便可以执行诸如更改保留持续时间、临时或永久删除保留或从 Office 365 保留策略中排除邮箱等任务。 在这些情况下，第一步是确定邮箱上放置的保留类型。 由于多个保留（和不同类型的保留）可以放置在单个邮箱上，因此，如果您想要删除或更改保留，则必须标识邮箱中的所有保留项。

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>步骤1：获取邮箱上放置的保留的 GUID

您可以在 Exchange Online PowerShell 中运行以下两个 cmdlet，以获取邮箱中放置的保留的 GUID。 获取 GUID 后，可以使用它来标识步骤2中的特定保留。 GUID 未标识诉讼保留。 为邮箱启用或禁用诉讼保留。

- **获取邮箱：** 此 cmdlet 可用于确定是否对邮箱启用了诉讼保留，并获取专门分配给邮箱的电子数据展示保留、就地保留和 Office 365 保留策略的 Guid。 此 cmdlet 的输出还将指示是否已从组织范围的保留策略中显式排除了邮箱。

- **Set-organizationconfig：** 此 cmdlet 可用于获取组织范围的保留策略的 Guid。

若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

### <a name="get-mailbox"></a>Get-Mailbox

运行以下命令以获取有关保留和 Office 365 保留策略应用于邮箱的信息。

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中的值过多，并且不是全部显示，则可以运行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令将每个 GUID 显示在单独的行上。

下表介绍在运行 InPlaceHolds **cmdlet 时**，如何根据*InPlaceHolds*属性中的值标识不同类型的保留。


|保留类型  |示例值  |如何识别保留  |
|---------|---------|---------|
|诉讼保留     |    `True`     |     当*LitigationHoldEnabled*属性设置为`True`时，将对邮箱启用诉讼保留。    |
|电子数据展示保留     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds 属性*包含与安全与合规中心中的电子数据展示事例关联的任何保留的 GUID。 你可以告诉这是电子数据展示保留，因为 GUID 以`UniH`前缀（表示统一保留）开头。      |
|就地保留     |     `c0ba3ce811b6432a8751430937152491` <br/> 或 <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds*属性包含邮箱中放置的就地保留的 GUID。 您可以指示这是就地保留，因为 GUID 既不以前缀开头，也不以`cld`前缀开头。     |
|专用于邮箱的 Office 365 保留策略     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> 或 <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds 属性包含应用于邮箱的任何特定位置保留策略的 Guid。 您可以确定保留策略，因为 GUID 以`mbx`或`skp`前缀开头。 `skp`前缀指示将保留策略应用于用户邮箱中的 Skype for business 会话。    |
|从组织范围的 Office 365 保留策略中排除     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     如果从组织范围的 Office 365 保留策略中排除了邮箱，则从 InPlaceHolds 属性中排除的保留策略的 GUID 将显示在 "" 属性中，并由`-mbx`前缀进行标识。    |

### <a name="get-organizationconfig"></a>Set-organizationconfig
如果运行**邮箱**cmdlet 时， *InPlaceHolds*属性为空，则仍可能会将一个或多个组织范围内的 Office 365 保留策略应用于邮箱。 在 Exchange Online PowerShell 中运行以下命令，获取组织范围内的 Office 365 保留策略的 Guid 列表。

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中的值过多，并且不是全部显示，则可以运行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令将每个 GUID 显示在单独的行上。

下表介绍了不同类型的组织范围的保留，以及在运行**set-organizationconfig** cmdlet 时如何根据*InPlaceHolds*属性中包含的 guid 标识每种类型。


|保留类型  |示例值  |说明  |
|---------|---------|---------|
|应用于 Exchange 邮箱、Exchange 公用文件夹和团队聊天的 Office 365 保留策略    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   在 Microsoft 团队中应用于 Exchange 邮箱、Exchange 公用文件夹和1xN 聊天的组织范围内的保留策略由以`mbx`前缀开头的 guid 进行标识。 注意1xN 聊天存储在各个聊天参与者的邮箱中。      |
|应用于 Office 365 组和团队频道消息的 office 365 保留策略     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    在 Microsoft 团队中应用于 Office 365 组和频道消息的组织范围内的保留策略由以`grp`前缀开头的 guid 标识。 注释通道邮件存储在与 Microsoft 团队相关联的组邮箱中。     |

有关应用于 Microsoft 团队的详细信息保留策略，请参阅[保留策略](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)的 "团队位置" 一节概述。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>了解保留策略的 InPlaceHolds 值的格式

除了将 InPlaceHolds 属性中的项目标识为 Office 365 保留策略的前缀（mbx、skp 或 grp）之外，此值还包含一个标识为策略配置的保留操作类型的后缀。 例如，在以下示例中，操作后缀以粗体突出显示：

   `skp127d7cf1076947929bf136b7a2a8c36f`**：1**

   `mbx7cfb30345d454ac0a989ab3041051209`**：2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**：3**

下表定义了三种可能的保留操作：

|值  |说明  |
|---------|---------|
|**1**     | 指示保留策略已配置为删除项目。 策略不会保留项目。        |
|**双面**    |    指示保留策略配置为保留项目。 在保留期过期后，策略不会删除项目。     |
|**第三章**     |   指示保留策略配置为保留项目，然后在保留期过期后将其删除。      |

有关保留操作的详细信息，请参阅[保留策略概述](retention-policies.md#retaining-content-for-a-specific-period-of-time)中的 "在特定时间段内保留内容" 部分。
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>步骤2：使用 GUID 标识保留

获取应用于邮箱的保留的 GUID 后，下一步是使用该 GUID 标识保留。 以下各节介绍如何使用保留 GUID 标识保留的名称（和其他信息）。

### <a name="ediscovery-holds"></a>电子数据展示保留

在 Security & 合规性中心 PowerShell 中运行以下命令，以确定应用于邮箱的电子数据展示保留。 使用您在步骤1中确定的电子数据展示保留的 GUID （不包括 UniH 前缀）。 第一个命令创建包含有关保留的信息的变量。 在其他命令中使用此变量。 第二个命令显示与保留相关联的电子数据展示事例的名称。 第三个命令显示保留的名称和应用保留的邮箱列表。

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

若要连接到安全 & 合规性中心 PowerShell，请参阅[connect To Security & 合规性中心 powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

### <a name="in-place-holds"></a>就地保留

在 Exchange Online PowerShell 中运行以下命令，以确定应用于邮箱的就地保留。 对您在步骤1中标识的就地保留使用 GUID。 该命令将显示保留的名称和应用保留的邮箱列表。

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

如果就地保留的 GUID 以`cld`前缀开头，请确保在运行前一个命令时包含前缀。

> [!IMPORTANT]
> 随着我们继续投资保留邮箱内容的不同方式，我们宣布在 Exchange 管理中心（EAC）中停用就地保留。 从2020年6月1日开始，你将无法在 Exchange Online 中创建新的就地保留。 但您仍可以在 EAC 中管理就地保留或通过在 Exchange Online PowerShell 中使用**new-mailboxsearch** cmdlet 来管理。 但是，从2020年10月1日开始，你将无法管理就地保留。 您只能将其从 EAC 中删除或使用**new-mailboxsearch** cmdlet。 有关停用就地保留的详细信息，请参阅[旧版电子数据展示工具的退休](legacy-ediscovery-retirement.md)。

### <a name="office-365-retention-policies"></a>Office 365 保留策略

在 Security & 合规中心 PowerShell 中运行以下命令，以标识应用于邮箱的 Office 365 保留策略（组织范围或特定位置）。 使用您在步骤1中标识的 GUID （不包括 mbx、skp 或 grp 前缀或操作后缀）。

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>由于已将保留标签应用于文件夹或项目，因此标识邮箱处于保留状态

只要用户应用配置为保留内容或保留内容的保留标签，然后将内容删除到其邮箱中的任何文件夹或项目， *ComplianceTagHoldApplied*邮箱属性将设置为**True**。 发生这种情况时，邮箱被视为处于保留状态，就像将其置于诉讼保留状态或分配到 Office 365 保留策略一样。 当*ComplianceTagHoldApplied*属性设置为**True**时，可能会出现以下情况：

- 如果删除了邮箱或用户的 Office 365 用户帐户，则邮箱将成为[非活动邮箱](inactive-mailboxes-in-office-365.md)。
- 您无法禁用邮箱（主邮箱或存档邮箱（如果已启用）。
- 邮箱中的项目可能会超过预期的保留时间。 这是因为邮箱处于保留状态，因此没有永久删除（清除）的邮件。

若要查看*ComplianceTagHoldApplied*属性的值，请在 Exchange Online PowerShell 中运行以下命令：

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

有关保留标签的详细信息，请参阅[Office 365 的概述保留标签](labels.md)。

## <a name="managing-mailboxes-on-delay-hold"></a>在延迟保留时管理邮箱

从邮箱中删除了任何类型的保留后，将应用*延迟保留*。 这意味着保留的实际删除延迟30天，以防止永久删除（清除）邮箱中的数据。 这使管理员有机会搜索或恢复在删除保留后将清除的邮箱项目。 在下一次托管文件夹助理处理邮箱并检测已删除保留时，会在邮箱上放置延迟保留。 具体来说，当托管文件夹助理将下列邮箱属性之一设置为**True**时，将对邮箱应用延迟保留：

- **DelayHoldApplied：** 此属性适用于存储在用户邮箱中的与电子邮件相关的内容（由使用 Outlook 和 web 上的 Outlook 生成的用户生成）。

- **DelayReleaseHoldApplied：** 此属性适用于存储在用户邮箱中的基于云的内容（由非 Outlook 应用程序（如 Microsoft 团队、Microsoft Forms 和 Microsoft Yammer）生成。 Microsoft 应用生成的云数据通常存储在用户邮箱的隐藏文件夹中。
 
 在邮箱上放置延迟保留（当上述任一属性设置为**True**）时，邮箱仍被视为无限制保留持续时间处于保留状态，就像邮箱处于诉讼保留状态一样。 30天后，延迟保留过期，Office 365 将自动尝试删除延迟保留（通过将 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为**False**），以便删除保留。 在这两个属性都设置为**False**后，在下一次由托管文件夹助理处理邮箱时，将清除标记为要删除的相应项。

若要查看邮箱的 DelayHoldApplied 和 DelayReleaseHoldApplied 属性的值，请在 Exchange Online PowerShell 中运行以下命令。

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

若要在过期之前删除延迟保留，可以在 Exchange Online PowerShell 中运行以下命令（或同时运行这两项），具体取决于要更改的属性： 
 
```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

或
 
```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

您必须在 Exchange Online 中向您分配 "合法保留" 角色，才能使用*RemoveDelayHoldApplied*或*RemoveDelayReleaseHoldApplied*参数。 

若要删除非活动邮箱的延迟保留，请在 Exchange Online PowerShell 中运行以下命令之一：

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

或

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> 在上一命令中指定非活动邮箱的最佳方法是使用其可分辨名称或 Exchange GUID 值。 使用下列值之一有助于避免意外指定错误的邮箱。 

有关使用这些参数管理延迟保留的详细信息，请参阅[设置邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。

在延迟保留时管理邮箱时，请记住以下事项：

- 如果将 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为**True** ，并且删除了一个邮箱（或对应的 Office 365 用户帐户），则该邮箱将成为非活动邮箱。 这是因为，如果将某个属性设置为**True**，并在保留时删除邮箱导致非活动邮箱中的邮箱，则认为邮箱处于保留状态。 若要删除邮箱而不使其成为非活动邮箱，必须将这两个属性都设置为**False**。

- 如前所述，如果 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为**True**，则会将邮箱视为无限制保留持续时间的保留。 但是，这并不意味着保留邮箱中的*所有*内容。 这取决于设置为每个属性的值。 例如，假设这两个属性都设置为**True** ，因为从邮箱中删除了保留。 然后，仅删除应用于非 Outlook 云数据的延迟保留（通过使用*RemoveDelayReleaseHoldApplied*参数）。 托管文件夹助理下次处理邮箱时，将清除标记为要删除的非 Outlook 项目。 由于 DelayHoldApplied 属性仍设置为**True**，因此不会清除任何标记为要删除的 Outlook 项目。 反之也是如此：如果将 DelayHoldApplied 设置为**False** ，DelayReleaseHoldApplied 设置为**true**，则仅清除标记为删除的 Outlook 项目。

## <a name="next-steps"></a>后续步骤

在确定了应用于邮箱的保留后，可以执行一些任务，如更改保留的持续时间、临时或永久删除保留或从 Office 365 保留策略中排除非活动邮箱。 有关执行与保留相关的任务的详细信息，请参阅下列主题之一：

- 在 Security & 合规中心 PowerShell 中运行[new-retentioncompliancepolicy-AddExchangeLocationException \<user 邮箱>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)命令，以从组织范围内的 Office 365 保留策略中排除邮箱。 此命令仅可用于*ExchangeLocation*属性值等于`All`的保留策略。

- 在 Exchange Online PowerShell 中运行[ExcludeFromOrgHolds \<不带前缀或后缀>命令中的设置邮箱-保留 GUID](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) ，以从组织范围内的 Office 365 保留策略中排除非活动邮箱。

- [在 Office 365 中更改非活动邮箱的保留期](change-the-hold-duration-for-an-inactive-mailbox.md)

- [删除 Office 365 中的非活动邮箱](delete-an-inactive-mailbox.md)

- [删除保留状态云邮箱的“可恢复的项目”文件夹中的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
