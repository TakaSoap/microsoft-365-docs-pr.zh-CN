---
title: Microsoft Defender for Office 365 中的自动调查后的补救措施
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
description: 了解在 Microsoft Defender for Office 365 中进行自动调查后的修正操作。
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 6ddfb2cb9597d1ddd955f7ec39e197a780b29881
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327671"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的自动调查后的补救措施

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>修正操作

[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)中 (空中) 的[自动化调查和响应功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)包括某些修正操作。 无论何时运行自动化调查或已完成，你通常会看到一个或多个修正操作需要由安全运营团队批准后才能继续。 此类修正操作可包括以下内容：

- 软删除电子邮件或群集
- 阻止 URL（单击时）
- 关闭外部邮件转发
- 关闭委派

> [!NOTE]
> 在 Microsoft Defender for Office 365 中，自动调查不会导致自动执行补救操作。 仅在组织的安全操作团队批准后才采取更正措施。

## <a name="threats-and-remediation-actions"></a>威胁和修正操作

下表汇总了 Microsoft Defender for Office 365 中的威胁和相应的修正操作。 在某些情况下，自动调查不会导致特定的修正操作。 您的安全操作团队可以进一步调查并采取相应的操作，如下表所述。

****

|类别|威胁/风险| (s) 的修正操作|
|---|---|---|
|电子邮件|恶意软件|软删除电子邮件/群集 <br/><br/>如果群集中的少量电子邮件包含恶意软件，则认为该群集是恶意的。|
|电子邮件|恶意 URL<br/> ([Office 365 ATP 中的安全链接](atp-safe-links.md)检测到恶意 URL。|软删除电子邮件/群集 <br/><br/>包含恶意 URL 的电子邮件被认为是恶意的。|
|电子邮件|网络钓鱼|软删除电子邮件/群集 <br/><br/>如果群集中的少量电子邮件包含网络钓鱼尝试，则认为该群集是网络钓鱼。|
|电子邮件|Zapped 网络钓鱼 <br/> (电子邮件已传递和 [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge)。 ) |软删除电子邮件/群集 <br/><br/>可查看 zapped 消息的报告。 [查看 ZAP 是否移动了邮件和 faq](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message)。|
|电子邮件|用户 [报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) 的丢失的网络钓鱼电子邮件|[由用户的报告触发的自动调查](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|电子邮件|卷异常 <br/> (最近的电子邮件数量超过前7-10 天，以匹配条件。 ) |自动调查不会导致特定的挂起操作。 <br/><br/>卷异常不是明确的威胁，而只是与过去的7-10 天相比，最近一天的电子邮件数量的指示。 虽然这可能表示潜在问题，但在恶意 verdicts 或电子邮件/群集的手动审核方面需要进行确认。 请参阅 [查找和删除已传递的可疑电子邮件](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered)。|
|电子邮件|未发现威胁 <br/> (系统找不到任何基于电子邮件群集 verdicts 的文件、url 或分析的威胁 ) |自动调查不会导致特定的挂起操作。 <br/><br/>调查完成后发现的威胁和 [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge) 不会反映在调查的数值发现中，但威胁 [资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)可查看此类威胁。|
|用户|用户单击了恶意 URL <br/> (导航到后来发现恶意的页面的用户，或者用户跳过了 " [安全链接" 警告页](atp-safe-links.md#warning-pages-from-safe-links) 以获取恶意页面。 ) |自动调查不会导致特定的挂起操作。 <br/><br/>使用威胁资源管理器 [查看有关 url 的数据，然后单击 "verdicts"](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict)。 <br/><br/>如果你的组织正在使用 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)，请考虑 [调查用户](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) 以确定其帐户是否受到威胁。|
|用户|用户正在发送恶意软件/网络钓鱼|自动调查不会导致特定的挂起操作。 <br/><br/>用户可能会报告恶意软件/网络钓鱼，或者有人可能会在攻击过程中 [欺骗用户](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection) 。 使用 [威胁资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) 查看和处理包含 [恶意软件](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware) 或 [网络钓鱼](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish)的电子邮件。|
|用户|电子邮件转发 <br/> (配置邮箱转发规则，这可用于数据 exfiltration。 ) |删除转发规则 <br/><br/>使用 [邮件流见解](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)（包括 " [自动转发的邮件" 报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)）可以查看有关转发电子邮件的更多具体详细信息。|
|用户|电子邮件委派规则 <br/> (用户的帐户设置了委派。 ) |删除委派规则 <br/><br/> 如果你的组织正在使用 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)，请考虑调查获取委派权限 [的用户](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) 。|
|用户|数据外泄<br/> (用户违反了电子邮件或文件共享 [DLP 策略](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)。 ) |自动调查不会导致特定的挂起操作。 <br/><br/>[查看 DLP 报告并执行操作](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)。|
|用户|异常电子邮件发送 <br/> (用户最近在过去的7-10 天内发送了多封电子邮件。 ) |自动调查不会导致特定的挂起操作。 <br/><br/>发送大量电子邮件本身并不恶意;用户可能只是向一个大型收件人组发送了一个事件的电子邮件。 若要进行调查，请使用 [邮件流见解](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)，包括 [邮件流映射报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report) ，以确定发生的情况并采取措施。|
|

## <a name="next-steps"></a>后续步骤

- [在 Microsoft Defender for Office 365 中查看自动调查的详细信息和结果](air-view-investigation-results.md)

- [查看 Microsoft Defender for Office 365 中的自动调查后的挂起或已完成的修正操作](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>相关文章

- [了解 Microsoft Defender for Endpoint 中的自动调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [了解 Microsoft 365 Defender 中的其他功能](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
