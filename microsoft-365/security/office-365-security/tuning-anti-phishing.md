---
title: 优化防钓鱼保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: 管理员可以了解在 Microsoft 365 中通过网络钓鱼邮件的原因和方式，以及在将来防止更多钓鱼邮件时要执行哪些操作。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d3abbafce36c589f60eb164fb29c714c980f8b98
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286485"
---
# <a name="tune-anti-phishing-protection"></a>优化防钓鱼保护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

尽管 Microsoft 365 附带了各种默认情况下启用的防钓鱼功能，但某些网络钓鱼邮件可能仍可以到达您的邮箱。 本主题介绍您可以执行哪些操作来发现网络钓鱼邮件通过的原因，以及您可以如何调整 Microsoft 365 组织中防钓鱼设置，而不会意外使情况变得 _更糟_。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>首先：处理任何遭到入侵的帐户，并确保阻止更多网络钓鱼邮件通过

如果收件人的帐户由于网络钓鱼邮件而遭到入侵，请按照 [Microsoft 365](responding-to-a-compromised-email-account.md)中响应遭到入侵的电子邮件帐户中的步骤操作。

如果你的订阅包含 Microsoft Defender for Office 365，可以使用 [Office 365 威胁](office-365-ti.md) 智能来标识还收到网络钓鱼邮件的其他用户。 有其他选项可以阻止网络钓鱼邮件：

- [Microsoft Defender for Office 365 中的安全链接](set-up-atp-safe-links-policies.md)

- [Microsoft Defender for Office 365 中的安全附件](set-up-atp-safe-attachments-policies.md)

- [Microsoft Defender for Office 365 中的防钓鱼策略](configure-atp-anti-phishing-policies.md)。 请注意，你可以暂时将策略中的高级网络钓鱼阈值从 **"标准**"提高为 **"主动**"、"**更主动**"**或"最主动"。**

验证这些 Defender for Office 365 功能是否打开。

## <a name="report-the-phishing-message-to-microsoft"></a>将网络钓鱼邮件报告给 Microsoft

报告网络钓鱼邮件有助于调整用于保护 Microsoft 365 中所有客户的筛选器。 有关说明，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="inspect-the-message-headers"></a>检查邮件头

您可以检查网络钓鱼邮件的邮件头，看看是否有自己能够阻止更多网络钓鱼邮件通过的内容。 换句话说，检查邮件头可以帮助您确定组织中负责允许钓鱼邮件的任何设置。

具体来说，应检查邮件头中的 **X-Forefront-Antispam-Report** 头字段，以在"垃圾邮件筛选裁定 (SFV) "值中指示跳过垃圾邮件或网络钓鱼筛选。 跳过筛选的邮件将具有一个条目，这意味着你的一个设置允许通过覆盖由服务确定的垃圾邮件或网络钓鱼裁定来传递 `SCL:-1` 此邮件。 若要详细了解如何获取邮件头以及所有可用的反垃圾邮件和反网络钓鱼邮件头的完整列表，请参阅 [Microsoft 365](anti-spam-message-headers.md)中的反垃圾邮件邮件头。

## <a name="best-practices-to-stay-protected"></a>保持受保护状态的最佳方案

- 每月运行安全 [分数](../mtp/microsoft-secure-score.md) 来评估组织的安全设置。

- 对于错误地最终隔离的邮件，或者对于允许通过的邮件，我们建议你在威胁资源管理器和实时检测中搜索这些 [邮件](threat-explorer.md)。 可以按发件人、收件人或邮件 ID 进行搜索。 找到邮件后，单击主题转到详细信息。 对于隔离的邮件，查看什么是"检测技术"，以便您可以使用适当的方法来替代。 对于允许的邮件，查看允许该邮件的策略。

- 在 Defender for Office 365 中，欺骗邮件被标记为网络钓鱼。 有时欺骗是恶意的，有时用户不希望隔离它。 若要尽可能减小对用户的影响，请定期查看 [欺骗智能报告](learn-about-spoof-intelligence.md)。 查看并进行必要的替代后，可以确信地将欺骗智能配置为 **隔离可疑邮件**，[](set-up-anti-phishing-policies.md#spoof-settings)而不是将其发送到用户的"垃圾邮件"文件夹。

- 您可以对域或用户域中的模拟 (重复上述) 。 模拟报告位于 **威胁** 管理仪表板 \>  \> **见解下**。

- 定期检查 [威胁防护状态报告](view-reports-for-atp.md#threat-protection-status-report)。

- 一些客户无意中通过将自己的域放入反垃圾邮件策略中的"允许发件人"或"允许域"列表中来允许网络钓鱼邮件。 尽管此配置允许某些合法邮件通过，但它还将允许通常被垃圾邮件和/或网络钓鱼筛选器阻止的恶意邮件。 应纠正基础问题，而不是允许域。

  处理由 Microsoft 365 (误报) 阻止的合法邮件（涉及域中的发件人）的最佳方法为在所有电子邮件域的 DNS 中完全完全配置 SPF、DKIM 和 DMARC 记录： 

  - 验证 SPF 记录是否 _标识域中_ 发件人的所有电子邮件 (不要忘记第三方服务！) 。

  - 使用硬 () ，以确保未经授权的发件人被配置为拒绝的电子邮件系统 \- 拒绝。 您可以使用 [欺骗智能](learn-about-spoof-intelligence.md) 来帮助识别正在使用你的域的发件人，以便可以在 SPF 记录中包括授权的第三方发件人。

  有关配置说明，请参阅：

  - [设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [使用 DKIM 验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)

  - [使用 DMARC 验证电子邮件](use-dmarc-to-validate-email.md)

- 如果可能，我们建议你直接将域的电子邮件发送到 Microsoft 365。 换句话说，将 Microsoft 365 域的 MX 记录指向 Microsoft 365。 Exchange Online Protection (EOP) 在邮件直接传递到 Microsoft 365 时，可以为云用户提供最佳保护。 如果必须在 EOP 前面使用第三方电子邮件清洁系统，请使用连接器的增强筛选。 有关说明，请参阅 [Exchange Online 中连接器的增强筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- 用户应该使用 ["报告](enable-the-report-message-add-in.md) 邮件"加载项或" [报告](enable-the-report-phish-add-in.md) 网络钓鱼"外接程序向 Microsoft 报告邮件，Microsoft 可以训练我们的系统。 管理员还应利用管理员 [提交](admin-submission.md) 功能。

- MFA (多重) 是防止帐户泄露的一个好方法。 你应强烈建议为所有用户启用 MFA。 对于分阶段方法，首先为最敏感的用户 (管理员、主管人员等) MFA，然后再为所有人启用 MFA。 有关说明，请参阅["设置多重身份验证"。](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- 攻击者通常使用将规则转发给外部收件人来提取数据。 使用 [Microsoft](../mtp/microsoft-secure-score.md) **安全分数中的"审阅邮箱转发** 规则"信息查找甚至阻止将规则转发给外部收件人。 有关详细信息，请参阅使用安全分数缓解客户端外部 [转发规则](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。
