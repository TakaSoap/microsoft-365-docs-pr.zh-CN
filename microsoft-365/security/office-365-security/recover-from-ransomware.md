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
description: Microsoft 365 管理员可以了解如何从勒索软件攻击中进行恢复。
ms.openlocfilehash: 2f8e5f5deb18cadfaea7acc1cffe73abbc43010b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827829"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>从 Microsoft 365 中的勒索软件攻击中恢复

即使你对组织采取全面预防措，你仍可以受到 [勒索软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) 攻击。 勒索软件的业务需要一定的业务，并验证了这一攻击。

本主题中的步骤可为你提供最佳机会来恢复勒索软件加密的数据，并且有助于停止组织中感染的分布。 在开始之前，请考虑以下事项：

- 无法保证支付勒索会返回对你的文件的访问权限。 事实上，支付勒索软件可使你成为更有机索软件的目标。 如果你已支付，但能够成功恢复文件，而无需使用攻击者的解决方案，则应调用银行来查看他们是否会阻止该事务。 我们还建议您如本主题后面所述，向法律强制、发布报告网站和 Microsoft 报告勒索软件攻击。

- 务必快速响应攻击及其后果。 您等待的时间就长，就是恢复受影响的数据的可能性就就就就是。

## <a name="step-1-verify-your-backups"></a>步骤 1：验证备份

如果您具有脱机备份，则当您从环境中删除勒索软件负载或恶意软件解决方案**after** (预) 数据后，您可能需要还原加密数据。

如果没有备份，或者备份也受勒索软件影响，则可跳过此步骤。

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>步骤 2：禁用 ActiveSync 和 OneDrive 同步

此处的要点是阻止勒索软件对数据加密进行分段的分布。

如果您要将某封电子邮件作为目标，则应临时禁用用户对邮箱的访问。 Exchange ActiveSync用于移动设备同步设备与 Exchange Online 邮箱之间的数据。

若要禁用邮箱的 ActiveSync，请参阅 ["如何在 Exchange Online Exchange ActiveSync用户"禁用此设置](https://support.microsoft.com/help/2795303)。

若要禁用邮箱的其他类型的访问，请参阅：

- [为邮箱启用或禁用 MAPI。](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [对用户启用或禁用 POP3 或 IMAP4 访问](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

暂停 OneDrive 同步有助于防止云数据被潜在感染的设备进行更新。 有关详细信息，请参阅"[如何在 OneDrive 中暂停和恢复同步"。](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>步骤 3：从受影响的设备中删除恶意软件

在所有可配置的计算机和设备上使用最新更新运行完整的防病毒扫描，以检测和删除与勒索软件关联的负载。 不要禁记同步数据的设备，或出于 (这些计算机和设备的映射网络驱动器的目标，也不要) 。

可以使用旧 [Windows Defender (](https://www.microsoft.com/windows/comprehensive-security) 的旧版客户端 [) Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)。

另外，可帮助你删除勒索软件或恶意软件的备用方法是[MSRT 软件 (工具) 。 ](https://www.microsoft.com/download/details.aspx?id=9905)

如果这些选项不起作用，您可以[尝试尝试使用Windows Defender脱机](https://support.microsoft.com/help/17466)[，或解决与检测和删除恶意软件有关的问题](https://support.microsoft.com/help/4466982)。

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>步骤 4：恢复已清除计算机或设备上的文件

在你完成上一步骤以从你的环境中删除勒索软件负载 (这样会阻止勒索软件加密或删除文件) ; [你可以在](https://support.microsoft.com/help/17128) Windows 7 中使用 Windows 10 和 Windows 8.1 或 System Protection 中的文件历史记录来尝试恢复你的本地文件和文件夹。

**注意**：

- 某些勒索软件还将加密或删除备份版本，因此无法使用文件历史记录或系统保护来还原文件。 如果发生这种情况，需要在不受勒索软件或 OneDrive 影响的外部驱动器或设备上使用备份，如下一节所述。

- 如果文件夹同步到 OneDrive，并且你未使用最新版本的 Windows，则与文件历史记录有一些限制。

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>步骤 5：恢复 OneDrive for Business 中的文件

OneDrive for Business 中的"文件还原"允许将整个 OneDrive 还原到过去 30 天的前一时点。 有关详细信息，请参阅"[还原 OneDrive"。](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="step-6-recover-deleted-email"></a>步骤 6：恢复已删除的电子邮件

在少数情况下，勒索软件删除了所有电子邮件，你可能会恢复已删除的项目。 有关详细信息，请参阅：

- [恢复用户邮箱中的已删除邮件](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [在 Outlook for Windows 中恢复已删除项目](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>步骤 7：重新启用 Exchange ActiveSync OneDrive 同步

在清理计算机和设备并恢复数据后，可重新启用之前在步骤 2 中禁用的 ActiveSync 和 OneDrive [同步](#step-2-disable-activesync-and-onedrive-sync)。

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>步骤 8 (可选) ：针对特定文件扩展名阻止 OneDrive 同步

恢复后，您可以防止 OneDrive for Business 客户端同步受此勒索软件影响的文件类型。 有关详细信息，请参阅 [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>报告攻击

### <a name="contact-law-enforcement"></a>联系人法律强制实施

您应与当地或法国法律机构联系。 例如，如果你在美国，可以联系 [FBI 本地字段办](https://www.fbi.gov/contact-us/field)公局 [IC3](http://www.ic3.gov/complaint/default.aspx) [或机业服务](http://www.secretservice.gov/)。

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>向您所在国家/地区的头报告网站提交报告

上标报告网站提供有关如何防护和避免上标的信息。 如果是外围环境的受损人，则它们还提供报告的机制。

- 澳大利亚 [：SCAMwatch](http://www.scamwatch.gov.au/)

- 加拿大 [：加拿大反片 Centre](http://www.antifraudcentre-centreantifraude.ca/)

- 法国 [：Agence nationale de la sécurité des systémes d'information](http://www.ssi.gouv.fr/)

- 德国 [：Bundesamt fár Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- [Ireland：Garda Sáochána](http://www.garda.ie/)

- 新西亚： [消费者信标](http://www.consumeraffairs.govt.nz/scams)

- 英国： [操作 Fraud](http://www.actionfraud.police.uk/)

- 美国：在线 [防护联机](http://www.onguardonline.gov/)

如果未列出你所在国家/地区，请询问当地或分部法律机构。

### <a name="submit-email-messages-to-microsoft"></a>将电子邮件提交给 Microsoft

您可以使用多种方法之一报告包含勒索软件的网络钓鱼邮件。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="see-also"></a>另请参阅

- [勒索软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [勒索软件响应 — 支付付费用？](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro 响应透明度的勒索软件攻击](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [在 OneDrive 中进行勒索软件检测和恢复文件](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft 安全智能报告](https://www.microsoft.com/securityinsights/)

- [启用或禁用 Office 文件中的宏](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [EOP 和 Office 365 ATP 安全的建议设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [值得的升级：Windows 10 上的下一代安全在 2017 年证明复原可以抵御勒索软件发感](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [无 Mas，Samas：此勒索软件操作数中的内容是什么？](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [锁定恶意软件，蓝牙以避免](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT 2016：Cerber 勒索软件](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [类似于 Cerberus 的 Cerberus 的三个耳机](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [受 (日感大国 (的) 件勒索软件](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
