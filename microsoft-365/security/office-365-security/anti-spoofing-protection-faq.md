---
title: 防欺骗保护常见问题
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以查看有关 Exchange Online Protection （EOP）中的反欺骗保护的常见问题和解答。
ms.openlocfilehash: 603293dd00100e3b93a225d94f2ed8fd9baae6a5
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209091"
---
# <a name="anti-spoofing-protection-faq"></a>防欺骗保护常见问题

本主题提供了有关使用 Exchange Online 中的邮箱或独立 Exchange Online Protection （EOP）组织（没有 Exchange Online 邮箱）的 Microsoft 365 组织的反欺诈保护的常见问题和解答。

有关反垃圾邮件保护的问题和解答，请参阅[反垃圾邮件保护常见问题解答](anti-spam-protection-faq.md)。

有关反恶意软件保护的问题和解答，请参阅[反恶意软件保护常见问题解答](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>为什么 Microsoft 选择未经身份验证的入站电子邮件？

由于网络钓鱼攻击的影响，并且电子邮件身份验证已有超过15年的时间，Microsoft 认为，继续允许未经验证的入站电子邮件的风险高于丢失合法入站电子邮件的风险。

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Junking 未通过身份验证的入站电子邮件是否会导致合法电子邮件被标记为垃圾邮件？

当 Microsoft 在2018中启用此功能时，会发生误报（好的邮件被标记为 "坏"）。 但是，随着时间的推移，发件人会调整到新的发件人身份验证要求，而 misidentified 为欺骗的邮件数量在大多数电子邮件路径中变得可以忽略。

Microsoft 本身在将新的电子邮件身份验证要求部署到客户之前，先将其在几周内采纳。 虽然最初出现了中断，但此现象逐渐减少了。

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>是否在没有 ATP 的情况下，Microsoft 365 客户可以使用欺骗版智能？

是的。 从10月2018起，欺骗智能可供具有邮箱的 Exchange Online 中的所有组织和独立 EOP 组织（无 Exchange Online 邮箱）。

仅向具有 Office 365 企业版 E5 订阅的组织或其订阅的 Office 365 高级威胁防护（Office 365 ATP）加载项部署反欺骗技术。

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>如何向 Microsoft 报告垃圾邮件或非垃圾邮件？

参见 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>我是管理员，我不知道我的电子邮件域中的邮件的所有来源！

请参阅[您不知道您的电子邮件的所有来源](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)。

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>如果我对我的组织禁用反欺骗保护，会发生什么？

我们不建议这样做，因为你将接触到更多错过的网络钓鱼和垃圾邮件。 并非所有网络钓鱼都是欺骗性的，并且并非所有欺骗都会错过。 但是，你面临的风险将高于启用反欺骗的客户。

现在，已[增强了连接器的筛选功能](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)，如果您的 MX 记录指向另一台服务器或服务，然后再将电子邮件传递到 EOP，我们将不再建议您关闭反欺骗保护。

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>反欺骗保护意味着我将免受所有网络钓鱼的阻止？

遗憾的是，不会。 攻击者将使用其他技术（例如，在免费电子邮件服务中受到危害的帐户或帐户）进行调整。 但是，反网络钓鱼保护的工作速度更好，可以检测到这些其他类型的网络钓鱼方法。 EOP 中的保护层设计为协同工作并在彼此之上建立。

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>其他大型电子邮件服务是否阻止未经身份验证的入站电子邮件？

几乎所有大型电子邮件服务都实现传统 SPF、DKIM 和 DMARC 检查。 有些服务有其他更严格的检查，但并不像 EOP 那样阻止未经身份验证的电子邮件，并将其视为欺骗性的邮件。 但是，该行业越来越多地意识到有关未经身份验证的电子邮件的问题，尤其是由于网络钓鱼问题而引起的。

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>如果我启用反欺骗，是否仍需要启用高级垃圾邮件筛选器设置 "SPF 记录：硬故障" （_MarkAsSpamSpfRecordHardFail_）？

不是。 此 ASF 设置不再需要，因为反欺骗不仅认为 SPF 硬失败，而且一组更广泛的条件。 如果已启用防欺骗和“SPF 记录:硬故障”****(_MarkAsSpamSpfRecordHardFail_)，可能会收到更多误报。

我们建议您禁用此功能，因为它几乎没有额外的优势来检测垃圾邮件或网络钓鱼邮件，而是生成大多数误报。 有关详细信息，请参阅[EOP 中的高级垃圾邮件筛选器（ASF）设置](advanced-spam-filtering-asf-options.md)。

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>发件人重写方案是否有助于修复转发的电子邮件？

SRS 仅部分修复了转发电子邮件的问题。 通过重写 SMTP**邮件**，SRS 可以确保转发的邮件在下一个目的地传递 SPF。 但是，由于反欺骗是基于 "**发**件人地址" 或 "DKIM-签名**域" （** 或其他信号）而进行的，因此阻止将 SRS 转发的电子邮件标记为 "欺骗" 是不够的。
