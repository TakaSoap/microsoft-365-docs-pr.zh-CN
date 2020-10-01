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
description: 管理员可以了解如何在 Microsoft 365 中确定仿冒邮件的原因以及在将来阻止更多网络钓鱼邮件的原因。
ms.openlocfilehash: 813a9c263d9cc620606c7a5e272e47bdaf1ff7a7
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328055"
---
# <a name="tune-anti-phishing-protection"></a>优化防钓鱼保护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


尽管 Microsoft 365 提供了在默认情况下启用的各种反网络钓鱼功能，但有些网络钓鱼邮件仍可能会到达您的邮箱。 本主题介绍您可以执行哪些操作来发现仿冒邮件的访问原因，以及您可以采取什么措施来调整 Microsoft 365 组织中的反网络钓鱼设置， _而不会意外地使事情更糟_。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>首先要做的第一件事：处理任何受损帐户，并确保阻止任何更多的网络钓鱼邮件

如果收件人的帐户因仿冒邮件而受到威胁，请按照在 [Microsoft 365 中响应已泄露电子邮件帐户中](responding-to-a-compromised-email-account.md)的步骤操作。

如果你的订阅包括高级威胁防护 (ATP) ，则可以使用 [Office 365 威胁智能](office-365-ti.md) 来标识也收到网络钓鱼邮件的其他用户。 您还可以使用其他选项阻止网络钓鱼邮件：

- [Office 365 ATP 中的安全链接](set-up-atp-safe-links-policies.md)

- [Office 365 ATP 中的安全附件](set-up-atp-safe-attachments-policies.md)

- [Office 365 ATP 中的反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。 请注意，可以暂时将策略中的 **高级网络钓鱼阈值** 从 **Standard** 提高到 **主动**、 **更主动**或 **最严格**的。

验证这些 ATP 功能是否已打开。

## <a name="report-the-phishing-message-to-microsoft"></a>向 Microsoft 报告网络钓鱼邮件

在调整用于保护 Microsoft 365 中所有客户的筛选器时，报告网络钓鱼邮件非常有帮助。 有关说明，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="inspect-the-message-headers"></a>检查邮件头

您可以检查网络钓鱼邮件的标头，以查看是否有任何可以执行的操作，以防止更多的网络钓鱼邮件进入。 换句话说，检查邮件头可以帮助您确定组织中负责允许网络钓鱼邮件的任何设置。

具体来说，应检查邮件头中的 **X-Forefront-反垃圾邮件报告** 标头字段，以了解垃圾邮件筛选判定中跳过的垃圾邮件或网络钓鱼筛选是否 (SFV) 值。 跳过筛选的邮件将具有一个条目 `SCL:-1` ，这意味着您的设置允许此邮件通过覆盖由该服务确定的垃圾邮件或网络钓鱼 verdicts。 有关如何获取邮件头以及所有可用反垃圾邮件和反网络钓鱼邮件头的完整列表的详细信息，请参阅 [Microsoft 365 中的反垃圾邮件邮件头](anti-spam-message-headers.md)。

## <a name="best-practices-to-stay-protected"></a>保持受保护状态的最佳做法

- 在每月的基础上，运行 [安全分数](../mtp/microsoft-secure-score.md) 以评估组织的安全设置。

- 对于因错误而在隔离的邮件中或允许通过的邮件，我们建议您在 [威胁资源管理器和实时检测](threat-explorer.md)中搜索这些邮件。 您可以按发件人、收件人或邮件 ID 进行搜索。 找到该邮件后，单击 "主题" 以转到 "详细信息"。 对于隔离的邮件，请查看 "检测技术" 是什么，以便您可以使用相应的方法进行替代。 对于允许的邮件，请查看允许邮件使用的策略。 

- 哄骗邮件在 ATP 中被标记为网络钓鱼。 有时欺骗是良性的，有时用户不希望隔离。 若要最大限度地减少对用户的影响，请定期查看 [欺骗智能报告](learn-about-spoof-intelligence.md)。 一旦您查看并进行了任何必需的替代，您就可以放心地 [将欺骗智能配置](set-up-anti-phishing-policies.md#spoof-settings) 为 **隔离** 可疑邮件，而不是将其传递到用户的 "垃圾邮件" 文件夹。

- 您可以对域或用户)  (模拟执行上述步骤。 在 **威胁管理** \> **仪表板** \> **见解**下找到模拟报告。

- 定期查看 [威胁防护状态报告](view-reports-for-atp.md#threat-protection-status-report)。

- 某些客户通过将自己的域放在反垃圾邮件策略中的 "允许发件人" 或 "允许域" 列表中，在无意中允许网络钓鱼邮件。 虽然此配置允许某些合法邮件通过，但它还会允许垃圾邮件和/或网络钓鱼筛选器通常会阻止的恶意邮件。 应更正基本问题，而不是允许域。

  若要处理由 Microsoft 365 阻止的合法邮件 (误报) （涉及域中的发件人）的最佳方式是为 _所有_ 电子邮件域在 DNS 中完全且完整地配置 SPF、DKIM 和 DMARC 记录：

  - 验证您的 SPF 记录是否标识了您的域中的发件人的 _所有_ 电子邮件源 (不会忘记第三方服务！ ) 。

  - 使用 "硬失败" (\- 所有) ，以确保配置为这样的电子邮件系统拒绝未经授权的发件人。 您可以使用 [欺骗智能](learn-about-spoof-intelligence.md) 来帮助标识使用您的域的发件人，以便您可以在 SPF 记录中包括授权的第三方发件人。

  有关配置说明，请参阅：
  
  - [设置 SPF 以帮助防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [使用 DKIM 验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)

  - [使用 DMARC 验证电子邮件](use-dmarc-to-validate-email.md)

- 如果可能，我们建议您将域的电子邮件直接传递到 Microsoft 365。 换句话说，将 Microsoft 365 域的 MX 记录指向 Microsoft 365。 Exchange Online Protection (EOP) 能够在将其邮件直接传递到 Microsoft 365 时为你的云用户提供最佳保护。 如果必须在 EOP 前面使用第三方电子邮件清洁系统，请对连接器使用增强的筛选。 有关说明，请参阅 [增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- 用户应将 [邮件报告](enable-the-report-message-add-in.md) 给 Microsoft，这样可以培训我们的系统。 管理员还应充分利用 [管理员提交](admin-submission.md) 功能。

- 多重因素身份验证 (MFA) 是一种防止受到攻击的帐户的有效方式。 强烈考虑为所有用户启用 MFA。 对于分阶段的方法，首先在为每个人启用 MFA 之前，先为最敏感的用户启用 MFA (管理员、主管等 ) 。 有关说明，请参阅 [设置多因素身份验证](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。

- 将规则转发给外部收件人通常由攻击者用来提取数据。 使用 "审阅[Microsoft 安全分数](../mtp/microsoft-secure-score.md)中的**邮箱转发规则**" 信息查找甚至阻止外部收件人的转发规则。 有关详细信息，请参阅 [通过安全分数缓解客户端外部转发规则](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。
