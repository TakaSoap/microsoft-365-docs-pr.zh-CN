---
title: 删除非活动邮箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: 当您不再需要保留非活动邮箱Microsoft 365，您可以永久删除非活动邮箱。
ms.openlocfilehash: 929b3d8a01dd9c88bc12e6e13bf4477a07496b34
ms.sourcegitcommit: e110f00dc6949a7a1345187375547beeb64225b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2021
ms.locfileid: "60804625"
---
# <a name="delete-an-inactive-mailbox"></a>删除非活动邮箱

非活动邮箱用于在前员工离开组织后保留其电子邮件。 如果您不再需要保留非活动邮箱的内容，可以通过删除保留永久性地删除非活动邮箱。 此外，还可以对非活动邮箱设置多个保留。 例如，非活动邮箱上可以设置诉讼保留以及一个或多个就地保留。 此外，在 (安全与合规中心内创建的保留Office 365 Microsoft 365) 可能会应用于非活动邮箱。 您必须从非活动邮箱中删除所有保留和保留策略，以将其删除。 删除保留和保留策略后，非活动邮箱将标记为删除，并且将在处理后永久删除。
  
> [!IMPORTANT]
> 由于我们将继续以不同方式投资来保留邮箱内容，因此我们将宣布停用 In-Place 管理中心中的 Exchange 保留。 这意味着您应使用诉讼保留和保留策略来创建非活动邮箱。 从 2020 年 7 月 1 日开始，将无法在 In-Place 中创建新的保留Exchange Online。 但你仍然可以更改非活动邮箱上In-Place保留的保留期。 但是，从 2020 年 10 月 1 日起，将不能更改保留期。 仅能删除非活动邮箱，即删除"In-Place保留"。 在删除保留之前，In-Place处于保留状态的现有非活动邮箱仍将保留。 有关停用保留In-Place，请参阅 [停用旧版电子数据展示工具](legacy-ediscovery-retirement.md)。
  
请参阅[详细信息](#more-information)部分了解从非活动邮箱删除保留后会发生什么情况。
  
## <a name="before-you-delete-an-inactive-mailbox"></a>删除非活动邮箱之前

- 您必须使用 Exchange Online PowerShell 从非活动邮箱中删除诉讼保留。 不能使用 Exchange 管理中心 (EAC)。 有关分步说明，请参阅[连接 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 在删除保留设置和非活动邮箱之前，您可以将非活动邮箱的内容复制到另一个邮箱中。 有关详细信息，请参阅[Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md)。

- 如果从非活动邮箱中删除保留或保留策略，并且邮箱的软删除邮箱保留期已过期，则邮箱将被永久删除。 在此邮箱删除后，您将无法恢复。 在删除保留设置之前，请确保您不再需要此邮箱中的内容。 如果要重新激活非活动邮箱，可以恢复它。 有关详细信息，请参阅[恢复邮箱中的非活动Office 365。](recover-an-inactive-mailbox.md)

- 有关非活动邮箱的信息，请参阅非活动[Office 365。](inactive-mailboxes-in-office-365.md)

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>第 1 步：识别非活动邮箱上设置的保留

如前所述，可能会将诉讼保留In-Place保留或保留策略置于非活动邮箱上。 第一步是识别非活动邮箱上设置的保留。
  
运行以下命令，显示组织中所有非活动邮箱的保留信息。
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

如果 **LitigationHoldEnabled** 属性的值为 **True** ，则表示非活动邮箱被置于诉讼保留状态。 如果非活动邮箱被置于就地保留状态，则保留的 GUID 会显示为 **InPlaceHolds** 属性的值。 例如，以下两个非活动邮箱的结果显示 Ann Beebe 处于诉讼保留状态，并且 pilar Pinilla In-Place保留策略。
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> 如果对非In-Place邮箱设置了许多保留或保留策略，则并非所有In-Place保留 GUID 都会显示出来。 可以运行以下命令来显示 InPlaceHolds 属性中所有的 GUID：  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
有关标识保留项详细信息，请参阅如何标识邮箱 [上放置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)。

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>步骤 2：从非活动邮箱删除保留

在确定了非活动邮箱上设置的保留类型（以及是否存在多个保留）后，接下来是删除邮箱上的保留。如前所述，您必须删除所有保留后方可永久删除非活动邮箱。
  
### <a name="remove-a-litigation-hold"></a>删除诉讼保留

如前所述，您必须使用 Windows PowerShell 从非活动邮箱删除诉讼保留。不能使用 EAC。运行以下命令以删除诉讼保留。
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> 若要识别非活动邮箱，最好的方法是通过其可分辨名称或 Exchange GUID 值。使用下列值之一有助于防止意外地指定了错误的邮箱。 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a>从保留策略中删除非活动邮箱

从非活动邮箱中删除非活动邮箱Microsoft 365保留策略取决于分配给非活动邮箱的保留策略是组织范围的还是显式的。 分配给非活动邮箱的保留策略类型。

- 分配给组织中所有邮箱的组织范围的保留策略。 使用 **PowerShell 中的 Get-OrganizationConfig** cmdlet Exchange Online获取有关组织范围的保留策略的信息。

- 分配给特定邮箱的特定位置保留策略。 这些是分配给特定用户的内容位置的策略。 使用 **PowerShell 中的 Get-Mailbox -IncludeInactiveMailbox** cmdlet Exchange Online获取有关分配给特定非活动邮箱的保留策略的信息。

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a>从组织范围的保留策略中删除非活动邮箱

在 PowerShell 中Exchange Online以下命令，从组织范围的保留策略中排除非活动邮箱。

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

有关标识应用于非活动邮箱的组织范围的保留策略和获取保留策略的 GUID 的信息，请参阅如何标识邮箱上保留类型的"Get-OrganizationConfig" [部分](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)。

或者，可以运行以下命令从组织范围内的所有策略中删除非活动邮箱：

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a>从特定位置保留策略中删除非活动邮箱

在安全与合规& [PowerShell 中](/powershell/exchange/connect-to-scc-powershell) 运行以下命令，从显式保留策略中删除非活动邮箱。

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

有关标识应用于非活动邮箱的特定位置保留策略和获取保留策略的 GUID 的信息，请参阅如何标识邮箱上放置的保留类型的"Get-Mailbox" [部分](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)。

### <a name="remove-in-place-holds"></a>删除就地保留

 有两种方法可以从非活动邮箱删除就地保留：
  
- **删除In-Place保留对象**。 如果要永久删除的非活动邮箱是邮件保留In-Place源邮箱，则只需删除In-Place保留对象。 

    > [!NOTE]
    > 您必须先禁用该保留，然后才能删除就地保留对象。如果尝试删除启用了该保留的就地保留对象，您将收到一条错误消息。 
  
- **删除非活动邮箱作为非活动保留的In-Place邮箱**。 如果想要保留就地保留的其他源邮箱，您可以从源邮箱列表中删除该非活动邮箱，并保留就地保留对象。

#### <a name="delete-an-in-place-hold"></a>删除In-Place保留

1. 创建一个变量，其中包含您想要删除的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. 禁用就地保留上的该保留。

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. 删除该就地保留。

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a>从保留状态中删除非In-Place邮箱

如果就地保留中包含大量的源邮箱，则非活动邮箱有可能不会列在 EAC 的“源”页面上。 在编辑就地保留时，“源”页面上最多显示 3000 个邮箱。 如果未在"源"页上列出非活动邮箱，可以使用 Exchange Online PowerShell 将其从"In-Place保留"。 
  
1. 创建一个变量，其中包含非活动邮箱上设置的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. 验证非活动邮箱是否作为就地保留的源邮箱列出。 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties. 由于此属性唯一标识非活动邮箱，因此使用"保留In-Place源属性有助于防止删除错误的邮箱。 如果两个邮箱具有相同的别名或 SMTP 地址，这还有助于避免出现问题。 

3. 从变量中的源邮箱列表删除非活动邮箱。 请务必使用上一步中命令返回的非活动邮箱的 **LegacyExchangeDN。** 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    例如，以下命令将删除 Pilar Pinilla 的非活动邮箱。

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. 验证非活动邮箱已从变量中的源邮箱列表中删除。

   ```powershell
   $InPlaceHold.Sources
   ```

5. 使用源邮箱的更新列表（其中不包括非活动邮箱）修改就地保留。

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. 验证非活动邮箱已从就地保留的源邮箱列表中删除。

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>详细信息

- **非活动邮箱是一种软删除邮箱。** 在 Exchange Online 中，软删除邮箱是指已删除但可以在特定保留期内恢复的邮箱。 对于未保留的软删除邮箱，邮箱将在 30 天内恢复。 非活动 (邮箱在被删除之前处于保留状态) 将保持软删除状态，直到删除该保留。 从非活动邮箱删除保留后，邮箱将不再处于非活动状态。 相反，它将变为软删除Exchange Online保留状态，从在此期间删除保留并恢复起 183 天。 183 天后，软删除邮箱将标记为永久删除且无法恢复。

- **如果删除非活动邮箱的保留设置，后面会怎么样？** 该邮箱被视为其他软删除邮箱，并标记为在 183 天软删除邮箱保留期到期后永久删除。 此保留期从从非活动邮箱中删除保留的日期开始。 *InactiveMailboxRetireTime* 属性是在邮箱从处于非活动状态 (软删除保留) 转换为不再处于非活动状态 (软删除，) 。 此时 *，InactiveMailboxRetireTime* 属性设置为转换发生的当前日期。 有一个助理 (*MailboxLifeCycle* 助手) ，用于查找设置了 *InactiveMailboxRetireTime* 属性的邮箱。 如果"InactiveMailboxRetireTime + 183 天"小于当前日期，则它将清除邮箱。

- **在您删除非活动邮箱的保留设置后，系统会立即永久删除此邮箱吗？** 以前处于非活动状态的邮箱将在 183 天内处于软删除状态。 183 天后，邮箱将被标记为永久删除。

- **在删除保留设置后，如何显示非活动邮箱的相关信息？** 删除保留设置且非活动邮箱恢复为软删除邮箱后，不会将  *InactiveMailboxOnly*  参数与 **Get-Mailbox** cmdlet 一同使用返回。 但是，您可以使用 **Get-Mailbox -SoftDeletedMailbox** 命令显示有关邮箱的信息。 例如：

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox,WasInactiveMailbox,InactiveMailboxRetireTime
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 6/16/2020 1:19:04 AM
  IsInactiveMailbox      : False
  WasInactiveMailbox     : True
  InactiveMailboxRetireTime : 9/30/2020 11:16:23 PM
  ```

  在以上示例中 *，WhenSoftDeleted* 属性标识软删除日期，本示例中为 2020 年 6 月 16 日。 *WasInactiveMailbox* 属性列为 ， `True` 因为它以前是非活动邮箱。 邮箱将在 2020 年 9 月 30 日之后 183 天内永久删除。

