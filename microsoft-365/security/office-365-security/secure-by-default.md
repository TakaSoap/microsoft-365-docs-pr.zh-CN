---
title: Office 365 中的默认安全
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: '详细了解 Exchange Online Protection (EOP) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a507abce8c18657794b56570241570e5048b89d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288509"
---
# <a name="secure-by-default-in-office-365"></a>Office 365 中的默认安全

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

"默认安全"一词用于定义尽可能安全的默认设置。

但是，安全性需要与工作效率平衡。 这可能包括以下各点之间的平衡：

- **可用性**：设置不应影响用户工作效率。
- **风险**：安全性可能会阻止重要活动。
- **旧设置**：出于业务原因，可能需要维护较旧产品和功能的一些配置，即使改进了新的新式设置。

在 Exchange Online 中拥有邮箱的 Microsoft 365 组织受 Exchange Online Protection (EOP) 。 此保护包括：

- 将自动隔离包含可疑恶意软件的电子邮件，并通知收件人。 请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。
- 标识为高可信度网络钓鱼的电子邮件将按照反垃圾邮件策略操作进行处理。 请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

有关 EOP 详细信息，请参阅 [Exchange Online Protection 概述](exchange-online-protection-overview.md)。

由于默认情况下，Microsoft 希望确保我们的客户安全，因此某些租户替代不适用于恶意软件或高可信度网络钓鱼。 这些替代包括：

- 允许的发件人列表或允许的域 (反垃圾邮件策略) 
- Outlook 安全发件人
- IP 允许列表 (连接筛选) 

有关这些替代项的更多信息，请参阅["创建安全发件人列表"。](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> 我们正在弃用 EOP 反垃圾邮件策略中高可信度网络钓鱼电子邮件裁定的"将邮件移动到垃圾邮件"文件夹操作。 对高可信度网络钓鱼邮件使用此操作的反垃圾邮件策略将转换为隔离 **邮件**。 高 **可信度网络钓鱼** 邮件的"重定向到电子邮件地址"操作不受影响。

默认情况下，安全不是可以打开或关闭的设置，而是我们的筛选功能开箱即用以将潜在危险或不需要的邮件从邮箱中排除的方式。 应隔离恶意软件和高可信度网络钓鱼邮件。 只有管理员才能管理被隔离为恶意软件或高可信度网络钓鱼的邮件，并且他们还可以从该邮件向 Microsoft 报告误报。 有关详细信息，请参阅在[EOP](manage-quarantined-messages-and-files.md)中以管理员角色管理隔离的邮件和文件

## <a name="more-on-why-were-doing-this"></a>详细了解我们这样做的原因

默认情况下，确保安全是：我们将对邮件执行相同的操作，如果您知道邮件是恶意邮件，即使已配置的异常会允许传递该邮件。</a0> 这是我们一直用于恶意软件的相同方法，现在我们将此相同行为扩展到高可信度网络钓鱼邮件。

我们的数据显示，与"隔离"相比，用户在"垃圾邮件"文件夹的邮件中单击恶意链接的可能性是"垃圾邮件"的 30 倍。 我们的数据还表明，对于高可信度网络钓鱼 (标记为错误) 的误报邮件，误报率非常低，管理员可以通过管理员提交解决任何误报。

我们还确定反垃圾邮件策略中的允许发件人和允许的域列表和 Outlook 中的安全发件人过于广泛，并且造成危害大于好。

另一方面：作为一项安全服务，我们代表你采取行动来防止你的用户受到威胁。 

## <a name="exceptions"></a>Exceptions

允许高可信度网络钓鱼邮件绕过筛选的唯一替代是 Exchange 邮件流规则 (也称为传输规则) 。 若要使用邮件流规则绕过筛选，请参阅"使用邮件流规则在邮件[中设置 SCL"。](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

只应考虑在下列情况下使用替代：

- 网络钓鱼模拟：模拟攻击可帮助您在真正的攻击影响组织之前识别易受攻击的用户。
- 安全/SecOps 邮箱：安全团队用于获取未筛选邮件的专用邮箱 (好和坏) 。 然后，团队可以查看它们是否包含恶意内容。
- 第三方筛选器：当域的 MX 记录不指向 Office 365 时，默认情况下不应用安全。
- 误报：你可能希望暂时允许 Microsoft 通过管理员提交仍在 [分析某些邮件](admin-submission.md)。 与所有替代一样，建议它们是临时的。
