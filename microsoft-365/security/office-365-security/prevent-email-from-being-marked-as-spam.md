---
title: 如何避免在 Office 365 中发生误报
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 了解如何在 Office 365、Exchange Online 和独立 Exchange Online Protection （EOP）中防止误报并阻止将真实邮件标记为垃圾邮件。
ms.openlocfilehash: 483bad168aa421e3fba4b0cc51e0b2e286f5701d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809234"
---
# <a name="how-to-prevent-good-email-messages-from-being-marked-as-spam-in-office-365"></a>如何避免在 Office 365 中将有效的电子邮件标记为“垃圾邮件”

 **真实电子邮件是否在 Office 365 中被标记为“垃圾邮件”？试试本文中介绍的方法吧。**

如果在 Office 365、Exchange Online 或独立 Exchange Online Protection （EOP）中，将正常传入的电子邮件标记为垃圾邮件（_误报_），则应使用“[报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)”向 Microsoft 报告该邮件。 此外，还可使用“[提交资源管理器](admin-submission.md)”。

## <a name="determine-why-the-message-was-marked-as-spam"></a>确定邮件被标记为垃圾邮件的原因

通过查看邮件头来确定邮件被标记为垃圾邮件的原因，可解决诸多与误报相关的问题。 若要查看邮件头，请参阅“[在 Outlook 中查看 Internet 邮件头](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)”。

具体来说，需要查找名为 “**X-Forefront-Antispam-Report**” 的标头字段。 要查找的重要值有：

- **SFV:SPM**：邮件被反垃圾邮件筛选器（也称“_内容筛选器_”）标记为垃圾邮件。 有关详细信息，请参阅 [Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)。

- **SFV:BLK**：邮件被标记为垃圾邮件，因为发件人的电子邮件地址位于**收件人**的阻止的发件人名单中。 有关详细信息，请参阅“[在 Outlook 网页版中筛选垃圾邮件](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)”和“[垃圾邮件筛选概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)”。

- **SFV:SKS**：邮件在由反垃圾邮件筛选器检查**前**被标记为垃圾邮件。 例如，邮件流规则（也称传输规则）将邮件的垃圾邮件可信度（SCL）设置为高值（9），该值表明邮件是垃圾邮件。 有关 SCL 的详细信息，请参阅“[垃圾邮件可信度](spam-confidence-levels.md)”。

  运行邮件跟踪，确定邮件流规则是否负责高垃圾邮件可信度值。 有关详细信息，请参阅“[安全与合规中心中的邮件跟踪](message-trace-scc.md)”。

- **SFV:SKB**：该邮件被标记为垃圾邮件，因为它与垃圾邮件筛选器策略中的一个阻止条目（例如阻止的发件人或阻止的发件人域）匹配。 有关详细信息，请参阅“[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)”。

- **SFV:BULK**：该邮件被反垃圾邮件筛选器标识为批量电子邮件，而不是垃圾邮件。 如果邮件的批量投诉级别（BCL）值**大于**反垃圾邮件策略设置中设定的批量阈值（较低的 BCL 值表示邮件更可能是垃圾邮件），则会发生这种情况。 可在 **X-Microsoft-Antispam** 标头字段中查看 BCL 值。

  批量电子邮件（也称“_灰色邮件_”）是用户故意或无意请求的不需要的、非恶意营销或广告电子邮件。 不同的用户对如何处理批量电子邮件有不同的预期，因此可创建不同的策略或规则，来相应允许或阻止批量电子邮件。 有关详细信息，请参阅下列主题：

  - [垃圾邮件和批量邮件之间有什么差异？](what-s-the-difference-between-junk-email-and-bulk-email.md)

  - [批量投诉级别值](bulk-complaint-level-values.md)

- **CAT:SPOOF** 或 **CAT:PHISH**：表示邮件具有欺诈性，这意味着消息源无法验证并且可疑。

  如果邮件来自欺骗的发件人，则相应的合法发件人将需要验证其公共 DNS 中的电子邮件域的 SPF 和 DKIM 记录。 有关详细信息，请查看 **Authentication-Results** 标头字段。 尽管很难让所有发件人都使用正确的电子邮件身份验证方法，但绕过这些检查可能非常危险，而且是欺诈和钓鱼邮件的首要原因。

> [!NOTE]
> • 若要详细了解其他反垃圾邮件的标头和数值，参见“[反垃圾邮件邮件头](anti-spam-message-headers.md)”。 <br/><br/>• 未专门介绍的其他标头字段和值只供 Microsoft 反垃圾团队用于诊断用途。 <br/><br/>• 邮件头中的 **X-CustomSpam** 标头字段表示邮件被高级垃圾邮件筛选（ASF）标记为垃圾邮件。 我们正将 ASF 功能移动到筛选堆叠的其他部分，并建议“**关闭**”反垃圾邮件策略中当前可用的 ASF 设置。 有关详细信息，请参阅“[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)”。

## <a name="solutions-for-too-much-spam"></a>垃圾邮件过多的解决方案

为使反垃圾邮件筛选最为有效，管理员需要对组织中的一些设置进行配置。 如果不是管理员，可跳至“用户”部分。

### <a name="for-admins"></a>对于管理员

- **将电子邮件域的 MX 记录指向 Office 365**：为了让 Office 365 提供保护，Office 365 中所有电子邮件域的 MX 记录必须指向 Office 365，并且仅指向 Office 365 （即这些域中的收件人电子邮件始终首先传递至 Office 365）。 如果 MX 记录指向某些其他位置（例如第三方反垃圾邮件解决方案或设备），则 Office 365 无法为用户提供垃圾邮件筛选。 在这种情况下，请考虑创建邮件流规则，绕过对所有邮件进行垃圾邮件筛选（将所有传入邮件的 SCL 值设置为 -1）。 如果稍后决定将 MX 记录指向 Office 365，务必删除此规则。

- **为用户开启报告邮件加载项**：我们强烈建议为用户启用报告邮件加载项。 有关说明，请参阅“[启用报告邮件加载项](enable-the-report-message-add-in.md)”。

- **使用提交资源管理器**：管理员现在可以提交电子邮件以供 Microsoft 扫描。 作为管理员，还可以查看用户发送的反馈。 可使用误报报告中的模式来调整垃圾邮件筛选设置。 有关详细信息，请参阅“[如何将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft 供 Office 365 扫描](admin-submission.md)”。

- **验证用户是否在允许的限制中**，如 Exchange Online 服务说明中的“[接受收和发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)”中所述。

- **验证反垃圾邮件策略中的 BCL 级别**，如本主题中前面所述。

### <a name="for-users"></a>对于用户

- 在 [Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) 或 [Outlook 网页版](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)中**添加发件人至安全发件人列表**。

  Office 365 将使用“安全发件人列表”和“安全收件人列表”，而不是“安全域名列表”。 无论如何将域添加到列表（在Outlook、Outlook 网页版中，或在 Outlook 并随后通过目录同步进行同步），都适用。

- **在 Outlook 中禁用 SmartScreen 筛选**：在较早的 Outlook 桌面版客户端中，请勿在“**垃圾电子邮件选项**”中启用 SmartScreen 筛选。 SmartScreen 筛选更新已于 2016 年 11 月终止。 如果在 Outlook 中启用“**低**”或“**高**”垃圾邮件防护，则使用 SmartScreen 筛选并可能收到误报。 注意，SmartScreen 筛选在新式 Outlook 桌面版客户端中不可用。 有关详细信息，请参阅“[停止为 Outlook 和 Exchange 中的 SmartScreen 提供支持](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/Deprecating-support-for-SmartScreen-in-Outlook-and-Exchange/ba-p/605332)”。

## <a name="troubleshooting-a-message-is-delivered-to-the-junk-email-folder-after-passing-anti-spam-filtering"></a>故障排除：通过反垃圾邮件筛选后，邮件被传递至“垃圾邮件”文件夹

如果用户在其 Outlook 垃圾邮件选项中选中了“**仅安全列表**”选项，无论邮件是否通过了组织的反垃圾邮件筛选，或邮件流规则将邮件标记为非垃圾邮件（SCL 值为 -1），来自不在非用户安全发件人列表或安全收件人列表中人员的所有邮件，都将转至“**垃圾邮件**”文件夹。

在 Outlook 网页版中，收件人将看到黄色安全提示，指示邮件位于“**垃圾邮件**”文件夹中，因为发件人不在安全发件人列表或安全收件人列表中。

邮件头将包含 **X-Forefront-Antispam-Report** 标头字段值 `SFV:SKN` （邮件在由反垃圾邮件筛选器处理前不被标记为垃圾邮件）或 `SFV:NSPM`（反垃圾邮件筛选器确定邮件不是垃圾邮件），但是邮件仍将传递至用户的“**垃圾邮件**”文件夹。

邮件头中没有任何内容表示因为用户的“**仅安全列表**”设置而使邮件传递为垃圾邮件。 但是，可在 Exchange Online PowerShell 中使用 **MailboxJunkEmailConfiguration** cmdlet，查看用户是否仅允许传递来自受信任发件人的邮件至收件箱。

将 \<MailboxIdentity\> 替换为邮箱的名称、别名或电子邮件地址，并在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 中运行以下命令：

```PowerShell
Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
```

- 如果 *TrustedListsOnly* 属性值也是 `True`：不是来自受信任的发件人或收件人的（即不在用户安全发件人列表和安全收件人列表中的人员）邮件将被转至“**垃圾邮件**”文件夹。

- 如果 *ContactsTrusted* 属性值是 `True`：用户的联系人也被标识为受信任的发件人。 如果 *TrustedListsOnly* 属性值也是 `True`，来自用户安全发件人列表、安全收件人列表或联系人的邮件将被转至“**垃圾邮件**”文件夹。

- *TrustedSendersAndDomains* 属性值包含用户的安全发件人列表。

若要更改邮箱中的这些设置，请将 \<MailboxIdentity\> 替换为邮箱的名称、别名或电子邮件地址，并运行以下命令：

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" -TrustedListsOnly $false -ContactsTrusted $false
```

有关语法、参数和所需权限的详细信息，请参阅 [MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-mailboxjunkemailconfiguration) 和 [MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)主题。

## <a name="directory-synchronization-for-standalone-eop-customers"></a>独立 EOP 客户的目录同步

如果使用独立 EOP 来帮助保护你的本地 Exchange 组织，则应使用目录同步将用户设置与服务同步。 执行此操作可确保 EOP 沿用用户安全发件人列表。 有关详细信息，请参阅“[使用目录同步管理邮件用户](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users)”。
