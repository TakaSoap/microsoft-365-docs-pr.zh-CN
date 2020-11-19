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
ms.openlocfilehash: 23c0cad2b96b3a2002f235db7739b903cf862366
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357859"
---
# <a name="secure-by-default-in-office-365"></a>默认情况下在 Office 365 中安全

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"默认情况下安全" 是一种术语，用于定义尽可能安全的默认设置。

但是，安全性需要与工作效率平衡。 这可能包括跨以下各项的平衡：

- 可用性：设置不应以用户工作效率为依据。
- 风险：安全性可能会阻止重要活动。
- 旧版设置：出于商业原因，可能需要维护某些旧产品和功能的一些配置，即使新的新式设置得到改进也是如此。

通过 exchange online 中邮箱的 Microsoft 365 组织受到 Exchange Online Protection (EOP) 的保护。 此保护包括：

1. 带有可疑恶意软件的电子邮件将自动被隔离，收件人将收到通知。 请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。
1. 被标识为 "高可信度" 的网络钓鱼电子邮件将根据反垃圾邮件策略操作进行处理。 请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

由于 Microsoft 想让我们的客户在默认情况下是安全的，因此某些租户替代不会应用于恶意软件或高可信度的网络钓鱼。 这些替代包括：

-  (反垃圾邮件策略的允许的发件人列表或允许的域列表) 
- Outlook 安全发件人
-  (连接筛选的 IP 允许列表) 

有关这些覆盖的详细信息，可参阅 [创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

默认情况下安全保护此处的设置不是可以打开或关闭的设置，但我们的筛选功能在框中的工作方式将可能有害或不需要的邮件保留在邮箱之外。 应将恶意软件和高可信度的网络钓鱼网站发送到隔离区。 只有管理员可以管理被隔离为恶意软件或高可信度的网络钓鱼的邮件，也可以在那里向 Microsoft 报告误报。 有关详细信息，请参阅 [在 EOP 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)

## <a name="exceptions"></a>Exceptions

允许高可信度仿冒邮件绕过筛选的唯一替代是 Exchange 邮件流规则 (也称为传输规则) 。 若要使用邮件流规则绕过筛选，请参阅 [使用邮件流规则在邮件中设置 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

替代只应用于：

- 网络钓鱼模拟：模拟攻击可帮助您在真正的攻击影响组织之前识别易受攻击的用户。
- Security/SecOps 邮箱：安全团队使用的专用邮箱)  (好的和坏的中获取未筛选的邮件。 然后，团队可以查看它们是否包含恶意内容。
- 第三方筛选器：某些第三方供应商建议将 EOP (SCL =-1) ，因为第三方筛选器将管理邮件筛选。 Microsoft 不建议关闭 EOP，因为 Defender for Office 365 需要 EOP。
- 误报：你可能需要允许 Microsoft 仍在通过 [管理员提交](admin-submission.md)进行分析的某些邮件。 与所有替代一样，建议它们是临时性的。
