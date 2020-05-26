---
title: 配置 Exchange Online 邮箱上的垃圾邮件设置
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online 邮箱中配置垃圾邮件设置。 Outlook 或 web 上的 Outlook 中的用户可以使用这些设置中的很多。
ms.openlocfilehash: 72b2680cb16e9d8d0f33ee3ec8a080206c68bf97
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352506"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>配置 Exchange Online 邮箱上的垃圾邮件设置

在 Exchange Online 中有邮箱的 Microsoft 365 组织中，组织反垃圾邮件设置由 Exchange Online Protection （EOP）控制。 有关详细信息，请参阅[EOP 中的反垃圾邮件保护](anti-spam-protection.md)。

但是，管理员还可以在 Exchange Online 中的各个邮箱上配置特定的反垃圾邮件设置：

- **启用或禁用垃圾邮件规则**： "垃圾邮件" 规则是一个隐藏的 "收件箱" 规则，默认情况下，在每个邮箱中启用该规则。 垃圾邮件规则控制以下功能：

  - **根据反垃圾邮件策略将邮件移动到 "垃圾邮件" 文件夹**：当使用 "操作**将邮件移动到垃圾邮件" 文件夹**中的垃圾邮件策略筛选判定时，垃圾邮件筛选规则会在邮件传递到邮箱后将邮件移动到 "垃圾邮件" 文件夹。 有关反垃圾邮件策略中的垃圾邮件筛选 verdicts 的详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。 同样，如果0小时自动清除（ZAP）确定传递的邮件是垃圾邮件或网络钓鱼，垃圾邮件筛选规则会将邮件移至 "垃圾邮件" 文件夹，以**将邮件移动到垃圾邮件文件夹**垃圾邮件筛选判定操作。 有关 ZAP 的详细信息，请参阅[Exchange Online 中的零小时自动清除（ZAP）](zero-hour-auto-purge.md)。
  
  - **用户在 outlook 或 web 上的 outlook 中为自己配置的垃圾邮件设置**：安全列表_集合_是安全发件人列表、安全收件人列表和每个邮箱的阻止发件人列表。 这些列表中的条目确定垃圾邮件规则是否将邮件移动到 "收件箱" 或 "垃圾邮件" 文件夹。 用户可以在 Outlook 或 web 上的 Outlook （以前称为 Outlook Web App）中为自己的邮箱配置安全列表集合。 管理员可以在任何用户的邮箱上配置安全列表集合。

在邮箱上启用垃圾邮件规则时，EOP 可以将邮件移动到 "垃圾邮件" 文件夹，具体取决于垃圾邮件筛选判定操作 "**将邮件移至垃圾邮件" 文件夹**或邮箱中的阻止发件人列表，并阻止邮件传递到 "垃圾邮件" 文件夹（基于邮箱上的 "安全发件人" 列表）。

 在邮箱上禁用垃圾邮件规则时，EOP 无法根据垃圾邮件筛选判定操作将邮件移动到 "垃圾邮件" 文件夹。**将邮件移动到 "垃圾邮件" 文件夹**或邮箱中的 "安全列表" 集合。

管理员可以使用 Exchange Online PowerShell 禁用、启用和查看邮箱上的垃圾邮件规则的状态。 管理员还可以使用 Exchange Online PowerShell 在邮箱（安全发件人列表、安全收件人列表和阻止发件人列表）上配置安全列表集合中的条目。

> [!NOTE]
> 来自用户添加到其自己的安全发件人列表中的发件人的邮件将跳过 EOP 筛选（SCL 为-1）。 若要阻止用户在 Outlook 中向其安全发件人列表添加条目，请按照本主题后面的[关于 Outlook 中的垃圾邮件设置](#about-junk-email-settings-in-outlook)一节中所述的那样使用组策略。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 只能使用 Exchange Online PowerShell 执行这些过程。 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

- 您需要先分配权限，然后才能执行这些过程。 具体来说，您需要 "**邮件收件人**" 角色（默认情况下分配给 "**组织管理**"、"**收件人管理**" 和 "**自定义邮件收件人**" 角色组）或 "**用户选项**" 角色（默认情况下分配给 "**组织管理**" 和 "**技术支持**" 角色组）。 若要向 Exchange Online 中的角色组添加用户，请参阅[在 Exchange online 中修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。 请注意，拥有默认权限的用户可以在其自己的邮箱上执行这些相同的过程，只要他们有[权访问 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)即可。

- 在 EOP 保护本地 Exchange 邮箱的独立 EOP 环境中，需要在本地 Exchange 中配置邮件流规则（亦称为“传输规则”），以转换 EOP 垃圾邮件筛选裁定，这样垃圾邮件规则才能将邮件移动到“垃圾邮件”文件夹。 有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

- 共享邮箱的安全发件人在设计时不会同步到 Azure AD 和 EOP。

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>使用 Exchange Online PowerShell 启用或禁用邮箱中的垃圾邮件规则

> [!NOTE]
> 您只能使用 **Set-MailboxJunkEmailConfiguration** cmdlet 来禁用在 Outlook（在"缓存"Exchange 模式中）或 Web 上的 Outlook 中打开的邮箱上的垃圾邮件规则。 如果尚未打开邮箱，则会收到错误： `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` 如果要对批量操作禁止显示此错误，可以添加 `-ErrorAction SlientlyContinue` 到**set-mailboxjunkemailconfiguration**命令。

若要启用或禁用邮箱上的垃圾邮件规则，请使用以下语法：

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

本示例禁用 Ori Epstein 邮箱上的垃圾邮件规则。

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

本示例禁用组织中的所有用户邮箱上的垃圾邮件规则。

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

有关语法和参数的详细信息，请参阅[set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。

> [!NOTE]
> 
> - 如果用户从未打开过其邮箱，则在运行以前的命令时可能会收到错误消息。 若要取消批量操作的此错误，请添加 `-ErrorAction SlientlyContinue` 到**set-mailboxjunkemailconfiguration**命令。
> 
> - 即使禁用垃圾邮件规则，Outlook 垃圾邮件筛选器（取决于其配置方式）也可以确定邮件是否为垃圾邮件，并且可以根据其自身的垃圾邮件结论和邮箱上的安全列表集合，将邮件移动到 "收件箱" 或 "垃圾邮件" 文件夹。 有关详细信息，请参阅本主题中的[有关 Outlook 中的垃圾邮件设置](#about-junk-email-settings-in-outlook)部分。

### <a name="how-do-you-know-this-worked"></a>您如何知道这有效？

若要验证是否已成功启用或禁用邮箱的垃圾邮件规则，请执行以下任一操作：

- 将_ \< MailboxIdentity \> _替换为邮箱的名称、别名或电子邮件地址，然后运行以下命令来验证**Enabled**属性值：

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>使用 Exchange Online PowerShell 在邮箱上配置安全列表集合

邮箱的安全列表集合包括"安全发件人"列表、"安全收件人"列表和"阻止的发件人"列表。 默认情况下，用户可以在 Outlook 或 web 上的 Outlook 中的自己的邮箱上配置安全列表集合。 管理员可以使用 **Set-MailboxJunkEmailConfiguration** cmdlet 上对应的参数在用户的邮箱上配置安全列表集合。 下表介绍了这些参数。

|||
|---|---|
|**Set-mailboxjunkemailconfiguration 上的参数**|**Outlook 网页设置**|
|_BlockedSendersAndDomains_|**将来自这些发件人或域的邮件移到我的"垃圾邮件"文件夹**|
|_ContactsTrusted_|**信任来自我的联系人的邮件**|
|_TrustedListsOnly_|**仅信任来自安全发件人和域列表和安全邮件列表中的地址的电子邮件**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**不将来自这些发件人的电子邮件移动到我的垃圾邮件文件夹**|
|

<sup>\*</sup>**备注**：

- 在 Exchange Online 中，不能识别安全发件人列表或_TrustedSendersAndDomains_参数中的**域条目**，因此只能使用电子邮件地址。 在具有目录同步的独立 EOP 中，默认情况下不会同步域条目，但可以为域启用同步。 有关详细信息，请参阅[KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange)。

- 您不能使用**set-mailboxjunkemailconfiguration** cmdlet 直接修改安全收件人列表（ _TrustedRecipientsAndDomains_参数不起作用）。 修改"安全发件人"列表后，这些更改将同步到"安全收件人"列表。

若要配置邮箱的安全列表集合，请使用以下语法：

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

若要输入多个值，并覆盖_BlockedSendersAndDomains_和_TrustedSendersAndDomains_参数的任何现有条目，请使用以下语法： `"<Value1>","<Value2>"...` 。 若要在不影响其他现有条目的情况下添加或删除一个或多个值，请使用以下语法：`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

本示例在 Ori Epstein 的邮箱上配置以下安全列表集合的设置：

- 将值 shopping@fabrikam.com 添加到阻止的发件人列表中。

- 从 "安全发件人" 列表和 "安全收件人" 列表中删除值 chris@fourthcoffee.com。

- 在"联系人"文件夹中配置被视为受信任的发件人的联系人。

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

本示例将域 contoso.com 从组织中所有用户的邮箱的"阻止的发件人"名单中删除。

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

有关语法和参数的详细信息，请参阅[set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。

> [!NOTE]
> 
> - 如果用户从未打开过其邮箱，则在运行以前的命令时可能会收到错误消息。 若要取消批量操作的此错误，请添加 `-ErrorAction SlientlyContinue` 到**set-mailboxjunkemailconfiguration**命令。
> 
> - 即使在邮箱上禁用了垃圾邮件规则，仍可以配置安全列表集合，并且 Outlook 垃圾邮件筛选器能够将邮件移动到 "收件箱" 或 "垃圾邮件" 文件夹。 有关详细信息，请参阅本主题中的[关于 Outlook 中的配置垃圾邮件设置](#about-junk-email-settings-in-outlook)部分。
> 
> - Outlook 垃圾邮件筛选器包含其他安全列表集合设置（例如，**自动将我的电子邮件添加到安全发件人列表**中）。 For more information, see [Use Junk Email Filters to control which messages you see](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>您如何知道这有效？

若要验证是否已成功配置邮箱的安全列表集合，请执行以下任一操作：

- 将_ \< MailboxIdentity \> _替换为邮箱的名称、别名或电子邮件地址，并运行以下命令来验证属性值：

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  如果值列表太长，请使用以下语法：

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>关于 Outlook 中的配置垃圾邮件设置

若要启用、禁用及配置在 Outlook 中可以使用的客户端"垃圾邮件筛选器"设置，请使用"组策略"。 有关详细信息，请参阅[管理模板文件（ADMX/ADML）和 Office 自定义工具 For Microsoft 365 Apps for enterprise、office 2019 和 office 2016](https://www.microsoft.com/download/details.aspx?id=49030)以及[如何使用组策略部署垃圾邮件设置（如安全发件人列表](https://support.microsoft.com/help/2252421/how-to-deploy-junk-email-settings-such-as-the-safe-senders-list-by-usi)）。

将 "Outlook 垃圾邮件筛选器" 设置为默认值 "在**家庭**垃圾邮件中**不自动筛选**" "垃圾 \> **Junk** \> **邮件选项** \> "**选项**时，Outlook 不会尝试将 massages 归类为垃圾邮件，但仍使用安全发件人列表、安全收件人列表和阻止发件人列表）将邮件移动到 "垃圾邮件" 文件夹。 有关这些设置的详细信息，请参阅[垃圾邮件筛选器概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。

When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder. 这种垃圾邮件分类独立于由 EOP 确定的垃圾邮件可信度（SCL）。 实际上，Outlook 会忽略 EOP 中的 SCL （除非 EOP 将邮件标记为 "跳过垃圾邮件筛选"），并使用其自己的条件来确定邮件是否为垃圾邮件。 当然，可能会出现来自 EOP 和 Outlook 的垃圾邮件结论。 有关这些设置的详细信息，请参阅在[垃圾邮件筛选器中更改保护级别](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。

> [!NOTE]
> 在2016年11月，Microsoft 已停止为 Exchange 和 Outlook 中的 SmartScreen 筛选器生成垃圾邮件定义更新。 现有的 SmartScreen 垃圾邮件定义保留不变，但其有效性可能会随着时间的推移而下降。 有关详细信息，请参阅“[停止为 Outlook 和 Exchange 中的 SmartScreen 提供支持](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)”。

因此，Outlook 垃圾邮件筛选器能够使用邮箱的安全列表集合及其自己的垃圾邮件分类将邮件移动到 "垃圾邮件" 文件夹，即使邮箱中禁用了垃圾邮件规则也是如此。

Outlook 和 Web 上的 Outlook 同等支持安全列表集合。 安全列表集合保存在 Exchange Online 邮箱中，因此对 Outlook 中的安全列表集合的更改会显示在 web 上的 Outlook 中，反之亦然。

## <a name="limits-for-junk-email-settings"></a>垃圾邮件设置的限制

存储在用户邮箱中的安全列表集合（安全发件人列表、安全收件人列表和阻止发件人列表）也会同步到 EOP。 通过目录同步，安全列表集合将同步到 Azure AD。

- 用户邮箱中的安全列表集合的限制为 510 KB，其中包含所有列表以及其他垃圾邮件筛选器设置。 如果用户超过此限制，将收到如下所示的 Outlook 错误：

  > 无法/无法将添加到 "垃圾邮件" 的服务器列表。 您已超出服务器允许的大小。 服务器上的垃圾邮件筛选器将被禁用，直到垃圾邮件列表缩小到服务器允许的大小。

  有关此限制以及如何更改此限制的详细信息，请参阅[KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit)。

- EOP 中的同步安全列表集合具有以下同步限制：

  - 1024如果启用了 **"来自我的联系人的信任电子邮件**"，则安全发件人列表、安全收件人列表和外部联系人中的条目总数。
  - 500阻止的发件人列表和阻止的域列表中的条目总数。

  达到1024项限制时，将发生以下情况：
  
  - 该列表将停止接受 PowerShell 中的条目和 web 上的 Outlook，但不会显示任何错误。

    Outlook 用户可以继续添加1024个以上的条目，直到达到 Outlook 限制值 510 KB。 Outlook 可以使用这些额外的条目，只要 EOP 筛选器在传递到邮箱之前不会阻止邮件（邮件流规则、反欺骗等）。

- 通过目录同步，这些项将按以下顺序同步到 Azure AD：

  1. 如果启用了 **"来自我的联系人的信任电子邮件"** ，则为邮件联系人。
  2. 只要对前1024个条目进行了更改，就会对安全发件人列表和安全收件人列表进行组合、消除重复并按字母顺序对其进行排序。

  使用前1024个条目，并在邮件头中标记相关信息。
  
  1024以上未同步到 Azure AD 的条目由 Outlook （而非 web 上的 Outlook）处理，邮件头中不会标记任何信息。

您可以看到，启用 "**来自我的联系人的信任电子邮件**" 设置可以减少可同步的安全发件人和安全收件人的数量。 如果这是个问题，我们建议使用组策略关闭此功能：

- 文件名： outlk16。 opax
- 策略设置：**信任来自联系人的电子邮件**
