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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以在 Exchange Online Protection 或 EOP 项目中查看有关反欺骗保护的常见问题 () 。
ms.openlocfilehash: 66dbedaf638154c4a35359a4e5bc66c326c04d1e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826669"
---
# <a name="anti-spoofing-protection-faq"></a>防欺骗保护常见问题

本主题为在 Exchange Online 中有邮箱的 Microsoft 365 组织反欺骗保护或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织提供了常见问题解答。

有关反垃圾邮件保护的问题和解答，请参阅"[反垃圾邮件保护常见问题解答"。](anti-spam-protection-faq.md)

有关反恶意软件保护的问题和解答，请参阅 ["反恶意软件保护常见问题解答"](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>为什么 Microsoft 选择垃圾未经身份验证的入站电子邮件？

由于网络钓鱼攻击的影响，并且电子邮件身份验证已存在超过 15 年，因此 Microsoft 相信允许未经身份验证的入站电子邮件允许使用漏报电子邮件的风险高于丢失合法入站电子邮件的风险。

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>垃圾邮件是否有未经身份验证的入站电子邮件会导致合法电子邮件被标记为垃圾邮件？

在 2018 年启用此功能时，可能会出现一些误报， (有正常消息被标记为错误) 。 但是，随着时间的了解，发件人已根据新的发件人身份验证要求进行调整，并且对于大多数电子邮件路径而被错误识别为欺骗邮件的邮件数量都是不可忽略的。

Microsoft 本身在部署到客户之前先几周采用新电子邮件身份验证要求。 虽然最初出现了中断，但此现象逐渐减少了。

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>非 ATP 的 Microsoft 365 客户是否提供欺骗智能？

是。 自 2018 年 10 月起，欺骗智能适用于所有在 Exchange Online 中有邮箱的组织和无 Exchange Online 邮箱的独立 EOP 组织。

反欺骗技术最初仅部署到订阅 Office 365 企业版 E5 订阅或 Office 365 高级威胁防护 (Office 365 ATP) 加载项的组织。

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>如何向 Microsoft 报告垃圾邮件或非垃圾邮件？

参见 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>我是管理员，并且不知道电子邮件域中邮件的所有来源！

请参阅 [你并不知道电子邮件的所有来源](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)。

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>如果对组织禁用反欺骗保护会发生什么情况？

我们不建议这样做，因为你将接触到更多错过的网络钓鱼和垃圾邮件。 并非所有网络钓鱼都是欺骗性的，并且并非所有欺骗都会错过。 但是，你面临的风险将高于启用反欺骗的客户。

既 [然可以使用连接器的增强筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 功能，在将电子邮件传递到 EOP 之前，如果 MX 记录指向了其他服务器或服务，我们不再建议您关闭反欺骗保护。

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>反欺骗防护是否意味着我将防止所有网络钓鱼？

遗遗而无法。 攻击者会不断采用其他技术， (例如，免费电子邮件服务组中被泄漏的帐户或) 。 但是，反网络钓鱼防护可以更好地检测这些其他类型的网络钓鱼方法。 EOP 中的保护层是通过一起设计的，并且是相当构建的。

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>其他大型电子邮件服务是否会阻止未经身份验证的入站电子邮件？

几上所有大型电子邮件服务都实施传统的 SPF、DKIM 和 DMARC 检查。 某些服务拥有其他更严格的检查，但少量使用 EOP 阻止未经身份验证的电子邮件并将其视为欺骗邮件。 但是，行业更加注解了有关未经身份验证的电子邮件问题的更加了解，特别是网络钓鱼问题。

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>如果启用反欺骗，是否仍需要启用高级垃圾邮件筛选 ("SPF 记录：硬失败"许可证标记标记标记 _) A"_ 重点失败"？

不正确。 不再需要此 ASF 设置，因为反欺骗不仅考虑 SPF 硬失败，还会考虑更广泛的标准。 如果已启用防欺骗和“SPF 记录:硬故障”****(_MarkAsSpamSpfRecordHardFail_)，可能会收到更多误报。

我们建议您禁用此功能，因为它几乎对检测垃圾邮件或网络钓鱼邮件提供其他任何好处，而是会生成大部分误报。 有关详细信息，请参阅" [高级垃圾邮件筛选 (EOP 中) ASF 筛选器设置](advanced-spam-filtering-asf-options.md)。

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>发件人重写方案是否帮助修复转发的电子邮件？

SRS 仅部分修复了转发电子邮件的问题。 通过重写 SMTP **MAIL FROM，SRS**可以确保转发的邮件在下一个目标位置通过 SPF。 但是，由于反欺骗基于发件人地址以及**MAIL FROM** **From**或 DKIM 签名域 (或其他信号) ，因此防止将 SRS 转发的电子邮件标记为欺骗邮件不够。
