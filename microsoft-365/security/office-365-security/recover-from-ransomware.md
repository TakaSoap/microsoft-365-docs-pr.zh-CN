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
description: Microsoft 365管理员可以了解如何从勒索软件攻击中恢复。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: da9b53aec47231446571a2ae5852bed842311079
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60552676"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>从 Microsoft 365 中的勒索软件攻击中Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

即使你采取一切预防措施来保护你的组织，你仍然可能会遭受勒索软件 [攻击](/windows/security/threat-protection/intelligence/ransomware-malware) 。 勒索软件是一项大业务，在当今的威胁Microsoft 365是复杂攻击[的不断增加的目标](https://i.blackhat.com/USA21/Wednesday-Handouts/us-21-Cloudy-With-A-Chance-Of-APT-Novel-Microsoft-365-Attacks-In-The-Wild.pdf)。

本文中的步骤将为您提供恢复数据和停止内部感染传播的最佳机会。 在开始之前，请考虑以下事项：

- 无法保证支付勒索金额将返回对文件的访问权限。 事实上，支付勒索金额可能会成为更多勒索软件的目标。

  如果已付款，但在没有使用攻击者的解决方案的情况下恢复，请与银行联系，看看他们能否阻止交易。

  我们还建议您向执法机构、欺诈报告网站和 Microsoft 报告勒索软件攻击，如本文稍后所述。

- 快速响应攻击及其后果非常重要。 等待的时间越长，恢复受影响数据的可能性就越小。

## <a name="step-1-verify-your-backups"></a>步骤 1：验证备份

如果你有脱机备份，你可能会在从环境中删除勒索软件有效负载 (恶意软件) 后，以及验证 Microsoft 365 环境中没有未经授权的访问后还原加密数据。 

如果没有备份，或者备份也受勒索软件影响，可以跳过此步骤。

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>步骤 2：禁用Exchange ActiveSync和OneDrive 同步

此处的关键点就是阻止勒索软件传播数据加密。

如果您怀疑电子邮件是勒索软件加密的目标，请暂时禁用用户对邮箱的访问。 Exchange ActiveSync在设备和邮箱之间Exchange Online数据。

若要禁用Exchange ActiveSync，请参阅如何为邮箱中的Exchange ActiveSync[禁用Exchange Online。](https://support.microsoft.com/help/2795303)

若要禁用对邮箱的其他类型的访问，请参阅：

- [为邮箱启用或禁用 MAPI。](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [为用户启用或禁用 POP3 或 IMAP4 访问](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

暂停OneDrive 同步有助于防止云数据被潜在感染的设备更新。 有关详细信息，请参阅如何在 OneDrive 中[暂停和恢复OneDrive。](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>步骤 3：从受影响的设备中删除恶意软件

在所有可疑计算机和设备上运行最新的完全防病毒扫描，以检测和删除与勒索软件关联的有效负载。

不要忘记扫描正在同步数据的设备或映射的网络驱动器的目标。

你可以将[Windows Defender](https://www.microsoft.com/windows/comprehensive-security)或 (用于较旧的客户端) Microsoft Security Essentials。 [](https://www.microsoft.com/download/details.aspx?id=5201)

此外，还可以帮助你删除勒索软件或恶意软件的替代方法是[MSRT (恶意软件) 。 ](https://www.microsoft.com/download/details.aspx?id=9905)

如果这些选项不起作用，可以尝试Windows Defender[脱机](https://support.microsoft.com/help/17466)或解决[检测和删除恶意软件的问题](https://support.microsoft.com/help/4466982)。

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>步骤 4：在已清理的计算机或设备上恢复文件

完成上一步以将勒索软件有效负载从你的环境 (这将阻止勒索软件加密或删除文件) 后，可以使用 Windows 11、Windows 10、Windows 8.1 中的文件历史记录，并使用 Windows [](https://support.microsoft.com/help/17128) 7 中的系统保护尝试恢复本地文件和文件夹。

**注意**：

- 某些勒索软件还会加密或删除备份版本，因此你无法使用文件历史记录或系统保护来还原文件。 如果发生这种情况，你需要在不受勒索软件或软件影响的外部驱动器或OneDrive备份，如下一节中所述。

- 如果文件夹已同步OneDrive并且您没有使用最新版本的 Windows，则使用文件历史记录可能有一些限制。

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>步骤 5：恢复用户OneDrive for Business

文件还原OneDrive for Business使您可以将整个OneDrive还原到过去 30 天内以前的时间点。 有关详细信息，请参阅“还原你的 OneDrive”[](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)。

## <a name="step-6-recover-deleted-email"></a>步骤 6：恢复已删除的电子邮件

在勒索软件删除所有电子邮件的极少数情况下，你或许可以恢复已删除的项目。 有关更多信息，请参阅：

- [恢复用户邮箱中的已删除邮件](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [在 Outlook for Windows 中恢复已删除项目](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>步骤 7：重新启用Exchange ActiveSync OneDrive 同步

在清理计算机和设备并恢复数据后，可以重新启用Exchange ActiveSync OneDrive 同步之前在步骤 2 中禁用的[Exchange ActiveSync 和 OneDrive 同步。](#step-2-disable-exchange-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>步骤 8 (可选) ：OneDrive 同步文件扩展名阻止访问

恢复后，你可以阻止OneDrive for Business客户端同步受此勒索软件影响的文件类型。 有关详细信息，请参阅 [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>报告攻击

### <a name="contact-law-enforcement"></a>联系执法机构

您应联系当地或联邦执法机构。 例如，如果你在美国，你可以联系["调查](https://www.fbi.gov/contact-us/field)局"本地现场办公室[、IC3 或](http://www.ic3.gov/complaint/default.aspx)[机密服务](http://www.secretservice.gov/)。

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>向你国家/地区欺诈报告网站提交报告

欺诈报告网站提供有关如何防止和避免欺诈的信息。 它们还提供报告您是否遭受欺诈的机制。

- 澳大利亚 [：SCAMwatch](http://www.scamwatch.gov.au/)

- 加拿大： [加拿大反欺诈中心](http://www.antifraudcentre-centreantifraude.ca/)

- 法国 [：Agence nationale de la sécurité des systcurmes d'information](http://www.ssi.gouv.fr/)

- 德国 [：Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- 爱尔兰 [：Garda Sí一一](http://www.garda.ie/)

- 新西兰： [消费者诈骗](http://www.consumeraffairs.govt.nz/scams)

- 瑞士 [国家/地区国家/地区会议](https://www.ncsc.admin.ch/ncsc/de/home.html)

- 英国： [行动欺诈](http://www.actionfraud.police.uk/)

- 美国 [：On Guard Online](http://www.onguardonline.gov/)

如果你的国家/地区未列出，请向当地或联邦执法机构询问。

### <a name="submit-email-messages-to-microsoft"></a>将电子邮件提交到 Microsoft

您可以使用多种方法之一报告包含勒索软件的网络钓鱼邮件。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="additional-ransomware-resources"></a>其他勒索软件资源

来自 Microsoft 的关键信息：

- [日趋严重的勒索软件威胁](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/)，2021 年 7 月 20 日 Microsoft 关于问题的博客文章
- [人工操作的勒索软件](/security/compass/human-operated-ransomware)
- [快速防范勒索软件和勒索](/security/compass/protect-against-ransomware)
- [2021 Microsoft 数字防御报告](https://www.microsoft.com/security/business/microsoft-digital-defense-report)（请参阅第 10-19 页）
- [勒索软件：Microsoft 365 Defender](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/overview)门户中的一份持续威胁威胁分析报告


Microsoft 365：

- [为 Microsoft 365 租户部署勒索软件保护](/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [使用 Azure 和 Microsoft 365 最大化勒索软件复原能力](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [恶意软件和勒索软件防护](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [保护你的Windows电脑免受勒索软件](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [在 SharePoint Online 中处理勒索软件](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)
- [Microsoft 365 Defender](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag)门户中勒索软件的威胁Microsoft 365 Defender报告

Microsoft 365 Defender：

- [使用高级搜寻查找勒索软件](/microsoft-365/security/defender/advanced-hunting-find-ransomware)

Microsoft Azure：

- [针对勒索软件攻击的 Azure 防御](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [使用 Azure 和 Microsoft 365 最大化勒索软件复原能力](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [备份和还原计划以防范勒索软件](/security/compass/backup-plan-to-protect-against-ransomware)
- [使用 26 分钟的视频Microsoft Azure备份 (](https://www.youtube.com/watch?v=VhLOr2_1MCg)保护免受勒索软件) 
- [从系统性标识泄露中恢复](/azure/security/fundamentals/recover-from-identity-compromise)
- [Azure Sentinel 中的高级多阶段攻击检测](/azure/sentinel/fusion#ransomware)
- [Azure Sentinel 中勒索软件融合检测](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Cloud App Security：

-  [在 Cloud App Security 中创建异常检测策略](/cloud-app-security/anomaly-detection-policy)

Microsoft 安全团队博客文章：

- [防范和从勒索软件中恢复的 3 个步骤（2021 年 9 月）](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [通过了解网络安全风险以增强恢复能力：第 4 部分 - 浏览当前威胁（2021 年 5 月）](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  请参阅 **勒索软件** 部分。

- [人为操作的勒索软件攻击：可预防的灾难（2020 年 3 月）](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  包括对实际攻击的攻击链分析。

- [勒索软件应对 - 是否支付勒索金额？（2019 年 12 月）](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro 以透明方式应对勒索软件攻击（2019 年 12 月）](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
