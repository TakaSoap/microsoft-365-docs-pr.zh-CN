---
title: 管理邮箱审核
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: 默认情况下，Microsoft 365 中启用邮箱审核日志记录 (默认情况下也称为默认邮箱审核或邮箱审核) 。 这意味着邮箱所有者、代理和管理员执行的某些操作会自动记录在邮箱审核日志，您可以在其中搜索对邮箱执行的活动。
ms.openlocfilehash: 8b97e18a6c5d24bd74bb04eecc91999c4aa61bb9
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175581"
---
# <a name="manage-mailbox-auditing"></a>管理邮箱审核

从 2019 年 1 月开始，Microsoft 将默认启用所有组织的邮箱审核日志记录。 这意味着自动记录由邮箱所有者、代理和管理员执行的某些操作，当您在邮箱邮箱中搜索相应的邮箱审核记录时，这些记录审核日志。 默认情况下，在启用邮箱审核之前，您必须为组织的每个用户邮箱手动启用它。

默认情况下，邮箱审核的一些好处是：

- 创建新邮箱时将自动启用审核。 无需为新用户手动启用它。

- 无需管理审核的邮箱操作。 默认情况下，会针对管理员、代理和所有者帐户的每个登录类型审核 (一组预定义的邮箱) 。

- 当 Microsoft 发布新的邮箱操作时，该操作可能会自动添加到默认审核的邮箱操作列表中 (用户拥有相应的许可证) 。 这意味着无需监视对邮箱添加新操作。

- 由于要审核组织中所有邮箱的相同 (，因此在组织中拥有一致的邮箱审核) 。

> [!NOTE]
>* 默认情况下，关于发布邮箱审核时，需要记住的重要一点就是：无需执行任何操作来管理邮箱审核。 但是，若要了解更多信息、从默认设置自定义邮箱审核或完全关闭邮箱审核，本主题可以帮助您。
>- 默认情况下，只有 E5 用户的邮箱审核事件在安全 审核日志 合规中心或 Office 365 管理活动 API 的 & 搜索中可用。 有关详细信息，请参阅本主题 [中的](#more-information) "详细信息"部分。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>验证邮箱审核默认是否打开

若要验证默认情况下是否为组织启用邮箱审核，请运行 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中的以下命令：

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

值 **False** 表示默认情况下为组织启用邮箱审核。 默认情况下，组织值会覆盖特定邮箱上的邮箱审核设置。 例如，如果禁用邮箱 (则邮箱) 的 *AuditEnabled* 属性为 **False，** 则仍将审核邮箱的默认邮箱操作，因为默认情况下会为组织启用邮箱审核。

若要为特定邮箱禁用邮箱审核，请为邮箱所有者和已委派邮箱访问权限的其他用户配置邮箱审核绕过。 有关详细信息，请参阅本主题中的 ["绕过邮箱审核](#bypass-mailbox-audit-logging) 日志记录"部分。

> [!NOTE]
> 当默认情况下为组织启用邮箱审核时，受影响邮箱的 *AuditEnabled* 属性不会从 **False** 更改为 **True。** 换句话说，默认情况下启用的邮箱审核将忽略邮箱上的 *AuditEnabled* 属性。

## <a name="supported-mailbox-types"></a>支持的邮箱类型

下表显示了默认情况下邮箱审核当前支持的邮箱类型：

|**邮箱类型**|**支持**|**不支持**|
|:---------|:---------:|:---------:|
|用户邮箱|![复选标记](../media/checkmark.png)||
|共享邮箱|![复选标记](../media/checkmark.png)||
|Microsoft 365 组邮箱|![复选标记](../media/checkmark.png)||
|资源邮箱||![复选标记](../media/checkmark.png)|
|公用文件夹邮箱||![复选标记](../media/checkmark.png)|

## <a name="logon-types-and-mailbox-actions"></a>登录类型和邮箱操作

登录类型对对邮箱执行审核操作的用户进行分类。 以下列表介绍了邮箱审核日志记录中使用的登录类型：

- **所有者**：邮箱 (与邮箱邮箱关联的帐户) 。

- **委派**：

  - 已分配有对另一个邮箱的 SendAs、SendOnBehalf 或 FullAccess 权限的用户。

  - 已分配有用户邮箱的 FullAccess 权限的管理员。

- **管理员**：

  - 邮箱使用下列 Microsoft 电子数据展示工具之一进行搜索：

    - 合规性中心的内容搜索。

    - 合规性中心中的电子数据展示或高级电子数据展示。

    - In-Place Exchange Online 中的电子数据展示。

  - 通过使用 MAPI 编辑器Microsoft Exchange Server邮箱。

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>用户邮箱和共享邮箱的邮箱操作

下表描述了在用户邮箱和共享邮箱的邮箱审核日志记录中可用的邮箱操作。

- 复选标记 ( ![复选标记](../media/checkmark.png)) 指示可以针对登录类型记录邮箱操作 (并非所有操作都可用于所有登录类型) 。

- 在选中 () ，默认情况下会记录登录类型的邮箱操作后，使用星号 <sup>\*</sup> 。

- 请记住，对邮箱具有完全访问权限的管理员被视为代理。

|**邮箱操作**|**说明**|**管理员**|**委派用户**|**所有者**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**注意**：尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且不会单独审核。 换句话说，请勿使用此值。||||
|**ApplyRecord**|项目标记为记录。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**复制**|已将某个邮件复制到另一个文件夹。|![复选标记](../media/checkmark.png)|||
|**创建**|在邮箱邮箱的"日历"、"联系人"、"便笺"或"任务"文件夹中创建了 (例如，会创建一个新的会议) 。 不会审核邮件的创建、发送或接收。 也不会审核邮箱文件夹的创建。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)|
|**默认**||![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|**FolderBind**|已访问某个邮箱文件夹。 管理员或代理打开邮箱时也会记录此操作。 <br/><br/> **注意**：合并由代理执行的文件夹绑定操作审核记录。 在 24 小时内为单个文件夹访问生成一条审核记录。|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|**HardDelete**|已将某个邮件从"已恢复邮件"文件夹中清除。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**MailItemsAccessed**|邮件协议和客户端可以访问邮件数据。 此值仅适用于 E5 或 E5 合规性附加订阅用户。 有关详细信息，请参阅"[为用户设置高级审核"。](advanced-audit.md#set-up-advanced-audit-for-users)|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|用户登录到其邮箱。 |||![复选标记](../media/checkmark.png)|
|**MessageBind**|邮件在预览窗格中查看或由管理员打开。注意：尽管此值被接受为邮箱操作，但不再记录这些操作。|![复选标记](../media/checkmark.png)|||
|**ModifyFolderPermissions**|**注意**：尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且不会单独审核。 换句话说，请勿使用此值。||||
|**移动**|已将某个邮件移至另一个文件夹。|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|**MoveToDeletedItems**|已删除邮件，并已将其移动到“已删除邮件”文件夹。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|标记为记录的项目被软删除， ("可恢复的项目"文件夹) 。 从"可恢复的项目"文件夹 (无法永久删除标记为记录) 。|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|**RemoveFolderPermissions**|**注意**：尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且不会单独审核。 换句话说，请勿使用此值。||||
|**Send**|用户发送电子邮件、答复电子邮件或转发电子邮件。 此值仅适用于 E5 或 E5 合规性附加订阅用户。 有关详细信息，请参阅"[为用户设置高级审核"。](advanced-audit.md#set-up-advanced-audit-for-users)|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|已使用“发送方式”权限发送邮件。 这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|已使用“代表发送”权限发送邮件。 这表示另一个用户代表邮箱所有者发送了邮件。 邮件将向收件人说明发送此邮件时使用的身份及实际发送者。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|已永久删除或已从“已删除邮件”文件夹中删除邮件。 软删除的项目将移动到"可恢复的项目"文件夹。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**更新**|已更改邮件或其属性。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|日历委派已分配给邮箱。 日历代理为同一组织内的其他人授予管理邮箱所有者日历的权限。|![复选标记](../media/checkmark.png)<sup>\*</sup>||![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|将不同的保留标签应用于邮件项目 (一个项目只能分配有一个保留标签) 。|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|**UpdateFolderPermissions**|文件夹权限已更改。 文件夹权限用于控制组织中的哪些用户可以访问邮箱中的文件夹以及位于这些文件夹中的邮件。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|已添加、删除或已更改收件箱规则。 收件箱规则用于根据指定条件处理用户收件箱中的邮件，在满足规则条件时采取措施，例如将邮件移动到指定文件夹或删除邮件。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|

> [!IMPORTANT]
> 如果在组织中默认启用邮箱审核之前自定义了要审核的任何登录类型的邮箱操作，则自定义设置将保留在邮箱上，并且不会覆盖默认邮箱操作，如本节中所述。 若要将审核邮箱操作还原到其默认值 (您随时都可以) ，请参阅本主题稍后的"还原默认邮箱操作"部分。 [](#restore-the-default-mailbox-actions)

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Microsoft 365 组邮箱的邮箱操作

默认情况下启用邮箱审核将邮箱审核日志记录引入 Microsoft 365 组邮箱，但无法自定义所记录的内容 (无法添加或删除为任何登录类型) 记录的邮箱操作。

下表介绍了每个登录类型的 Microsoft 365 组邮箱上默认记录的邮箱操作。

请记住，对 Microsoft 365 组邮箱具有完全访问权限的管理员将被视为代理。

|**邮箱操作**|**说明**|**管理员**|**委派用户**|**所有者**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**创建**|创建日历项目。 不会审核邮件的创建、发送或接收。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|已将某个邮件从"已恢复邮件"文件夹中清除。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|已删除邮件，并已将其移动到“已删除邮件”文件夹。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|已使用“发送方式”权限发送邮件。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|已使用“代表发送”权限发送邮件。 |![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|已永久删除或已从“已删除邮件”文件夹中删除邮件。 软删除的项目将移动到"可恢复的项目"文件夹。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**更新**|已更改邮件或其属性。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>验证是否正在针对每种登录类型记录默认邮箱操作

默认情况下启用的邮箱审核会向所有邮箱添加新 *的 DefaultAuditSet* 属性。 此属性的值指示是否正在审核由 Microsoft (管理的默认) 操作。

若要在用户邮箱或共享邮箱上显示值，请替换为邮箱的名称、别名、电子邮件地址或用户主体名称 (用户名) ，然后运行 Exchange Online PowerShell 中的以下 \<MailboxIdentity\> 命令：

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

若要在 Microsoft 365 组邮箱上显示值，请替换为共享邮箱的名称、别名或电子邮件地址，然后运行 Exchange Online PowerShell 中的以下 \<MailboxIdentity\> 命令：

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

值 `Admin, Delegate, Owner` 指示：

- 将审核所有三种登录类型的默认邮箱操作。 这是你将在 Microsoft 365 组邮箱上看到的唯一值。

- 管理员 *未更改* 用户邮箱或共享邮箱上任何登录类型的审核邮箱操作。 请注意，这是邮箱审核默认在组织中最初打开后的默认状态。

如果管理员曾经使用 **Set-Mailbox** cmdlet) 上的 *AuditAdmin、AuditDelegate* 或 *AuditOwner* 参数更改了审核登录类型 (的邮箱操作，属性值将有所不同。 

例如，用户 `Owner` 邮箱或共享邮箱 *的 DefaultAuditSet* 属性的值指示：

- 正在审核邮箱所有者的默认邮箱操作。

- 已根据默认操作更改了对 `Delegate` 和 `Admin` 登录类型的审核邮箱操作。

*DefaultAuditSet* 属性的空值指示用户邮箱或共享邮箱上所有三种登录类型的邮箱操作已更改。

有关详细信息，请参阅本主题中的"[](#change-or-restore-mailbox-actions-logged-by-default)更改或还原默认记录的邮箱操作"

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>显示正在登录邮箱的邮箱操作

To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.

> [!NOTE]
> 尽管您可以为 Microsoft 365 组邮箱将开关添加到以下 `-GroupMailbox` **Get-Mailbox** 命令，但不要认为返回的值。 本主题前面"Microsoft 365 组邮箱的邮箱操作"部分介绍了为 [Microsoft 365](#mailbox-actions-for-microsoft-365-group-mailboxes) 组邮箱审核的默认和静态邮箱操作。

#### <a name="owner-actions"></a>所有者操作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>委派操作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>管理员操作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>更改或还原默认情况下记录的邮箱操作

如前所述，默认情况下启用邮箱审核的主要好处之一是：无需管理审核的邮箱操作。 Microsoft 会为此进行此操作，我们将在发布后自动添加新的邮箱操作，以在默认情况下审核这些操作。

但是，您的组织可能需要审核用户邮箱和共享邮箱的不同邮箱操作集。 本节中的过程将向您展示如何更改针对每种登录类型审核的邮箱操作，以及如何还原回 Microsoft 管理的默认操作。

> [!IMPORTANT]
> 如果您使用以下过程自定义登录用户邮箱或共享邮箱的邮箱操作，Microsoft 发布的任何新的默认邮箱操作将不会在这些邮箱上自动审核。 需要手动将任何新邮箱操作添加到自定义操作列表中。

### <a name="change-the-mailbox-actions-to-audit"></a>更改要审核的邮箱操作

可以使用 **Set-Mailbox** cmdlet 上的 *AuditAdmin、AuditDelegate* 或 *AuditOwner* 参数更改为用户邮箱和共享邮箱审核的邮箱操作 (无法自定义 Microsoft 365 组邮箱的审核操作) 。 

可以使用两种不同的方法来指定邮箱操作：

- *使用此* (替换) 现有邮箱操作。 `action1,action2,...actionN`

- *使用此语法* 添加或删除邮箱操作，而不影响其他现有 `@{Add="action1","action2",..."actionN"}` 值：或 `@{Remove="action1","action2",..."actionN"}` 。

此示例通过用 SoftDelete 和 HardDelete 覆盖默认操作来更改名为"Gabriela Laureano"的邮箱的管理员邮箱操作。

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

本示例将 MailboxLogin 所有者操作添加到邮箱laura@contoso.onmicrosoft.com。

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

此示例删除工作组讨论邮箱的 MoveToDeletedItems 委派操作。

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

无论您使用哪种方法，自定义用户邮箱或共享邮箱上的已审核邮箱操作都会获得以下结果：

- 对于自定义的登录类型，Microsoft 不再管理审核的邮箱操作。

- 自定义的登录类型不再显示在邮箱的 *DefaultAuditSet* 属性值中，如 [前面所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。

### <a name="restore-the-default-mailbox-actions"></a>还原默认邮箱操作

如果自定义了在用户邮箱或共享邮箱上审核的邮箱操作，可以使用以下语法还原一种或所有登录类型的默认邮箱操作：

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

可以指定用逗号分隔的多个 *DefaultAuditSet* 值

**注意**：以下过程不适用于 Microsoft 365 组邮箱 (它们仅限于此处所述的 [默认) 。](#mailbox-actions-for-microsoft-365-group-mailboxes)

此示例还原邮箱邮箱上所有登录类型的默认审核mark@contoso.onmicrosoft.com。

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

此示例还原邮箱 chris@contoso.onmicrosoft.com 上管理员登录类型的默认审核邮箱操作，但保留委派和所有者登录类型的自定义审核邮箱操作。

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

还原登录类型的默认审核邮箱操作将具有以下结果：

- 当前邮箱操作列表将替换为登录类型的默认邮箱操作。

- Microsoft 发布的任何新邮箱操作都会自动添加到登录类型的审核操作列表中。

- 邮箱 *的 DefaultAuditSet* 属性值已更新为包含还原的登录类型。

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>默认情况下，为组织关闭邮箱审核

默认情况下，可以通过在 Exchange Online PowerShell 中运行以下命令来为整个组织关闭邮箱审核：

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

默认情况下关闭邮箱审核具有以下结果：

- 为组织禁用邮箱审核。

- 在默认情况下禁用邮箱审核时，不会审核任何邮箱操作，即使对邮箱启用了审核 (邮箱的 *AuditEnabled* 属性为 **True**) 。

- 不会为新邮箱启用邮箱审核，并且将新邮箱或现有邮箱的 *AuditEnabled* 属性设置为 **True** 将被忽略。

- 使用 **Set-MailboxAuditBypassAssociation** cmdlet (配置的任何邮箱审核旁路关联设置) 忽略。

- 现有邮箱审核记录将一直保留到审核日志期限到期。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>默认情况下打开邮箱审核

若要为组织重新启用邮箱审核，请运行 Exchange Online PowerShell 中的以下命令：

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>绕过邮箱审核日志记录

目前，当组织中默认启用邮箱审核时，无法禁用特定邮箱的邮箱审核。 例如，将 *AuditEnabled 邮箱属性* 设置为 **False** 将被忽略。

但是，您仍可以使用 Exchange Online PowerShell 中的 **Set-MailboxAuditBypassAssociation** cmdlet 阻止记录指定用户的任何和所有邮箱操作，无论操作发生的位置如何。  例如：

- 旁路用户执行的邮箱所有者操作不会记录。

- 被绕过用户在其他用户的邮箱上执行的委派操作 (包括未) 共享邮箱。

- 旁路用户执行的管理员操作不会记录。

若要绕过特定用户的邮箱审核日志记录，请替换为该用户的名称、电子邮件地址、别名或用户主体名称 (用户名) 并运行 \<MailboxIdentity\> 以下命令：

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

若要验证是否绕过指定用户的审核，请运行以下命令：

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

值为 **True** 表示已绕过用户的邮箱审核日志记录。

## <a name="more-information"></a>详细信息

- 尽管默认情况下会为所有组织启用邮箱审核日志记录，但只有拥有 E5 许可证的用户才能在安全 & 合规中心或通过 [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)管理活动 API 在 审核日志 搜索中返回邮箱 [审核日志](search-the-audit-log-in-security-and-compliance.md)**事件**。

  若要检索审核日志 E5 许可证的用户的邮箱邮箱条目，您可以：

  - 手动启用单个邮箱的邮箱审核 (运行命令 `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` ，) 。 完成此操作后，可以使用安全审核日志合规中心& Office 365 管理活动 API 进行搜索。
  
    > [!NOTE]
    > 如果邮箱审核似乎已在邮箱上启用，但您的搜索未返回任何结果，请更改 _AuditEnabled_ 参数的值，然后再更改 `$false` 回 `$true` 。
  
  - 在 Exchange Online PowerShell 中使用以下 cmdlet：

    - [Search-MailboxAuditLog，](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) 用于搜索审核日志用户的邮箱邮箱。

    - [New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxauditlogsearch) 可搜索审核日志用户的邮箱邮箱，并通过电子邮件将结果发送给指定收件人。

  - 在 Exchange Online (EAC) Exchange 管理中心执行以下操作：

    - [导出邮箱审核日志](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [运行非所有者邮箱访问报告](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- 默认情况下，邮箱审核日志记录在删除前保留 90 天。 您可以使用 Exchange Online PowerShell 中 **Set-Mailbox** cmdlet 上的 *AuditLogAgeLimit* 参数更改审核日志记录期限。 但是，如果增加此值，则不允许搜索超过 90 天的事件。审核日志。

  如果增加期限，则需要使用 Exchange Online PowerShell 中的 [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) cmdlet 在用户的邮箱 审核日志 中搜索超过 90 天的记录。

- 如果在默认情况下为组织启用邮箱审核之前更改了邮箱的 *AuditLogAgeLimit* 属性，则邮箱的现有 审核日志 期限不会更改。 换句话说，默认情况下启用的邮箱审核不会影响邮箱审核记录的当前期限。

- 若要更改 Microsoft 365 组邮箱上的 *AuditLogAgeLimit* 值，需要将开关包括在 `-GroupMailbox` **Set-Mailbox** 命令中。

- 邮箱审核日志存储在每个用户邮箱的 ("可恢复的项目"文件夹中) "审核"子文件夹中。 对于邮箱审核记录和"可恢复的项目"文件夹，请记住以下事项：

  - 邮箱审核记录计入"可恢复邮件"文件夹的存储配额，默认为 30 GB， (警告配额为 20 GB) 。 当发生以下事件时，存储配额 (90 GB 警告配额) 达到 100 GB：

    - 将邮箱置于保留状态。

    - 邮箱将分配给合规性中心中的保留策略。

  - 邮箱审核记录还计入"可恢复的项目"文件夹 [的文件夹限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。 审核记录中最多可 (300 万) 审核记录存储在"审核"子文件夹内。

    > [!NOTE]
    > 默认情况下，邮箱审核不太可能影响"可恢复的项目"文件夹的存储配额或文件夹限制。

    - 您可以在 Exchange Online PowerShell 中运行以下命令，以显示"可恢复的项目"文件夹中"审核"子文件夹中的项目大小和数量：

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - You can't directly access an 审核日志 record in the Recoverable Items folder;而是使用 **Search-MailboxAuditLog** cmdlet 或搜索审核日志查找和查看邮箱审核记录。

- 如果邮箱处于保留状态或分配给合规中心中的保留策略，审核日志 记录在默认情况下仍保留由邮箱 *的 AuditLogAgeLimit* 属性定义的持续时间 (90) 。 若要将审核日志保留的邮箱保留更长时间，需要增加邮箱 *的 AuditLogAgeLimit* 值。

- 在多地理位置环境中，不支持跨地理位置邮箱审核。 例如，如果为某用户分配了访问其他地理位置的共享邮箱的权限，此用户执行的邮箱操作不会记录在共享邮箱的邮箱审核日志中。
