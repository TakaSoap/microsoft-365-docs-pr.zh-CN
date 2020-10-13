---
title: 从勒索软件攻击中恢复
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft 365 管理员可以了解如何从勒索软件攻击中恢复。
ms.openlocfilehash: c9a8e1035e00509f5c57b8699966544b60b7f9c1
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430605"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>在 Microsoft 365 中从勒索软件攻击中恢复

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


即使您在保护组织时采取了任何预防措施，仍可成为 [勒索软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) 攻击的牺牲品。 勒索软件是大型企业，攻击的验证非常复杂。

本主题中的步骤将为您提供恢复由勒索软件加密的数据的最佳机会，并帮助停止组织中的感染的传播。 在开始之前，请考虑以下事项：

- 不能保证付款勒索将返回对您的文件的访问权限。 实际上，支付勒索可以使您成为更多勒索软件的目标。 如果你已支付，但你可以成功恢复文件，而无需使用攻击者的解决方案，则应致电你的银行以了解它们是否可以阻止事务。 此外，我们还建议您将勒索软件攻击报告给执法部门、诈骗报告网站和 Microsoft，如本主题后面所述。

- 快速响应攻击及其后果非常重要。 等待时间越长，可以恢复受影响数据的可能性就越小。

## <a name="step-1-verify-your-backups"></a>步骤1：验证备份

如果您具有脱机备份，则在从您的环境中删除勒索软件有效负载 (恶意软件) **后** ，可能会还原加密的数据。

如果你没有备份，或者你的备份也受到勒索软件的影响，则可以跳过此步骤。

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>步骤2：禁用 ActiveSync 和 OneDrive 同步

此处的关键点是停止勒索软件的数据加密传播。

如果您怀疑电子邮件是目标，应暂时禁用用户对邮箱的访问。 移动设备使用 Exchange ActiveSync 在设备与 Exchange Online 邮箱之间同步数据。

若要禁用邮箱的 ActiveSync，请参阅 [如何在 Exchange Online 中禁用用户的 Exchange activesync](https://support.microsoft.com/help/2795303)。

若要禁用对邮箱的其他类型的访问，请参阅：

- [启用或禁用邮箱的 MAPI](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。

- [对用户启用或禁用 POP3 或 IMAP4 访问](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

暂停 OneDrive 同步将有助于防止可能受感染的设备更新你的云数据。 有关详细信息，请参阅 [如何暂停和恢复 OneDrive 中的同步](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>步骤3：从受影响的设备中删除恶意软件

在所有可疑计算机和设备上运行完整的防病毒扫描，以检测和删除与勒索软件相关联的有效负载。 不要忘记正在同步数据的设备，或者在需要扫描的已映射网络驱动器的目标 (这些计算机和设备也) 。

您可以将 [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) 或 (用于旧客户端) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)。

另一种方法也可帮助您删除勒索软件或恶意软件，这是 [ (MSRT) 的恶意软件删除工具 ](https://www.microsoft.com/download/details.aspx?id=9905)。

如果这些选项不起作用，可以尝试让 [Windows Defender 脱机](https://support.microsoft.com/help/17466) 或 [解决检测和删除恶意软件的问题](https://support.microsoft.com/help/4466982)。

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>步骤4：在已清理的计算机或设备上恢复文件

在完成上一步以从环境中删除勒索软件负载时 (这将阻止勒索软件加密或删除文件) ，可以使用 windows 10 中的 Windows 10 和 Windows 8.1 中的 [文件历史记录](https://support.microsoft.com/help/17128) 或 windows 7 中的系统保护尝试恢复您的本地文件和文件夹。

**注意**：

- 有些勒索软件还将加密或删除备份版本，因此不能使用文件历史记录或系统保护来还原文件。 如果发生这种情况，您需要在不受勒索软件或 OneDrive 影响的外部驱动器或设备上使用备份，如下一节中所述。

- 如果将文件夹同步到 OneDrive，并且未使用最新版本的 Windows，则可能会有一些使用文件历史记录的限制。

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>步骤5：在 OneDrive for Business 中恢复文件

通过 OneDrive for Business 还原文件，可以在过去的30天内将整个 OneDrive 还原到以前的时间点。 有关详细信息，请参阅 [还原 OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)。

## <a name="step-6-recover-deleted-email"></a>步骤6：恢复已删除的电子邮件

在少数情况下，勒索软件删除了所有电子邮件，您可能可以恢复已删除的项目。 有关更多信息，请参阅：

- [恢复用户邮箱中的已删除邮件](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [在 Outlook for Windows 中恢复已删除项目](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>步骤7：重新启用 Exchange ActiveSync 和 OneDrive 同步

在清理了计算机和设备并恢复了数据之后，可以重新启用您之前在 [步骤 2](#step-2-disable-activesync-and-onedrive-sync)中禁用的 ActiveSync 和 OneDrive 同步。

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>第8步 (可选) ：阻止特定文件扩展名的 OneDrive 同步

恢复后，可以阻止 OneDrive for Business 客户端同步受此勒索软件影响的文件类型。 有关详细信息，请参阅 [get-spotenantsyncclientrestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>报告攻击

### <a name="contact-law-enforcement"></a>联系执法部门

您应联系当地或联邦法律实施机构。 例如，如果你处于美国，你可以联系 [FBI local field](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) 或 [Secret Service](http://www.secretservice.gov/)。

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>将报告提交到你的国家/地区的骗局报告网站

诈骗报告网站提供有关如何阻止和避免诈骗的信息。 它们还提供了在您受到诈骗攻击时报告的机制。

- 澳大利亚： [SCAMwatch](http://www.scamwatch.gov.au/)

- 加拿大： [加拿大反欺诈中心](http://www.antifraudcentre-centreantifraude.ca/)

- 法国： [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- 德国： [Bundesamt Für Sicherheit in Der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- 爱尔兰： [Garda Síochána](http://www.garda.ie/)

- 新西兰： [消费者事务诈骗](http://www.consumeraffairs.govt.nz/scams)

- 英国： [操作欺诈](http://www.actionfraud.police.uk/)

- 美国：[在保护联机](http://www.onguardonline.gov/)状态

如果未列出你的国家/地区，请咨询当地或联邦法律实施机构。

### <a name="submit-email-messages-to-microsoft"></a>将电子邮件提交给 Microsoft

您可以使用几种方法之一报告包含勒索软件的网络钓鱼邮件。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="see-also"></a>另请参阅

- [软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [勒索软件响应—要支付还是不支付？](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro 使用透明度响应勒索软件攻击](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [你的 OneDrive 中的勒索软件检测和恢复文件](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft 安全研究报告](https://www.microsoft.com/securityinsights/)

- [启用或禁用 Office 文件中的宏](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [EOP 和 Office 365 ATP 安全性的建议设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [值得升级： Windows 10 上的下一代安全性证明可在2017中对勒索软件发作进行恢复](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [没有 ma，Samas：此勒索软件的 modus operandi 中有什么？](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Locky 恶意软件，幸运的是要避免它](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT 2016 年7月： Cerber 勒索软件](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Cerberus Cerber 勒索软件的三个头部](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [ () Da Vinci 代码影响的 Troldesh 勒索软件](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
