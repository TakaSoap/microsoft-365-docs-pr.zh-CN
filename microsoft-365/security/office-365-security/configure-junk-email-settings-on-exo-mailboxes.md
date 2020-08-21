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
description: 管理员可以了解如何配置 Exchange Online 邮箱中的垃圾邮件设置。 许多这些设置可供 Outlook 或 Outlook 网页版中的用户使用。
ms.openlocfilehash: 171eca8535958f01a7f749ad678e6ea9dd83d80c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825709"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>配置 Exchange Online 邮箱上的垃圾邮件设置

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，组织反垃圾邮件设置由 Exchange Online Protection (EOP) 。 有关详细信息，请参阅 [EOP 中的反垃圾邮件保护](anti-spam-protection.md)。

但是，管理员还可以在 Exchange Online 中的个别邮箱上配置特定的反垃圾邮件设置：

- **启用或禁用垃圾邮件规则：垃圾邮件**规则是一个隐藏的"收件箱"规则，默认情况下，在每个邮箱中启用"垃圾邮件规则"。 垃圾邮件规则控制下列功能：

  - **根据反垃圾邮件策略将邮件移动到"垃圾邮件"文件夹**：当通过操作 **"将** 邮件移至垃圾邮件"文件夹以进行垃圾邮件筛选后，垃圾电子邮件筛选规则会将邮件移动到"垃圾邮件"文件夹之后，垃圾邮件筛选规则会将邮件移至"垃圾邮件"文件夹。 若要详细了解反垃圾邮件策略中的垃圾邮件筛选谓词，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。 同样，如果零时差自动清除 (ZAP) 确定已传递的邮件是垃圾邮件或网络钓鱼邮件，垃圾邮件筛选器规则将邮件移至"垃圾邮件"文件夹，以执行"将邮件移至 **垃圾邮件** "文件夹的垃圾邮件筛选结合操作。 有关 ZAP 的详细信息，请参阅[Exchange Online 中的零时 (自动 (ZAP) 零时差。](zero-hour-auto-purge.md)

  - 用户在 Outlook 或 Web 上的 Outlook 中为**自己配置的垃圾邮件设置**：_安全列表集合_是每个邮箱的安全发件人列表、安全收件人列表和阻止发件人列表。 这些列表中的条目确定垃圾邮件规则是将邮件移动到"收件箱"还是"垃圾邮件"文件夹。 用户可以在 Outlook 中为自己的邮箱配置安全列表集合，或者在 Outlook 网页版中 (称为"Outlook Web App) 。 管理员可以在任何用户邮箱中配置安全列表集合。

在邮箱上启用垃圾邮件规则后，EOP 能够根据垃圾邮件筛选检查检查将邮件移动到"垃圾邮件"文件夹 **。"将邮件移动到邮箱的垃圾邮件** "文件夹或"阻止的发件人"列表中，并根据邮箱 () 上的"安全发件人"列表阻止邮件传递到"垃圾邮件"文件夹。

 禁用邮箱的垃圾邮件规则后，EOP 无法根据垃圾邮件筛选检查检查操作将邮件移动到"垃圾邮件"文件夹或邮箱上的安全列表集合的"垃圾邮件"**Move message to Junk Email folder**文件夹。

管理员可以使用 Exchange Online PowerShell 来禁用、启用和查看邮箱上的垃圾邮件规则状态。 管理员还可以使用 Exchange Online PowerShell 在"安全发件人"列表、"安全收件人"列表和"阻止发件人"列表格式的邮箱 (配置设置通知列表中的) 。

> [!NOTE]
> 来自用户已添加到其自己安全发件人列表中的邮件将跳过作为 EOP 功能的一部分 (而由 SCL 发送的连接筛选) 。 若要防止用户将条目添加到 Outlook 中安全发件人列表中，请使用本主题后面"  [关于 Outlook](#about-junk-email-settings-in-outlook) 中的垃圾邮件设置"部分中所述的组策略。 策略筛选、内容筛选和高级威胁防 (ATP) 检查仍将应用于邮件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 只能使用 Exchange Online PowerShell 执行这些步骤。 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 您必须先拥有权限，然后才能执行这些过程。 具体而说，需要 **"邮件收件人**"角色 (，该角色组默认被分配**Recipient Management****到"组织管理**"、"收件人管理"和"**自定义邮件**收件人"角色组) 或 **"用户选项** ("角色组（默认情况下，分配给**组织**管理角色组和**技术**支持角色组) ）。 若要在 Exchange Online 中将用户添加到角色组，请参阅 [Exchange Online 中的修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。 请注意，具有默认权限的用户可以对其自己的邮箱执行这些相同过程，只要他们有[权访问 Exchange Online PowerShell。](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

- 在 EOP 保护本地 Exchange 邮箱的独立 EOP 环境中，需要在本地 Exchange 中配置邮件流规则（亦称为“传输规则”），以转换 EOP 垃圾邮件筛选裁定，这样垃圾邮件规则才能将邮件移动到“垃圾邮件”文件夹。 有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

- 共享邮箱安全发件人的设计不会同步到 Azure AD 和 EOP。

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>使用 Exchange Online PowerShell 启用或禁用邮箱中的垃圾邮件规则

> [!NOTE]
> 您只能使用 **Set-MailboxJunkEmailConfiguration** cmdlet 来禁用在 Outlook（在"缓存"Exchange 模式中）或 Web 上的 Outlook 中打开的邮箱上的垃圾邮件规则。 如果尚未打开邮箱，您将收到此错误消息： `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` 如果您希望禁止此错误消息进行批量操作，您可以将此错误添加到 `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** 命令。

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
> - 如果用户从未打开过邮箱，则在你运行之前的命令时可能会收到一条错误。 若要禁止此错误消息进行批量操作，请将添加到 `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** 命令。
>
> - 即使您禁用垃圾邮件规则，Outlook 垃圾邮件筛选器 (可以根据其配置的) 如何确定邮件是否为垃圾邮件，也可以根据邮件本身的垃圾邮件判断情况和邮箱上的安全列表集合将邮件移动到"收件箱"或"垃圾邮件"文件夹。 有关详细信息，请参阅本主题中的[有关 Outlook 中的垃圾邮件设置](#about-junk-email-settings-in-outlook)部分。

### <a name="how-do-you-know-this-worked"></a>您如何知道这有效？

若要验证是否已成功启用或禁用邮箱的垃圾邮件规则，请执行以下任一操作：

- 将 _\<MailboxIdentity\>_ 邮箱的名称、别名或电子邮件地址替换，然后运行以下命令来验证 **Enabled** 属性值：

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>使用 Exchange Online PowerShell 配置邮箱的安全列表集合

邮箱的安全列表集合包括"安全发件人"列表、"安全收件人"列表和"阻止的发件人"列表。 默认情况下，用户可以在 Outlook 或 Web 上的 Outlook 中配置自己邮箱的安全列表集合。 管理员可以使用 **Set-MailboxJunkEmailConfiguration** cmdlet 上对应的参数在用户的邮箱上配置安全列表集合。 下表介绍了这些参数。

****

|Set-MailboxJunkEmailConfiguration 上的参数|Outlook 网页版设置|
|---|---|
|_BlockedSendersAndDomains_|**将来自这些发件人或域的邮件移到我的"垃圾邮件"文件夹**|
|_ContactsTrusted_|**信任来自我的联系人的邮件**|
|_TrustedListsOnly_|**仅信任来自我的安全发件人和域列表及安全邮件列表的电子邮件**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**不将来自这些发件人的邮件移到我的"垃圾邮件"文件夹**|
|

<sup>\*</sup>**注意**：

- 在 Exchange Online 中 **，无法** 识别安全发件人列表或 _TrustedSendersAndDomains_ 参数中的域条目，因此仅使用电子邮件地址。 在使用目录同步的独立 EOP 中，域条目默认情况下不同步，但您可以为域启用同步。 有关详细信息，请参阅[KB3019657。](https://support.microsoft.com/help/3019657)

- You can't directly modify the Safe Recipients list by using the **Set-MailboxJunkEmailConfiguration** cmdlet (the _TrustedRecipientsAndDomains_ parameter doesn't work) . 修改"安全发件人"列表后，这些更改将同步到"安全收件人"列表。

若要配置邮箱的安全列表集合，请使用以下语法：

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

若要输入多个值并覆盖 _BlockedSendersAndDomains 和_ _TrustedSendersAndDomains 参数的任何现有条目_ ，请使用以下语法 `"<Value1>","<Value2>"...` ： 若要在不影响其他现有条目的情况下添加或移除一个或多个值，请使用以下语法： `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

本示例在 Ori Epstein 的邮箱上配置以下安全列表集合的设置：

- 将该值添加到shopping@fabrikam.com发件人"列表中。

- 删除包含chris@fourthcoffee.com"安全发件人"列表和"安全收件人"列表中的值。

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
> - 如果用户从未打开过邮箱，则在你运行之前的命令时可能会收到一条错误。 若要禁止此错误消息进行批量操作，请将添加到 `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** 命令。
>
> - 即使禁用了邮箱的垃圾邮件规则，您仍然可以配置安全列表集合中，且 Outlook 垃圾邮件筛选器可以将邮件移动到"收件箱"或"垃圾邮件"文件夹。 有关详细信息，请参阅本主题中的[关于 Outlook 中的配置垃圾邮件设置](#about-junk-email-settings-in-outlook)部分。
>
> - The Outlook Junk Email Filter has additional safelist collection settings (for example， **Automatically add people I email to the Safe Senders list**) . For more information, see [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>您如何知道这有效？

若要验证是否已成功配置邮箱的安全列表集合，请执行以下任一操作：

- _\<MailboxIdentity\>_ 将邮箱的名称、别名或电子邮件地址替换，并运行以下命令来验证属性值：

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  如果值列表过长，请使用以下语法：

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>关于 Outlook 中的配置垃圾邮件设置

若要启用、禁用及配置在 Outlook 中可以使用的客户端"垃圾邮件筛选器"设置，请使用"组策略"。 有关详细信息，请参阅"管理 [模板文件 (ADMX/ADML) >"和"适用于 Microsoft 365 企业应用版、Office 2019"和"Office 2016"的 Office 自定义工具](https://www.microsoft.com/download/details.aspx?id=49030) ，以及如何使用组策略部署垃圾邮件 [设置（如"安全发件人"列表](https://support.microsoft.com/help/2252421)）。

当"Outlook 垃圾邮件筛选器"设置为**默认值"不再自动**筛选**主**垃圾邮件选项 \> **Junk** \> **Junk E-Mail Options** \> **选项"时**，Outlook 不会尝试将封有掩答分类为垃圾邮件，但仍使用安全列表集合 (安全列表、安全收件人列表和"阻止的发件人列表) "在传递后将邮件移动到"垃圾邮件"文件夹。 有关这些设置的详细信息，请参阅垃圾邮件 [筛选器概述](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。

When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder. 此垃圾邮件分类不同于由 EOP 确定的 (SCL) SCL 可信度。 事实上，Outlook 会忽略来自 EOP (中的 SCL，除非 EOP 将邮件标记为跳过垃圾邮件筛选) 并使用其自身的标准来确定邮件是否是垃圾邮件。 当然，EOP 和 Outlook 的垃圾邮件的验证可能相同。 有关这些设置的详细信息，请参阅" [更改垃圾邮件筛选器"中的保护级别](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。

> [!NOTE]
> 2016 年 11 月，Microsoft 停止为 Exchange 和 Outlook 中的 SmartScreen 筛选器生成垃圾邮件定义更新。 现有的 SmartScreen 垃圾邮件定义已就位，但其效力可能会随时间的过时下降。 有关详细信息，请参阅“[停止为 Outlook 和 Exchange 中的 SmartScreen 提供支持](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)”。

因此，即使禁用了邮箱的垃圾邮件规则，Outlook 垃圾邮件筛选器也可以使用邮箱的安全列表集合和其自身的垃圾邮件分类将邮件移动到"垃圾邮件"文件夹。

Outlook 和 Web 上的 Outlook 同等支持安全列表集合。 安全列表集合是在 Exchange Online 邮箱中保存，因此安全列表集合在 Outlook 中的更改会出现在 Web 上的 Outlook 中，反之亦如此。

## <a name="limits-for-junk-email-settings"></a>垃圾邮件设置限制

安全列表集合 (在用户邮箱中存储的"安全发件人"列表、"安全收件人") 安全发件人列表和"阻止的发件人"列表功能也会同步到 EOP。 通过目录同步，安全列表集合将同步到 Azure AD。

- 用户邮箱中的安全列表集合的限制为 510 KB，其中包括所有列表以及其他垃圾邮件筛选器设置。 如果用户超过此限制，将收到一个如下所示的 Outlook 错误：

  > 无法/无法添加到服务器的垃圾邮件列表中。 超过该服务器上允许的大小。 除非您将垃圾邮件列表减少为服务器所允许的大小，否则，服务器上的垃圾邮件筛选器将一直处于禁用状态。

  有关此限制及其更改方法的详细信息，请参阅[KB2669081。](https://support.microsoft.com/help/2669081)

- EOP 中的同步安全列表集合具有以下同步限制：

  - 1024 个条目中：如果我的联系人发送的电子邮件已启用，则安全发件人列表、 **安全收件人列表和外部联系人中的** 条目就是 1024 个。
  - "阻止的发件人"列表和"阻止的域"列表中的条目总数为 500 个。

  达到 1024 个条目限制时，会发生以下情况：

  - 该列表停止接受 PowerShell 和 Web 上的 Outlook 中的条目，但不显示任何错误。

    Outlook 用户可以继续添加 1024 个以上的条目，直到达到 Outlook 限制 510 KB。 Outlook 可以使用这些其他条目，只要在发送至邮箱 (邮件流规则、反欺骗等服务之前，EOP 筛选器不会阻止 ) 邮件。

- 通过目录同步，条目将按以下顺序同步到 Azure AD：

  1. 信任我的 **联系人发送的电子邮件已启用** 的邮件联系人。
  2. 每当对前 1024 个条目进行更改时，都将组合、取消重复的安全发件人列表和安全收件人列表，并按字母顺序排序。

  使用前 1024 个条目，并在邮件头中标记相关信息。

  未同步到 Azure AD 的超过 1024 个条目由 Outlook (（而不是 Outlook 网页版) 处理，并且邮件头中没有任何信息标记。

如你所见，启用 **来自我的联系人的"信任"** 电子邮件会减少可以同步的安全发件人和安全收件人数。 如果你需要考虑此问题，我们建议使用组策略关闭此功能：

- 文件名：outlk16.opax
- 策略设置 **：信任来自联系人的电子邮件**
