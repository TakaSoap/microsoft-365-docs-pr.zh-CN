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
ms.custom:
- seo-marvel-apr2020
description: 了解如何标识可在 Microsoft 365 中的 Exchange Online 邮箱上放置的不同类型的保留。
ms.openlocfilehash: a5bea8cd279bb980ba2f8a57950c8a66857ba502
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423623"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>如何识别为 Exchange Online 邮箱设置的保留类型

本文介绍如何标识在 Microsoft 365 中对 Exchange Online 邮箱的保留。

Microsoft 365 提供了组织可以阻止邮箱内容被永久删除的几种方法。 这样，组织可以保留内容以满足合规性法规，或在法律和其他类型的调查期间保留内容。 下面列出了 Office 365 中 (*保留*) 保留功能：

- **[诉讼保留](create-a-litigation-hold.md)：** 应用于 Exchange Online 中的用户邮箱的保留。

- **[电子数据展示保留](create-ediscovery-holds.md)：** 与安全与合规中心的核心电子数据展示案例相关联的保留。 电子数据展示保留可应用于用户邮箱和 Microsoft 365 组和 Microsoft Teams 的相应邮箱。

- **[就地保留](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds)：** 通过使用 Exchange Online Exchange 管理中心中的In-Place电子数据展示&保留工具应用于用户邮箱的保留。 

   > [!NOTE]
   > In-Place保留已停用，并且你无法再创建In-Place保留或将其应用于邮箱。 但是，In-Place保留可能仍应用于您组织的邮箱，这就是为什么它们包含在本文中的原因。 有关详细信息，请参阅停用 [旧版电子数据展示工具](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center)。

- **[Microsoft 365 保留策略](retention.md)：** 可以配置为保留或 (，然后删除 Exchange Online 用户邮箱和 Microsoft 365 组和 Microsoft Teams 的相应邮箱中的) 内容。 还可以创建保留策略来保留存储在用户邮箱中的 Skype for Business 对话。

  有两种类型的 Microsoft 365 保留策略可以分配给邮箱。

    - **特定位置保留策略：** 这些是分配给特定用户的内容位置的策略。 您可以使用 Exchange Online PowerShell 中的 **Get-Mailbox** cmdlet 获取有关分配给特定邮箱的保留策略的信息。 有关此类型的保留策略详细信息，请参阅包含保留策略文档中特定 [包含或](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) 排除项的策略一节。

    - **组织范围的保留策略：** 这些是分配给组织中所有内容位置的策略。 您可以使用 Exchange Online PowerShell **中的 Get-OrganizationConfig** cmdlet 获取有关组织范围的保留策略的信息。 有关此类型的保留策略详细信息，请参阅适用于保留策略文档中的整个[](create-retention-policies.md#a-policy-that-applies-to-entire-locations)位置的策略一节。

- **[Microsoft 365](retention.md)** 保留标签：如果用户应用 Microsoft 365 保留标签 (其中一个配置为保留内容或保留内容，然后将内容) 删除到其邮箱中任何文件夹或项目，则邮箱将置于保留状态，就像将邮箱置于诉讼保留或分配给 Microsoft 365 保留策略一样。 有关详细信息，请参阅本文中的"标识保留 [邮箱](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) "部分，因为保留标签已应用于文件夹或项目部分。

若要管理处于保留状态中的邮箱，可能需要确定邮箱上放置的保留类型，以便执行诸如更改保留期、临时或永久删除保留或者从 Microsoft 365 保留策略中排除邮箱等任务。 在这些情况下，第一步是标识邮箱上的保留类型。 由于多个保留 (，并且可以将不同类型的保留) 一个邮箱上，因此如果要删除或更改保留，必须标识邮箱上的所有保留。

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>步骤 1：获取置于邮箱上的保留项的 GUID

您可以在 Exchange Online PowerShell 中运行以下两个 cmdlet，获取邮箱上保留项的 GUID。 获取 GUID 后，可以使用它标识步骤 2 中的特定保留。 诉讼保留不是由 GUID 标识的。 为邮箱启用或禁用诉讼保留。

- **Get-Mailbox：** 使用此 cmdlet 可确定是否为邮箱启用诉讼保留，并获取专门分配给邮箱的电子数据展示保留、In-Place 保留和 Microsoft 365 保留策略的 GUID。 此 cmdlet 的输出还将指示邮箱是否已被明确从组织范围的保留策略中排除。

- **Get-OrganizationConfig：** 使用此 cmdlet 可获取组织范围的保留策略的 GUID。

若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

### <a name="get-mailbox"></a>Get-Mailbox

运行以下命令，获取有关应用于邮箱的保留和 Microsoft 365 保留策略的信息。

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中的值太多，但并非所有值都显示，您可以运行命令以在单独的行上显示每个 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` GUID。

下表介绍了在运行 **Get-Mailbox** cmdlet 时，如何根据 *InPlaceHolds* 属性的值标识不同类型的保留。

|保留类型  |示例值  |如何识别保留  |
|---------|---------|---------|
|诉讼保留     |    `True`     |     当 *LitigationHoldEnabled* 属性设置为时，会为邮箱启用诉讼保留 `True` 。    |
|电子数据展示保留     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds 属性* 包含在安全与合规中心内与电子数据展示案例关联的任何保留的 GUID。 你可以判断这是电子数据展示保留，因为 GUID 以前缀 (表示统一保留 `UniH`) 。      |
|就地保留     |     `c0ba3ce811b6432a8751430937152491` <br/> 或 <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds* 属性包含In-Place保留的 GUID。 你可以判断这是一个In-Place保留，因为 GUID 不是以前缀开头，就是以前缀 `cld` 开头。     |
|专门应用于邮箱的 Microsoft 365 保留策略     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> 或 <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds 属性包含应用于邮箱的任何特定位置保留策略的 GUID。 您可以标识保留策略，因为 GUID 以前缀 `mbx` 或前缀 `skp` 开头。 前缀 `skp` 指示保留策略应用于用户邮箱中的 Skype for Business 对话。    |
|从组织范围内的 Microsoft 365 保留策略中排除     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     如果邮箱从组织范围的 Microsoft 365 保留策略中排除，则从中排除邮箱的保留策略的 GUID 将显示在 InPlaceHolds 属性中，并且由前缀标识。 `-mbx`    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
如果在运行 **Get-Mailbox** cmdlet 时 *InPlaceHolds* 属性为空，则仍可能有一个或多个应用于邮箱的组织范围的 Microsoft 365 保留策略。 在 Exchange Online PowerShell 中运行以下命令，获取组织范围内的 Microsoft 365 保留策略的 GUID 列表。

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中的值太多，但并非所有值都显示，您可以运行命令以在单独的行上显示每个 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` GUID。

下表介绍了不同类型的组织范围内的保留，以及如何在运行 **Get-OrganizationConfig** cmdlet 时根据 *InPlaceHolds* 属性中包含的 GUID 标识每种类型。

|保留类型  |示例值  |说明  |
|---------|---------|---------|
|应用于 Exchange 邮箱、Exchange 公用文件夹和 Teams 聊天的 Microsoft 365 保留策略    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   应用于 Exchange 邮箱、Exchange 公用文件夹和 Microsoft Teams 中的 1xN 聊天的组织范围的保留策略由以前缀开头的 GUID `mbx` 标识。 注意 1xN 聊天存储在单个聊天参与者的邮箱中。      |
|应用于 Microsoft 365 组和 Teams 频道消息的 Microsoft 365 保留策略     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    适用于 Microsoft 365 组和 Microsoft Teams 中的频道消息的组织范围的保留策略由以前缀开头的 GUID `grp` 标识。 请注意，频道邮件存储在与 Microsoft 团队关联的组邮箱中。     |

有关应用于 Microsoft Teams 的保留策略详细信息，请参阅了解 [Microsoft Teams 的保留策略](retention-policies-teams.md)。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>了解保留策略的 InPlaceHolds 值的格式

除了将 InPlaceHolds 属性中的项目标识为 Microsoft 365 保留策略的前缀 (mbx、skp 或 grp) 之外，值还包含一个后缀，用于标识为策略配置的保留操作的类型。 例如，在下面的示例中，操作后缀以粗体突出显示：

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

下表定义了三种可能的保留操作：

|值  |说明  |
|---------|---------|
|**1**     | 指示保留策略配置为删除项目。 该策略不保留项目。        |
|**2**    |    指示保留策略配置为保留项目。 策略不会在保留期到期后删除项目。     |
|**3**     |   指示保留策略配置为保留项目，然后在保留期到期后将其删除。      |

有关保留操作详细信息，请参阅"保留特定时间段 [的内容"部分](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) 。
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>步骤 2：使用 GUID 标识保留

获取应用于邮箱的保留的 GUID 后，下一步是使用该 GUID 标识保留。 以下各节显示如何使用保留 GUID 标识保留 (和其他) 名称。

### <a name="ediscovery-holds"></a>电子数据展示保留

在安全与合规& PowerShell 中运行以下命令，以标识应用于邮箱的电子数据展示保留。 使用 GUID (不包括在步骤 1 中) 电子数据展示保留的 UniH 前缀值。 

若要连接到安全与&中心 PowerShell，请参阅"连接到安全与合规&[中心 PowerShell。](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

第一个命令创建一个包含有关保留信息的变量。 此变量用于其他命令。 第二个命令显示与保留相关联的电子数据展示案例的名称。 第三个命令显示保留的名称和应用于保留的邮箱列表。

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

在 Exchange Online PowerShell 中运行以下命令In-Place应用于邮箱的保留状态。 使用在步骤 1 In-Place标识的保留的 GUID。 该命令显示保留的名称和应用于保留的邮箱列表。

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

如果保留的 GUID In-Place前缀开始，请确保在运行上一个命令时包含 `cld` 前缀。

> [!IMPORTANT]
> 由于我们将继续以不同方式投资来保留邮箱内容，我们宣布在 Exchange 管理中心 (EAC) 中停用 In-Place 保留。 从 2020 年 7 月 1 日开始，你将无法在 Exchange Online In-Place保留。 但你仍然可以在 EAC 中In-Place Exchange Online PowerShell 中的 **Set-MailboxSearch** cmdlet 管理保留。 但是，从 2020 年 10 月 1 日起，你将无法管理In-Place保留。 你将仅在 EAC 中或通过使用 **Remove-MailboxSearch** cmdlet 删除它们。 有关停用保留In-Place，请参阅停用 [旧版电子数据展示工具](legacy-ediscovery-retirement.md)。

### <a name="microsoft-365-retention-policies"></a>Microsoft 365 保留策略

在安全与合规& PowerShell 中运行以下命令，以标识应用于邮箱的 Microsoft 365 (或) 位置策略。 使用 GUID (不包括在步骤 1 中标识的 mbx、skp 或 grp 前缀或) 后缀。

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>标识保留邮箱，因为保留标签已应用于文件夹或项目

每当用户应用配置为保留内容或保留内容，然后删除其邮箱中任何文件夹或项目的保留标签时 *，ComplianceTagHoldApplied* 邮箱属性设置为 **True**。 发生这种情况时，邮箱被视为处于保留状态，就像将其置于诉讼保留或分配给 Microsoft 365 保留策略一样。 当 *ComplianceTagHoldApplied* 属性设置为 **True** 时，可能会发生以下情况：

- 如果删除邮箱或用户的用户帐户，则邮箱将成为非 [活动邮箱](inactive-mailboxes-in-office-365.md)。
- 如果主邮箱或存档 (邮箱已启用，则不能禁用) 。
- 邮箱中的项目保留时间可能会超过预期。 这是因为邮箱已置于保留状态，因此在邮件被清除后 (永久) 。

若要查看 *ComplianceTagHoldApplied* 属性的值，请运行 Exchange Online PowerShell 中的以下命令：

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

有关保留标签详细信息，请参阅 [保留标签](retention.md#retention-labels)。

## <a name="managing-mailboxes-on-delay-hold"></a>管理延迟保留中的邮箱

从邮箱中删除任何类型的保留后，将 *应用延迟* 保留。 这意味着将保留的实际删除延迟 30 天，以防止从邮箱中 (数据) 删除。 这使管理员有机会搜索或恢复将在删除保留后清除的邮箱项目。 下次托管文件夹助理处理邮箱并检测到已删除保留时，邮箱上将设置延迟保留。 具体来说，当托管文件夹助理将下列邮箱属性之一设置为 True 时，会向邮箱应用延迟 **保留**：

- **DelayHoldApplied：** 此属性适用于用户 (Outlook 和 Outlook 网页) 用户邮箱中生成的电子邮件相关内容。

- **DelayReleaseHoldApplied：** 此属性适用于由非 Outlook (（如 Microsoft Teams、Microsoft Forms 和 Microsoft Yammer) ）生成的基于云的内容，这些内容存储在用户邮箱中。 由 Microsoft 应用生成的云数据通常存储在用户邮箱的隐藏文件夹中。

当将邮箱 (当之前任一属性设置为 **True**) 时，仍认为邮箱处于保留状态，保留期不受限制，就像邮箱处于诉讼保留状态一样。 30 天后，延迟保留过期，Microsoft 365 将自动尝试通过将 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **False**) 来删除延迟保留 (，以便删除该保留。 在将其中任一属性设置为 **False** 后，下一次托管文件夹助理处理邮箱时，将清除标记为删除的相应项目。

若要查看邮箱的 DelayHoldApplied 和 DelayReleaseHoldApplied 属性的值，请运行 Exchange Online PowerShell 中的以下命令。

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

若要在延迟保留过期之前删除延迟保留， (或同时运行) Exchange Online PowerShell 中的以下命令，具体取决于要更改的属性：

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

或

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

必须在 Exchange Online 中分配法定保留角色，以使用 *RemoveDelayHoldApplied* 或 *RemoveDelayReleaseHoldApplied* 参数。 

若要删除非活动邮箱的延迟保留，请运行 Exchange Online PowerShell 中的以下命令之一：

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

或

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> 在上一个命令中指定非活动邮箱的最佳方法就是使用其可分辨名称或 Exchange GUID 值。 使用下列值之一有助于避免意外指定错误的邮箱。 

有关使用这些参数管理延迟保留的信息，请参阅 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。

管理置于延迟保留状态邮箱时，请记住以下事项：

- 如果 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **True，** 并删除邮箱 (或相应的用户帐户) ，则邮箱将成为非活动邮箱。 这是因为如果任一属性设置为 **True，** 则认为邮箱处于保留状态，删除保留邮箱会导致邮箱处于非活动状态。 若要删除邮箱，而不要将其设置为非活动邮箱，您必须将两个属性都设置为 **False**。

- 如前文所指出，如果 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **True，** 则认为邮箱将保持无限期保留。 但是， *这并不意味着保留邮箱* 中所有内容。 它取决于设置为每个属性的值。 例如，假设这两个属性都设置为 **True，** 因为保留从邮箱中删除。 然后，使用 *RemoveDelayReleaseHoldApplied* 参数 (删除应用于非 Outlook 云数据应用的延迟) 。 下次托管文件夹助理处理邮箱时，将清除标记为删除的非 Outlook 项目。 任何标记为删除的 Outlook 项目将不会清除，因为 DelayHoldApplied 属性仍设置为 **True**。 另一方面也是如此：如果 DelayHoldApplied 设置为 False，DelayReleaseHoldApplied 设置为 **True，** 则只会清除标记为删除的 Outlook 项目。 

## <a name="next-steps"></a>后续步骤

确定应用于邮箱的保留后，可以执行以下任务：更改保留期、临时或永久删除保留，或者从 Microsoft 365 保留策略中排除非活动邮箱。 有关执行与保留项相关的任务详细信息，请参阅下列主题之一：

- 在安全与合规中心 PowerShell 中运行[Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationExcept & ion \<user mailbox> ](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)命令，从组织范围内的 Microsoft 365 保留策略中排除邮箱。 此命令只能用于 *ExchangeLocation* 属性的值等于的保留策略 `All` 。

- [更改非活动邮箱的保留期](change-the-hold-duration-for-an-inactive-mailbox.md)

- [删除非活动邮箱](delete-an-inactive-mailbox.md)

- [删除保留状态云邮箱的“可恢复的项目”文件夹中的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
