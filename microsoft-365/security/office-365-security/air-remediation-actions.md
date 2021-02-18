---
title: Microsoft Defender for Office 365 中的修正操作
keywords: AIR， autoIR， ATP， 自动化， 调查， 响应， 修正， 威胁， 高级， 威胁， 保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 了解 Microsoft Defender for Office 365 中自动调查后采取的修正操作。
ms.date: 02/09/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bef2fbd1e9e3d3525f9c274b5f9127acfb218396
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287121"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的修正操作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="remediation-actions"></a>修正操作

Microsoft Defender [for Office 365](office-365-atp.md) 中的威胁防护功能包括某些修正操作。 此类修正操作可能包括：

- 软删除电子邮件或群集
- 阻止 URL（单击时）
- 关闭外部邮件转发
- 关闭委派

在 Microsoft Defender for Office 365 中，不会自动采取修正操作。 相反，修正操作仅在组织的安全运营团队批准后执行。

## <a name="threats-and-remediation-actions"></a>威胁和修正操作

Microsoft Defender for Office 365 包括解决各种威胁的修正操作。 自动调查通常会导致一个或多个修正操作进行审阅和批准。 在某些情况下，自动调查不会产生特定的修正操作。 若要进一步调查和采取相应的操作，请使用下表中的指导。

|类别|威胁/风险|修正操作 () |
|:---|:---|:---|
|电子邮件|恶意软件|软删除电子邮件/群集 <p> 如果群集中的多封电子邮件包含恶意软件，则群集被视为恶意邮件。|
|电子邮件|恶意 URL<br/> (安全链接[.) ](atp-safe-links.md)|软删除电子邮件/群集 <br/>单击 (验证时阻止 URL) <p> 包含恶意 URL 的电子邮件被视为恶意邮件。|
|电子邮件|网络钓鱼|软删除电子邮件/群集 <p> 如果群集中的多封电子邮件包含网络钓鱼尝试，则整个群集被视为网络钓鱼尝试。|
|电子邮件|Zapped phish <br> (传递电子邮件，然后 [删除](zero-hour-auto-purge.md).) |软删除电子邮件/群集 <p>报告可用于查看已删除的邮件。 [查看 ZAP 是否移动了消息和常见问题解答](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)。|
|电子邮件|用户报告的错过 [的](enable-the-report-message-add-in.md) 网络钓鱼电子邮件|[由用户报告触发的自动调查](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|电子邮件|卷异常 <br>  (匹配条件，最近发送的电子邮件数量超过前 7-10 ) |自动调查不会导致特定的待处理操作。 <p>卷异常不是一个明显的威胁，而只是最近几天与过去 7-10 天相比更大的电子邮件卷的指示。 <p>尽管大量电子邮件可能会指示潜在问题，但需要确认恶意裁定或手动审阅电子邮件/群集。 请参阅["查找已送达的可疑电子邮件"。](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|电子邮件|未发现威胁 <br>  (系统根据文件、URL 或电子邮件群集裁定分析来查找任何威胁。) |自动调查不会导致特定的待处理操作。 <p>调查 [完成后发现](zero-hour-auto-purge.md) 和消除的威胁不会反映在调查的数字结果中，但威胁资源管理器中可查看此类 [威胁](threat-explorer.md)。|
|用户|用户单击了恶意 URL <br>  (用户导航到之后发现是恶意页面，或者用户绕过安全链接警告页面进入恶意页面。) [](atp-safe-links.md#warning-pages-from-safe-links)|自动调查不会导致特定的待处理操作。 <p>阻止 URL（单击时） <p>使用威胁资源管理器 [查看有关 URL 的数据并单击裁定](threat-explorer.md#view-phishing-url-and-click-verdict-data)。 <p>如果你的组织使用 [Microsoft Defender for Endpoint，](https://docs.microsoft.com/windows/security/threat-protection/)请考虑调查 [用户](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) 以确定他们的帐户是否遭到入侵。|
|用户|用户正在发送恶意软件/网络钓鱼|自动调查不会导致特定的待处理操作。 <p> 用户可能会报告恶意软件/网络钓鱼，或者 [有人可能在攻击](anti-spoofing-protection.md) 中欺骗用户。 使用 [威胁资源管理器](threat-explorer.md) 查看和处理包含恶意软件 [或](threat-explorer-views.md#email--malware) 网络钓鱼 [的电子邮件](threat-explorer-views.md#email--phish)。|
|用户|电子邮件转发 <br>  (邮箱转发规则，这些规则可用于数据) |删除转发规则 <p> 使用 [邮件流见解](mail-flow-insights-v2.md)（包括 ["](mfi-auto-forwarded-messages-report.md)自动转发邮件"报告）查看有关转发电子邮件的更具体的详细信息。|
|用户|电子邮件委派规则 <br>  (用户帐户设置了委派。) |删除委派规则 <p> 如果你的组织使用[Microsoft Defender for Endpoint，](https://docs.microsoft.com/windows/security/threat-protection/)请考虑调查正在获取委派权限的用户。 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)|
|用户|数据外泄 <br>  (用户违反电子邮件或文件共享 [DLP](../../compliance/data-loss-prevention-policies.md)策略 .) |自动调查不会导致特定的待处理操作。 <p> [查看 DLP 报告并采取措施](../../compliance/view-the-dlp-reports.md)。|
|用户|异常电子邮件发送 <br>  (用户最近发送的电子邮件数多于前 7-10 天) |自动调查不会导致特定的待处理操作。 <p> 发送大量电子邮件本身不是恶意的;用户可能只是向事件的一大组收件人发送电子邮件。 若要调查，请使用 [邮件流见解](mail-flow-insights-v2.md)，包括 [邮件](mfi-mail-flow-map-report.md) 流映射报告，以确定正在执行哪些操作并采取措施。|

## <a name="next-steps"></a>后续步骤

- [在 Microsoft Defender for Office 365 中查看自动调查的详细信息和结果](air-view-investigation-results.md)
- [在 Microsoft Defender for Office 365 中自动调查后查看挂起或已完成的修正操作](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>相关文章

- [了解 Microsoft Defender for Endpoint 中的自动调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [了解 Microsoft 365 Defender 中的功能](../mtp/microsoft-threat-protection.md)
