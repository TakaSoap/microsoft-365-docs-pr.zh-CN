---
title: 在 Office 365 中的 Exchange Online 邮箱上配置垃圾邮件设置
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
ms.openlocfilehash: 2b138830cff7337d7949606cc110ea8f7ae1c0ff
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42897010"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes-in-office-365"></a>在 Office 365 中的 Exchange Online 邮箱上配置垃圾邮件设置

Exchange Online 中的组织反垃圾邮件设置由 Exchange Online Protection （EOP）控制。 有关详细信息，请参阅[Office 365 中的反垃圾邮件保护](anti-spam-protection.md)。

但是，管理员还可以在 Exchange Online 中的各个邮箱上配置特定的反垃圾邮件设置：

- **启用或禁用垃圾邮件规则**： "垃圾邮件" 规则是一个隐藏的 "收件箱" 规则，默认情况下，在每个邮箱中启用该规则。 垃圾邮件规则控制以下功能：

  - **根据反垃圾邮件策略将邮件移动到 "垃圾邮件" 文件夹**：当使用 "操作**将邮件移动到垃圾邮件" 文件夹**中的垃圾邮件策略筛选判定时，垃圾邮件筛选规则会在邮件传递到邮箱后将邮件移动到 "垃圾邮件" 文件夹。 有关反垃圾邮件策略中的垃圾邮件筛选 verdicts 的详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。 同样，如果自动清除（ZAP）在已传递的邮件中检测到垃圾邮件或网络钓鱼，垃圾邮件筛选规则会将邮件移至 "垃圾邮件" 文件夹，以便**将邮件移动到垃圾邮件文件夹垃圾邮件**筛选判定操作。 有关 ZAP 的详细信息，请参阅[针对 Office 365 中的垃圾邮件和恶意软件的零小时自动清除（ZAP）保护](zero-hour-auto-purge.md)。
  
  - **用户在 outlook 或 web 上的 outlook 中为自己配置的垃圾邮件设置**：安全列表_集合_是安全发件人列表、安全收件人列表和每个邮箱的阻止发件人列表。 这些列表中的条目确定垃圾邮件规则是否将邮件移动到 "收件箱" 或 "垃圾邮件" 文件夹。 用户可以在 Outlook 或 web 上的 Outlook （以前称为 Outlook Web App）中为自己的邮箱配置安全列表集合。 管理员可以在任何用户的邮箱上配置安全列表集合。

在邮箱上启用垃圾邮件规则时，EOP 可以将邮件移动到 "垃圾邮件" 文件夹，具体取决于垃圾邮件筛选判定操作 "**将邮件移至垃圾邮件" 文件夹**或邮箱中的阻止发件人列表，并阻止邮件传递到 "垃圾邮件" 文件夹（基于邮箱上的 "安全发件人" 列表）。

 在邮箱上禁用垃圾邮件规则时，EOP 无法根据垃圾邮件筛选判定操作将邮件移动到 "垃圾邮件" 文件夹。**将邮件移动到 "垃圾邮件" 文件夹**或邮箱中的 "安全列表" 集合。

管理员可以使用 Exchange Online PowerShell 禁用、启用和查看邮箱上的垃圾邮件规则的状态。 管理员还可以使用 Exchange Online PowerShell 在邮箱（安全发件人列表、安全收件人列表和阻止发件人列表）上配置安全列表集合中的条目。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 只能使用 Exchange Online PowerShell 执行这些过程。 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

- 您需要先分配权限，然后才能执行这些过程。 具体来说，您需要 "**邮件收件人**" 角色（默认情况下分配给 "**组织管理**"、"**收件人管理**" 和 "**自定义邮件收件人**" 角色组）或 "**用户选项**" 角色（默认情况下分配给 "**组织管理**" 和 "**技术支持**" 角色组）。 若要向 Exchange Online 中的角色组添加用户，请参阅[在 Exchange online 中修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。 请注意，拥有默认权限的用户可以在其自己的邮箱上执行这些相同的过程，只要他们有[权访问 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)即可。

- 在 EOP 保护本地 Exchange 邮箱的独立 EOP 环境中，您需要在内部部署 Exchange 中配置邮件流规则（也称为传输规则），以翻译 EOP 垃圾邮件筛选判定，以便垃圾邮件规则可以将邮件移动到"垃圾邮件" 文件夹。 有关详细信息，请参阅[Configure 独立 EOP 以将垃圾邮件传递到混合环境中的 "垃圾邮件" 文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>使用 Exchange Online PowerShell 启用或禁用邮箱中的垃圾邮件规则

> [!NOTE]
> 您只能使用 **Set-MailboxJunkEmailConfiguration** cmdlet 来禁用在 Outlook（在"缓存"Exchange 模式中）或 Web 上的 Outlook 中打开的邮箱上的垃圾邮件规则。 如果尚未打开该邮箱，则会收到错误： `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.`如果要对批量操作禁止显示此错误，可以添加`-ErrorAction SlientlyContinue`到**set-mailboxjunkemailconfiguration**命令

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

有关语法和参数的详细信息，请参阅[set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)。

 **注意**：

- 如果用户从未打开过其邮箱，则在运行以前的命令时可能会收到错误消息。 若要取消批量操作的此错误， `-ErrorAction SlientlyContinue`请添加到**set-mailboxjunkemailconfiguration**命令。

- 即使禁用垃圾邮件规则，Outlook 垃圾邮件筛选器（取决于其配置方式）也可以确定邮件是否为垃圾邮件，并且可以根据其自身的垃圾邮件结论和安全列表集合，将邮件移动到 "收件箱" 或 "垃圾邮件" 文件夹邮箱。 有关详细信息，请参阅本主题中的[有关 Outlook 中的垃圾邮件设置](#about-junk-email-settings-in-outlook)部分。

### <a name="how-do-you-know-this-worked"></a>您如何知道这有效？

若要验证是否已成功启用或禁用邮箱的垃圾邮件规则，请执行以下任一操作：

- 将_ \<MailboxIdentity\> _替换为邮箱的名称、别名或电子邮件地址，然后运行以下命令来验证**Enabled**属性值：

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

- 将_ \<MailboxIdentity\> _替换为邮箱的名称、别名或电子邮件地址，并运行以下命令来验证垃圾邮件规则的**Enabled**属性值。

  ```PowerShell
  Get-InboxRule "Junk E-mail Rule" -Mailbox "<MailboxIdentity>" -IncludeHidden
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

若要输入多个值，并覆盖_BlockedSendersAndDomains_和_TrustedSendersAndDomains_参数的任何现有条目，请使用以下`"<Value1>","<Value2>"...`语法：。 若要在不影响其他现有条目的情况下添加或删除一个或多个值，请使用以下语法：`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

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

有关语法和参数的详细信息，请参阅[set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)。

 **注意**：

- 如果用户从未打开过其邮箱，则在运行以前的命令时可能会收到错误消息。 若要取消批量操作的此错误， `-ErrorAction SlientlyContinue`请添加到**set-mailboxjunkemailconfiguration**命令。

- 即使在邮箱上禁用了垃圾邮件规则，仍可以配置安全列表集合，并且 Outlook 垃圾邮件筛选器能够将邮件移动到 "收件箱" 或 "垃圾邮件" 文件夹。 有关详细信息，请参阅本主题中的[关于 Outlook 中的配置垃圾邮件设置](#about-junk-email-settings-in-outlook)部分。

- Outlook 垃圾邮件筛选器包含其他安全列表集合设置（例如，**自动将我的电子邮件添加到安全发件人列表**中）。 For more information, see [Use Junk Email Filters to control which messages you see](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>您如何知道这有效？

若要验证是否已成功配置邮箱的安全列表集合，请执行以下任一操作：

- 将_ \<MailboxIdentity\> _替换为邮箱的名称、别名或电子邮件地址，并运行以下命令来验证属性值：

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  如果值列表太长，请使用以下语法：

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>关于 Outlook 中的配置垃圾邮件设置

若要启用、禁用及配置在 Outlook 中可以使用的客户端"垃圾邮件筛选器"设置，请使用"组策略"。 有关详细信息，请参阅[管理模板文件（ADMX/ADML）和 Office 自定义工具 For office 365 专业增强版、office 2019 和 office 2016](https://www.microsoft.com/download/details.aspx?id=49030)。

将 "Outlook 垃圾邮件筛选器" 设置为默认值 "在**家庭** \> **垃圾** \>邮件中**不自动筛选**" "垃圾**邮件选项** \> "**选项**时，Outlook 不会尝试将 massages 归类为垃圾邮件，但仍使用安全发件人列表、安全收件人列表和阻止发件人列表）将邮件移动到 "垃圾邮件" 文件夹。 有关这些设置的详细信息，请参阅[垃圾邮件筛选器概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。

When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder. 这种垃圾邮件分类独立于由 EOP 确定的垃圾邮件可信度（SCL）。 实际上，Outlook 会忽略 EOP 中的 SCL （除非 EOP 将邮件标记为 "跳过垃圾邮件筛选"），并使用其自己的条件来确定邮件是否为垃圾邮件。 当然，可能会出现来自 EOP 和 Outlook 的垃圾邮件结论。 有关这些设置的详细信息，请参阅在[垃圾邮件筛选器中更改保护级别](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。

> [!NOTE]
> 在2016年11月，Microsoft 已停止为 Exchange 和 Outlook 中的 SmartScreen 筛选器生成垃圾邮件定义更新。 现有的 SmartScreen 垃圾邮件定义保留不变，但其有效性可能会随着时间的推移而下降。 有关详细信息，请参阅“[停止为 Outlook 和 Exchange 中的 SmartScreen 提供支持](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)”。

因此，Outlook 垃圾邮件筛选器能够使用邮箱的安全列表集合及其自己的垃圾邮件分类将邮件移动到 "垃圾邮件" 文件夹，即使邮箱中禁用了垃圾邮件规则也是如此。

Outlook 和 Web 上的 Outlook 同等支持安全列表集合。 安全列表集合保存在 Exchange Online 邮箱中，因此对 Outlook 中的安全列表集合的更改会显示在 web 上的 Outlook 中，反之亦然。
