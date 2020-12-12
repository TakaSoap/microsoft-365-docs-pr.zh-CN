---
title: 配置 Exchange Online 邮箱上的垃圾邮件设置
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online 邮箱中配置垃圾邮件设置。 许多这些设置都可供 Outlook 或 Outlook 网页中的用户使用。
ms.openlocfilehash: 5469143e0a924478e0bbb7285ac607095d4a169f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659722"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>配置 Exchange Online 邮箱上的垃圾邮件设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在具有 Exchange Online 邮箱的 Microsoft 365 组织中，组织反垃圾邮件设置由 Exchange Online Protection (EOP) 。 有关详细信息，请参阅 [EOP 中的反垃圾邮件保护](anti-spam-protection.md)。

但是，管理员还可以在 Exchange Online 中的单个邮箱上配置特定的反垃圾邮件设置：

- **启用或禁用垃圾邮件规则**：垃圾邮件规则是一个隐藏的收件箱规则，名为"垃圾邮件规则"，默认在每个邮箱中启用。 垃圾邮件规则控制以下功能：

  - 根据反垃圾邮件策略将邮件移动到"垃圾邮件"文件夹：当使用"将邮件移动到垃圾邮件"文件夹的操作配置反垃圾邮件策略进行垃圾邮件筛选裁定时，垃圾邮件筛选器规则在邮件传递到邮箱后将邮件移动到"垃圾邮件"文件夹。 有关反垃圾邮件策略中的垃圾邮件筛选裁定详细信息，请参阅"在 EOP 中配置[反垃圾邮件策略"。](configure-your-spam-filter-policies.md) 同样，如果零时差自动清除 (ZAP) 确定已传递的邮件是垃圾邮件或网络钓鱼邮件，垃圾邮件筛选器规则会将邮件移动到"垃圾邮件"文件夹，以执行"将邮件移动到垃圾邮件" **文件夹** 垃圾邮件筛选裁定操作。 有关 ZAP 详细信息，请参阅 Exchange Online 中的零时差 [ (ZAP) 清除](zero-hour-auto-purge.md)。

  - **用户在 Outlook** 或 Web 上的 Outlook 中为自己配置的垃圾邮件设置： _安全_ 列表集合是每个邮箱上的"安全发件人"列表、"安全收件人"列表和"阻止的发件人"列表。 这些列表中条目确定垃圾邮件规则是将邮件移动到"收件箱"还是"垃圾邮件"文件夹。 用户可以在 Outlook 或 Web 上的 Outlook 中为其自己的邮箱配置安全列表 (以前称为Outlook Web App) 。 管理员可以在任何用户的邮箱上配置安全列表集合。

在邮箱上启用垃圾邮件规则后，EOP 能够根据垃圾邮件筛选裁定操作将邮件移动到"垃圾邮件"文件夹或邮箱上的"阻止的发件人"列表，并基于邮箱) 上的"安全发件人"列表阻止邮件传递到"垃圾邮件"文件夹 (。

 在邮箱上禁用垃圾邮件规则后，EOP 无法根据垃圾邮件筛选裁定操作将邮件移动到"垃圾邮件"文件夹或邮箱的安全列表集合，将邮件移动到"垃圾邮件"文件夹。

管理员可以使用 Exchange Online PowerShell 禁用、启用和查看邮箱上的垃圾邮件规则的状态。 管理员还可使用 Exchange Online PowerShell 配置邮箱的安全列表集合中的条目 (安全发件人列表、安全收件人列表和阻止的发件人列表) 。

> [!NOTE]
> 用户已添加到其自己的安全发件人列表的发件人的邮件将跳过连接筛选作为 EOP 的一部分 (SCL 为 -1) 。 若要阻止用户在 Outlook 中向其安全发件人列表添加条目，请使用本文稍后部分"关于  [Outlook](#about-junk-email-settings-in-outlook) 垃圾邮件设置"部分中提到的组策略。 策略筛选、内容筛选和适用于 Office 365 的 Defender 检查仍将应用于邮件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 只能使用 Exchange Online PowerShell 执行本文中的过程。 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 您需在 Exchange Online 中获得权限，然后才能执行本文中的过程。 具体来说，您需要默认情况下分配给组织管理、收件人管理和自定义邮件收件人角色组的"邮件收件人"角色)  (或默认分配给"组织管理"和"技术支持"角色组的用户选项角色 () 。      若要将用户添加到 Exchange Online 中的角色组，请参阅["修改 Exchange Online 中的角色组"。](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 请注意，具有默认权限的用户可以在自己的邮箱上执行这些相同的过程，只要他们有权访问[Exchange Online PowerShell。](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

- 在 EOP 保护本地 Exchange 邮箱的独立 EOP 环境中，需要在本地 Exchange 中配置邮件流规则（亦称为“传输规则”），以转换 EOP 垃圾邮件筛选裁定，这样垃圾邮件规则才能将邮件移动到“垃圾邮件”文件夹。 有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

- 根据设计，共享邮箱的安全发件人不会同步到 Azure AD 和 EOP。

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>使用 Exchange Online PowerShell 启用或禁用邮箱中的垃圾邮件规则

> [!NOTE]
> 您只能使用 **Set-MailboxJunkEmailConfiguration** cmdlet 来禁用在 Outlook（在"缓存"Exchange 模式中）或 Web 上的 Outlook 中打开的邮箱上的垃圾邮件规则。 如果邮箱尚未打开，您将收到错误：如果要禁止批量操作出现此错误，可以添加到 `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** 命令。

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

有关语法和参数的详细信息，请参阅[Set-MailboxJunkEmailConfiguration。](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)

> [!NOTE]
>
> - 如果用户从未打开其邮箱，则当您运行上一个命令时，您可能会收到错误。 若要禁止批量操作出现此错误，请 `-ErrorAction SilentlyContinue` 添加到 **Set-MailboxJunkEmailConfiguration** 命令。
>
> - 即使您禁用垃圾邮件规则，Outlook 垃圾邮件筛选器 (也可以根据邮件的配置方式确定) 是否包含垃圾邮件，并可以基于自己的垃圾邮件裁定和邮箱的安全列表集合将邮件移动到收件箱或垃圾邮件文件夹。 有关详细信息，请参阅本文中的" [关于 Outlook 中的](#about-junk-email-settings-in-outlook) 垃圾邮件设置"部分。

### <a name="how-do-you-know-this-worked"></a>您如何知道这有效？

若要验证是否已成功启用或禁用邮箱的垃圾邮件规则，请执行以下任一操作：

- 替换为邮箱的名称、别名或电子邮件地址，并运行以下命令 _\<MailboxIdentity\>_ 来验证 **Enabled** 属性值：

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>使用 Exchange Online PowerShell 配置邮箱的安全列表集合

邮箱的安全列表集合包括"安全发件人"列表、"安全收件人"列表和"阻止的发件人"列表。 默认情况下，用户可以在 Outlook 或 Web 上的 Outlook 中配置自己的邮箱的安全列表集合。 管理员可以使用 **Set-MailboxJunkEmailConfiguration** cmdlet 上对应的参数在用户的邮箱上配置安全列表集合。 下表介绍了这些参数。

****

|参数Set-MailboxJunkEmailConfiguration|Web 上的 Outlook 设置|
|---|---|
|_BlockedSendersAndDomains_|**将来自这些发件人或域的邮件移到我的"垃圾邮件"文件夹**|
|_ContactsTrusted_|**信任来自我的联系人的邮件**|
|_TrustedListsOnly_|**仅信任来自我的安全发件人和域列表和安全邮件列表中地址的电子邮件**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**不要将来自这些发件人的电子邮件移动到我的"垃圾邮件"文件夹**|
|

<sup>\*</sup>**注意**：

- 在 Exchange  Online 中，无法识别安全发件人列表或 _TrustedSendersAndDomains_ 参数中的域条目，因此只能使用电子邮件地址。 在具有目录同步的独立 EOP 中，默认情况下不会同步域条目，但您可以为域启用同步。 有关详细信息，请参阅[KB3019657。](https://support.microsoft.com/help/3019657)

- 不能通过使用 **Set-MailboxJunkEmailConfiguration** cmdlet (_TrustedRecipientsAndDomains_ 参数不能直接修改安全收件人列表) 。 修改"安全发件人"列表后，这些更改将同步到"安全收件人"列表。

若要配置邮箱的安全列表集合，请使用以下语法：

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

若要输入多个值并覆盖 _BlockedSendersAndDomains_ 和 _TrustedSendersAndDomains_ 参数的任何现有条目，请使用以下 `"<Value1>","<Value2>"...` 语法： 若要在不影响其他现有条目的情况下添加或删除一个或多个值，请使用以下语法： `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

本示例在 Ori Epstein 的邮箱上配置以下安全列表集合的设置：

- 将值shopping@fabrikam.com阻止的发件人列表。

- 从"chris@fourthcoffee.com发件人"列表和安全收件人列表中删除该值。

- 在"联系人"文件夹中配置被视为受信任的发件人的联系人。

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

本示例将域 contoso.com 从组织中所有用户的邮箱的"阻止的发件人"名单中删除。

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

有关语法和参数的详细信息，请参阅[Set-MailboxJunkEmailConfiguration。](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)

> [!NOTE]
>
> - 如果用户从未打开其邮箱，则当您运行之前的命令时，您可能会收到错误。 若要禁止批量操作出现此错误，请 `-ErrorAction SilentlyContinue` 添加到 **Set-MailboxJunkEmailConfiguration** 命令。
>
> - 即使邮箱上禁用了垃圾邮件规则，您仍可以配置安全列表集合，并且 Outlook 垃圾邮件筛选器可以将邮件移动到"收件箱"或"垃圾邮件"文件夹。 有关详细信息，请参阅本文中的" [关于 Outlook 中的](#about-junk-email-settings-in-outlook) 垃圾邮件设置"部分。
>
> - Outlook 垃圾邮件筛选器具有其他安全列表集合 (例如，自动将我电子邮件的人添加到安全发件人 **列表) 。** For more information, see [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>您如何知道这有效？

若要验证是否已成功配置邮箱的安全列表集合，请执行以下任一操作：

- 替换为邮箱的名称、别名或电子邮件地址，并运行以下命令 _\<MailboxIdentity\>_ 来验证属性值：

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  如果值列表太长，请使用以下语法：

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>关于 Outlook 中的配置垃圾邮件设置

若要启用、禁用及配置在 Outlook 中可以使用的客户端"垃圾邮件筛选器"设置，请使用"组策略"。 有关详细信息，[请参阅 Microsoft 365 企业应用版、Office 2019 和 Office 2016 的管理模板文件 (ADMX/ADML) ](https://www.microsoft.com/download/details.aspx?id=49030)和 Office 自定义工具，以及如何使用组策略部署垃圾邮件设置（如安全发件人列表）。 [](https://support.microsoft.com/help/2252421)

当 Outlook 垃圾邮件筛选器设置为默认值"主页垃圾邮件选项"中"无自动筛选"时，Outlook 不会尝试将垃圾邮件分类为垃圾邮件，但仍使用安全列表集合 (安全发件人列表、安全收件人列表和阻止的发件人列表) 在传递后将邮件移动到"垃圾邮件 \>  \>  \> "文件夹。 有关这些设置详细信息，请参阅["垃圾邮件筛选器概述"。](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder. 此垃圾邮件分类独立于由 EOP (SCL) 垃圾邮件可信度。 事实上，Outlook 会忽略 EOP (中的 SCL，除非 EOP 将邮件标记为跳过垃圾邮件筛选) 并使用自己的条件来确定邮件是否是垃圾邮件。 当然，来自 EOP 和 Outlook 的垃圾邮件裁定可能相同。 有关这些设置详细信息，请参阅"更改垃圾邮件 [筛选器"中的保护级别](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。

> [!NOTE]
> 2016 年 11 月，Microsoft 停止为 Exchange 和 Outlook 中的 SmartScreen 筛选器生成垃圾邮件定义更新。 现有 SmartScreen 垃圾邮件定义已留在现有位置，但其有效性可能会随着时间的推移而降低。 有关详细信息，请参阅“[停止为 Outlook 和 Exchange 中的 SmartScreen 提供支持](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)”。

因此，Outlook 垃圾邮件筛选器可以使用邮箱的安全列表集合及其自己的垃圾邮件分类将邮件移动到"垃圾邮件"文件夹，即使邮箱中已禁用垃圾邮件规则。

Outlook 和 Web 上的 Outlook 同等支持安全列表集合。 安全列表集合保存在 Exchange Online 邮箱中，因此 Outlook 中的安全列表集合的更改显示在 Outlook 网页版中，反之亦然。

## <a name="limits-for-junk-email-settings"></a>垃圾邮件设置的限制

安全列表集合 (用户邮箱中存储的安全发件人列表、安全收件人列表和阻止的发件人列表) 也会同步到 EOP。 通过目录同步，安全列表集合将同步到 Azure AD。

- 用户邮箱中的安全列表集合限制为 510 KB，其中包括所有列表，以及其他垃圾邮件筛选器设置。 如果用户超过此限制，将收到如下所示的 Outlook 错误：

  > 无法/无法添加到服务器垃圾邮件列表。 您超过服务器上允许的大小。 在垃圾邮件列表减小到服务器允许的大小之前，将禁用该服务器上垃圾邮件筛选器。

  有关此限制以及如何更改它，请参阅[KB2669081。](https://support.microsoft.com/help/2669081)

- EOP 中的同步安全列表集合具有以下同步限制：

  - 如果启用了"信任来自我的联系人的电子邮件"，则安全发件人列表、安全收件人列表和外部联系人中的总条目数为1024。
  - "阻止的发件人"列表和"阻止的域"列表中共有 500 个条目。

  当达到 1024 条目限制时，将发生以下情况：

  - 该列表将停止接受 PowerShell 和 Web 上的 Outlook 中的条目，但不显示任何错误。

    Outlook 用户可以继续添加超过 1024 个条目，直到达到 Outlook 510 KB 的限制。 Outlook 可以使用这些附加条目，只要 EOP 筛选器在将邮件发送到邮箱之前不阻止 (邮件流规则、反欺骗等) 。

- 借助目录同步，条目将按以下顺序同步到 Azure AD：

  1. 如果启用了 **信任来自我的联系人的电子邮件，则邮件** 联系人。
  2. 只要对前 1024 个条目进行了更改，就会组合安全发件人列表和安全收件人列表、取消重复列表并按字母顺序排序。

  使用前 1024 个条目，相关信息标记在邮件头中。

  超过 1024 个未同步到 Azure AD 的条目由 Outlook (而不是 Web 上的 Outlook) 处理，邮件头中不会标记任何信息。

可以看到，启用"来自我的联系人的信任电子邮件"设置可以减少可以同步的安全发件人和安全收件人的数量。 如果这是一个问题，我们建议使用组策略关闭此功能：

- 文件名：outlk16.opax
- 策略设置 **：信任来自联系人的电子邮件**
