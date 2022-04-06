---
title: 配置 Exchange Online 邮箱上的垃圾邮件设置
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何配置邮箱中的垃圾邮件Exchange Online设置。 这些设置中的许多设置都可供 Outlook 或 Outlook 网页版。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9e2db8fc6c88e3945081d3b2800aa5ea9cd57a11
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682452"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>配置 Exchange Online 邮箱上的垃圾邮件设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在Microsoft 365拥有邮箱的组织Exchange Online，组织反垃圾邮件设置由 Exchange Online Protection (EOP) 。 有关详细信息，请参阅 [EOP 中的反垃圾邮件保护](anti-spam-protection.md)。

但是，管理员还可以在邮箱中的单个邮箱上配置特定的反垃圾邮件Exchange Online：

> [!NOTE]
> EOP 现在使用自己的邮件流传递代理将邮件路由到"垃圾邮件"文件夹，而不是使用垃圾邮件规则。 **Set-MailboxJunkEmailConfiguration** cmdlet 上的 _Enabled_ 参数不再对邮件流有任何影响。 EOP 根据反垃圾邮件策略中设置的操作路由邮件。 用户的发件人保险箱阻止的发件人列表将继续照常工作。

- **根据** 反垃圾邮件策略将邮件移动到"垃圾邮件"文件夹：当使用"将邮件移动到垃圾邮件文件夹"操作配置反垃圾邮件策略以做出垃圾邮件筛选裁定时，邮件在传递到邮箱后将移动到"垃圾邮件"文件夹。 有关反垃圾邮件策略中的垃圾邮件筛选裁定详细信息，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。 同样，如果零时差自动清除 (ZAP) 确定已传递的邮件是垃圾邮件或网络钓鱼邮件，则邮件将移动到"垃圾邮件"文件夹，以执行"将邮件移动到垃圾邮件文件夹"垃圾邮件筛选裁定操作。 有关 ZAP 详细信息，请参阅 EXCHANGE ONLINE 中的零时[差自动清除 (ZAP) 。](zero-hour-auto-purge.md)

- 用户在 **Outlook 或 Outlook 网页版** 中为自己配置的垃圾邮件设置：安全列表集合是每个邮箱上的 保险箱 发件人列表、保险箱 收件人列表和阻止的发件人列表。 这些列表的条目确定邮件是移动到"收件箱"还是"垃圾邮件"文件夹。 用户可以在邮箱中为其自己的邮箱配置安全列表集合Outlook Outlook 网页版 (以前称为Outlook Web App) 。 管理员可以在任何用户的邮箱上配置安全列表集合。

EOP 能够根据垃圾邮件筛选裁定操作将邮件移动到"垃圾邮件"文件夹或邮箱上的"阻止的发件人"列表，并基于邮箱) 上的 保险箱 发件人列表阻止邮件传递到"垃圾邮件"文件夹 (。

管理员可以使用 Exchange Online PowerShell 配置邮箱的安全列表集合中的条目 (保险箱 发件人列表、保险箱 收件人列表和阻止的发件人) 。

> [!NOTE]
> 来自用户已添加到其自己的发件人列表的保险箱发件人的邮件将跳过作为 EOP 的一部分的内容筛选 (SCL 为 -1) 。 若要阻止用户向 Outlook 中的 保险箱 发件人列表添加条目，请使用本文稍后的关于 [Outlook](#about-junk-email-settings-in-outlook) 中的垃圾邮件设置部分中提到的组策略。 策略筛选、内容筛选和 defender Office 365检查仍将应用于邮件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 只能使用 Exchange Online PowerShell 执行本文中的过程。 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 您需在Exchange Online权限，然后才能执行本文中的过程。 具体来说，您需要"邮件收件人"角色 (该角色默认情况下分配给"组织管理"、"收件人管理"和"自定义邮件收件人"角色组) 或"用户选项"角色 (该角色默认分配给"组织管理"和"技术支持"角色组) 。   若要将用户添加到角色角色Exchange Online，请参阅修改[角色Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups)。 请注意，具有默认权限的用户可以在其自己的邮箱上执行这些相同的过程，只要他们有权访问 [Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)。

- 在 EOP 保护本地 Exchange 邮箱的混合环境中，需要在本地 Exchange 中配置邮件流规则（也称为传输规则）。这些邮件流量规则转换 EOP 垃圾邮件筛选裁定，以便邮箱中的垃圾邮件规则可以将邮件移动到垃圾邮件文件夹。有关详细信息，请参阅 [配置 EOP 以将垃圾邮件传递到混合环境中的垃圾邮件文件夹](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。

- 保险箱共享邮箱的发件人不会根据设计Azure AD与 EOP 同步。

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>使用 Exchange Online PowerShell 配置邮箱的安全列表集合

邮箱的安全列表集合包括"安全发件人"列表、"安全收件人"列表和"阻止的发件人"列表。 默认情况下，用户可以在邮箱或邮箱中配置自己的Outlook Outlook 网页版。 管理员可以使用 **Set-MailboxJunkEmailConfiguration** cmdlet 上对应的参数在用户的邮箱上配置安全列表集合。 下表介绍了这些参数。

|上Set-MailboxJunkEmailConfiguration|Outlook 网页版设置|
|---|---|
|_BlockedSendersAndDomains_|**将来自这些发件人或域的邮件移到我的"垃圾邮件"文件夹**|
|_ContactsTrusted_|**信任来自我的联系人的邮件**|
|_TrustedListsOnly_|**仅信任来自我的发件人和保险箱列表中地址的电子邮件，保险箱邮件列表**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**不要将来自这些发件人的电子邮件移动到我的"垃圾邮件"文件夹**|

<sup>\*</sup>**注意**：

- 在 **Exchange Online中，** 无法识别 保险箱 发件人列表或 _TrustedSendersAndDomains_ 参数中的域条目，因此只能使用电子邮件地址。 在具有目录同步的独立 EOP 中，默认情况下不会同步域条目，但您可以为域启用同步。 有关详细信息，请参阅 [KB3019657](https://support.microsoft.com/help/3019657)。
- 不能通过使用 **Set-MailboxJunkEmailConfiguration** cmdlet (_TrustedRecipientsAndDomains_ 参数不能直接修改 保险箱 收件人列表) 。 修改"安全发件人"列表后，这些更改将同步到"安全收件人"列表。

若要配置邮箱的安全列表集合，请使用以下语法：

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

若要输入多个值并覆盖 _BlockedSendersAndDomains_ 和 _TrustedSendersAndDomains_ 参数的任何现有条目，请使用以下语法： `"<Value1>","<Value2>"...`。 若要添加或删除一个或多个值而不影响其他现有条目，请使用以下语法： `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

本示例在 Ori Epstein 的邮箱上配置以下安全列表集合的设置：

- 将值 shopping@fabrikam.com 阻止的发件人列表。
- 从"chris@fourthcoffee.com 发件人保险箱和"收件人"保险箱值。
- 在"联系人"文件夹中配置被视为受信任的发件人的联系人。

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

本示例将域 contoso.com 从组织中所有用户的邮箱的"阻止的发件人"名单中删除。

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

有关语法和参数的详细信息，请参阅 [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration)。

> [!NOTE]
>
> - 如果用户从未打开过邮箱，则当您运行之前的命令时，您可能会收到错误。 若要禁止批量操作出现此错误，请 `-ErrorAction SilentlyContinue` 添加到 **Set-MailboxJunkEmailConfiguration** 命令。
> - The Outlook Junk Email Filter has additional safelist collection settings (for example， **Automatically add people I email to the 保险箱 Senders list**) . For more information, see [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>您如何知道这有效？

若要验证是否已成功配置邮箱的安全列表集合，请执行以下任一操作：

- 将 _\<MailboxIdentity\>_ 替换为邮箱的名称、别名或电子邮件地址，并运行以下命令来验证属性值：

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  如果值列表太长，请使用以下语法：

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>关于 Outlook 中的配置垃圾邮件设置

若要启用、禁用及配置在 Outlook 中可以使用的客户端"垃圾邮件筛选器"设置，请使用"组策略"。 有关详细信息，请参阅 Microsoft 365 企业应用版、[Office 2019 和 Office 2016 的管理模板文件 (ADMX/ADML) 和 Office](https://www.microsoft.com/download/details.aspx?id=49030) 自定义工具以及如何使用组策略部署垃圾邮件设置，如 [保险箱 发件人列表](https://support.microsoft.com/help/2252421)。

当"Outlook  \>  \>  \> 垃圾邮件筛选器"设置为默认值"主页垃圾邮件选项"中的"自动筛选"时，Outlook 不会尝试将邮件分类为垃圾邮件，但仍使用安全列表集合 ("保险箱发件人"列表保险箱 收件人列表和阻止的发件人) ，以在邮件传递后将邮件移动到"垃圾邮件"文件夹。 有关这些设置详细信息，请参阅 [垃圾邮件筛选器概述](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。

When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder. 此垃圾邮件分类独立于由 EOP (SCL) 的垃圾邮件可信度。 事实上，Outlook EOP (SCL，除非 EOP 将邮件标记为跳过垃圾邮件筛选) 并使用自己的条件来确定邮件是否是垃圾邮件。 当然，来自 EOP 和 EOP 的垃圾邮件裁定可能Outlook相同。 有关这些设置详细信息，请参阅更改垃圾邮件 [筛选器中的保护级别](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。

> [!NOTE]
> 2016 年 11 月，Microsoft 停止为 Exchange 和 Outlook 中的 SmartScreen 筛选器生成垃圾邮件定义更新。 现有的 SmartScreen 垃圾邮件定义已就位，但其有效性可能会随着时间的推移而降低。 有关详细信息，请参阅“[停止为 Outlook 和 Exchange 中的 SmartScreen 提供支持](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)”。

因此，Outlook垃圾邮件筛选器可以使用邮箱的安全列表集合及其自己的垃圾邮件分类将邮件移动到"垃圾邮件"文件夹。

Outlook 和 Web 上的 Outlook 同等支持安全列表集合。 安全列表集合保存在安全Exchange Online中，因此对安全列表集合Outlook的更改将显示在Outlook 网页版中，反之亦然。

## <a name="limits-for-junk-email-settings"></a>垃圾邮件设置的限制

存储在 (中的 保险箱 发件人列表、保险箱 收件人列表和阻止的发件人列表) 安全列表集合也会同步到 EOP。 通过目录同步，安全列表集合将同步到Azure AD。

- 用户邮箱中的安全列表集合限制为 510 KB，其中包括所有列表，以及其他垃圾邮件筛选器设置。 如果用户超过此限制，他们将收到Outlook如下所示的错误：

  > 无法/无法添加到服务器垃圾邮件列表。 您超过服务器上允许的大小。 在服务器上禁用垃圾邮件筛选器，直到垃圾邮件列表减小到服务器允许的大小。

  有关此限制以及如何更改它的信息，请参阅 [KB2669081](https://support.microsoft.com/help/2669081)。

- EOP 中的同步安全列表集合具有以下同步限制：
  - 如果启用了"信任来自我的联系人的电子邮件"，保险箱发件人列表、保险箱 收件人"列表和外部联系人中的总条目数为 1024。
  - "阻止的发件人"列表和"阻止的域"列表中的总条目数为 500。

  当达到 1024 条目限制时，将发生以下情况：

  - 该列表将停止接受 PowerShell 和 Outlook 网页版条目，但不显示任何错误。

    Outlook可以继续添加 1024 多个条目，直到达到 510 KB Outlook限制。 Outlook EOP 筛选器在传递至邮箱之前没有阻止邮件， (邮件流规则、反欺骗等，就可以使用这些附加条目) 。

- 通过目录同步，条目将按以下Azure AD同步到目录：
  1. 如果启用" **信任来自我的联系人的电子邮件"，则邮件** 联系人。
  2. 只要保险箱 1024 个条目保险箱，"发件人"列表和"收件人"列表就会组合、取消重复和按字母顺序排序。

  使用前 1024 个条目，相关信息标记在邮件头中。

  超过 1024 个且未同步到 Azure AD条目由 Outlook (处理Outlook 网页版) ，并且邮件头中不会标记任何信息。

如你所见，启用"信任来自我的联系人的电子邮件"设置可以减少可同步保险箱发件人保险箱收件人数。 如果这是一个问题，我们建议使用组策略关闭此功能：

- 文件名：outlk16.opax
- 策略设置 **：信任来自联系人的电子邮件**
