---
title: 默认情况下在 Office 365 中安全
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: '有关详细信息，请参阅 Exchange Online Protection (EOP 中的默认安全设置) '
ms.openlocfilehash: 54000d351463ba90751f1f27638fb52847cf05ce
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558498"
---
# <a name="secure-by-default-in-office-365"></a>默认情况下在 Office 365 中安全

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"默认情况下安全" 是一种术语，用于定义尽可能安全的默认设置。

但是，安全性需要与工作效率平衡。 这可能包括跨以下各项的平衡：

- **可用性**：设置不应以用户工作效率为依据。
- **风险**：安全性可能会阻止重要活动。
- **旧版设置**：出于商业原因，可能需要维护某些旧产品和功能的一些配置，即使新的新式设置得到改进也是如此。

通过 exchange online 中邮箱的 Microsoft 365 组织受到 Exchange Online Protection (EOP) 的保护。 此保护包括：

- 带有可疑恶意软件的电子邮件将自动被隔离，收件人将收到通知。 请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。
- 被标识为高可信度网络钓鱼的电子邮件将根据反垃圾邮件策略操作进行处理。 请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

由于 Microsoft 想让我们的客户在默认情况下是安全的，因此某些租户替代不会应用于恶意软件或高可信度的网络钓鱼。 这些替代包括：

-  (反垃圾邮件策略的允许的发件人列表或允许的域列表) 
- Outlook 安全发件人
-  (连接筛选的 IP 允许列表) 

有关这些覆盖的详细信息，可参阅 [创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

"默认安全" 不是一种可以打开或关闭的设置，但也是我们的筛选在框中的工作方式，以防止邮箱中出现潜在危险或不需要的邮件。 应隔离恶意软件和高可信度的网络钓鱼邮件。 只有管理员可以管理被隔离为恶意软件或高可信度网络钓鱼的邮件，也可以在那里向 Microsoft 报告误报。 有关详细信息，请参阅 [在 EOP 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>有关此操作的原因的详细信息

默认情况下安全的精神是：我们对邮件采取相同的操作，如果您知道邮件是恶意的，即使有允许的地方也是如此。 这与我们在恶意软件中使用的方法相同，现在我们将此相同的行为扩展到高可信度的网络钓鱼邮件。 我们的数据表明高可信度的网络钓鱼邮件的误报利率极低，管理员可以使用管理员提交的任何误报来解决。 我们的数据还表示在反垃圾邮件策略和 Outlook 中的安全发件人中，允许的发件人列表和允许的域列表过于广泛，因而导致更大损害。

为了使其成为另一种方式：作为一项安全服务，我们正在代表你，以防止你的用户受到危害。 此外，默认情况下安全不会完全接管反垃圾邮件策略中的高可信度网络钓鱼邮件的可用选项。 尽管我们建议隔离，但仍可使用的其他操作仍可用 (移动到 "垃圾邮件" 文件夹或重定向到电子邮件地址) 。

## <a name="exceptions"></a>Exceptions

允许高可信度仿冒邮件绕过筛选的唯一替代是 Exchange 邮件流规则 (也称为传输规则) 。 若要使用邮件流规则绕过筛选，请参阅 [使用邮件流规则在邮件中设置 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

仅在以下情况下，才应考虑使用替代：

- 网络钓鱼模拟：模拟攻击可帮助您在真正的攻击影响组织之前识别易受攻击的用户。
- Security/SecOps 邮箱：安全团队使用的专用邮箱)  (好的和坏的中获取未筛选的邮件。 然后，团队可以查看它们是否包含恶意内容。
- 第三方筛选器：某些第三方供应商建议将 EOP (SCL =-1) ，因为第三方筛选器将管理邮件筛选。 Microsoft 不建议关闭 EOP，因为 Defender for Office 365 需要 EOP。 相反，此处的建议是为连接器启用 [增强的筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)功能。
- 误报：您可能希望临时允许某些邮件仍由 Microsoft [通过管理员提交](admin-submission.md)进行分析。 与所有替代一样，建议它们是临时性的。
