---
title: 为置于保留状态的邮箱增加可恢复项目的配额
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 启用存档邮箱并打开自动扩展存档，以增加 Microsoft 365 中邮箱的 "可恢复的项目" 文件夹的大小。
ms.openlocfilehash: c674d3df4ad14dabce13effd0dd6729edaeab715
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804641"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>为置于保留状态的邮箱增加可恢复项目的配额

将自动应用于 Exchange Online 中的新邮箱的默认 Exchange 保留策略（名为 " *默认 MRM 策略* "）包含一个名为 "可恢复的项目" 的保留标记。移动到存档的14天。 此保留标记将项目从用户主邮箱中的 "可恢复的项目" 文件夹移动到用户的存档邮箱中的 "可恢复的项目" 文件夹中，在该项目的14天保留期到期之后。 为此，必须启用用户的存档邮箱。 如果未启用存档邮箱，则不会执行任何操作，这意味着保留邮箱的 "可恢复的项目" 文件夹中的项目在14天保留期过期后不会移动到存档邮箱。 由于保留邮箱时不会从邮箱中删除任何内容，因此可能会超出 "可恢复的项目" 文件夹的存储配额，尤其是在未启用用户的存档邮箱的情况下。 
  
为了帮助降低超出此限制的可能性，在 Exchange Online 中的邮箱上放置保留时，"可恢复的项目" 文件夹的存储配额将自动从 30 GB 增加到 100 GB。 如果启用存档邮箱，则存档邮箱中的 "可恢复的项目" 文件夹的存储配额也会从 30 GB 增加到 100 GB。 如果启用了 Exchange Online 中的自动扩展存档功能，则用户存档中的 "可恢复的项目" 文件夹的存储配额将不受限制。
  
 下表汇总了 "可恢复的项目" 文件夹的存储配额。 
  
|**"可恢复的项目" 文件夹的位置**|**不处于保留状态的邮箱**|**处于保留状态的邮箱**|
|:-----|:-----|:-----|
|主邮箱  <br/> |30 GB  <br/> |100 GB  <br/> |
|存档邮箱<sup>\*</sup> <br/> |无限制  <br/> |无限制  <br/> |
|**"可恢复的项目" 文件夹的总存储配额** <br/> |无限制  <br/> |无限制  <br/> |
   
> [!NOTE]
> <sup>\*</sup> 存档邮箱的初始存储配额为 100 GB （适用于具有 Exchange Online (Plan 2) 许可证的用户）。 但是，如果在保留时为邮箱启用自动扩展存档，则存档邮箱和 "可恢复的项目" 文件夹的存储配额将增加到 110 GB。 必要时将预配其他存档存储空间，从而导致存档存储量不受限制。 有关自动扩展存档的详细信息，请参阅 [Office 365 中的无限制存档概述](unlimited-archiving.md)。 
  
当置于保留状态的邮箱的主邮箱"可恢复的项目"文件夹的存储配额接近其限额时，可以执行以下操作：
  
- **启用存档邮箱并启用自动扩展存档。** 只需启用存档邮箱，然后启用 ExchangeOnline 中的自动扩展存档功能，就可以为“可恢复的项目”文件夹开启无限制存储容量。 这将导致主邮箱中的 "可恢复的项目" 文件夹的 110 GB 和用户存档中 "可恢复的项目" 文件夹的存储容量不受限制。 请参阅如何： [在安全 & 合规性中心中启用存档邮箱](enable-archive-mailboxes.md) ，以及如何 [在 Office 365 中启用无限存档](enable-unlimited-archiving.md)。
    
    > [!NOTE]
    > 在为接近于 "可恢复的项目" 文件夹的存储配额的邮箱启用存档后，您可能需要运行 "托管文件夹助理" 手动触发助理以处理邮箱，以便将过期项目移至存档邮箱中的 "可恢复的项目" 文件夹中。 有关说明，请参阅 [步骤 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 。 注意，用户邮箱中的其他项目可能会移至新的存档邮箱。 请考虑告诉用户在启用存档邮箱后可能会发生这种情况。 
  
- **为处于保留状态的邮箱创建自定义 Exchange 保留策略。** 除了在诉讼保留或 In-Place 保留中启用邮箱的存档邮箱和自动扩展存档之外，您可能还需要为处于保留状态的邮箱创建自定义 Exchange 保留策略。 这使您可以将保留策略应用于保留的邮箱，这些邮箱与应用于不保留的邮箱的默认 MRM 策略不同，并允许您应用专为邮箱保留的保留标记。 其中包括为"可恢复的项目"文件夹创建新的保留标记。 
    
本主题的其余部分介绍了为处于保留状态的邮箱创建自定义 Exchange 保留策略的分步过程。
  
[步骤1：为 "可恢复的项目" 文件夹创建自定义保留标记](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[步骤2：为处于保留状态的邮箱创建新的 Exchange 保留策略](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[步骤3：将新的 Exchange 保留策略应用于处于保留状态的邮箱](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[ (可选) 步骤4：运行托管文件夹助理以应用新的保留设置](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>步骤1：为 "可恢复的项目" 文件夹创建自定义保留标记

第一步是为 "可恢复的项目" 文件夹创建名为 "保留策略标记" 或 "RPT) " 的自定义保留标记 (。 如前所述，此 RPT 将项目从用户主邮箱中的 "可恢复的项目" 文件夹移动到用户的存档邮箱中的 "可恢复的项目" 文件夹中。 您必须使用 PowerShell 为 "可恢复的项目" 文件夹创建 RPT。 不能使用 Exchange 管理中心 (EAC)。 
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. 运行以下命令，为 "可恢复的项目" 文件夹创建一个新的 RPT： 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    例如，以下命令为 "保留的邮箱为30天" 的 "可恢复的项目" 文件夹创建一个 RPT，保留期为30天。 这意味着项目已在 "可恢复的项目" 文件夹中的30天后，它将移至用户存档邮箱中的 "可恢复的项目" 文件夹中。
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > 建议由  _AgeLimitForRetention_ 参数) 为可恢复项目 RPT 定义的保留期 (与 RPT 将应用到的邮箱的已删除项目保留期相同。 这允许用户整个已删除项目的保留期在将已删除邮件移至存档邮箱之前将其恢复。 在上面的示例中，假定邮箱的已删除邮件保留期也为30天，则保留期已设置为30天。 默认情况下，Exchange Online 邮箱配置为将已删除项目保留14天。 但您最多可以将此设置更改为30天。 有关详细信息，请参阅 [在 Exchange Online 中更改邮箱的已删除邮件保留期](https://www.microsoft.com/?ref=go)。 
  
## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a>步骤2：为处于保留状态的邮箱创建新的 Exchange 保留策略

下一步是创建新的保留策略并向其添加保留标记，包括您在步骤1中创建的 "可恢复的项目" RPT。 在下一步中，此新策略将应用于处于保留状态的邮箱。 
  
在创建新的保留策略之前，请确定要添加的其他保留标记。 有关添加到默认 MRM 策略的保留标记列表，以及有关创建新的保留标记的信息，请参阅以下内容：
  
- [Exchange Online 中的默认保留策略](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [支持保留策略标记的默认文件夹](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- " [创建保留策略](https://go.microsoft.com/fwlink/p/?LinkId=404422) " 主题中的 "创建保留标记" 部分。
    
您可以使用 EAC 或 Exchange Online PowerShell 创建保留策略。
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>使用 EAC 创建保留策略
  
1. 在 EAC 中，转到 " **合规性管理** \> **保留策略** "，然后单击 " **添加** " "添加" ![ 图标 ](../media/ITPro-EAC-AddIcon.gif) 。
    
2. 在 " **新建保留策略** " 页上的 " **名称** " 下，键入描述保留策略用途的名称;例如，处于 **保留状态的邮箱的 MRM 策略** 。 
    
3. 在 " **保留标记** " 下，单击 " **添加** " "添加" ![ 图标 ](../media/ITPro-EAC-AddIcon.gif) 。
    
4. 在 "保留标记" 列表中，选择您在步骤1中创建的 "可恢复的项目" RPT，然后单击 " **添加** "。
    
    ![选择自定义的“可恢复的项目”保留标记](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. 选择要添加到保留策略中的其他保留标记。 例如，您可能希望添加默认 MRM 策略中包含的相同标记。
    
6. 添加完保留标记后，单击 **"确定"** 。
    
7. 单击 " **保存** " 以创建新的保留策略。 
    
    请注意，链接到保留策略的保留标记将显示在详细信息窗格中。
    
    ![在详细信息窗格中显示链接到保留策略的保留标记](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>使用 Exchange Online PowerShell 创建保留策略
  
运行以下命令，为处于保留状态的邮箱创建新的保留策略。 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

例如，以下命令将创建在上图中显示的保留策略和链接的保留标记。
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a>步骤3：将新的 Exchange 保留策略应用于处于保留状态的邮箱

最后一步是将您在步骤2中创建的新的保留策略应用于组织中的 "保留中的邮箱"。 您可以使用 EAC 或 Exchange Online PowerShell 将保留策略应用于单个邮箱或多个邮箱。 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>使用 EAC 应用新的保留策略
  
1. 转到 " **收件人** " "  >  **邮箱** "。
    
2. 在列表视图中，选择要应用保留策略的邮箱，然后单击 " **编辑** ![ 编辑图标" ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。
    
3. 在 " **用户邮箱** " 页上，单击 " **邮箱功能** "。
    
4. 在 " **保留策略** " 下，选择您在步骤2中创建的保留策略，然后单击 " **保存** "。
    
您还可以使用 EAC 将保留策略应用于多个邮箱。
  
1. 转到 " **收件人** " "  >  **邮箱** "。
    
2. 在此列表视图中，使用 Shift 或 Ctrl 键选择多个邮箱。
    
3. 在详细信息窗格中，单击“更多选项”  。
    
4. 在“保留策略”  下，单击“更新”  。
    
5. 在 " **批量分配保留策略** " 页上，选择您在步骤2中创建的保留策略，然后单击 " **保存** "。 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>使用 Exchange Online PowerShell 应用新的保留策略
  
您可以使用 Exchange Online PowerShell 将新的保留策略应用于单个邮箱。 但是，PowerShell 真正的强大之处在于，您可以使用它来快速识别组织中的所有邮箱是否处于诉讼保留或 In-Place 保留状态，然后在单个命令中将新的保留策略应用于保留的所有邮箱。 下面是使用 Exchange PowerShell 将保留策略应用于一个或多个邮箱的一些示例。 所有示例都应用在步骤2中创建的保留策略。
  
本示例将新的保留策略应用于 Pilar Pinilla 的邮箱。
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

本示例将新的保留策略应用于组织中处于诉讼保留状态的所有邮箱。
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

本示例将新的保留策略应用于组织中所有处于 In-Place 保留状态的邮箱。
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

您可以使用 " **获取邮箱** " cmdlet 验证是否已应用新的保留策略。 
  
下面是一些示例，用于验证前面示例中的命令是否将 "MRM Policy for 邮箱保留" 保留策略应用于在 In-Place 保留上的诉讼保留和邮箱上的邮箱。
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a> (可选) 步骤4：运行托管文件夹助理以应用新的保留设置

将新的 Exchange 保留策略应用于保留邮箱后，在 Exchange Online 中可能需要长达7天的时间，托管文件夹助理才能使用新保留策略中的设置处理这些邮箱。 您可以使用 **start-managedfolderassistant** cmdlet 手动触发助理以处理应用新的保留策略的邮箱，而不是等待托管文件夹助理运行。 
  
运行以下命令以启动 Pilar Pinilla 的邮箱的托管文件夹助理。
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

运行以下命令以启动处于保留状态的所有邮箱的托管文件夹助理。
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>更多信息

- 启用用户的存档邮箱后，请考虑告诉用户其邮箱中的其他项目 (不只是 "可恢复的项目" 文件夹中的项目) 可能会被移至存档邮箱。 这是因为分配给 Exchange Online 邮箱的默认 MRM 策略包含一个名为默认值2年的保留 (标记。移动到存档) 在将项目传递到邮箱或由用户创建的日期后两年将项目移动到存档邮箱。 有关详细信息，请参阅 [Exchange Online 中的默认保留策略 ](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- 启用用户的存档邮箱后，您可能还会告诉用户他们可以在其存档邮箱中的 "可恢复的项目" 文件夹中恢复已删除的邮件。 在 Outlook 中，可以通过选择存档邮箱中的 " **已删除邮件** " 文件夹，然后在 " **开始** " 选项卡上单击 " **从服务器恢复已删除邮件** " 来执行此操作。有关恢复已删除项目的详细信息，请参阅 [在 Outlook For Windows 中恢复已删除的项目](https://go.microsoft.com/fwlink/p/?LinkId=624829)。 
