---
title: 优化防钓鱼保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: 管理员可以了解网络钓鱼邮件进入 Microsoft 365 的原因和方式，以及在将来防止更多网络钓鱼邮件时要执行哪些操作。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 299488a7ed8a891d870efb3ace618178c36552f1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206465"
---
# <a name="tune-anti-phishing-protection"></a>优化防钓鱼保护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

尽管Microsoft 365附带了各种默认情况下启用的防钓鱼功能，但某些网络钓鱼邮件可能仍可以到达您的邮箱。 本主题介绍您可以执行哪些操作来发现网络钓鱼邮件通过的原因，以及您可以如何调整 Microsoft 365 组织的反网络钓鱼设置，而不会意外使情况 _变得更糟_。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>首先：处理所有遭到入侵的帐户，并确保阻止更多网络钓鱼邮件通过

如果收件人的帐户由于网络钓鱼邮件而遭到入侵，请按照响应电子邮件中遭到入侵的电子邮件帐户中的[Microsoft 365。](responding-to-a-compromised-email-account.md)

如果你的订阅包含 Microsoft Defender for Office 365，可以使用 Office 365[威胁](office-365-ti.md)智能来识别还收到网络钓鱼邮件的其他用户。 有其他选项可以阻止钓鱼邮件：

- [保险箱Microsoft Defender for Office 365](set-up-safe-links-policies.md)

- [保险箱Microsoft Defender for Office 365](set-up-safe-attachments-policies.md)

- [Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md)中的防钓鱼策略。 请注意，你可以暂时将策略中的高级网络钓鱼阈值从 **"标准**"提高为 **"主动**"、更 **主动** 或 **最具有攻击性**。

验证这些 Defender Office 365功能是否打开。

## <a name="report-the-phishing-message-to-microsoft"></a>向 Microsoft 报告网络钓鱼邮件

报告网络钓鱼邮件有助于优化用于保护电子邮件中所有客户的Microsoft 365。 有关说明，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="inspect-the-message-headers"></a>检查邮件头

你可以检查网络钓鱼邮件的邮件头，看看是否有自己能够阻止更多网络钓鱼邮件通过的内容。 换句话说，检查邮件头可以帮助您识别组织中负责允许网络钓鱼邮件进入的任何设置。

具体来说，应检查邮件头中的 **X-Forefront-Antispam-Report** 头字段，以在 SFV 垃圾邮件筛选裁定 (值中指示已跳过对垃圾邮件或网络钓鱼) 筛选。 跳过筛选的邮件将具有 的条目，这意味着你的设置之一通过覆盖由服务确定的垃圾邮件或网络钓鱼裁定来 `SCL:-1` 允许此邮件通过。 若要详细了解如何获取邮件头以及所有可用反垃圾邮件和反网络钓鱼邮件头的完整列表，请参阅 Microsoft 365[中的反垃圾邮件邮件头](anti-spam-message-headers.md)。

## <a name="best-practices-to-stay-protected"></a>保持受保护状态的最佳方案

- 每月运行安全 [分数](../defender/microsoft-secure-score.md) 来评估组织的安全设置。

- 对于错误地隔离的邮件，或允许通过的邮件，我们建议你在威胁资源管理器和实时检测中搜索 [这些邮件](threat-explorer.md)。 可以按发件人、收件人或邮件 ID 进行搜索。 找到邮件后，单击主题转到详细信息。 对于隔离的邮件，查看"检测技术"是什么，以便您可以使用适当的方法进行覆盖。 对于允许的邮件，查看允许邮件的策略。

- 来自欺骗 (发件人的电子邮件地址与邮件来源不匹配的邮件) 在 Defender for Office 365 中分类为网络钓鱼。 有时欺骗是恶意的，有时用户不希望隔离来自特定欺骗发件人的邮件。 若要最大程度地减小对用户的影响，请定期查看[](learn-about-spoof-intelligence.md)欺骗智能见解、租户允许[/](tenant-allow-block-list.md)阻止列表中的"欺骗"选项卡和欺骗[检测报告](view-email-security-reports.md#spoof-detections-report)。 查看允许和阻止的欺骗发件人并进行必要的替代后，你可以确信地将反网络钓鱼策略中的欺骗智能配置为隔离可疑[](set-up-anti-phishing-policies.md#spoof-settings)邮件，而不是将它们发送到用户的垃圾邮件文件夹。 

- 你可以对 Microsoft Defender 中的 (或用户) 模拟重复上述Office 365。 模拟报告位于威胁 **管理仪表板** \>  \> Insights。

- 定期检查威胁 [防护状态报告](view-reports-for-mdo.md#threat-protection-status-report)。

- 一些客户无意中允许网络钓鱼邮件通过，他们通过将自己的域放在反垃圾邮件策略的"允许发件人"或"允许域"列表中。 尽管此配置将允许一些合法邮件通过，但它还将允许通常会被垃圾邮件和/或网络钓鱼筛选器阻止的恶意邮件。 应纠正基础问题，而不是允许域。

  处理由 Microsoft 365 (误报) 阻止的合法邮件（涉及域中的发件人）的最好办法就是在所有电子邮件域的 DNS 中完全配置 SPF、DKIM 和 DMARC 记录： 

  - 验证 SPF 记录是否 _标识_ 域中发件人的所有电子邮件 (不要忘记第三方服务！) 。

  - 使用硬 (所有) ，以确保配置为拒绝未经授权的发件人的电子邮件 \- 系统。 您可以使用欺骗 [智能见解](learn-about-spoof-intelligence.md) 来帮助识别正在使用你的域的发件人，以便可以在 SPF 记录中包括授权的第三方发件人。

  有关配置说明，请参阅：

  - [设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [使用 DKIM 验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)

  - [使用 DMARC 验证电子邮件](use-dmarc-to-validate-email.md)

- 建议尽可能将域的电子邮件直接发送到Microsoft 365。 换句话说，将你的Microsoft 365域的 MX 记录指向Microsoft 365。 Exchange Online Protection (EOP) 能够为云用户提供最佳保护，当其邮件直接传递到 Microsoft 365。 如果必须在 EOP 前面使用第三方电子邮件清洁系统，请使用增强的连接器筛选功能。 有关说明，请参阅[增强的连接器筛选Exchange Online。](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- 用户应该使用["报告邮件"](enable-the-report-message-add-in.md)加载项或"报告[](enable-the-report-phish-add-in.md)钓鱼邮件"加载项向 Microsoft 报告邮件，Microsoft 可以训练我们的系统。 管理员还应利用管理员 [提交](admin-submission.md) 功能。

- 使用 MFA (多重) 是防止帐户遭到入侵的一个好方法。 你应强烈建议为所有用户启用 MFA。 对于分阶段方法，首先为最敏感的用户 (管理员、主管人员等) ，然后再为所有人启用 MFA。 有关说明，请参阅 [设置多重身份验证](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。

- 向外部收件人转发规则通常被攻击者用来提取数据。 使用 [Microsoft](../defender/microsoft-secure-score.md) **安全分数中的"** 审阅邮箱转发规则"信息查找甚至阻止将规则转发给外部收件人。 有关详细信息，请参阅使用安全分数缓解客户端 [外部转发规则](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。
