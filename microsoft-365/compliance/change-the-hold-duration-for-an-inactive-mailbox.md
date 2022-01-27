---
title: 更改非活动邮箱的保留期
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/29/2017
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
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: 在Office 365邮箱变为非活动邮箱后，更改保留期或Office 365分配给非活动邮箱的保留策略。
ms.openlocfilehash: bf1131aa0d14222bec7ab1c94983925cfe39e673
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241607"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>更改非活动邮箱的保留期

非 [活动](inactive-mailboxes-in-office-365.md) 邮箱是邮箱状态，用于在前员工离开组织后保留其电子邮件。 在删除用户对象之前，如果对邮箱应用了适用的保留Microsoft 365邮箱将变为非活动状态。  以下类型的保留将在删除用户帐户时启动非活动邮箱的创建：

- [Microsoft 365保留策略和标签以及](retention.md)保留和删除设置

- 与电子数据展示[案例关联的保留](ediscovery.md)

- [诉讼保留](create-a-litigation-hold.md)

- 现有In-Place保留。

> [!IMPORTANT]
> 尽管上述任何保留将强制邮箱在删除用户帐户Microsoft 365变为非活动状态，但强烈建议在主动计划利用非活动邮箱时使用 Microsoft 365 保留。
>
> - 电子数据展示保留适用于与法律问题相关的特定、有时间限制的情况。 有时，法律案件可能会结束，并且与该案件关联的保留将被删除，电子数据展示案例将在最终 (或删除) 。 如果非活动邮箱上置于的保留与电子数据展示案例关联，并且该保留已释放或者电子数据展示案例已关闭或删除，则非活动邮箱将被永久删除。
>
> - In-Place管理Exchange中的保留现已停用。 自 2020 年 7 月 1 日起，无法在 In-Place 中创建新的保留Exchange Online。 从 2020 年 10 月 1 日起，就地保留的保留期无法再更改。 任何应用了"In-Place"的非活动邮箱都只能通过删除"保留"In-Place删除。 在删除保留之前，In-Place处于保留状态的现有非活动邮箱将继续保留。 有关保留停用In-Place，请参阅 [停用旧版电子数据展示工具](legacy-ediscovery-retirement.md)。
>
> - [诉讼保留](create-a-litigation-hold.md) 仍受支持，作为在删除用户帐户后保留邮箱内容并使其处于非活动状态的替代方法。 但是，作为较旧的技术，我们建议你改为Microsoft 365保留。

一旦变为非活动状态，邮箱的内容（包括"[](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder)可恢复的项目"文件夹）将一直保留，直到邮箱变为非活动邮箱之前所置于的保留不再适用。  

如果适用的保留不是基于时间，例如与仅无限期保留 Microsoft 365 保留策略或标签相关联的保留、未配置) 电子数据展示案例或诉讼保留 (，邮箱内容将无限期保留，直到删除保留。 ```LitigationHoldDuration```  

但是，如果保留基于时间，则邮箱内容将一直保留到保留期过期，此时"可恢复的项目"文件夹中的任何项目都将从非活动邮箱中 (永久删除) 。

> [!NOTE]
> 对于非活动邮箱，我们建议对邮箱保留策略或标签Microsoft 365保留和删除设置。  如果选择"仅保留"设置，"可恢复的项目"文件夹将在保留期结束时清除，但是任何其他未删除的项目将无限期地保留在非活动邮箱中。

随着法规和策略的不断发展，在某些情况下，可能需要更改分配给非活动邮箱的保留期。  以下步骤概述了如何执行这一操作。

## <a name="connect-to-powershell"></a>连接 PowerShell

如前所述，许多不同类型的保留可能会触发非活动邮箱的创建。  因此，为了更改应用于非活动邮箱的保留期，您必须先确定影响该邮箱的保留类型。  为此，必须使用 Exchange Online PowerShell 标识保留类型，如果非活动邮箱受 Microsoft 365 保留策略或标签的影响，则还必须使用安全与合规中心 PowerShell 标识特定策略。

- 若要连接到 Exchange Online PowerShell 或安全&合规中心 PowerShell，请参阅下列主题之一：

  - [连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

  - [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>第 1 步：识别非活动邮箱上设置的保留

由于不同类型的保留或一Microsoft 365保留策略可能会置于非活动邮箱上，因此第一步是标识非活动邮箱上的保留。
  
在 PowerShell Exchange Online以下命令，以显示组织中特定非活动邮箱的保留信息。
  
```powershell
Get-Mailbox -Identity <identity of inactive mailbox> -InactiveMailboxOnly | FL DisplayName,Name,DistinguishedName,ExchangeGuid,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,LitigationHoldDate,LitigationHoldOwner,InPlaceHolds,ComplianceTagHoldApplied
```

如果需要确定多个非活动邮箱的保留类型，并且您的组织具有大量非活动邮箱，则使用 PowerShell 查看可能变得不可管理。 在这种情况下，可以使用以下命令，并根据需要修改环境，将所有适用信息导出到 CSV ```Path``` 文件：

```powershell
Get-Mailbox -InactiveMailboxOnly -ResultSize Unlimited | Select DisplayName,Name,DistinguishedName,ExchangeGuid,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,LitigationHoldDate,LitigationHoldOwner,InPlaceHolds,ComplianceTagHoldApplied | Export-Csv -NoTypeInformation -Path "C:\Temp\InactiveMailboxHoldTypes.csv"
```

对于此示例，下面显示了具有不同可能保留类型的六个非活动邮箱的结果。

> [!NOTE]
> 包含多个保留类型的多个保留可应用于单个非活动邮箱。
  
```text
DisplayName              : Ann Beebe
Name                     : annb
DistinguishedName        : CN=annb,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 664ef44e-c1a0-47b0-9553-2ecdfc6ef840
IsInactiveMailbox        : True
LitigationHoldEnabled    : True
LitigationHoldDuration   : 365.00:00:00
LitigationHoldDate       : 10/25/2021 6:54:57 PM
LitigationHoldOwner      : admin@contoso.com
InPlaceHolds             : {}
ComplianceTagHoldApplied : False
...
DisplayName              : Carol Olson
Name                     : carolo
DistinguishedName        : CN=carolo,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : e646a369-00bf-43d3-837a-8eae8b301d44
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {mbxcdbbb86ce60342489bff371876e7f224:3}
ComplianceTagHoldApplied : False
...
DisplayName              : Megan Bowen
Name                     : meganb
DistinguishedName        : CN=meganb,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 36ec77cb-c524-468a-a8e8-bfb75e01a176
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {mbx6fe063689d404a5bb9940eed0f0bf5d2:1}
ComplianceTagHoldApplied : True
...
DisplayName              : Mario Necaise
Name                     : marion
DistinguishedName        : CN=marion,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 0579e039-a695-40d5-8f0a-0dc04f4b4c8f
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {}
ComplianceTagHoldApplied : False
...
DisplayName              : Abraham McMahon
Name                     : abrahamm
DistinguishedName        : CN=abrahamm,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 55ad8905-4e68-4c8d-940d-e068ec6b51fc
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
ComplianceTagHoldApplied : False
...
DisplayName              : Pilar Pinilla
Name                     : pilarp
DistinguishedName        : CN=pilarp,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 8d7867d6-bb6d-4cd8-a51f-09d208f97fcc
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {c0ba3ce811b6432a8751430937152491}
ComplianceTagHoldApplied : False
```

下表标识了以上示例中用于使每个邮箱处于非活动状态的六种不同的保留类型。
  
|**非活动邮箱**|**保留类型**|**如何识别非活动邮箱上的保留**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |诉讼保留  <br/> | `LitigationHoldEnabled`属性设置为 `True` 指示邮箱已置于诉讼保留状态。 <br/><br/> 此外，设置为 指示邮箱项目在创建日期 365 天后将不再受诉讼保留 (`LitigationHoldDuration` `365.00:00:00` 发送/接收) 。  <br/><br/> `LitigationHoldDate`指示 LitigationHold 的启用日期， `LitigationHoldOwner` 并标识发起诉讼保留的人。 <br/> |
|表示 Olson  <br/> |Microsoft 365应用于特定邮箱Microsoft 365 合规中心保留策略  <br/> |`InPlaceHolds`属性包含应用于非活动Microsoft 365保留策略的 GUID。 你可以判断这是应用于特定邮箱的保留策略，因为 GUID 以 前缀开头，以 `mbx` `:2` 或 结尾 `:3` 。 <br/><br/> 有关详细信息，请参阅了解保留策略 [的 InPlaceHolds 值的格式](identify-a-hold-on-an-exchange-online-mailbox.md#understanding-the-format-of-the-inplaceholds-value-for-retention-policies)。  <br/> |
|Megan Bowen <br/> | Microsoft 365保留和删除操作保留标签应用于邮箱中的至少一个项目  <br/> |`ComplianceTagHoldApplied`属性表示 `True` 项目已标记有保留或保留和删除标签。  <br/><br/> 此外，该属性包含应用于非Microsoft 365邮箱的保留标签策略的 `InPlaceHolds` GUID。  <br/><br/> 有关详细信息，请参阅标识保留邮箱，因为保留标签 [已应用于文件夹或项目](identify-a-hold-on-an-exchange-online-mailbox.md#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) <br/>  |
|为百分卡  <br/> |组织范围内的Microsoft 365保留策略来自Microsoft 365 合规中心  <br/> |属性  `InPlaceHolds`  为空、是 `LitigationHoldEnabled` `False` 和 `ComplianceTagHoldApplied` `False` 。 这表示一个或多个整个 (Exchange) 保留Microsoft 365应用于非活动邮箱所继承的组织。 <br/><br/> 有关详细信息，请参阅 [如何确认组织范围的保留策略已应用于邮箱](identify-a-hold-on-an-exchange-online-mailbox.md#how-to-confirm-that-an-organization-wide-retention-policy-is-applied-to-a-mailbox) <br/> |
|为 McMahon  <br/> |电子数据展示服务中的Microsoft 365 合规中心  <br/> |属性包含非活动邮箱上电子数据展示案例保留  `InPlaceHolds`  的 GUID。 你可以判断这是电子数据展示案例保留，因为 GUID 以前缀  `UniH` 开头。  <br/><br/> 有关详细信息，请参阅电子 [数据展示保留](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)。 <br/> |
|Pilar Pinilla  <br/> |就地保留  <br/> |`InPlaceHolds`属性包含非活动邮箱In-Place保留的 GUID。 你可以判断这是一个In-Place保留，因为 GUID 不以前缀开头。  <br/><br/> **注意**：自 2020 年 10 月 1 日起，就地保留的保留期将无法再更改。 只能删除In-Place保留，这可能会导致删除非活动邮箱。 <br/><br/> 有关详细信息，请参阅 [停用旧版电子数据展示工具](legacy-ediscovery-retirement.md)。 <br/> |

## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>第 2 步：更改非活动邮箱的保留期

在确定了非活动邮箱上设置的保留的类型（以及是否设置多个保留）后，下一步就要更改保留期了。  此过程因应用的保留类型而异。

- [更改保留策略Microsoft 365持续时间](#change-the-duration-for-a-microsoft-365-retention-policy)

- [更改保留标签Microsoft 365持续时间](#change-the-duration-for-a-microsoft-365-retention-label)

- [更改电子数据展示保留的持续时间](#change-the-duration-for-an-ediscovery-hold)

- [更改诉讼保留的持续时间](#change-the-duration-for-a-litigation-hold)

- [更改保留In-Place持续时间](#change-the-duration-for-an-in-place-hold)

### <a name="change-the-duration-for-a-microsoft-365-retention-policy"></a>更改保留策略Microsoft 365持续时间

为了修改 Microsoft 365 保留策略的保留期，您必须先在安全与合规中心 PowerShell 中通过邮箱属性的关联 GUID 运行来识别影响非活动邮箱 `Get-RetentionCompliancePolicy` `InPlaceHolds` 的策略。

运行此命令时，请务必从 GUID 中删除前缀和后缀。  例如，使用上述示例信息，您将获取 的值 `InPlaceHolds` `mbxcdbbb86ce60342489bff371876e7f224:3` ，然后删除 ，并生成 策略 `mbx` `:3` `cdbbb86ce60342489bff371876e7f224` GUID。  在此例中，你想要运行：

```powershell
Get-RetentionCompliancePolicy cdbbb86ce60342489bff371876e7f224 | FL Name
```

在知道策略名称后，只需在合规性中心内修改Microsoft 365策略。  请注意，保留策略通常应用于多个位置，因此修改策略将影响所有已应用的位置（非活动位置和活动位置，其中可能还包括非活动Exchange）。  有关详细信息，请参阅创建 [和配置保留策略](create-retention-policies.md)。  

> [!IMPORTANT]
> 启用了保留 [锁定的保留](retention-preservation-lock.md) 策略可以延长保留期，但不能减少或删除保留期。

如果打算仅修改非活动邮箱或仅特定非活动邮箱的保留期，可以考虑部署自适应策略作用域，这些作用域可用于使用[](retention.md#adaptive-or-static-policy-scopes-for-retention)Azure AD 和 Exchange 属性单独面向特定邮箱或邮箱类型（如非活动邮箱）。

### <a name="change-the-duration-for-a-microsoft-365-retention-label"></a>更改保留标签Microsoft 365持续时间

与保留策略一样，在修改 Microsoft 365 保留标签的保留期时，必须先在安全与合规中心 PowerShell 中通过邮箱属性运行关联的 GUID 来运行发布影响非活动邮箱中内容的标签的策略。 `Get-RetentionCompliancePolicy` `InPlaceHolds`

运行此命令时，请务必从 GUID 中删除前缀和后缀。  例如，使用上述示例信息，您将获取 的值 `InPlaceHolds` `mbx6fe063689d404a5bb9940eed0f0bf5d2:1` ，然后删除 ，并生成 策略 `mbx` `:1` `6fe063689d404a5bb9940eed0f0bf5d2` GUID。  在此例中，你想要运行：

```powershell
Get-RetentionCompliancePolicy 6fe063689d404a5bb9940eed0f0bf5d2 | FL Name
```

确定策略后，你将知道已发布哪些标签及其设置。  由于标签适用于单个项目，具体取决于随策略发布的标签数量及其设置，因此可能无法直接标识哪个标签正在影响内容。  

可用于标识每个标签所应用的内容的一个方法是使用 [内容搜索](content-search.md)。  例如，使用上述示例信息，假定策略发布了多个标签，其中一个标签名为"HR-Content"。  使用正确的 [权限](microsoft-365-compliance-center-permissions.md)，可以使用 [New-ComplianceSearch PowerShell](/powershell/module/exchange/new-compliancesearch)命令运行内容搜索，以指定非活动邮箱的主 SMTP 地址、预先使用时间段 () 以及参数跳过 `.` `-AllowNotFoundExchangeLocationsEnabled $true` 验证：

```powershell
New-ComplianceSearch -Name "MeganB Inactive Mailbox HR-Content Label Search" -ExchangeLocation .meganb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true -ContentMatchQuery "compliancetag=HR-Content"
```

创建搜索后，您将使用下列命令开始搜索：

```powershell
Start-ComplianceSearch "MeganB Inactive Mailbox HR-Content Label Search"
```

使用此方法，您可以标识标识的标签策略中的哪些标签适用于非活动邮箱中的内容，以便可以修改其保留期。 请注意，保留标签通常应用于多个位置，因此修改标签将影响所有应用的位置和标记的内容，其中可能还包括位置和Exchange。 有关详细信息，请参阅创建 [保留标签，并应用在应用中](create-apply-retention-labels.md)。

> [!NOTE]
> 并非所有类型的保留标签都可以修改。  对于一些标签，可能只能增加保留时间，而对于其他标签，你完全不能修改保留期。

### <a name="change-the-duration-for-an-ediscovery-hold"></a>更改电子数据展示保留的持续时间

与电子数据展示事例关联的保留是无限期保留，这意味着没有可更改的保留期。 项目将永久保留，或者一直保留 [到移除](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold) 保留或案例关闭。
  
### <a name="change-the-duration-for-a-litigation-hold"></a>更改诉讼保留的保留期

必须使用 Exchange Online PowerShell 更改非活动邮箱上设置的诉讼保留的保留期。 不能使用 EAC。 运行以下命令，更改保留期。 本示例中，保留期更改为无限期：
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

结果是非活动邮箱中的项目会无限期保留，或者一直保留到删除保留或将保留期更改为其他值。
  
> [!TIP]
> 标识非活动邮箱的最佳方式是使用 **Distinguished Name** 或 **Exchange GUID** 值。 使用下列值之一有助于避免意外指定错误的邮箱。

### <a name="change-the-duration-for-an-in-place-hold"></a>更改就地保留的保留期

In-Place保留已停用且无法再修改。 如果非活动邮箱应用了In-Place保留，则不能更改保留期。 只能删除In-Place保留，这可能会导致删除非活动邮箱。 有关详细信息，请参阅删除 [非活动邮箱](delete-an-inactive-mailbox.md#remove-in-place-holds)。
  
## <a name="more-information"></a>详细信息

- **如何计算非活动邮箱中项目的保留期？** 保留期从邮箱项目的接收或创建原始日期开始计算。
    
- **当保留期过期时，会怎么样？** 当"可恢复的项目"文件夹中的邮箱项目的保留期过期时，会从非活动邮箱中 (项目) 永久删除。 如果没有为非活动邮箱上的保留指定持续时间，则永远不会清除"可恢复的项目"文件夹中的项目 (除非非活动邮箱的保留期) 。 
    
- **是否仍在Exchange非活动邮箱上处理 MRM 策略？**  如果 MRM 保留策略在邮箱处于非活动状态之前应用于邮箱 (则使用删除操作) 配置的 MRM 保留标记将继续在非活动邮箱上进行处理。 这意味着，在保留期到期时，用 MRM 删除策略标记的项目将移动到"可恢复的项目"文件夹。 在保留期过期时，这些项目会从非活动邮箱中清除。 如果没有为非活动邮箱指定保留期，则"恢复项目"文件夹中的项目将无限期保留。

    相反，任何存档策略 (分配给非活动邮箱的 MRM 保留策略中包含的使用 **MoveToArchive** 操作) 配置的 MRM 保留标记。 也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。 这些项目不会移到存档邮箱或其中的“可恢复的项目”文件夹内。 它们将被无限期保留。
    > [!NOTE]
    > 如果对 Exchange Online) 中的Exchange保留策略 (邮件记录管理或 MRM 功能，则删除用户帐户时不会创建非活动邮箱。

- **与常规邮箱一样，托管文件夹助理 (MFA) 处理非活动邮箱。** 在Exchange Online中，MFA 大约每七天处理一次邮箱。 更改非活动邮箱的保留期后，您可以使用 **Start-ManagedFolderAssistant** cmdlet 立即开始处理非活动邮箱的新保留期。 运行以下命令。 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **如果 `InPlaceHolds` 多个邮箱被置于非活动邮箱上，则并非所有保留 GUID 都会显示出来。** 可以运行以下命令来显示非活动邮箱上所有放置的 `InPlaceHolds` GUID。
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
