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
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: 默认情况下，邮箱审核日志记录在默认情况下处于打开状态Microsoft 365 (也称为默认邮箱审核或邮箱审核) 。 这意味着邮箱所有者、委托和管理员执行的某些操作会自动记录在邮箱审核日志中，你可以在其中搜索在邮箱上执行的活动。
ms.openlocfilehash: 1f566ee46520047e1bc125e505d53911fb07c912
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64705332"
---
# <a name="manage-mailbox-auditing"></a>管理邮箱审核

从 2019 年 1 月开始，Microsoft 默认为所有组织启用邮箱审核日志记录。 这意味着邮箱所有者、委托和管理员执行的某些操作会自动记录，当您在邮箱审核日志中搜索相应的邮箱审核记录时，这些记录将可用。 默认情况下，在启用邮箱审核之前，必须为组织中的每个用户邮箱手动启用它。

默认情况下，邮箱审核的一些优点如下：

- 创建新邮箱时会自动启用审核。 无需为新用户手动启用它。
- 无需管理审核的邮箱操作。 默认情况下，将针对管理员、委托和所有者)  (每个登录类型审核预定义的邮箱操作集。
- 当 Microsoft 发布新的邮箱操作时，该操作可能会自动添加到默认审核的邮箱操作列表中， (受用户具有相应许可证) 的约束。 这意味着无需监视在邮箱上添加新操作。
- 在组织 (，你拥有一致的邮箱审核策略，因为你正在审核所有邮箱) 的相同操作。

> [!NOTE]
>
> - 默认情况下，对于邮箱审核的发布，需要记住的重要事项是：无需执行任何操作来管理邮箱审核。 但是，若要了解详细信息，请从默认设置自定义邮箱审核，或将其完全关闭，本文可帮助你。
> - 默认情况下，只有 E5 用户的邮箱审核事件在Microsoft 365 合规中心或通过Office 365管理活动 API 的审核日志搜索中可用。 有关详细信息，请参阅本文中的 ["详细信息](#more-information) "部分。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>验证是否已默认启用邮箱审核。

若要验证默认情况下是否为组织启用了邮箱审核，请在 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 中运行以下命令：

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

**False 值** 指示默认情况下为组织启用邮箱审核。 默认情况下，组织值会覆盖特定邮箱上的邮箱审核设置。 例如，如果邮箱的邮箱审核已禁用， (邮箱) 上的 *AuditEnabled* 属性为 **False** ，则仍会审核邮箱的默认邮箱操作，因为默认情况下为组织启用了邮箱审核。

若要禁用特定邮箱的邮箱审核，请为邮箱所有者和其他已委派访问邮箱的用户配置邮箱审核旁路。 有关详细信息，请参阅本文中的 ["绕过邮箱审核日志记录](#bypass-mailbox-audit-logging) "部分。

> [!NOTE]
> 当默认情况下为组织启用邮箱审核时，受影响邮箱的 *AuditEnabled* 属性不会从 **False** 更改为 **True**。 换句话说，默认情况下，邮箱审核会忽略邮箱上的 *AuditEnabled* 属性。

## <a name="supported-mailbox-types"></a>支持的邮箱类型

下表显示默认情况下邮箱审核当前支持的邮箱类型：

<br>

****

|邮箱类型|受支持|
|---|:---:|
|用户邮箱|![复选标记。](../media/checkmark.png)|
|共享邮箱|![复选标记。](../media/checkmark.png)|
|Microsoft 365组邮箱|![复选标记。](../media/checkmark.png)|
|资源邮箱||
|公用文件夹邮箱||
|

## <a name="logon-types-and-mailbox-actions"></a>登录类型和邮箱操作

登录类型对在邮箱上执行审核操作的用户进行分类。 以下列表描述了邮箱审核日志记录中使用的登录类型：

- **所有者**：邮箱所有者 (与邮箱) 关联的帐户。
- **委托**：
  - 已将 SendAs、SendOnBehalf 或 FullAccess 权限分配到另一个邮箱的用户。
  - 已将 FullAccess 权限分配给用户邮箱的管理员。
- **管理员**：
  - 使用以下 Microsoft 电子数据展示工具之一搜索邮箱：
    - 合规中心中的内容搜索。
    - 合规中心内的电子数据展示或Advanced eDiscovery。
    - Exchange Online中的In-Place电子数据展示。
  - 通过使用 Microsoft Exchange Server MAPI 编辑器访问邮箱。

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>用户邮箱和共享邮箱的邮箱操作

下表描述了用于用户邮箱和共享邮箱的邮箱审核日志记录中提供的邮箱操作。

- 复选标记 (![复选标记。](../media/checkmark.png)) 指示可以记录登录类型的邮箱操作 (并非所有操作都可用于所有登录类型) 。
- 复选标记指示默认记录登录类型的邮箱操作后，星号 ( <sup>\*</sup> ) 。
- 请记住，具有邮箱完全访问权限的管理员被视为委托。

<br>

****

|邮箱操作|说明|管理员|委派用户|所有者|
|---|---|:---:|:---:|:---:|
|**AddFolderPermissions**|虽然此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且不会单独审核。 换句话说，不要使用此值。||||
|**ApplyRecord**|项标记为记录。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|
|**复制**|已将某个邮件复制到另一个文件夹。|![复选标记。](../media/checkmark.png)|||
|**创建**|在邮箱的"日历"、"联系人"、"草稿"、"备注"或"任务"文件夹中创建了一个项目 (例如，) 创建了新的会议请求。 不会审核邮件的创建、发送或接收。 也不会审核邮箱文件夹的创建。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)|
|**FolderBind**|已访问某个邮箱文件夹。 管理员或委托打开邮箱时也会记录此操作。 <br/><br/> **注意**：合并委托执行的文件夹绑定操作的审核记录。 在 24 小时内为单个文件夹访问生成一条审核记录。|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)||
|**HardDelete**|已将某个邮件从"已恢复邮件"文件夹中清除。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|用户登录到其邮箱。|||![复选标记](../media/checkmark.png)|
|**MailItemsAccessed**|**注意**：此值仅适用于 E5 或 E5 合规性加载项订阅用户。 有关详细信息，请参阅[在 Microsoft 365 中设置高级审核](set-up-advanced-audit.md)。 <p> 邮件数据由邮件协议和客户端访问。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**MessageBind**|**注意**：此值仅适用于没有 E5 或 E5 合规性加载项订阅的 E3 用户 (用户) 。 <p> 在预览窗格中查看或由管理员打开消息。|![复选标记](../media/checkmark.png)|||
|**ModifyFolderPermissions**|虽然此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且不会单独审核。 换句话说，不要使用此值。||||
|**移动**|已将某个邮件移至另一个文件夹。|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|**MoveToDeletedItems**|已删除邮件，并已将其移动到“已删除邮件”文件夹。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|标记为记录的项被软删除 (移动到"可恢复邮件"文件夹) 。 标记为记录的项不能永久删除 (从"可恢复邮件"文件夹) 中清除。|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|**RemoveFolderPermissions**|虽然此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且不会单独审核。 换句话说，不要使用此值。||||
|**SearchQueryInitiated**|**注意**：此值仅适用于 E5 或 E5 合规性加载项订阅用户。 有关详细信息，请参阅[在 Microsoft 365 中设置高级审核](set-up-advanced-audit.md)。 <p> 用户使用Outlook (Windows、Mac、iOS、Android、Outlook na Web) 或邮件应用Windows 10在邮箱中搜索项目。|||![复选标记](../media/checkmark.png)|
|**Send**|**注意**：此值仅适用于 E5 或 E5 合规性加载项订阅用户。 有关详细信息，请参阅[在 Microsoft 365 中设置高级审核](set-up-advanced-audit.md)。 <p> 用户发送电子邮件、回复电子邮件或转发电子邮件。|![复选标记。](../media/checkmark.png)<sup>\*</sup>||![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|已使用“发送方式”权限发送邮件。 这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|已使用“代表发送”权限发送邮件。 这表示另一个用户代表邮箱所有者发送了邮件。 邮件将向收件人说明发送此邮件时使用的身份及实际发送者。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|已永久删除或已从“已删除邮件”文件夹中删除邮件。 软删除的项将移动到"可恢复的项目"文件夹。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**更新**|消息或其任何属性已更改。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|已将日历委派分配给邮箱。 日历代理为同一组织内的其他人授予管理邮箱所有者日历的权限。|![复选标记。](../media/checkmark.png)<sup>\*</sup>||![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|另一个保留标签应用于邮件项 (项目只能) 分配一个保留标签。|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|**UpdateFolderPermissions**|文件夹权限已更改。 文件夹权限用于控制组织中的哪些用户可以访问邮箱中的文件夹以及位于这些文件夹中的邮件。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|已添加、删除或更改收件箱规则。 收件箱规则用于根据指定的条件处理用户收件箱中的消息，并在满足规则条件时执行操作，例如将消息移动到指定的文件夹或删除消息。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|

> [!IMPORTANT]
> 如果在组织中默认启用邮箱审核 *之前* 自定义了用于审核任何登录类型的邮箱操作，则会在邮箱中保留自定义设置，并且不会被本部分中所述的默认邮箱操作覆盖。 若要将审核邮箱操作还原为默认值 (你可以随时) 执行，请参阅本文后面的 ["还原默认邮箱操作](#restore-the-default-mailbox-actions) "部分。

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Microsoft 365组邮箱的邮箱操作

默认情况下，邮箱审核会将邮箱审核日志记录带到Microsoft 365组邮箱，但无法自定义正在记录的内容 (无法添加或删除针对任何登录类型) 记录的邮箱操作。

下表描述了默认记录在每个登录类型的Microsoft 365组邮箱上的邮箱操作。

请记住，具有对Microsoft 365组邮箱的完全访问权限的管理员被视为委托。

<br>

****

|邮箱操作|说明|管理员|委派用户|所有者|
|---|---|:---:|:---:|:---:|
|**创建**|创建日历项。 不会审核邮件的创建、发送或接收。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|已将某个邮件从"已恢复邮件"文件夹中清除。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|已删除邮件，并已将其移动到“已删除邮件”文件夹。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|已使用“发送方式”权限发送邮件。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|已使用“代表发送”权限发送邮件。|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|已永久删除或已从“已删除邮件”文件夹中删除邮件。 软删除的项将移动到"可恢复的项目"文件夹。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|**更新**|消息或其任何属性已更改。|![复选标记。](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|![复选标记](../media/checkmark.png)<sup>\*</sup>|
|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>验证是否正在为每个登录类型记录默认邮箱操作

默认情况下，邮箱审核会将新的 *DefaultAuditSet* 属性添加到所有邮箱。 此属性的值指示是否正在邮箱上审核由 Microsoft) 管理的默认邮箱操作 (。

若要在用户邮箱或共享邮箱上显示该值，请替换\<MailboxIdentity\>为邮箱用户名)  (名称、别名、电子邮件地址或用户主体名称，并在 Exchange Online PowerShell 中运行以下命令：

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

若要在Microsoft 365组邮箱上显示值，请替换\<MailboxIdentity\>为共享邮箱的名称、别名或电子邮件地址，并在 Exchange Online PowerShell 中运行以下命令：

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

该值 `Admin, Delegate, Owner` 指示：

- 正在审核所有三种登录类型的默认邮箱操作。 这是你在Microsoft 365组邮箱中看到的唯一值。
- 管理员 *尚未* 更改用户邮箱或共享邮箱上任何登录类型的审核邮箱操作。 请注意，这是默认情况下在组织中最初打开邮箱审核后的默认状态。

如果管理员在 **Set-Mailbox** cmdlet) 上使用 *AuditAdmin*、*AuditDelegate* 或 *AuditOwner* 参数更改了针对登录类型 (审核的邮箱操作，则属性值将有所不同。

例如，用户邮箱或共享邮箱上 *DefaultAuditSet* 属性的值`Owner`指示：

- 正在审核邮箱所有者的默认邮箱操作。
- 已从默认操作更改了针对 `Delegate` 和 `Admin` 登录类型的审核邮箱操作。

*DefaultAuditSet* 属性的空白值指示用户邮箱或共享邮箱上已更改所有三种登录类型的邮箱操作。

有关详细信息，请参阅本文中[默认记录的更改或还原邮箱操作](#change-or-restore-mailbox-actions-logged-by-default)

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>显示正在邮箱上记录的邮箱操作

若要查看当前正在用户邮箱或共享邮箱上记录的邮箱操作，请替换\<MailboxIdentity\>为邮箱的名称、别名、电子邮件地址或用户主体名称 (用户名) ，并在 Exchange Online PowerShell 中运行以下一个或多个命令。

> [!NOTE]
> 尽管可以将开关添加`-GroupMailbox`到以下 **Get-Mailbox** 命令中，以便Microsoft 365组邮箱，但不要相信返回的值。 本文前面的"Microsoft 365组邮箱"部分的邮箱操作中介绍了针对[Microsoft 365组邮](#mailbox-actions-for-microsoft-365-group-mailboxes)箱审核的默认和静态邮箱操作。

#### <a name="owner-actions"></a>所有者操作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>委托操作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>管理操作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>更改或还原默认记录的邮箱操作

如前所述，默认启用邮箱审核的主要好处之一是：无需管理审核的邮箱操作。 Microsoft 会为你执行此操作，我们将自动添加新的邮箱操作，以便在默认情况下进行审核，因为它们已发布。

但是，组织可能需要审核用户邮箱和共享邮箱的一组不同的邮箱操作。 本部分中的过程介绍如何更改针对每个登录类型审核的邮箱操作，以及如何还原到 Microsoft 托管的默认操作。

> [!IMPORTANT]
> 如果使用以下过程自定义用户邮箱或共享邮箱上记录的邮箱操作，Microsoft 发布的任何新的默认邮箱操作都不会在这些邮箱上自动审核。 需要手动将任何新的邮箱操作添加到自定义操作列表。

### <a name="change-the-mailbox-actions-to-audit"></a>更改邮箱操作以进行审核

可以使用 **Set-Mailbox** cmdlet 上的 *AuditAdmin*、*AuditDelegate* 或 *AuditOwner* 参数更改针对用户邮箱和共享邮箱审核的邮箱操作， (无法自定义Microsoft 365组邮箱的审核操作) 。

可以使用两种不同的方法来指定邮箱操作：

- 使用以下语法 *替换* () 现有邮箱操作： `action1,action2,...actionN`
- 使用以下语法 *添加或删除* 邮箱操作，而不会影响其他现有值：`@{Add="action1","action2",..."actionN"}`或 `@{Remove="action1","action2",..."actionN"}`。

本示例通过使用 SoftDelete 和 HardDelete 覆盖默认操作来更改名为"Gabriela Laureano"的邮箱的管理员邮箱操作。

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

本示例将 MailboxLogin 所有者操作添加到邮箱 laura@contoso.onmicrosoft.com。

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

本示例删除团队讨论邮箱的 MoveToDeletedItems 委托操作。

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

无论使用何种方法，在用户邮箱或共享邮箱上自定义审核的邮箱操作都具有以下结果：

- 对于自定义的登录类型，已审核的邮箱操作不再由 Microsoft 管理。
- 自定义的登录类型不再显示在邮箱的 *DefaultAuditSet* 属性值中，如 [前所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。

### <a name="restore-the-default-mailbox-actions"></a>还原默认邮箱操作

> [!NOTE]
> 以下过程不适用于Microsoft 365组邮箱， (这些邮箱仅限于默认[操作，如下](#mailbox-actions-for-microsoft-365-group-mailboxes)) 所述。

如果自定义了在用户邮箱或共享邮箱上审核的邮箱操作，则可以使用以下语法还原一种或所有登录类型的默认邮箱操作：

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

可以指定多个用逗号分隔的 *DefaultAuditSet* 值

本示例还原邮箱 mark@contoso.onmicrosoft.com 上所有登录类型的默认审核邮箱操作。

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

本示例还原邮箱 chris@contoso.onmicrosoft.com 上管理员登录类型的默认审核邮箱操作，但会为委托和所有者登录类型留下自定义的审核邮箱操作。

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

还原登录类型的默认审核邮箱操作的结果如下：

- 当前邮箱操作列表将替换为登录类型的默认邮箱操作。
- Microsoft 发布的任何新邮箱操作都会自动添加到登录类型的审核操作列表中。
- 邮箱的 *DefaultAuditSet* 属性值已更新，以包含还原的登录类型。

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>默认情况下，为组织关闭邮箱审核

默认情况下，可以通过在 Exchange Online PowerShell 中运行以下命令来关闭整个组织的邮箱审核：

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

默认情况下，关闭邮箱审核具有以下结果：

- 已为组织禁用邮箱审核。
- 自默认禁用邮箱审核时起，不会审核任何邮箱操作，即使邮箱上启用了审核， (邮箱上的 *AuditEnabled* 属性为 **True**) 。
- 未为新邮箱启用邮箱审核，将新邮箱或现有邮箱上的 *AuditEnabled* 属性设置为 **True** 将被忽略。
- 使用 **Set-MailboxAuditBypassAssociation** cmdlet (配置的任何邮箱审核绕过关联设置) 将被忽略。
- 现有邮箱审核记录将保留到记录的审核日志年龄限制过期。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>默认启用邮箱审核

若要为组织重新启用邮箱审核，请在 Exchange Online PowerShell 中运行以下命令：

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>绕过邮箱审核日志记录

目前，组织内已默认启用邮箱审核时，不能为特定邮箱禁用邮箱审核。 例如，将 *AuditEnabled* 邮箱属性设置为 **False** 将被忽略。

但是，仍可在 Exchange Online PowerShell 中使用 **Set-MailboxAuditBypassAssociation** cmdlet 来防止记录指定用户 *的任何和所有* 邮箱操作，而不考虑操作的发生位置。 例如：

- 旁路用户执行的邮箱所有者操作不会记录。
- 旁路用户在其他用户邮箱上执行的委托操作 (包括未记录) 共享邮箱。
- 不会记录绕过的用户执行的管理员操作。

若要绕过特定用户的邮箱审核日志记录，请将 \<MailboxIdentity\> 替换为用户的姓名、电子邮件地址、别名或用户主体名称（用户名），并运行以下命令：

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

若要验证是否已绕过对指定用户的审核，请运行以下命令：

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

值 **True** 表示用户绕过邮箱审核日志记录。

## <a name="more-information"></a>详细信息

- 尽管默认情况下，所有组织都启用了邮箱审核日志记录，但 **默认** 情况下，只有拥有 E5 许可证的用户才会 [在 Microsoft 365 合规中心审核日志搜索中](search-the-audit-log-in-security-and-compliance.md)或通过 [Office 365管理活动 API](/office/office-365-management-api/office-365-management-activity-api-reference) 返回邮箱审核日志事件。

  若要检索没有 E5 许可证的用户的邮箱审核日志条目，可以：

  - ) ，在运行命令 `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` (单个邮箱上手动启用邮箱审核。 执行此操作后，可以在Microsoft 365 合规中心中或通过Office 365管理活动 API 使用审核日志搜索。

    > [!NOTE]
    > 如果邮箱审核似乎已在邮箱上启用，但搜索未返回任何结果，_请将 AuditEnabled_ 参数的值更改为`$false`"回退"。`$true`

  - 在 Exchange Online PowerShell 中使用以下 cmdlet：
    - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) 以搜索特定用户的邮箱审核日志。
    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) 用于搜索特定用户的邮箱审核日志，并通过电子邮件将结果发送到指定收件人。

  - 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Online 中使用 Exchange 管理中心 (EAC) </a>执行以下操作：
    - [导出邮箱审核日志](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)
    - [运行非所有者邮箱访问报告](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- 默认情况下，邮箱审核日志记录在删除之前会保留 90 天。 可以通过在 Exchange Online PowerShell 中的 **Set-Mailbox** cmdlet 上使用 *AuditLogAgeLimit* 参数来更改审核日志记录的年龄限制。 但是，增加此值不允许在审核日志中搜索早于 90 天的事件。

  如果增加年龄限制，则需要在 Exchange Online PowerShell 中使用 [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) cmdlet 搜索用户的邮箱审核日志，以查找超过 90 天的记录。

- 如果在默认情况下为组织启用邮箱审核之前更改了邮箱的 *AuditLogAgeLimit* 属性，则不会更改邮箱的现有审核日志年龄限制。 换句话说，默认情况下，邮箱审核不会影响邮箱审核记录的当前年龄限制。

- 若要更改Microsoft 365组邮箱上的 *AuditLogAgeLimit* 值，需要在 **Set-Mailbox** 命令中包含`-GroupMailbox`该开关。

- 邮箱审核日志记录存储在子文件夹中， (每个用户邮箱的"可恢复邮件"文件夹中名为 *Audits*) 。 请记住以下有关邮箱审核记录和"可恢复邮件"文件夹的内容：

  - 邮箱审核记录对可恢复邮件文件夹的存储配额进行计数，默认情况下为 30 GB， (警告配额为 20 GB) 。 在以下情况下，存储配额将自动增加到 100 GB (，) 90 GB 的警告配额：
    - 将保留放在邮箱上。
    - 邮箱分配给合规中心中的保留策略。

  - 邮箱审核记录还计入 ["可恢复邮件"文件夹的文件夹限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。 审核子文件夹中最多可以存储 300 万项 (审核记录) 。

    > [!NOTE]
    > 默认情况下，邮箱审核不太可能影响"可恢复邮件"文件夹的存储配额或文件夹限制。

    - 可以在 Exchange Online PowerShell 中运行以下命令，在"可恢复邮件"文件夹的 Audits 子文件夹中显示项的大小和数量：

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - 无法直接访问"可恢复邮件"文件夹中的审核日志记录;而是使用 **Search-MailboxAuditLog** cmdlet 或搜索审核日志来查找和查看邮箱审核记录。

- 如果邮箱处于保留状态或分配给合规中心中的保留策略，则默认情况下，审核日志记录仍会保留由邮箱的 *AuditLogAgeLimit* 属性定义的持续时间 (90 天) 。 若要将邮箱的审核日志记录保留更长时间，需要增加邮箱的 *AuditLogAgeLimit* 值。

- 在多地理位置环境中，不支持跨地理位置邮箱审核。 例如，如果为某用户分配了访问其他地理位置的共享邮箱的权限，此用户执行的邮箱操作不会记录在共享邮箱的邮箱审核日志中。 Exchange管理员审核事件目前仅适用于默认位置。
