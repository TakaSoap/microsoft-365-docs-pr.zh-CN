---
title: Office 365 中的补救措施自动化调查和响应
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解 Office 365 高级威胁防护计划2中的自动调查和响应功能中的补救措施。
ms.openlocfilehash: d0f08c3e89882e21263c18246612949ea68ac1ad
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528925"
---
# <a name="remediation-actions-in-office-365"></a>Office 365 中的修正操作

## <a name="remediation-actions"></a>修正操作

Office 365 中的[自动化调查和响应功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)（AIR）[高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)（Office 365 ATP）计划2包括某些修正操作。 当自动调查运行或完成时，您通常会看到一个或多个需要安全操作团队批准才能继续执行的修正操作。 此类修正操作可包括以下内容：

- 软删除电子邮件或群集
- 阻止 URL（单击时）
- 关闭外部邮件转发
- 关闭委派

> [!NOTE]
> 在 Office 365 ATP 中，自动调查不会自动修正。 仅在组织的安全团队进行审批时才采取更正措施。

## <a name="threats-and-remediation-actions"></a>威胁和修正操作

下表汇总了 Office 365 ATP 中的威胁和相应的补救措施。 在某些情况下，自动调查不会导致特定的修正操作。 您的安全操作团队可以进一步调查并采取相应的操作，如下表所述。

||||
|---|---|---|
|**类别**|**威胁/风险**|**修正操作**|
|电子邮件|恶意软件| 软删除电子邮件/群集 <br/><br/>如果群集中的少量电子邮件包含恶意软件，则认为该群集是恶意的。|
|电子邮件|恶意 URL<br/>（ [Office 365 ATP 安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-atp-safe-links-works)检测到恶意 URL。）|软删除电子邮件/群集 <br/><br/>包含恶意 URL 的电子邮件被认为是恶意的。|
|电子邮件|诈骗| 软删除电子邮件/群集 <br/><br/>如果群集中的少量电子邮件包含网络钓鱼尝试，则认为该群集是网络钓鱼。|
|电子邮件|Zapped 网络钓鱼 <br/>（电子邮件已传递和[zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge)。）|软删除电子邮件/群集 <br/><br/>可查看 zapped 消息的报告。 [查看 ZAP 是否移动了邮件和 faq](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message)。|
|电子邮件|用户[报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)的丢失的网络钓鱼电子邮件| [由用户的报告触发的自动调查](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|电子邮件|卷异常 <br/>（最近的电子邮件数量超过前7-10 天，以匹配条件。）|自动调查不会导致特定的挂起操作。 <br/><br/>卷异常不是明确的威胁，而只是与过去的7-10 天相比，最近一天的电子邮件数量的指示。 虽然这可能表示潜在问题，但在恶意 verdicts 或电子邮件/群集的手动审核方面需要进行确认。 请参阅[查找和删除已传递的可疑电子邮件](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered)。|
|电子邮件|未发现威胁 <br/>（根据电子邮件群集 verdicts 的文件、url 或分析，系统找不到任何威胁。）|自动调查不会导致特定的挂起操作。 <br/><br/>调查完成后发现的威胁和[zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge)不会反映在调查的数值发现中，但威胁[资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)可查看此类威胁。|
|User|用户单击了恶意 URL <br/>（一个用户导航到后来发现为恶意的页面，或者用户跳过了 "[安全链接" 警告页](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-warning-pages)以获取恶意页面。）|自动调查不会导致特定的挂起操作。 <br/><br/>使用威胁资源管理器[查看有关 url 的数据，然后单击 "verdicts"](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict)。 <br/><br/>如果您的组织使用的是[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/)，请考虑[调查用户](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)以确定其帐户是否受到威胁。|
|User|用户正在发送恶意软件/网络钓鱼|自动调查不会导致特定的挂起操作。 <br/><br/>用户可能会报告恶意软件/网络钓鱼，或者有人可能会在攻击过程中[欺骗用户](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection)。 使用[威胁资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)查看和处理包含[恶意软件](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware)或[网络钓鱼](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish)的电子邮件。|
|User|电子邮件转发 <br/>（邮箱转发规则已配置，可用于数据 exfiltration。）|删除转发规则 <br/><br/>使用[邮件流见解](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)（包括 "[自动转发的邮件" 报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)）可以查看有关转发电子邮件的更多具体详细信息。|
|User|电子邮件委派规则 <br/>（用户的帐户已设置委派。）|删除委派规则 <br/><br/> 如果您的组织使用的是[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/)，请考虑调查获取委派权限[的用户](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)。|
|User|数据 exfiltration<br/>（用户违反了电子邮件或文件共享[DLP 策略](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)。）|自动调查不会导致特定的挂起操作。 <br/><br/>[查看 DLP 报告并执行操作](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)。|
|User|异常电子邮件发送 <br/>（最近一次收到的电子邮件数超过前7-10 天。）|自动调查不会导致特定的挂起操作。 <br/><br/>发送大量电子邮件本身并不恶意;用户可能只是向一个大型收件人组发送了一个事件的电子邮件。 若要进行调查，请使用[邮件流见解](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)，包括[邮件流映射报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report)，以确定发生的情况并采取措施。|
|

## <a name="next-steps"></a>后续步骤

- [在 Office 365 中查看自动调查的详细信息和结果](air-view-investigation-results.md)

- [查看 Office 365 中的自动调查后的挂起或已完成的修正操作](air-review-approve-pending-completed-actions.md)


## <a name="related-articles"></a>相关文章

- [Microsoft Defender 高级威胁防护中的自动调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [了解 Microsoft 威胁防护](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
