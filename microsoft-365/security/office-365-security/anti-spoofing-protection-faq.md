---
title: 防欺骗保护常见问题
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以查看有关 Exchange Online Protection (EOP) 中的反欺骗保护的常见问题和) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2d307d201af8ad09a4faf7a865a29da8942bdf8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288905"
---
# <a name="anti-spoofing-protection-faq"></a>防欺骗保护常见问题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

本文提供有关在 Exchange Online 中拥有邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织的反欺骗保护的常见问题和解答。

有关反垃圾邮件保护的问题和解答，请参阅 [反垃圾邮件保护常见问题解答](anti-spam-protection-faq.md)。

有关反恶意软件保护的问题和解答，请参阅 [反恶意软件保护常见问题解答](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>为什么 Microsoft 选择垃圾邮件未经身份验证的入站电子邮件？

Microsoft 认为，继续允许未经身份验证的入站电子邮件的风险高于丢失合法入站电子邮件的风险。

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>垃圾邮件未经身份验证的入站电子邮件是否会导致合法电子邮件被标记为垃圾邮件？

当 Microsoft 在 2018 年启用此功能时，一些误报 (邮件被标记为错误) 。 但是，随着时间的推移，发件人会根据要求进行调整。 对于大多数电子邮件路径来说，被误识别为欺骗的邮件数量可以忽略不计。

Microsoft 本身首先在将新的电子邮件身份验证要求部署到客户之前几周采用了该要求。 虽然最初出现了中断，但此现象逐渐减少了。

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>没有 Defender for Office 365 的 Microsoft 365 客户是否可以使用欺骗智能？

是的。 自 2018 年 10 日起，欺骗智能适用于在 Exchange Online 中拥有邮箱的所有组织和没有 Exchange Online 邮箱的独立 EOP 组织。

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>如何向 Microsoft 报告垃圾邮件或非垃圾邮件？

参见 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>我是管理员，不知道我电子邮件域中的所有邮件源！

See [You't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>如果我为组织禁用反欺骗保护，会发生什么情况？

建议不要禁用反欺骗保护。 禁用保护将允许在组织中传递更多的网络钓鱼和垃圾邮件。 并非所有网络钓鱼都是欺骗，并非所有欺骗邮件都会丢失。 但是，风险会更高。

现在 [，连接器的](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 增强筛选功能已可用，我们不再建议在 EOP 之前通过其他服务路由电子邮件时关闭反欺骗保护。

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>反欺骗保护是否意味着将保护我免受所有网络钓鱼的防护？

遗憾的是，否。 攻击者将适应其他技术 (例如，在免费电子邮件服务中遭到入侵的帐户) 。 但是，防钓鱼保护可以更好地检测这些其他类型的网络钓鱼方法。 EOP 中的保护层设计为协同工作，并相互构建。

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>其他大型电子邮件服务是否阻止未经身份验证的入站电子邮件？

几乎所有大型电子邮件服务都实现了传统的 SPF、DKIM 和 DMARC 检查。 某些服务具有其他更严格的检查，但很少服务会执行 EOP 来阻止未经身份验证的电子邮件，并视为欺骗邮件。 但是，行业对未经身份验证的电子邮件的问题越来越了解，特别是因为网络钓鱼问题。

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>如果启用反欺骗，是否仍然需要启用 MarkAsSpamSpfRecordHardFail (高级垃圾邮件筛选器设置"SPF 记录： 硬失败") _MarkAsSpamSpfRecordHardFail？_

否。 不再需要此 ASF 设置。 反欺骗保护考虑 SPF 硬失败和更广泛的条件集。 如果已启用防欺骗和“SPF 记录:硬故障”(_MarkAsSpamSpfRecordHardFail_)，可能会收到更多误报。

建议您禁用此功能，因为它几乎不会为检测垃圾邮件或网络钓鱼邮件提供任何其他好处，而是会生成大部分误报。 有关详细信息，请参阅 [EOP 中的"高级垃圾邮件筛选器 (ASF) 设置](advanced-spam-filtering-asf-options.md)。

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>发件人重写方案是否有助于修复转发的电子邮件？

SRS 仅部分修复了转发电子邮件的问题。 通过重写 SMTP MAIL **FROM，SRS** 可以确保转发的邮件通过下一个目标的 SPF。 但是，由于反欺骗基于"收件人"地址以及 **MAIL FROM** 或 DKIM 签名域 (或其他信号) ，因此无法阻止 SRS 转发的电子邮件被标记为欺骗邮件。
