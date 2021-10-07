---
title: 更改非活动邮箱的保留期
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.openlocfilehash: be7877e3087004e6b633e0967d72173fa83a3948
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170819"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>更改非活动邮箱的保留期

非活动邮箱用于在前员工离开组织后保留其电子邮件。 当邮箱上设置诉讼保留、In-Place 保留、Microsoft 365 保留策略或与电子数据展示案例关联的保留时，邮箱将变为非活动状态，并删除相应的用户帐户。 在非活动邮箱变为非活动邮箱之前，非活动邮箱的内容将在邮箱上置于保留状态期间保留。 保留期定义了"可恢复的项目"文件夹中的项目的保留持续时间。 如果"可恢复的项目"文件夹中的项目的保留期过期，则此项目会从非活动邮箱中永久删除（清除）。 邮箱变为非活动邮箱后，可以更改分配给非活动邮箱Microsoft 365保留策略的保留期。
  
> [!IMPORTANT]
> 由于我们将继续以不同方式投资来保留邮箱内容，因此我们将宣布停用 In-Place 管理中心中的 Exchange 保留。 这意味着您应该使用诉讼保留和Microsoft 365保留策略来创建非活动邮箱。 从 2020 年 4 月 1 日起，将无法在 Exchange Online 中创建新的 In-Place 保留。 但你仍然可以更改非活动邮箱上In-Place保留的保留期。 但是，从 2020 年 7 月 1 日开始，将不能更改保留期。 仅能删除非活动邮箱，即删除"In-Place保留"。 在删除保留之前，In-Place处于保留状态的现有非活动邮箱仍将保留。 有关停用保留In-Place，请参阅 [停用旧版电子数据展示工具](legacy-ediscovery-retirement.md)。
  
## <a name="connect-to-powershell"></a>连接 PowerShell

- 您必须使用 Exchange Online PowerShell 更改非活动邮箱上诉讼保留的保留期。 不能使用 Exchange 管理中心 (EAC)。 不过，您可以使用 Exchange Online PowerShell 或 EAC 更改保留期In-Place保留。 可以使用安全与合规中心或安全与合规& PowerShell 更改保留策略的保留Microsoft 365持续时间。
    
- 若要连接到 Exchange Online PowerShell 或安全&合规中心 PowerShell，请参阅下列主题之一：
    
  - [连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)
    
- 与电子数据展示事例关联的保留是无限期保留，这意味着没有可更改的保留期。 项目将永久保留，或一直保留到删除保留并删除非活动邮箱。
    
- 有关非活动邮箱的信息，请参阅非活动[Microsoft 365。](inactive-mailboxes-in-office-365.md)
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>第 1 步：识别非活动邮箱上设置的保留

由于不同类型的保留或一Microsoft 365保留策略可能会置于非活动邮箱上，因此第一步是标识非活动邮箱上的保留。
  
在 PowerShell Exchange Online以下命令，以显示组织中所有非活动邮箱的保留信息。
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

如果 **LitigationHoldEnabled** 属性的值为 **True** ，则表示非活动邮箱被置于诉讼保留状态。 如果将In-Place保留、电子数据展示保留或 Microsoft 365 保留策略置于非活动邮箱上，则保留或保留策略的 GUID 将显示为 **InPlaceHolds** 属性的值。 例如，下面显示了五个非活动邮箱的结果。 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

下表标识了使每个邮箱变为非活动状态的五种不同的保留类型。
  
|**非活动邮箱**|**保留类型**|**如何识别非活动邮箱上的保留**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |诉讼保留  <br/> |*LitigationHoldEnabled* 属性设置为 `True` 。  <br/> |
|Pilar Pinilla  <br/> |就地保留  <br/> |*InPlaceHolds* 属性包含非活动邮箱In-Place保留的 GUID。 你可以判断这是一个In-Place保留，因为 ID 不以前缀开头。  <br/> 可以使用 PowerShell 中的 Exchange Online 获取有关非活动邮箱In-Place `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` 保留的信息。  <br/> |
|为百分卡  <br/> |组织中组织Microsoft 365保留策略Microsoft 365 合规中心  <br/> |*InPlaceHolds* 属性为空。 这表示一个或多个组织范围内的保留策略 (Exchange或) Microsoft 365保留策略应用于非活动邮箱。 在这种情况下，可以在 Exchange Online PowerShell 中运行命令，获取组织范围内保留策略的 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` GUID Microsoft 365列表。 应用于邮箱的组织范围的保留策略的 GUID Exchange前缀开头; `mbx` 例如， `mbxa3056bb15562480fadb46ce523ff7b02` 。  <br/> <br/>若要标识Microsoft 365邮箱的保留策略，请运行安全与合规中心 PowerShell &命令。  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|表示 Olson  <br/> |Microsoft 365应用于特定邮箱Microsoft 365 合规中心保留策略  <br/> |*InPlaceHolds* 属性包含应用于非活动Microsoft 365保留策略的 GUID。 你可以判断这是应用于特定邮箱的保留策略，因为 GUID 以前缀  `mbx` 开头。 如果应用于非活动邮箱的保留策略的 GUID 以前缀开头，则表明保留策略应用于Skype for Business `skp` 对话。  <br/><br/> 若要标识Microsoft 365邮箱的保留策略，请运行安全与合规中心 PowerShell &命令。<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>运行此命令时，  `mbx` 请务必删除 或  `skp` 前缀。  <br/> |
|为 McMahon  <br/> |电子数据展示服务中的Microsoft 365 合规中心  <br/> |*InPlaceHolds* 属性包含非活动邮箱上设置电子数据展示案例保留的 GUID。 你可以判断这是电子数据展示案例保留，因为 GUID 以前缀  `UniH` 开头。  <br/> 您可以使用安全与合规中心 PowerShell & cmdlet 获取有关非活动邮箱上的保留相关联的电子数据展示  `Get-CaseHoldPolicy` 案例的信息。 例如，可以运行命令来显示非活动邮箱上案例保留  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 的名称。 运行此命令时  `UniH` ，请务必删除前缀。  <br/><br/> 若要标识与非活动邮箱上的保留相关联的电子数据展示案例，请运行以下命令。  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **注意：** 建议不要对非活动邮箱使用电子数据展示保留。 这是因为电子数据展示事例适用于与安全问题相关的特定、有时间限制的事例。 有时，法律案件可能会结束，并且与该案件关联的保留将被删除，电子数据展示案例将在最终 (或删除) 。 事实上，如果非活动邮箱上的保留与电子数据展示案例关联，并且该保留已释放或者电子数据展示案例已关闭或删除，则非活动邮箱将被永久删除。 

有关保留策略Microsoft 365，请参阅了解[保留策略和保留标签](retention.md)。
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>第 2 步：更改非活动邮箱的保留期

在确定了非活动邮箱上设置的保留的类型（以及是否设置多个保留）后，下一步就要更改保留期了。 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>更改诉讼保留的保留期

下面将Exchange Online PowerShell 更改非活动邮箱上设置的诉讼保留的保留期。 不能使用 EAC。 运行以下命令，更改保留期。 在此示例中，可将保留期更改为无限期。
  
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
    
- **当保留期过期时，会怎么样？** 当"可恢复的项目"文件夹中的邮箱项目的保留期过期时，该项目 (从非活动) 中清除。 如果没有为非活动邮箱上的保留指定持续时间，则永远不会清除"可恢复的项目"文件夹中的项目 (除非非活动邮箱的保留期) 。 
    
- **是否仍在Exchange邮箱上处理保留策略？** 如果 Exchange 保留策略 (邮件记录管理或 MR Exchange Online) M 功能在变为非活动邮箱时应用于邮箱，则删除策略 (即使用删除保留操作) 配置的保留标记将继续在非活动邮箱上进行处理。  也就是说，在保留期过期时，标记有删除策略的项目会移到“可恢复的项目”文件夹中。 当项目的保留期过期时，这些项目会从非活动邮箱中清除。 
    
    当项目的保留期过期时，这些项目会从非活动邮箱中清除。 相反，分配给非活动邮箱的保留策略中包含的所有存档策略（配置了 MoveToArchive 保留操作的保留标记）会遭到忽略。也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。这些项目不会移到存档邮箱或其中的"可恢复的项目"文件夹内。由于用户无法登录非活动邮箱，因此没有理由消耗数据中心资源来处理存档策略。 相反，分配给非活动邮箱的保留策略中包含的所有存档策略（配置了 MoveToArchive 保留操作的保留标记）会遭到忽略。 也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。 

- **若要检查诉讼保留的新保留期，请运行以下命令** 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- **托管文件夹助理 (MFA) 还会处理非活动邮箱，就像处理常规邮箱一样。** 在Exchange Online，MFA 大约每七天处理一次邮箱。 更改非活动邮箱的保留期后，您可以使用 **Start-ManagedFolderAssistant** cmdlet 立即开始处理非活动邮箱的新保留期。 运行以下命令。 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **如果非活动邮箱上设置了许多保留，则并非所有保留项 GUID 都会显示出来。** 可以运行以下命令来显示非活动邮箱上 (保留) 保留的 GUID。 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```