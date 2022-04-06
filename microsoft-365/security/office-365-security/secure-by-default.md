---
title: 默认情况下安全Office 365
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
description: 详细了解 Exchange Online Protection (EOP) 中的默认安全设置
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 09395775cc5ecbd420dc7197664401c01c24d6c3
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664207"
---
# <a name="secure-by-default-in-office-365"></a>默认情况下安全Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"默认情况下安全"是一个术语，用于定义尽可能安全的默认设置。

但是，安全性需要与工作效率相平衡。 这可以包括以下内容之间的平衡：

- **可用性**：设置不应妨碍用户的工作效率。
- **风险**：安全性可能会阻止重要活动。
- **旧版设置**：出于业务原因，可能需要维护旧版产品和功能的某些配置，即使改进了新的新式设置。

Exchange Online中包含邮箱的Microsoft 365组织受 Exchange Online Protection (EOP) 的保护。 此保护包括：

- 具有可疑恶意软件的电子邮件将自动隔离。 接收方是否收到有关隔离恶意软件消息的通知由隔离策略和反恶意软件策略中的设置控制。 有关详细信息，请参阅 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。
- 识别为高可信度网络钓鱼的电子邮件将根据反垃圾邮件策略操作进行处理。 请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

有关 EOP 的详细信息，[请参阅Exchange Online Protection概述](exchange-online-protection-overview.md)。

由于 Microsoft 希望在默认情况下保护客户的安全，因此某些租户替代不会应用于恶意软件或高置信度网络钓鱼。 这些替代包括：

- 允许的发件人列表或允许的域列表 (反垃圾邮件策略) 
- Outlook 保险箱发件人
- IP 允许列表 (连接筛选) 
- Exchange邮件流规则 (也称为传输规则) 

有关这些替代的详细信息，请参阅 ["创建安全发件人"列表](create-safe-sender-lists-in-office-365.md)。

> [!NOTE]
> 我们已弃用 **"将邮件移动到垃圾邮件"文件夹** 操作，以便在 EOP 反垃圾邮件策略中做出 **高可信度网络钓鱼电子邮件** 判决。 将此操作用于高置信度网络钓鱼消息的反垃圾邮件策略将转换为 **隔离消息**。 高置信度网络钓鱼 **邮件的重定向邮件到电子邮件地址** 操作不受影响。

默认情况下，安全不是可以打开或关闭的设置，而是我们的筛选工作方式，以便将潜在危险或不需要的邮件从邮箱中排除。 应隔离恶意软件和高置信度网络钓鱼消息。 默认情况下，只有管理员可以管理被隔离为恶意软件或高可信度网络钓鱼的消息，他们也可以从那里向 Microsoft 报告误报。 有关详细信息，请参阅 [在 EOP 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)。

## <a name="more-on-why-were-doing-this"></a>详细了解我们执行此操作的原因

默认情况下，安全的精神是：如果知道消息存在恶意，我们会对消息执行相同的操作，即使配置的异常会允许传递消息。 这与我们一直对恶意软件使用的方法相同，现在我们将这种行为扩展到高置信度网络钓鱼消息。

我们的数据表明，用户单击垃圾邮件文件夹中邮件中的恶意链接的可能性是"隔离"的 30 倍。 我们的数据还表明，假正率 (标记为高置信度网络钓鱼消息的不良) 的好消息非常低，管理员可以通过管理员提交来解决任何误报。

我们还确定，反垃圾邮件策略中允许的发件人和允许的域列表以及Outlook中的保险箱发件人过于宽泛，造成的危害大于好处。

换句话说：作为安全服务，我们代表你采取行动，防止用户遭到入侵。

## <a name="exceptions"></a>例外

在以下方案中，应只考虑使用替代：

- 网络钓鱼模拟：模拟攻击可以帮助你在实际攻击影响组织之前识别易受攻击的用户。 若要防止筛选网络钓鱼模拟消息，请参阅 [高级传递策略中配置第三方网络钓鱼模拟](/microsoft-365/security/office-365-security/configure-advanced-delivery#use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy)。
- 安全性/SecOps 邮箱：安全团队用来获取未经筛选邮件的专用邮箱 (好坏) 。 然后，Teams可以查看它们是否包含恶意内容。 有关详细信息，请参阅 [高级传递策略中的配置 SecOps 邮箱](/microsoft-365/security/office-365-security/configure-advanced-delivery#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy)。
- 第三方筛选器：默认情况下，仅当域的 MX 记录设置为Exchange Online Protection (contoso.mail.protection.outlook.com) 时才适用安全。 如果设置为其他服务或设备，则默认情况下，可以使用 [传输规则](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl) 重写 Secure 以绕过所有垃圾邮件筛选。 当 Microsoft 检测到具有此规则的高置信度网络钓鱼时，它们仍会传送到收件箱。 
- 误报：你可能希望暂时允许 Microsoft [通过管理员提交](admin-submission.md)分析的某些消息。 与所有重写一样，建议它们是临时的。
