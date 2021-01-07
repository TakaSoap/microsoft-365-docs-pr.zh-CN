---
title: Microsoft 365 中优先级帐户的安全建议
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何提升安全设置，并使用其 Microsoft 365 组织中优先级帐户的报告、警报和调查。
ms.openlocfilehash: 9788131ea881a1cb3c36a60dfaac01ed5daf0901
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769240"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Microsoft 365 中优先级帐户的安全建议

如果收到来自组织主管的紧急消息，要求您执行某些操作，该怎么办？ 是否执行？ 大多数用户都会遵守该请求。

对于攻击者，通过转换随机网络获取随机或未知用户的凭据的普通网络钓鱼攻击效率低下。 另一方面，以职位或权威职位的用户为目标的网络钓鱼或钓鱼攻击对攻击者来说更加具有攻击性。 如果这些优先级帐户遭到入侵，攻击者可能会使用组织中管理员、财务、产品甚至物理访问功能获取对帐户的访问权限。

Microsoft 365 和 Microsoft Defender for Office 365 包含许多不同的功能，可帮助你为优先帐户提供其他安全层。 本文讨论了可用功能及其使用方法。

![图标表单中的安全建议摘要](../../media/security-recommendations-for-priority-users.png)

## <a name="increase-sign-in-security-for-priority-accounts"></a>提高优先级帐户的登录安全性

优先级帐户要求提高登录安全性。 通过要求使用多重身份验证和禁用传统身份验证协议， (MFA) 提高登录安全性。

有关说明，请参阅 [步骤 1。使用 MFA 提高远程工作者的登录安全性](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in)。 虽然本文介绍的是远程工作者，但相同的概念也适用于优先用户。

**注意**：

- Exchange Online for Exchange Web Services (EWS) 、Exchange ActiveSync、POP3、IMAP4 和远程 PowerShell 正在弃用基本身份验证。 有关详细信息，请参阅此 [博客文章](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)。

- 您可以使用 Exchange Online 中的 [身份验证](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) 策略和 [客户端访问规则](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 来阻止基本身份验证和旧版身份验证协议，如 POP3、IMAP4 和经过身份验证的 SMTP。

- 可以在单个邮箱上禁用 POP3 和 IMAP4 访问。 您可以在组织级别禁用经过身份验证的 SMTP，并启用它，以在仍然需要它的特定邮箱上启用它。 有关说明，请参阅以下主题：
  - [为用户启用或禁用 POP3 或 IMAP4 访问](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [启用或禁用 SMTP AUTH (身份验证的客户端 SMTP) ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>对优先级帐户使用严格预设安全策略

优先级用户需要针对 Exchange Online Protection、EOP (和 Defender for Office 365) 中提供的各种保护执行更严格的操作。

例如，如果邮件用于优先级帐户，则不应将分类为垃圾邮件的邮件发送到"垃圾邮件"文件夹，而应隔离这些相同的邮件。

可以使用预设安全策略中的"严格"配置文件为优先级帐户实施此严格方法。

预设安全策略是一个方便且集中的位置，用于将建议的严格策略设置应用于 EOP 和 Defender for Office 365 的所有保护。 有关详细信息，请参阅 [EOP 和 Microsoft Defender for Office 365](preset-security-policies.md)中的预设安全策略。

有关严格策略设置与默认和标准策略设置的区别的详细信息，请参阅 EOP 和 [Microsoft Defender for Office 365 安全性的推荐设置](recommended-settings-for-eop-and-office365-atp.md)。

## <a name="apply-user-tags-to-priority-accounts"></a>将用户标记应用于优先级帐户

Microsoft Defender for Office 365 计划 2 (中的用户标记作为 Microsoft 365 E5 或附加订阅) 的一部分，是一种在报告和事件调查中快速标识特定用户或用户组并进行分类的方法。

**优先级帐户** 是一种内置用户标记 (称为系统标记) ，可用于标识涉及优先级帐户的事件和警报。 有关优先级帐户 **详细信息，请参阅** 管理和 [监视优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。

您还可以创建自定义标记以进一步标识优先级帐户并进行分类。 有关详细信息，请参阅用户 [标记](user-tags.md)。 请注意，可以在自定义 **用户标记 (** 界面) 系统标记管理优先级帐户。

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>监视警报、报告和检测中的优先级帐户

保护优先级用户并标记用户后，可以使用 EOP 和 Office 365 Defender 中的可用报告、警报和调查来快速识别涉及优先级帐户的事件或检测。 下表介绍了支持用户标记的功能。

<br>

****

|功能|说明|
|---|---|
|警报|受影响用户的用户标记在安全与合规中心的"查看警报"页上可见并&筛选器。 有关详细信息，请参阅"[查看警报"。](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)|
|威胁资源管理器 <p> 实时检测|在威胁资源管理器 **(** Microsoft Defender for Office 365 计划 2) 或实时检测 **(** Microsoft Defender for Office 365 计划 1) 中，用户标记显示在电子邮件网格视图和电子邮件详细信息飞出中。 用户标记也可作为可筛选属性使用。 有关详细信息，请参阅威胁  [资源管理器中的标记](threat-explorer.md#tags-in-threat-explorer)。|
|市场活动视图|用户标记是 Microsoft Defender for Office 365 计划 2 的"市场活动视图"中的许多可筛选属性之一。 有关详细信息，请参阅"[宣传活动视图"。](campaigns.md)|
|威胁防护状态报告|在威胁防护状态报告中几乎所有视图和详细信息表中，你可以按优先级帐户 **筛选结果**。 有关详细信息，请参阅 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。|
|优先级帐户的电子邮件问题报告|EAC **管理中心** 中的"优先级帐户的电子邮件问题" (EAC) 包含有关优先级帐户的未送达和延迟 **邮件的信息**。 有关详细信息，请参阅"优先级 [帐户的电子邮件问题"报告](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。|
|

## <a name="see-also"></a>另请参阅

[宣布在 Microsoft Defender for Office 365 中提供优先帐户保护](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
