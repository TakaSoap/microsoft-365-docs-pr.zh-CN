---
title: 默认情况下，安全Office 365
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
description: '详细了解 EOP Exchange Online Protection (中的默认设置) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2d5cdc8f8faa9c2d5772fd1572134ea49cdd77da
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624045"
---
# <a name="secure-by-default-in-office-365"></a>默认情况下，安全Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"默认保护"一词用于定义尽可能安全的默认设置。

但是，安全性需要与生产力平衡。 这可能包括以下各点之间的平衡：

- **可用性** 设置不应影响用户工作效率。
- **风险**：安全性可能会阻止重要活动。
- **旧设置**：出于业务原因，可能需要维护较旧产品和功能的一些配置，即使新的新式设置已改进。

Microsoft 365邮箱的组织Exchange Online EOP Exchange Online Protection (保护) 。 此保护包括：

- 包含可疑恶意软件的电子邮件将自动隔离，并通知收件人。 请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。
- 标识为高可信度网络钓鱼的电子邮件将按照反垃圾邮件策略操作进行处理。 请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

有关 EOP 详细信息，请参阅Exchange Online Protection[概述](exchange-online-protection-overview.md)。

由于 Microsoft 默认希望保护我们的客户安全，因此某些租户替代不适用于恶意软件或高可信度网络钓鱼。 这些替代包括：

- 允许发件人列表或允许的域 (反垃圾邮件策略) 
- Outlook 保险箱发件人
- IP 允许列表 (连接筛选) 

有关这些替代项详细信息，请参阅创建 [安全发件人列表](create-safe-sender-lists-in-office-365.md)。

> [!NOTE]
> 我们正在弃用 EOP 反垃圾邮件策略中的高可信度网络钓鱼电子邮件裁定的"将邮件移动到垃圾邮件文件夹"操作。 对高可信度网络钓鱼邮件使用此操作的反垃圾邮件策略将转换为隔离 **邮件**。 高 **可信度网络钓鱼** 邮件的"将邮件重定向到电子邮件地址"操作不受影响。

默认情况下，"安全"不是可以打开或关闭的设置，而是我们的筛选开箱即用来将潜在危险或不需要的邮件从邮箱中排除的方式。 应隔离恶意软件和高可信度网络钓鱼邮件。 只有管理员才能管理被隔离为恶意软件或高可信度网络钓鱼的邮件，并且他们还可以从该邮件向 Microsoft 报告误报。 有关详细信息，请参阅在 EOP 中以管理员角色管理隔离 [的邮件和文件](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>有关我们这样做的原因的更多

默认情况下，确保安全的提示是：即使您知道邮件是恶意邮件，我们将对邮件执行相同的操作，即使已配置的异常将允许传递该邮件。 这是我们一直对恶意软件使用的相同方法，现在我们正在将相同的行为扩展到高可信度网络钓鱼邮件。

我们的数据显示，与隔离相比，用户点击垃圾邮件文件夹中邮件中的恶意链接的可能性是 30 倍。 我们的数据还表明，对于高可信度网络钓鱼 (误报率) 误报率非常低，管理员可以通过管理员提交来解决任何误报。

我们还确定反垃圾邮件策略中允许的发件人和允许的域列表保险箱发件人Outlook过广，导致危害大于好。

另一方面：作为一项安全服务，我们代表你采取行动，防止你的用户遭到入侵。

## <a name="exceptions"></a>例外

> [!NOTE]
> 2021 年 7 月，默认将安全扩展到Exchange传输规则 (传输规则) 。 如果使用邮件流规则允许第三方网络钓鱼模拟或未经筛选地传递至安全操作邮箱，则最终需要消除这些规则，并切换到使用高级传递策略（如果该功能可供你 [](configure-advanced-delivery.md)_使用）。_

允许高可信度网络钓鱼邮件绕过筛选的唯一替代是邮件流规则。 若要使用邮件流规则绕过筛选，请参阅使用邮件流[规则设置邮件中的 SCL。](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

只应考虑在下列情况下使用替代：

- 网络钓鱼模拟：模拟攻击可以帮助你在真实攻击影响组织之前识别易受攻击的用户。
- Security/SecOps 邮箱：安全团队用于获取未筛选邮件的专用邮箱 (好和坏) 。 Teams查看它们是否包含恶意内容。
- 第三方筛选器：当域的 MX 记录不指向域的 MX 记录时，默认情况下Office 365。
- 误报：你可能希望暂时允许 Microsoft 通过管理员提交分析某些 [邮件](admin-submission.md)。 与所有替代一样，建议它们为临时替代。
