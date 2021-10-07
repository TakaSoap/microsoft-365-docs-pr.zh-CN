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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: 默认情况下，邮箱审核日志记录在邮箱Microsoft 365 (也称为默认邮箱审核或默认启用邮箱审核) 。 这意味着邮箱所有者、代理人和管理员执行的某些操作会自动记录在邮箱 审核日志 中，您可以在其中搜索对邮箱执行的活动。
ms.openlocfilehash: 4487defd4c971b5decda3442739730adcafac453
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207303"
---
# <a name="manage-mailbox-auditing"></a>管理邮箱审核

从 2019 年 1 月开始，Microsoft 将默认启用所有组织的邮箱审核日志记录。 这意味着自动记录由邮箱所有者、代理人和管理员执行的某些操作，当您在邮箱邮箱中搜索相应的邮箱审核记录时，这些记录审核日志。 默认情况下，在启用邮箱审核之前，您必须为组织的每个用户邮箱手动启用它。

以下是默认情况下启用邮箱审核的一些好处：

- 创建新邮箱时将自动启用审核。 无需为新用户手动启用它。
- 无需管理审核的邮箱操作。 默认情况下，会针对管理员、代理和所有者管理员 (类型的预定义邮箱操作) 。
- 当 Microsoft 发布新的邮箱操作时，该操作可能会自动添加到默认审核的邮箱操作列表中 (用户拥有相应的许可证) 。 这意味着无需监视在邮箱上添加新操作。
- 由于要审核组织中所有邮箱的相同操作，因此 (组织中具有一致的邮箱审核) 。

> [!NOTE]
>
> - 默认情况下，关于发布邮箱审核的重要一点要记住：无需执行任何操作来管理邮箱审核。 但是，若要了解更多信息，请根据默认设置自定义邮箱审核，或完全关闭它，本文将帮助你。
> - 默认情况下，仅 E5 用户的邮箱审核事件可用于 审核日志 搜索Microsoft 365 合规中心或通过 Office 365 管理活动 API。 有关详细信息，请参阅本文 [中的](#more-information) 详细信息部分。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>验证是否已默认启用邮箱审核。

若要验证默认情况下是否为组织启用邮箱审核，请运行[PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中的Exchange Online命令：

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

值 **False** 表示默认情况下为组织启用邮箱审核。 默认情况下，此启用的组织值会覆盖特定邮箱上的邮箱审核设置。 例如，如果对邮箱禁用邮箱审核 (则邮箱) 的 *AuditEnabled* 属性为 **False，** 则仍将审核邮箱的默认邮箱操作，因为默认情况下会为组织启用邮箱审核。

若要对特定邮箱禁用邮箱审核，请为邮箱所有者和已委派邮箱访问权限的其他用户配置邮箱审核绕过。 有关详细信息，请参阅本文中的 [绕过邮箱审核](#bypass-mailbox-audit-logging) 日志记录部分。

> [!NOTE]
> 当组织默认启用邮箱审核时，受影响邮箱的 *AuditEnabled* 属性不会从 **False** 更改为 **True**。 换句话说，默认情况下启用的邮箱审核将忽略邮箱上的 *AuditEnabled* 属性。

## <a name="supported-mailbox-types"></a>支持的邮箱类型

下表显示了默认情况下邮箱审核当前支持的邮箱类型：

<br>

****

|邮箱类型|支持|
|---|:---:|
|用户邮箱|![复选标记。](../media/checkmark.png)|
|共享邮箱|![复选标记。](../media/checkmark.png)|
|Microsoft 365组邮箱|![复选标记。](../media/checkmark.png)|
|资源邮箱||
|公用文件夹邮箱||
|

## <a name="logon-types-and-mailbox-actions"></a>登录类型和邮箱操作

登录类型对对邮箱执行审核操作的用户进行分类。 以下列表介绍了邮箱审核日志记录中使用的登录类型：

- **所有者**：邮箱 (与邮箱邮箱关联的帐户) 。
- **委派**：
  - 已分配有其他邮箱的 SendAs、SendOnBehalf 或 FullAccess 权限的用户。
  - 已分配有用户邮箱的 FullAccess 权限的管理员。
- **管理员**：
  - 使用下列 Microsoft 电子数据展示工具之一搜索邮箱：
    - 合规性中心的内容搜索。
    - 合规性中心Advanced eDiscovery电子数据展示或电子数据展示。
    - In-Place电子数据展示Exchange Online。
  - 通过使用 MAPI 编辑器访问Microsoft Exchange Server邮箱。

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>用户邮箱和共享邮箱的邮箱操作

下表描述了用户邮箱和共享邮箱的邮箱审核日志记录中可用的邮箱操作。

- 复选标记 (![复选标记。](../media/checkmark.png)) 指示可以针对登录类型记录邮箱操作， (并非所有操作都可用于所有登录类型) 。
- 在选中标记 () 默认情况下会记录登录类型的邮箱操作后，使用星号 <sup>\*</sup> 。
- 请记住，对邮箱具有完全访问权限的管理员将被视为代理。

<br>

****

|邮箱操作|说明|管理员|委派用户|所有者|
|---|---|:---:|:---:|:---:|
|**AddFolderPermissions**|尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且未单独审核。 换句话说，请勿使用此值。||||
|**ApplyRecord**|项目标记为记录。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|
|**复制**|已将某个邮件复制到另一个文件夹。|![复选标记。](../media/checkmark.png)|||
|**Create**|在邮箱邮箱的日历、联系人、便笺或任务文件夹中创建了 (例如，会创建一个新的会议) 。 不会审核邮件的创建、发送或接收。 也不会审核邮箱文件夹的创建。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)|
|**FolderBind**|已访问某个邮箱文件夹。 管理员或代理人打开邮箱时也会记录此操作。 <br/><br/> **注意**：合并由代理执行的文件夹绑定操作审核记录。 在 24 小时内为单个文件夹访问生成一个审核记录。|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)||
|**HardDelete**|已将某个邮件从"已恢复邮件"文件夹中清除。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|用户登录到其邮箱。|||![复选标记](../media/checkmark.png)|
|**MailItemsAccessed**|**注意**：此值仅适用于 E5 或 E5 合规性附加订阅用户。 有关详细信息，请参阅在 Microsoft 365[中设置高级Microsoft 365。](set-up-advanced-audit.md) <p> 邮件数据由邮件协议和客户端访问。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**MessageBind**|**注意**：此值仅适用于没有 E5 或 E5 (E5 合规性加载项订阅的 E3 用户) 。 <p> 邮件在预览窗格中查看或由管理员打开。|![复选标记](../media/checkmark.png)|||
|**ModifyFolderPermissions**|尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且未单独审核。 换句话说，请勿使用此值。||||
|**移动**|已将某个邮件移至另一个文件夹。|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|**MoveToDeletedItems**|已删除邮件，并已将其移动到“已删除邮件”文件夹。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|标记为记录的项目被软删除， ("可恢复的项目"文件夹) 。 标记为记录的项目无法永久删除， ("可恢复的项目"文件夹中) 。|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|**RemoveFolderPermissions**|尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且未单独审核。 换句话说，请勿使用此值。||||
|**SearchQueryInitiated**|**注意**：此值仅适用于 E5 或 E5 合规性附加订阅用户。 有关详细信息，请参阅在 Microsoft 365[中设置高级Microsoft 365。](set-up-advanced-audit.md) <p> 用户使用 Outlook (Windows、Mac、iOS、Android 或 Outlook 网页版) 或邮件应用程序Windows 10搜索邮箱中的项目。|||![复选标记](../media/checkmark.png)|
|**Send**|**注意**：此值仅适用于 E5 或 E5 合规性附加订阅用户。 有关详细信息，请参阅在 Microsoft 365[中设置高级Microsoft 365。](set-up-advanced-audit.md) <p> 用户发送电子邮件、答复电子邮件或转发电子邮件。|![复选标记。](../media/checkmark.png)<sup>\*</sup>||![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|已使用“发送方式”权限发送邮件。 这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|已使用“代表发送”权限发送邮件。 这表示另一个用户代表邮箱所有者发送了邮件。 邮件将向收件人说明发送此邮件时使用的身份及实际发送者。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|已永久删除或已从“已删除邮件”文件夹中删除邮件。 软删除的项目将移动到"可恢复的项目"文件夹。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**更新**|已更改邮件或邮件的任何属性。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|日历委派已分配给邮箱。 日历代理为同一组织内的其他人授予管理邮箱所有者日历的权限。|![复选标记。](../media/checkmark.png)<sup>\*</sup>||![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|另一个保留标签应用于邮件 (一个项目只能分配有一个保留标签) 。|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|**UpdateFolderPermissions**|文件夹权限已更改。 文件夹权限用于控制组织中的哪些用户可以访问邮箱中的文件夹以及位于这些文件夹中的邮件。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|已添加、删除或已更改收件箱规则。 收件箱规则用于根据指定条件处理用户收件箱中的邮件，并满足规则条件时采取措施，例如将邮件移动到指定文件夹或删除邮件。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|

> [!IMPORTANT]
> 如果在组织中默认启用邮箱审核之前，自定义了要审核的任何登录类型的邮箱操作，则自定义设置将保留在邮箱上，并且不会覆盖默认邮箱操作，如本节中所述。 若要将审核邮箱操作还原为 (您随时都可以) ，请参阅本文稍后的还原默认邮箱操作部分。 [](#restore-the-default-mailbox-actions)

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>组邮箱Microsoft 365操作

默认情况下启用的邮箱审核将邮箱审核日志记录引入 Microsoft 365 组邮箱，但无法自定义要记录的内容 (无法添加或删除为任何登录类型) 记录的邮箱操作。

下表介绍了默认情况下在每个登录类型的组邮箱Microsoft 365记录的邮箱操作。

请记住，对组邮箱具有完全访问权限Microsoft 365管理员将被视为代理。

<br>

****

|邮箱操作|说明|管理员|委派用户|所有者|
|---|---|:---:|:---:|:---:|
|**Create**|创建日历项目。 不会审核邮件的创建、发送或接收。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|已将某个邮件从"已恢复邮件"文件夹中清除。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|已删除邮件，并已将其移动到“已删除邮件”文件夹。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|已使用“发送方式”权限发送邮件。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|已使用“代表发送”权限发送邮件。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|已永久删除或已从“已删除邮件”文件夹中删除邮件。 软删除的项目将移动到"可恢复的项目"文件夹。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**更新**|已更改邮件或邮件的任何属性。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>验证是否针对每种登录类型记录默认邮箱操作

默认情况下启用的邮箱审核会将新的 *DefaultAuditSet* 属性添加到所有邮箱。 此属性的值指示是否正在审核由 Microsoft (管理) 操作。

若要在用户邮箱或共享邮箱上显示值，请将 替换为邮箱的名称、别名、电子邮件地址或用户主体名称 (用户名) ，在 Exchange Online PowerShell 中运行 \<MailboxIdentity\> 以下命令：

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

若要在组邮箱Microsoft 365值，请将 替换为共享邮箱的名称、别名或电子邮件地址，然后使用 PowerShell 运行以下 \<MailboxIdentity\> Exchange Online命令：

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

值 `Admin, Delegate, Owner` 指示：

- 将审核所有三种登录类型的默认邮箱操作。 这是你将在组邮箱上看到的唯Microsoft 365值。
- 管理员 *未更改* 用户邮箱或共享邮箱上任何登录类型的已审核邮箱操作。 请注意，这是在组织中最初启用邮箱审核之后的默认状态。

如果管理员曾经使用 **Set-Mailbox** cmdlet) 上的 AuditAdmin、AuditDelegate或 *AuditOwner* 参数更改了针对登录类型 (审核的邮箱操作，属性值将有所不同。

例如，用户邮箱或共享邮箱的 `Owner` *DefaultAuditSet* 属性的值指示：

- 正在审核邮箱所有者的默认邮箱操作。
- 和 登录类型的审核邮箱 `Delegate` 操作已更改 `Admin` 为默认操作。

*DefaultAuditSet* 属性的空值表示用户邮箱或共享邮箱上所有三种登录类型的邮箱操作已更改。

有关详细信息，请参阅本文中的更改或还原默认 [记录的](#change-or-restore-mailbox-actions-logged-by-default) 邮箱操作部分。

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>显示正在登录的邮箱的邮箱操作

若要查看当前正在登录的用户邮箱或共享邮箱的邮箱操作，请将 替换为邮箱的名称、别名、电子邮件地址或用户主体名称 \<MailboxIdentity\> (用户名) ，在 Exchange Online PowerShell 中运行以下一个或多个命令。

> [!NOTE]
> 尽管可以将开关添加到组邮箱的以下 `-GroupMailbox` **Get-Mailbox** Microsoft 365，但不要认为返回的值。 为组邮箱审核的默认和静态邮箱Microsoft 365组邮箱的邮箱操作一节Microsoft 365[组](#mailbox-actions-for-microsoft-365-group-mailboxes)邮箱的邮箱操作部分。

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

如前所述，默认情况下启用邮箱审核的主要好处之一是：无需管理审核的邮箱操作。 Microsoft 会为用户完成此操作，我们将在发布新邮箱操作时自动添加要默认审核的新邮箱操作。

但是，您的组织可能需要审核用户邮箱和共享邮箱的不同邮箱操作集。 本节中的过程将向您展示如何更改针对每种登录类型审核的邮箱操作，以及如何还原到 Microsoft 管理的默认操作。

> [!IMPORTANT]
> 如果您使用以下过程自定义已登录用户邮箱或共享邮箱的邮箱操作，Microsoft 发布的任何新的默认邮箱操作将不会在这些邮箱上自动审核。 需要手动将任何新邮箱操作添加到自定义操作列表。

### <a name="change-the-mailbox-actions-to-audit"></a>将邮箱操作更改为审核

可以使用 **Set-Mailbox** cmdlet 上的 *AuditAdmin、AuditDelegate* 或 *AuditOwner* 参数更改已审核的用户邮箱和共享邮箱的邮箱操作 (Microsoft 365 组邮箱的审核操作无法自定义) 。 

可以使用两种不同的方法来指定邮箱操作：

- *使用此* (替换) 覆盖现有邮箱操作的内容 `action1,action2,...actionN` ：。
- *使用此语法* 添加或删除邮箱操作，而不影响其他现有 `@{Add="action1","action2",..."actionN"}` 值：或 `@{Remove="action1","action2",..."actionN"}` 。

此示例通过用 SoftDelete 和 HardDelete 覆盖默认操作来更改名为"Gabriela Laureano"的邮箱的管理邮箱操作。

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

本示例将 MailboxLogin 所有者操作添加到邮箱 laura@contoso.onmicrosoft.com。

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

本示例删除团队讨论邮箱的 MoveToDeletedItems 委派操作。

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

无论使用哪种方法，自定义用户邮箱或共享邮箱上的已审核邮箱操作都会产生以下结果：

- 对于自定义的登录类型，Microsoft 不再管理审核的邮箱操作。
- 您自定义的登录类型不再如前面所述显示在邮箱的 *DefaultAuditSet* [属性值中](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。

### <a name="restore-the-default-mailbox-actions"></a>还原默认邮箱操作

> [!NOTE]
> 以下过程不适用于组Microsoft 365组 (仅限于此处所述的[默认) 。](#mailbox-actions-for-microsoft-365-group-mailboxes)

如果自定义了在用户邮箱或共享邮箱上审核的邮箱操作，可以使用以下语法还原一种或所有登录类型的默认邮箱操作：

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

可以指定用逗号分隔的多个 *DefaultAuditSet* 值

本示例还原邮箱邮箱上所有登录类型的默认审核 mark@contoso.onmicrosoft.com。

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

本示例还原邮箱 chris@contoso.onmicrosoft.com 上管理员登录类型的默认审核邮箱操作，但保留"委派"和"所有者"登录类型的自定义审核邮箱操作。

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

还原登录类型的默认审核邮箱操作将具有以下结果：

- 邮箱操作的当前列表将替换为登录类型的默认邮箱操作。
- Microsoft 发布的任何新邮箱操作都会自动添加到登录类型的审核操作列表中。
- 更新 *邮箱的 DefaultAuditSet* 属性值以包括还原的登录类型。

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>默认情况下，为组织关闭邮箱审核

默认情况下，可以在 PowerShell 中运行以下命令，为整个组织关闭Exchange Online审核：

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

默认情况下关闭邮箱审核具有以下结果：

- 为组织禁用邮箱审核。
- 从默认情况下禁用邮箱审核起，不会审核任何邮箱操作，即使对邮箱启用了审核 (邮箱的 *AuditEnabled* 属性为 **True**) 。
- 未针对新邮箱启用邮箱审核，并且将忽略新邮箱或现有邮箱的 *AuditEnabled* 属性设置为 **True。**
- 使用 **Set-MailboxAuditBypassAssociation** cmdlet (配置的任何邮箱审核绕过关联设置) 忽略。
- 现有邮箱审核记录将一直保留到审核日志期限到期为止。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>默认情况下打开邮箱审核

若要为组织重新启用邮箱审核，请运行 PowerShell 中的Exchange Online命令：

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>绕过邮箱审核日志记录

目前，组织内已默认启用邮箱审核时，不能为特定邮箱禁用邮箱审核。 例如，将 *AuditEnabled* 邮箱属性设置为 **False** 将被忽略。

但是，您仍可以在 Exchange Online PowerShell 中使用 **Set-MailboxAuditBypassAssociation** cmdlet来防止记录指定用户的任何邮箱操作以及所有邮箱操作，而不管这些操作在何处发生。 例如：

- 不会记录绕过的用户执行的邮箱所有者操作。
- 由被绕过的用户对其他用户邮箱执行的委派操作 (包括共享邮箱) 记录。
- 不会记录绕过用户执行的管理员操作。

若要绕过特定用户的邮箱审核日志记录，请将 替换为用户的名称、电子邮件地址、别名或用户主体名称 (用户名) 并运行 \<MailboxIdentity\> 以下命令：

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

若要验证是否已绕过对指定用户的审核，请运行以下命令：

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

值 **True** 表示将绕过用户的邮箱审核日志记录。

## <a name="more-information"></a>更多信息

- 尽管默认情况下会为所有组织启用邮箱审核日志记录，但只有具有 E5 许可证的用户才能在 审核日志 搜索中返回 [Microsoft 365 合规中心](search-the-audit-log-in-security-and-compliance.md)中的邮箱 审核日志 事件，或者默认情况下通过 [Office 365 管理活动 API](/office/office-365-management-api/office-365-management-activity-api-reference)返回邮箱 审核日志 **事件**。

  若要检索审核日志 E5 许可证的用户的邮箱邮箱条目，您可以：

  - 手动启用单个邮箱的邮箱审核 (运行命令 `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` ，) 。 完成此操作后，可以在 审核日志中或通过 Microsoft 365 合规中心 管理活动 API Office 365搜索。

    > [!NOTE]
    > 如果邮箱审核在邮箱上显示为已启用，但搜索未返回任何结果，请更改 _AuditEnabled_ 参数的值，然后再更改 `$false` 回 `$true` 。

  - 在 PowerShell 中使用以下 cmdlet Exchange Online cmdlet：
    - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) 搜索特定审核日志邮箱邮箱。
    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) 可搜索特定审核日志邮箱邮箱，并通过电子邮件将结果发送给指定收件人。

  - 在Exchange EAC (管理) Exchange Online执行以下操作：
    - [导出邮箱审核日志](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)
    - [运行非所有者邮箱访问报告](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- 默认情况下，邮箱审核日志记录在被删除前保留 90 天。 您可以使用 PowerShell 中 **Set-Mailbox** cmdlet 审核日志 *AuditLogAgeLimit* 参数更改记录Exchange Online期限。 但是，如果增加此值，则不允许搜索超过 90 天的 审核日志。

  如果增加期限，则需要使用 Exchange Online PowerShell 中的[Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) cmdlet 在用户的邮箱 审核日志 中搜索超过 90 天的记录。

- 如果在默认情况下为组织启用邮箱审核之前更改了邮箱的 *AuditLogAgeLimit* 属性，则邮箱的现有 审核日志 期限不会更改。 换句话说，默认情况下启用的邮箱审核不会影响邮箱审核记录的当前期限。

- 若要更改组邮箱上的 *AuditLogAgeLimit* Microsoft 365，您需要在 `-GroupMailbox` **Set-Mailbox** 命令中包括开关。

- 邮箱审核日志记录存储在名为"审核 (文件夹的子文件夹中) 每个用户邮箱的"可恢复的项目"文件夹中。 对于邮箱审核记录和"可恢复的项目"文件夹，请牢记以下事项：

  - 邮箱审核记录计数针对"可恢复的项目"文件夹的存储配额（默认为 30 GB） (警告配额为 20 GB) 。 存储配额自动增加到 100 GB， (达到 90 GB 警告配额) 时：
    - 将邮箱置于保留状态。
    - 邮箱将分配给合规性中心中的保留策略。

  - 邮箱审核记录还计入 ["可恢复的项目"文件夹的文件夹限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。 审核记录中最多可以 (300 万) 审核记录可存储在"审核"子文件夹。

    > [!NOTE]
    > 默认情况下启用的邮箱审核不太可能影响"可恢复的项目"文件夹的存储配额或文件夹限制。

    - 可以在 PowerShell 中Exchange Online以下命令，以显示"可恢复的项目"文件夹中"审核"子文件夹中的项目大小和数量：

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - You can't directly access an 审核日志 record in the Recoverable Items folder;而是使用 **Search-MailboxAuditLog** cmdlet 或搜索审核日志查找和查看邮箱审核记录。

- 如果邮箱处于保留状态或分配到合规性中心中的保留策略，审核日志 记录在默认情况下仍保留由邮箱 *的 AuditLogAgeLimit* 属性定义的持续时间 (90 天) 。 若要将审核日志保留的邮箱保留更长时间，需要增加邮箱的 *AuditLogAgeLimit* 值。

- 在多地理位置环境中，不支持跨地理位置邮箱审核。 例如，如果为某用户分配了访问其他地理位置的共享邮箱的权限，此用户执行的邮箱操作不会记录在共享邮箱的邮箱审核日志中。
