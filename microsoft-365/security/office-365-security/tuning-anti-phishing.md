---
title: 优化防钓鱼保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 管理员可了解以下原因：如果用户在 Microsoft 365 中网络钓鱼邮件的介绍以及如何在将来阻止出现更多网络钓鱼邮件的原因。
ms.openlocfilehash: b0fbb29489cece6d708811c5c8d8d60450938f0c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825205"
---
# <a name="tune-anti-phishing-protection"></a>优化防钓鱼保护

尽管 Microsoft 365 提供了各种默认启用的防钓鱼功能，但某些网络钓鱼邮件可能仍能通过你的邮箱。 本主题介绍通过哪些操作可以发现网络钓鱼邮件的循环，以及你可以执行哪些操作来调整 Microsoft 365 组织中防钓鱼设置而不会意外地带来 _。_

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>首先，请处理任何被攻击的帐户，并确保阻止所有其他网络钓鱼邮件获取内容

如果收件人的帐户由于网络钓鱼邮件而被攻击，请按照 [Microsoft 365 中响应被入解的电子邮件帐户的步骤进行操作](responding-to-a-compromised-email-account.md)。

如果订阅包含高级威胁防 (ATP) ，则 [可以使用 Office 365 威胁智能](office-365-ti.md) 标识同时收到网络钓鱼邮件的其他用户。 你还可以选择阻止网络钓鱼邮件：

- [ATP 安全链接](set-up-atp-safe-links-policies.md)

- [ATP 安全附件](set-up-atp-safe-attachments-policies.md)

- [Microsoft 365 中的 ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)。 请注意，你可以通过标准增加、更能被攻击**Advanced phishing thresholds**或最高效性来临时提高策略中的**高级网络钓鱼阈值**。 **Standard** **Aggressive** **More aggressive**

验证这些 ATP 功能是否已打开。

## <a name="report-the-phishing-message-to-microsoft"></a>向 Microsoft 报告网络钓鱼邮件

报告网络钓鱼邮件有助于调整用于保护 Microsoft 365 中所有客户的筛选器。 有关说明，请参阅"[报告邮件和文件"发送到 Microsoft。](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>检查邮件头

你可以检查网络钓鱼邮件头，确定是否有你可以自己执行的任何操作，以防止传递更多的网络钓鱼邮件。 换句话说，检查消息头可以帮助您确定你组织中负责允许钓鱼邮件的任何设置。

具体来说，您应当 **在邮件标头中检查 X-Forefront-Antispam-Report** 头字段，以了解"垃圾邮件筛选"版本 SFV 版本值中跳过的垃圾邮件或 (钓鱼) 指示。 跳过筛选的邮件包含一个条目，这意味着其中一项设置允许您通过覆盖服务确定的垃圾邮件或网络钓鱼裁定 `SCL:-1` 允许此邮件。 有关如何获取邮件头和所有可用反垃圾邮件和反网络钓鱼邮件头完整列表的详细信息，请参阅 [Microsoft 365 中的"反垃圾邮件"标头](anti-spam-message-headers.md)。

## <a name="best-practices-to-stay-protected"></a>保持受保护的最佳做法

- 每月运行安全 [功能分](../mtp/microsoft-secure-score.md) 数来评估组织的安全设置。

- 对于错误地或被允许通过的邮件，我们建议您在威胁资源管理器和实时检测中 [搜索那些邮件](threat-explorer.md)。 您可以按发件人、收件人或邮件 ID 进行搜索。 找到邮件后，单击主题可查看详细信息。 对于隔离邮件，请查看"检测技术"是什么，以便你可以使用合适的方法进行替代。 对于允许的消息，查看哪个策略允许此邮件。 

- 伪邮件在 ATP 中标记为钓鱼邮件。 有时欺骗性高效，有时用户不希望隔离它。 若要最大程度地减少对用户的影响，请定期查看 [欺骗智能报告](learn-about-spoof-intelligence.md)。 一经检查并进行了必要的替代，你会相信地将欺骗智能配置**为隔离**可疑邮件，而不是将其传递到用户的"垃圾邮件"文件夹。 [configure spoof intelligence](set-up-anti-phishing-policies.md#spoof-settings)

- 可以对"模拟"或"用户" (重复上述) 。 模拟报告位于威 **胁管理** \> **仪表板** \> **见解下**。

- 定期查看威胁 [防护状态报告](view-reports-for-atp.md#threat-protection-status-report)。

- 某些客户通过将自己域放入反垃圾邮件策略中的"允许发件人"或"允许域"列表中，以意外方式允许邮件受到钓鱼。 虽然通过此配置可允许一些合法的邮件，但是也会允许恶意邮件，这些邮件通常会被垃圾邮件和/或钓鱼邮件筛选器阻止。 应该更正基本问题，而不是允许域。

  处理被 Microsoft 365 (误报) 阻止的与来自域的合法邮件，最佳方法是，为您的所有电子邮件域完全完整地在 DNS 中为 SPF、DKIM 和 DMARC 记录配置_all_SPF、DKIM 和 DMARC 记录：

  - 请验证 SPF 记录是否识别 _了_ 域中发件人的所有电子邮件源 (不会错误第三方服务！) 。

  - 使用硬 (\- 所有) 以确保未经授权的发件人被配置为执行此操作的电子邮件系统拒绝。 你可以使用 [欺骗智能保护来](learn-about-spoof-intelligence.md) 帮助确定使用你的域的发件人，这样就可以在 SPF 记录中添加授权的第三方发件人。

  有关配置说明，请参阅：
  
  - [设置 SPF 以帮助防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [使用 DKIM 验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)

  - [使用 DMARC 验证电子邮件](use-dmarc-to-validate-email.md)

- 建议尽可能地将你的域的电子邮件直接传递到 Microsoft 365。 换句话说，将 Microsoft 365 域的 MX 记录指向 Microsoft 365。 Exchange Online Protection (EOP) 用户的邮件直接传递到 Microsoft 365 时为云用户提供最佳保护。 如果您必须在 EOP 前面使用第三方电子邮件安全机制系统，请使用"增强的连接器筛选"。 有关说明，请参阅["增强的 Exchange Online 中的连接器筛选"。](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- 用户应 [向](enable-the-report-message-add-in.md) Microsoft 报告邮件，告片系统的培训。 管理员还应该利用管理员 [提交](admin-submission.md) 功能。

- MFA 多 (身份验证是) 帐户被泄泄的好方法。 你应该强考虑为所有用户启用 MFA。 有关分阶段方法，首先为你最敏感的用户 (管理员和管理人员等 ) 启用 MFA，然后再为所有人启用 MFA。 有关说明，请参阅["设置多重身份验证"。](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- 攻击者通常使用转发规则给外部收件人来提取数据。 使用" **在 Microsoft 安全功能分数"** 中使用邮箱 [转发规则信息](../mtp/microsoft-secure-score.md) 查找甚至防止将转发规则转发到外部收件人。 有关详细信息，请参阅 [使用安全功能分数缓解客户端外部转发规则](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。
