---
title: 从勒索软件攻击中恢复
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- m365solution-ransomware
description: Microsoft 365管理员可以了解如何从勒索软件攻击中恢复。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8e5e942bb39097fffa955d5bb9c3b8a72212d0cc
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "64730829"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>从Microsoft 365中的勒索软件攻击中恢复过来

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

即使你采取一切预防措施来保护你的组织，你仍然可以成为 [勒索软件](/windows/security/threat-protection/intelligence/ransomware-malware) 攻击的受害者。 勒索软件是大生意，在当今的威胁环境中，Microsoft 365是[复杂攻击](https://i.blackhat.com/USA21/Wednesday-Handouts/us-21-Cloudy-With-A-Chance-Of-APT-Novel-Microsoft-365-Attacks-In-The-Wild.pdf)的不断增加的目标。

本文中的步骤将为你提供恢复数据和阻止感染内部传播的最佳机会。 在开始之前，请考虑以下事项：

- 无法保证支付赎金会返回对文件的访问权限。 事实上，支付赎金可以让你成为更多勒索软件的目标。

  如果已付款，但未使用攻击者的解决方案进行恢复，请联系您的银行，看看他们是否可以阻止交易。

  我们还建议向执法部门、诈骗报告网站和 Microsoft 报告勒索软件攻击，如本文后面所述。

- 对你快速应对攻击及其后果非常重要。 等待的时间越长，恢复受影响数据的可能性就越小。

## <a name="step-1-verify-your-backups"></a>步骤 1：验证备份

如果有脱机备份，则可能在从环境中删除勒索软件有效负载 **(** 恶意软件) 以及验证Microsoft 365环境中没有未经授权的访问 **之后**，还原加密的数据。

如果没有备份，或者备份也受到勒索软件的影响，则可以跳过此步骤。

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>步骤 2：禁用Exchange ActiveSync和OneDrive 同步

此处的要点是停止勒索软件的数据加密的传播。

如果怀疑电子邮件是勒索软件加密的目标，请暂时禁用用户对邮箱的访问。 Exchange ActiveSync在设备和Exchange Online邮箱之间同步数据。

若要禁用邮箱的Exchange ActiveSync，[请参阅如何为Exchange Online中的用户禁用Exchange ActiveSync](https://support.microsoft.com/help/2795303)。

若要禁用对邮箱的其他类型的访问，请参阅：

- [为邮箱启用或禁用 MAPI](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。

- [为用户启用或禁用 POP3 或 IMAP4 访问](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

暂停OneDrive 同步将有助于保护云数据免受潜在受感染设备的更新。 有关详细信息，请参阅[如何在OneDrive中暂停和恢复同步](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>步骤 3：从受影响的设备中删除恶意软件

对所有可疑计算机和设备运行完整的当前防病毒扫描，以检测和删除与勒索软件关联的有效负载。

不要忘记扫描正在同步数据的设备或映射网络驱动器的目标。

可以将[Windows Defender](https://www.microsoft.com/windows/comprehensive-security)或 (用于旧客户端) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)。

此外，还可帮助你删除勒索软件或恶意软件的替代方法是 [恶意软件删除工具 (MSRT) ](https://www.microsoft.com/download/details.aspx?id=9905)。

如果这些选项不起作用，可以尝试[Windows Defender脱机](https://support.microsoft.com/help/17466)或[排查检测和删除恶意软件的问题](https://support.microsoft.com/help/4466982)。

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>步骤 4：恢复已清理计算机或设备上的文件

完成上一步以从环境中删除勒索软件有效负载后， (将阻止勒索软件加密或删除文件) ，可以使用Windows 11、Windows 10、Windows 8.1中[的文件历史](https://support.microsoft.com/help/17128)记录，并在 Windows 7 中使用系统保护尝试恢复本地文件和文件夹。

**注意**:

- 某些勒索软件还会加密或删除备份版本，因此不能使用文件历史记录或系统保护来还原文件。 如果发生这种情况，则需要在未受勒索软件或OneDrive影响的外部驱动器或设备上使用备份，如下一部分所述。

- 如果文件夹同步到OneDrive并且未使用最新版本的Windows，则使用文件历史记录可能会有一些限制。

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>步骤 5：恢复OneDrive for Business中的文件

OneDrive for Business中的文件还原允许你在过去 30 天内将整个OneDrive还原到以前的时间点。 有关详细信息，请参阅“还原你的 OneDrive”[](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)。

## <a name="step-6-recover-deleted-email"></a>步骤 6：恢复已删除的电子邮件

在极少数情况下，勒索软件删除了所有电子邮件，你或许可以恢复已删除的项。 有关详细信息，请参阅：

- [恢复用户邮箱中的已删除邮件](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [在 Outlook for Windows 中恢复已删除项目](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>步骤 7：重新启用Exchange ActiveSync和OneDrive 同步

清理计算机和设备并恢复数据后，可以重新启用之前在[步骤 2](#step-2-disable-exchange-activesync-and-onedrive-sync) 中禁用的Exchange ActiveSync和OneDrive 同步。

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>步骤 8 (可选) ：阻止特定文件扩展名的OneDrive 同步

恢复后，可以阻止OneDrive for Business客户端同步受此勒索软件影响的文件类型。 有关详细信息，请参阅 [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>报告攻击

### <a name="contact-law-enforcement"></a>联系执法部门

应联系本地或联邦执法机构。 例如，如果你在美国你可以联系 [FBI 本地外地办事处](https://www.fbi.gov/contact-us/field)、[IC3](http://www.ic3.gov/complaint/default.aspx) 或[特勤局](http://www.secretservice.gov/)。

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>将报表提交到所在国家的诈骗报告网站

诈骗报告网站提供有关如何防止和避免诈骗的信息。 它们还提供机制来报告你是诈骗的受害者。

- 澳大利亚： [SCAMwatch](http://www.scamwatch.gov.au/)

- 加拿大： [加拿大反欺诈中心](http://www.antifraudcentre-centreantifraude.ca/)

- 法国：[法国国家/](http://www.ssi.gouv.fr/)地区

- 德国： [德国联邦议院 Für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- 爱尔兰： [Garda Síochána](http://www.garda.ie/)

- 新西兰： [消费者事务诈骗](http://www.consumeraffairs.govt.nz/scams)

- 瑞士 [国家报 Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)

- 英国： [行动欺诈](http://www.actionfraud.police.uk/)

- 美国：[在线防护](http://www.onguardonline.gov/)

如果您的国家/地区未列出，请询问您的地方或联邦执法机构。

### <a name="submit-email-messages-to-microsoft"></a>将电子邮件提交到 Microsoft

可以使用多种方法之一报告包含勒索软件的网络钓鱼消息。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="additional-ransomware-resources"></a>其他勒索软件资源

来自 Microsoft 的关键信息：

- [日趋严重的勒索软件威胁](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/)，2021 年 7 月 20 日 Microsoft 关于问题的博客文章
- [人工操作的勒索软件](/security/compass/human-operated-ransomware)
- [快速防范勒索软件和勒索](/security/compass/protect-against-ransomware)
- [2021 Microsoft 数字防御报告](https://www.microsoft.com/security/business/microsoft-digital-defense-report)（请参阅第 10-19 页）
- [勒索软件：Microsoft 365 Defender](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/overview)门户中的一份持续威胁分析报告

Microsoft 365：

- [为 Microsoft 365 租户部署勒索软件保护](/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [使用 Azure 和 Microsoft 365 最大化勒索软件复原能力](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [恶意软件和勒索软件防护](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [保护Windows电脑免受勒索软件的侵害](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [在 SharePoint Online 中处理勒索软件](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)
- Microsoft 365 Defender门户中[勒索软件的威胁分析报告](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag)

Microsoft 365 Defender：

- [使用高级搜寻查找勒索软件](/microsoft-365/security/defender/advanced-hunting-find-ransomware)

Microsoft Azure：

- [针对勒索软件攻击的 Azure 防御](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [使用 Azure 和 Microsoft 365 最大化勒索软件复原能力](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [备份和还原计划以防范勒索软件](/security/compass/backup-plan-to-protect-against-ransomware)
- [通过 Microsoft Azure 备份 (](https://www.youtube.com/watch?v=VhLOr2_1MCg) 26 分钟的视频帮助防止勒索软件) 
- [从系统性标识泄露中恢复](/azure/security/fundamentals/recover-from-identity-compromise)
- [Microsoft Sentinel 中的高级多阶段攻击检测](/azure/sentinel/fusion#ransomware)
- [Microsoft Sentinel 中的勒索软件融合检测](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Defender for Cloud Apps：

-  [在 Defender for Cloud Apps 中创建异常检测策略](/cloud-app-security/anomaly-detection-policy)

Microsoft 安全团队博客文章：

- [防范和从勒索软件中恢复的 3 个步骤（2021 年 9 月）](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [抵御人工操作勒索软件的指南：第 1 部分（2021 年 9 月）](https://www.microsoft.com/security/blog/2021/09/20/a-guide-to-combatting-human-operated-ransomware-part-1/)

  有关 Microsoft 检测和响应团队 (DART) 执行勒索软件事件调查的关键步骤。

- [抵御人工操作勒索软件的指南：第 2 部分（2021 年 9 月）](https://www.microsoft.com/security/blog/2021/09/27/a-guide-to-combatting-human-operated-ransomware-part-2/)

  建议和最佳做法。

- [通过了解网络安全风险以增强恢复能力：第 4 部分 - 浏览当前威胁（2021 年 5 月）](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  请参阅 **勒索软件** 部分。

- [人为操作的勒索软件攻击：可预防的灾难（2020 年 3 月）](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  包括对实际攻击的攻击链分析。

- [勒索软件应对 - 是否支付勒索金额？（2019 年 12 月）](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro 以透明方式应对勒索软件攻击（2019 年 12 月）](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
