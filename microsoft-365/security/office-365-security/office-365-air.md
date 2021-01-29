---
title: Microsoft Defender for Office 365 中的自动调查和响应
keywords: AIR， autoIR， ATP， 自动化， 调查， 响应， 修正， 威胁， 高级， 威胁， 保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/28/2021
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 开始使用 Microsoft Defender for Office 365 中的自动调查和响应功能。
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ee448e31ccbddbf1d1d5653614ec75fa94768b3b
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040528"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 (AIR) 自动调查和响应

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender for Office 365](office-365-atp.md) 包括强大的自动调查和响应 (AIR) 功能，可节省安全运营团队的时间和精力。 触发警报后，由安全运营团队来审阅、确定优先级并响应这些警报。 与传入警报的量保持一起可能会很不知所措。 自动执行其中一些任务可能会有所帮助。

AIR 使安全运营团队可以更高效地运行。 AIR 功能包括自动调查流程，以响应当今存在的已知威胁。 适当的修正操作等待审批，使安全运营团队能够有效响应检测到的威胁。 使用 AIR，安全运营团队可以专注于优先级较高的任务，而不会忽略触发的重要警报。

本文内容：

- AIR [的整体流](#the-overall-flow-of-air);
- [如何获取 AIR;](#how-to-get-air)and
- [配置或使用](#required-permissions-to-use-air-capabilities)AIR 功能所需的权限。

本文还包括下 [一步](#next-steps)，以及了解更多信息的资源。

## <a name="the-overall-flow-of-air"></a>AIR 的整体流

触发警报，安全手册启动自动调查，从而产生发现和推荐操作。 下面是 AIR 的整体流程，分步说明：

1. 自动调查以下列方式之一启动：

   - 警报 [由](#which-alert-policies-trigger-automated-investigations) 电子邮件内容中的可疑内容 (例如邮件、附件、URL 或遭到入侵的用户帐户) 。 创建事件，并开始自动调查。

     --- 或 ---

   - 安全分析 [员在使用威胁资源管理器时](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 启动 [自动调查](threat-explorer.md)。

2. 当自动调查运行时，它将收集有关相关电子邮件和与该电子邮件相关的实体的其他数据。 此类实体可以包括文件、URL 和收件人。  随着新警报和相关警报的触发，调查的范围可能会增加。

3. 在自动调查期间和之后， [可以查看](air-view-investigation-results.md) 详细信息和结果。 结果 [包括可](air-remediation-actions.md) 采取的建议操作，以响应和修正发现的任何威胁。 此外，还有 [一个可](air-view-investigation-results.md#playbook-log) 跟踪所有调查活动的手册日志。

4. 安全运营团队会审阅 [测试结果和建议](air-view-investigation-results.md)，并 [批准或拒绝修正操作](air-review-approve-pending-completed-actions.md)。

5. 随着挂起的修正操作得到批准 (或拒绝) ，自动调查将完成。

> [!IMPORTANT]
> 在 Microsoft Defender for Office 365 中，不会自动执行任何修正操作。 只有在组织的安全团队批准后，才会执行修正操作。
>
> AIR 功能通过确定修正操作并提供做出明智决定所需的详细信息来节省安全运营团队的时间。

在每个自动调查期间和之后，安全运营团队可以：

- [查看与调查相关的警报的详细信息](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [查看调查的结果详细信息](air-view-investigation-results.md#view-details-of-an-investigation)

- [查看和批准调查后的操作](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 有关更详细的概述，请参阅 [AIR 的工作原理](automated-investigation-response-office.md)。

## <a name="how-to-get-air"></a>如何获取 AIR

AIR 功能包含在 [Microsoft Defender for Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)中，但已配置策略和警报。 若要获得一些帮助，请按照"防止威胁"中的指南[](protect-against-threats.md)设置或配置以下保护设置：

1. [审核日志记录](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (应打开) 

2. [反恶意软件策略](protect-against-threats.md#part-1---anti-malware-protection)

3. [反Phishing protection](protect-against-threats.md#part-2---anti-phishing-protection)

4. [反垃圾邮件保护](protect-against-threats.md#part-3---anti-spam-protection)。

5. [安全链接和安全附件](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)。

6. [SharePoint、OneDrive](protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)和 Microsoft Teams 的安全附件。

7. [零时差自动清除电子邮件](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)。

此外，请确保 [查看组织的](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)警报策略，尤其是威胁管理 [类别中的默认策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)。

## <a name="which-alert-policies-trigger-automated-investigations"></a>哪些警报策略会触发自动调查？

Microsoft 365 提供了许多内置警报策略，可帮助识别 Exchange 管理员权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。 一些 [默认警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 可以触发自动调查。 下表介绍了触发自动调查的警报、Microsoft 365 安全中心中警报的严重性以及如何生成这些警报：

|警报|Severity|如何生成警报|
|:---|:---|:---|
|检测到潜在恶意 URL 单击|**High**|发生以下任一情况时，将生成此警报： <ul><li>组织中受安全 [链接](atp-safe-links.md) 保护的用户单击恶意链接</li><li>URL 裁定更改由 Microsoft Defender for Office 365 标识</li><li>用户根据组织的安全链接 (覆盖安全链接[警告) 。](set-up-atp-safe-links-policies.md)</li></ul> <p> 有关触发此警报的事件详细信息，请参阅["设置安全链接策略"。](set-up-atp-safe-links-policies.md)|
|用户将电子邮件报告为恶意软件或网络钓鱼邮件|**信息**|当组织中用户使用报告邮件外接程序或报告网络钓鱼外接程序将邮件报告为网络钓鱼电子邮件时[](enable-the-report-message-add-in.md)，[将生成此警报](enable-the-report-phish-add-in.md)。|
|包含恶意软件的电子邮件在传递后被删除|**信息**|当包含恶意软件的任何电子邮件传递到您组织的邮箱时，将生成此警报。 如果发生此事件，Microsoft 使用零时差自动清除从 Exchange Online 邮箱中删除 [受感染的邮件](zero-hour-auto-purge.md)。|
|包含网络钓鱼 URL 的电子邮件在传递后被删除|**信息**|当包含网络钓鱼的任何邮件传递到您组织的邮箱时，将生成此警报。 如果发生此事件，Microsoft 使用零时差自动清除从 Exchange Online 邮箱中删除 [受感染的邮件](zero-hour-auto-purge.md)。|
|检测到可疑的电子邮件发送模式|**Medium**|当组织中有人已发送可疑电子邮件，并且存在被限制发送电子邮件的风险时，将生成此警报。 这是一个行为的早期警告，可能指示帐户受到威胁，但不够严重，无法限制用户。 <p> 尽管这种情况很少见，但此策略生成的警报可能是异常情况。 但是，检查用户帐户是否遭到入侵 [是一](responding-to-a-compromised-email-account.md)个好主意。|
|用户被限制发送电子邮件|**High**|当组织中有人被限制发送出站邮件时，将生成此警报。 这通常会导致电子邮件帐户 [遭到入侵](responding-to-a-compromised-email-account.md)。 <p> 有关受限用户详细信息，请参阅 [Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md)中的"从受限用户"门户删除被阻止的用户。|
|

> [!TIP]
> 若要了解有关警报策略或编辑默认设置的信息，请参阅 Microsoft [365 合规中心](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)中的警报策略。

## <a name="required-permissions-to-use-air-capabilities"></a>使用 AIR 功能所需的权限

权限通过某些角色授予，如下表中所述的角色：

|任务|需要 (角色) 角色|
|---|---|
|设置 AIR 功能|下列角色之一： <ul><li>全局管理员</li><li>安全管理员</li></ul> <p> 这些角色可以在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或安全与合规中心& [分配](permissions-in-the-security-and-compliance-center.md)。|
|启动自动调查 <p> --- 或 --- <p> 批准或拒绝建议的操作|在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或安全与合规中心& [角色之一](permissions-in-the-security-and-compliance-center.md)： <ul><li>全局管理员</li><li>安全管理员</li><li>安全操作员</li><li>安全读取者 <br> --- 和 --- </li><li>搜索和 (此角色仅在安全与合规中心& [分配](permissions-in-the-security-and-compliance-center.md)。 您可能必须在那里创建一个新角色组，然后向该新角色组添加搜索和清除角色。</li></ul>|
|

## <a name="required-licenses"></a>所需的许可证

[Microsoft Defender for Office 365 计划 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 许可证应分配给：

- 安全管理员 (全局管理员) 
- 组织的安全运营团队 (包括安全读者和具有"搜索和清除"角色) 
- 最终用户

## <a name="next-steps"></a>后续步骤

- [查看自动调查的详细信息和结果](air-view-investigation-results.md#view-details-of-an-investigation)

- [审阅和批准挂起的操作](air-remediation-actions.md)

## <a name="see-also"></a>另请参阅

- [Microsoft Defender for Endpoint 中的自动调查和修正](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 Defender 中的自动调查和响应](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
