---
title: Microsoft Defender for Office 365 中的自动调查和响应
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/05/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 开始在 Microsoft Defender for Office 365 中使用自动调查和响应功能。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 8b6ef712e2e90e6798f16c54bc82f99590dbea42
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614830"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的自动调查和响应 (空中) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender For Office 365](office-365-atp.md) 包括功能强大的自动化调查和响应 (空中) 功能，可节省安全运营团队的时间和精力。 随着警报的触发，安全操作团队可以对这些警报进行检查、设置优先级和响应。 跟上传入警报的数量的持续很大。 自动执行其中一些任务可能会有所帮助。

通过 AIR，您的安全操作团队可以更高效地运行。 空中功能包括自动调查过程，以响应目前存在的已知威胁。 适当的补救措施等待批准，使安全操作团队能够有效地对检测到的威胁做出响应。 借助 AIR，安全操作团队可以将精力集中在优先级较高的任务上，而不会丢失触发的重要警报。

本文内容：

- [空气的整体流量](#the-overall-flow-of-air);
- [如何获取空气](#how-to-get-air);并
- 配置或使用 AIR 功能 [所需的权限](#required-permissions-to-use-air-capabilities) 。

此外，本文还包括 [后续步骤](#next-steps)以及了解详细信息的资源。

## <a name="the-overall-flow-of-air"></a>空气的整体流动

触发警报，安全行动手册开始进行自动调查，这将导致发现和推荐的操作。 下面是空中的整体流，具体步骤如下：

1. 可通过以下方式之一启动自动调查：

   - 电子邮件 (（例如邮件、附件、URL 或已损坏的用户帐户) ）中的某些可疑项 [会触发警报](#which-alert-policies-trigger-automated-investigations) 。 创建一个事件，并开始进行自动调查。

     --- 或 ---

   - 安全分析员在使用[威胁资源管理器](threat-explorer.md)时[开始进行自动调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

2. 在自动调查运行过程中，它将收集有关与该电子邮件相关的相关电子邮件和实体的其他数据。 此类实体可以包括文件、Url 和收件人。  调查的范围可以随着新的和相关的警报的触发而增加。

3. 在自动调查期间和之后，可以查看 [详细信息和结果](air-view-investigation-results.md) 。 结果包括 [建议的操作](air-remediation-actions.md) ，可采取这些操作来响应和修正发现的任何威胁。 此外，还可以使用 [行动手册日志](air-view-investigation-results.md#playbook-log) 来跟踪所有调查活动。

4. 您的安全操作团队将检查 [调查结果和建议](air-view-investigation-results.md)，并 [批准或拒绝修正操作](air-review-approve-pending-completed-actions.md)。

5. 由于已批准挂起的修正操作 (或拒绝) ，因此自动调查完成。

> [!IMPORTANT]
> 在 Microsoft Defender for Office 365 中，不会自动执行任何修正操作。 只有在组织的安全团队批准后，才会执行修正操作。
>
> AIR 功能通过确定纠正措施并提供做出明智决策所需的详细信息来节省安全运营团队的时间。

在每次自动调查期间和之后，安全操作团队可以执行以下操作：

- [查看与调查相关的警报的详细信息](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [查看调查的结果详细信息](air-view-investigation-results.md#view-details-of-an-investigation)

- [查看和批准作为调查结果的操作](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 有关更详细的概述，请参阅 [AIR 的工作原理](automated-investigation-response-office.md)。

## <a name="how-to-get-air"></a>如何获取空中

在 [Microsoft Defender For Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)中包含空中功能，前提是你的策略和警报已配置。 如果您想了解这方面的一些帮助，请按照 [针对威胁进行保护](protect-against-threats.md) 以设置或配置以下保护设置的指导：

1. 应启用[审核日志记录](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) () 

2. [反恶意软件策略](protect-against-threats.md#part-1---anti-malware-protection)

3. [Antiphishing 保护](protect-against-threats.md#part-2---anti-phishing-protection)

4. [反垃圾邮件保护](protect-against-threats.md#part-3---anti-spam-protection)。

5. [安全链接和安全附件](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)。

6. [SharePoint、OneDrive 和 Microsoft 团队的安全附件](protect-against-threats.md#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)。

7. [电子邮件的零小时自动清除](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)。

此外，请务必 [查看组织的通知策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)，尤其是 " [威胁管理" 类别中的默认策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)。

## <a name="which-alert-policies-trigger-automated-investigations"></a>哪些警报策略会触发自动调查？

Microsoft 365 提供了许多内置的警报策略，可帮助确定 Exchange 管理员权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。 有几个 [默认的警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 可以触发自动调查。 下表介绍了触发自动调查的警报、Microsoft 365 安全中心中的严重性以及它们的生成方式：

|警报|Severity|如何生成警报|
|---|---|---|
|检测到潜在的恶意 URL 单击|**High**|发生以下任一情况时，将生成此警报： <ul><li>由组织中的 [安全链接](atp-safe-links.md) 保护的用户单击恶意链接</li><li>Url 的判定更改由 Microsoft Defender for Office 365 标识</li><li>用户根据组织的 " [安全链接" 策略](set-up-atp-safe-links-policies.md))  (替代 "安全链接" 警告页面。</li></ul> <p> 有关触发此警报的事件的详细信息，请参阅 [设置安全链接策略](set-up-atp-safe-links-policies.md)。|
|用户将电子邮件报告为恶意软件或网络钓鱼|**之**|当您的组织中的用户使用 [报告邮件加载项将](enable-the-report-message-add-in.md)邮件报告为仿冒电子邮件时，将生成此警报。|
|传递后删除包含恶意软件的电子邮件|**之**|将包含恶意软件的任何电子邮件发送到组织中的邮箱时，会生成此警报。 如果发生此事件，Microsoft 将使用 [零小时自动清除](zero-hour-auto-purge.md)从 Exchange Online 邮箱中删除受感染的邮件。|
|传递后删除包含网络钓鱼 Url 的电子邮件|**之**|将包含网络钓鱼的任何邮件传递给组织中的邮箱时，会生成此警报。 如果发生此事件，Microsoft 将使用 [零小时自动清除](zero-hour-auto-purge.md)从 Exchange Online 邮箱中删除受感染的邮件。|
|检测到可疑的电子邮件发送模式|**Medium**|当组织中的某个人发送了可疑电子邮件，并且受到限制而无法发送电子邮件时，将生成此警报。 这是一种针对可能表示帐户受到威胁但不够严重以限制用户的行为的早期警告。 <p> 尽管极少数情况下，此策略生成的警报也可能是异常情况。 但是，最好 [检查用户帐户是否受到威胁](responding-to-a-compromised-email-account.md)。|
|限制用户发送电子邮件|**High**|如果组织中的某个人受到限制，无法发送出站邮件，则会生成此警报。 这通常 [会在电子邮件帐户受到威胁](responding-to-a-compromised-email-account.md)时产生。 <p> 有关受限用户的详细信息，请参阅 [Microsoft 365 中的受限用户门户中的删除阻止的用户](removing-user-from-restricted-users-portal-after-spam.md)。|
|

> [!TIP]
> 若要了解有关通知策略或编辑默认设置的详细信息，请参阅 [Microsoft 365 合规性中心中的警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。

## <a name="required-permissions-to-use-air-capabilities"></a>使用空中功能所需的权限

通过某些角色（如下表中所述的角色）授予权限：

|任务|角色 (s) 必需|
|---|---|
|设置空中功能|以下角色之一： <ul><li>全局管理员</li><li>安全管理员</li></ul> <p> 可以在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合规性中心](permissions-in-the-security-and-compliance-center.md)中分配这些角色。|
|开始自动调查 <p> --- 或 --- <p> 批准或拒绝建议的操作|在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合规性中心](permissions-in-the-security-and-compliance-center.md)中分配的以下角色之一： <ul><li>全局管理员</li><li>安全管理员</li><li>安全读取者 <br> --- 和 --- </li><li>搜索和清除 (仅在 [安全 & 合规中心](permissions-in-the-security-and-compliance-center.md)中分配此角色。 您可能需要在其中创建新的角色组，并将搜索和清除角色添加到该新角色组。</li></ul>|
|

## <a name="required-licenses"></a>必需的许可证

[Microsoft Defender For Office 365 计划 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 许可证应分配给：

- 安全管理员 (包括全局管理员) 
- 您的组织的安全操作团队 (包括安全读者和那些具有 **搜索和清除** 角色的读者) 
- 最终用户

## <a name="next-steps"></a>后续步骤

- [查看自动调查的详细信息和结果](air-view-investigation-results.md#view-details-of-an-investigation)

- [查看和批准挂起的操作](air-remediation-actions.md)

## <a name="see-also"></a>另请参阅

- [Microsoft Defender for Endpoint 中的自动调查和修正](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 Defender 中的自动化调查和响应](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
