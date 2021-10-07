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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 启用存档邮箱并启用自动扩展存档，以增加邮箱中邮箱的"可恢复的项目"文件夹Microsoft 365。
ms.openlocfilehash: eb729ca48ea4cca1af009e43ef0d3c420b567273
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200493"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>为置于保留状态的邮箱增加可恢复项目的配额

自动Exchange新邮箱的默认保留策略（名为"*默认 MR Exchange Online M* 策略）"包含名为"可恢复的项目 14 天移动到存档"的保留标记。 此保留标记在项目的 14 天保留期到期后，将项目从用户主邮箱中的"可恢复的项目"文件夹移动到用户存档邮箱中的"可恢复的项目"文件夹。 为此，必须启用用户的存档邮箱。 如果未启用存档邮箱，则不执行任何操作，这意味着保留邮箱的"可恢复的项目"文件夹中的项目在 14 天保留期到期后不会移动到存档邮箱。 由于不会从保留邮箱中删除任何内容，因此可能会超出"可恢复的项目"文件夹的存储配额，尤其是在用户的存档邮箱未启用的情况下。

为了帮助降低超出此限制的可能性，当邮箱处于保留状态时，"可恢复的项目"文件夹的存储配额会自动从 30 GB 增加到 100 GB Exchange Online。 如果存档邮箱已启用，则存档邮箱中"可恢复的项目"文件夹的存储配额也将从 30 GB 增加到 100 GB。 如果启用用户存档中的自动扩展存档Exchange Online，则用户存档中"可恢复的项目"文件夹的存储配额为 1.5 TB。

 下表总结了"可恢复的项目"文件夹的存储配额。

|**"可恢复的项目"文件夹的位置**|**邮箱未置于保留状态**|**保留的邮箱**|
|:-----|:-----|:-----|
|主邮箱  <br/> |30 GB  <br/> |100 GB  <br/> |
|存档邮箱<sup>\*</sup> <br/> |1.5 TB  <br/> |1.5 TB  <br/> |
|**"可恢复的项目"文件夹的总存储配额** <br/> |1.5 TB  <br/> |1.5 TB  <br/> |

> [!NOTE]
> <sup>\*</sup>存档邮箱的初始存储配额是 100 GB（对于拥有 Exchange Online（计划 2） 许可证的用户）。 但是，当为保留邮箱启用自动扩展存档时，存档邮箱和"可恢复的项目"文件夹的存储配额将增加到 110 GB。 如有必要，将预配高达 1.5 TB 的额外存档存储空间。 有关自动扩展存档的信息，请参阅 [自动扩展存档概述](autoexpanding-archiving.md)。

当置于保留状态的邮箱的主邮箱"可恢复的项目"文件夹的存储配额接近其限额时，可以执行以下操作：

- **启用存档邮箱并启用自动扩展存档。** 只需启用存档邮箱，然后在存档邮箱中打开自动扩展存档功能，就可以为"可恢复的项目"文件夹启用Exchange Online。 这导致主邮箱中的"可恢复的项目"文件夹为 110 GB，用户存档中的"可恢复的项目"文件夹的存储容量高达 1.5 TB。 请参阅如何[：启用存档邮箱和](enable-archive-mailboxes.md)[启用自动扩展存档](enable-autoexpanding-archiving.md)。

    > [!NOTE]
    > 为即将超过"可恢复的项目"文件夹存储配额的邮箱启用存档后，您可能需要运行托管文件夹助理以手动触发助理处理邮箱，以便过期项目移动到存档邮箱中的"可恢复的项目"文件夹。 有关[说明，请参阅步骤 4。](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 注意，用户邮箱中的其他项目可能会移至新的存档邮箱。 请考虑告知用户启用存档邮箱后可能会发生这种情况。

- **为保留Exchange邮箱创建自定义保留策略。** 除了为诉讼保留或 In-Place 保留的邮箱启用存档邮箱和自动扩展存档外，您可能还需要为保留邮箱创建自定义 Exchange 保留策略。 这使你可以将保留策略应用于保留的邮箱，该策略不同于应用于未置于保留状态邮箱的默认 MRM 策略，并允许您应用为保留邮箱设计的保留标记。 其中包括为"可恢复的项目"文件夹创建新的保留标记。

本主题的其余部分介绍了为保留邮箱创建自定义保留Exchange策略的分步过程。

[步骤 1：为"可恢复的项目"文件夹创建自定义保留标记](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[步骤 2：为保留Exchange创建新的保留策略](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[步骤 3：将新的Exchange保留策略应用于保留的邮箱](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[ (可选) 步骤 4：运行托管文件夹助理以应用新的保留设置](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)

## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>步骤 1：为"可恢复的项目"文件夹创建自定义保留标记

第一步是为"可恢复的项目"文件夹 (保留策略标记或 RPT) 保留标记。 如前所述，此 RPT 将项目从用户主邮箱中的"可恢复的项目"文件夹移动到用户存档邮箱中的"可恢复的项目"文件夹。 您必须使用 PowerShell 为"可恢复的项目"文件夹创建 RPT。 不能使用 Exchange 管理中心 (EAC)。

1. [使用远程 PowerShell 连接到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)

2. 运行以下命令，为"可恢复的项目"文件夹创建新的 RPT：

    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    例如，以下命令为名为"保留邮箱的可恢复项目 30 天"的"可恢复的项目"文件夹创建一个 RPT，保留期为 30 天。 这意味着，在项目在"可恢复的项目"文件夹中保留 30 天后，该项目将移动到用户存档邮箱中的"可恢复的项目"文件夹。

    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > 我们建议由  _AgeLimitForRetention_ 参数) 为"可恢复的项目"RPT 定义的保留期 (与将应用 RPT 的邮箱的已删除项目保留期相同。 这允许用户在将已删除项目移至存档邮箱之前，在已删除邮件的整个保留期内恢复这些项目。 在上一示例中，根据邮箱的已删除项目保留期也为 30 天的假设，将保留期设置为 30 天。 默认情况下Exchange Online邮箱将已删除项目保留 14 天。 但你可以将此设置更改为最多 30 天。 有关详细信息，请参阅 Change [the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go)。

## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a>步骤 2：为保留Exchange创建新的保留策略

下一步是创建新的保留策略，并添加保留标记，包括在步骤 1 中创建的"可恢复的项目 RPT"。 此新策略将应用于下一步中保留的邮箱。

在创建新的保留策略之前，确定要添加的其他保留标记。 有关添加到默认 MRM 策略的保留标记的列表，以及有关创建新的保留标记的信息，请参阅以下内容：

- [Exchange Online 中的默认保留策略](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- [支持保留策略标记的默认文件夹](/exchange/security-and-compliance/messaging-records-management/default-folders)

- 创建保留策略主题中的"创建 [保留标记"](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) 部分。

可以使用 EAC 或 Exchange Online PowerShell 创建保留策略。

### <a name="use-the-eac-to-create-a-retention-policy"></a>使用 EAC 创建保留策略

1. 在 EAC 中，转到" **合规性管理**""保留 \> **策略**"，然后单击" **添加添加** ![ 图标 ](../media/ITPro-EAC-AddIcon.gif) "。

2. 在" **新建保留策略"** 页上的" **名称"** 下，键入描述保留策略用途的名称;例如， **保留邮箱的 MRM 策略**。

3. 在" **保留标记"下**，单击 **"添加** ![ 添加图标 ](../media/ITPro-EAC-AddIcon.gif) "。

4. 在保留标记列表中，选择在步骤 1 中创建的"可恢复的项目 RPT"，然后单击"添加 **"。**

    ![选择自定义"可恢复的项目"保留标记。](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)

5. 选择要添加到保留策略的其他保留标记。 例如，您可能需要添加默认 MRM 策略中包含的相同标记。

6. 添加完保留标记后，单击"确定 **"。**

7. 单击 **"保存** "创建新的保留策略。

    请注意，链接到保留策略的保留标记将显示在详细信息窗格中。

    ![链接到保留策略的保留标记显示在详细信息窗格中。](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)

### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>使用 Exchange Online PowerShell 创建保留策略

运行以下命令，为保留邮箱创建新的保留策略。

```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

例如，以下命令将创建上图中显示的保留策略和链接的保留标记。

```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a>步骤 3：将新的Exchange保留策略应用于保留的邮箱

最后一步是将步骤 2 中创建的新保留策略应用于组织中保留的邮箱。 可以使用 EAC 或 Exchange Online PowerShell 将保留策略应用于单个邮箱或多个邮箱。

### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>使用 EAC 应用新的保留策略

1. 转到 **"收件人**  >  **""邮箱"。**

2. 在列表视图中，选择要应用保留策略的邮箱，然后单击"编辑 **编辑** ![ "图标 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。

3. 在"**用户邮箱"页上**，单击"**邮箱功能"。**

4. 在 **"保留策略**"下，选择在步骤 2 中创建的保留策略，然后单击"保存 **"。**

您还可以使用 EAC 将保留策略应用于多个邮箱。

1. 转到 **"收件人**  >  **""邮箱"。**

2. 在此列表视图中，使用 Shift 或 Ctrl 键选择多个邮箱。

3. 在详细信息窗格中，单击“更多选项”。

4. 在“保留策略”下，单击“更新”。

5. 在"**批量分配保留策略"** 页上，选择在步骤 2 中创建的保留策略，然后单击"保存 **"。**

### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>使用 Exchange Online PowerShell 应用新的保留策略

可以使用 PowerShell Exchange Online单个邮箱应用新的保留策略。 但 PowerShell 的真正功能是，您可以使用它快速识别组织中置于诉讼保留或 In-Place 保留状态的所有邮箱，然后在单个命令中将新的保留策略应用于所有保留邮箱。 下面是使用 PowerShell 将保留Exchange应用于一个或多个邮箱的一些示例。 所有示例都应用在步骤 2 中创建的保留策略。

本示例将新的保留策略应用于 Pilar Pinilla 的邮箱。

```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

本示例将新的保留策略应用于组织中置于诉讼保留状态的所有邮箱。

```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

本示例将新的保留策略应用于组织中所有置于保留In-Place邮箱。

```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

您可以使用 **Get-Mailbox** cmdlet 验证是否应用了新的保留策略。

下面是一些示例，用于验证之前示例中的命令是否将"保留邮箱的 MRM 策略"保留策略应用于诉讼保留的邮箱和置于保留In-Place邮箱。

```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a> (可选) 步骤 4：运行托管文件夹助理以应用新的保留设置

将新的 Exchange 保留策略应用于保留的邮箱后，托管文件夹助理可能需要 Exchange Online 7 天的时间才能使用新保留策略中的设置处理这些邮箱。 无需等待托管文件夹助理运行，您可以使用 **Start-ManagedFolderAssistant** cmdlet 手动触发助理，以处理应用了新保留策略的邮箱。

运行以下命令以启动 Pilar Pinilla 邮箱的托管文件夹助理。

```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

运行以下命令以启动所有保留邮箱的托管文件夹助理。

```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>更多信息

- 启用用户的存档邮箱后，请考虑告知用户其邮箱中的其他项目 ("可恢复的项目"文件夹中的项目) 可能会移动到存档邮箱。 这是因为分配给 Exchange Online 邮箱的默认 MRM 策略包含名为"默认 2 年"的保留标记 (移动到存档) ，该标记在邮件传递到邮箱或由用户创建项目两年后将项目移动到存档邮箱。 有关详细信息，请参阅默认[保留策略Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- 启用用户的存档邮箱后，您还可以告诉用户他们可以恢复其存档邮箱中"可恢复的项目"文件夹中的已删除项目。 他们可以通过选择存档邮箱Outlook"已删除邮件"文件夹，然后单击"开始"选项卡上的"从服务器恢复已删除邮件"，来在邮件 **中执行这** 一操作。有关恢复已删除项目的信息，请参阅 Recover [deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829)。
