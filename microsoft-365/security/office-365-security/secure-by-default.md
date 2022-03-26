---
title: 默认情况下，安全Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: '详细了解 EOP Exchange Online Protection (中的默认设置) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 59f29b0e923bdeb7481a64fb9ba1c3890e2b1369
ms.sourcegitcommit: 9c8eca862a2f0fdca7a66c641e382e37fcaefa10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "63775491"
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

- 包含可疑恶意软件的电子邮件将自动隔离。 是否向收件人通知隔离的恶意软件邮件由隔离策略和反恶意软件策略中的设置控制。 有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。
- 标识为高可信度网络钓鱼的电子邮件将按照反垃圾邮件策略操作进行处理。 请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

有关 EOP 详细信息，请参阅Exchange Online Protection[概述](exchange-online-protection-overview.md)。

由于 Microsoft 默认希望保护我们的客户安全，因此某些租户替代不适用于恶意软件或高可信度网络钓鱼。 这些替代包括：

- 允许的发件人列表或允许的域 (反垃圾邮件策略) 
- Outlook 保险箱发件人
- IP 允许列表 (连接筛选) 
- Exchange邮件流规则 (传输规则) 

有关这些替代项详细信息，请参阅创建 [安全发件人列表](create-safe-sender-lists-in-office-365.md)。

> [!NOTE]
> 我们已在 EOP 反垃圾邮件策略中针对高可信度网络钓鱼电子邮件裁定弃用"将邮件移动到垃圾邮件文件夹"操作。 对高可信度网络钓鱼邮件使用此操作的反垃圾邮件策略将转换为隔离 **邮件**。 高 **可信度网络钓鱼** 邮件的"将邮件重定向到电子邮件地址"操作不受影响。

默认情况下，"安全"不是可以打开或关闭的设置，而是我们的筛选开箱即用以将潜在危险或不需要的邮件从邮箱中排除的方式。 应隔离恶意软件和高可信度网络钓鱼邮件。 默认情况下，只有管理员才能管理被隔离为恶意软件或高可信度网络钓鱼的邮件，并且他们还可以从该位置向 Microsoft 报告误报。 有关详细信息，请参阅 [在 EOP 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)。

## <a name="more-on-why-were-doing-this"></a>有关我们这样做的原因的更多

默认情况下，确保安全的提示是：即使您知道邮件是恶意邮件，我们将对邮件执行相同的操作，即使配置的异常会允许传递该邮件。 这是我们一直对恶意软件使用的相同方法，现在我们正在将相同的行为扩展到高可信度网络钓鱼邮件。

我们的数据显示，与隔离相比，用户点击垃圾邮件文件夹中邮件中的恶意链接的可能性是 30 倍。 我们的数据还指示， (高可信度网络钓鱼邮件标记为错误) 的误报邮件的误报率非常低，管理员可以通过管理员提交来解决任何误报。

我们还确定反垃圾邮件策略中的允许发件人和允许的域列表和 Outlook 中的保险箱发件人过于广泛，导致危害大于好。

另一方面：作为一项安全服务，我们代表你采取行动，防止你的用户受到威胁。

## <a name="exceptions"></a>Exceptions

只应考虑在下列情况下使用替代：

- 网络钓鱼模拟：模拟攻击可以帮助你在真实攻击影响组织之前识别易受攻击的用户。 若要阻止筛选网络钓鱼模拟邮件，请参阅在高级传递策略中配置第三 [方网络钓鱼模拟](/microsoft-365/security/office-365-security/configure-advanced-delivery#use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy)。
- Security/SecOps 邮箱：安全团队用于获取未筛选邮件的专用邮箱 (好和坏) 。 Teams查看它们是否包含恶意内容。 有关详细信息，请参阅在高级传递策略中配置 [SecOps 邮箱](/microsoft-365/security/office-365-security/configure-advanced-delivery#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy)。
- 第三方筛选器：默认情况下，安全仅适用于域的 MX 记录设置为 Exchange Online Protection (contoso.mail.protection.outlook.com) 。 如果设置为其他服务或设备，则默认情况下，可以通过传输规则替代 Secure 以绕过所有垃圾邮件筛选。[](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl) 当 Microsoft 检测到邮件为高可信度钓鱼邮件时，如果此规则已就位，它们仍将发送到收件箱。 
- 误报：你可能希望暂时允许 Microsoft 通过管理员提交分析某些 [邮件](admin-submission.md)。 与所有替代一样，建议它们为临时替代。
