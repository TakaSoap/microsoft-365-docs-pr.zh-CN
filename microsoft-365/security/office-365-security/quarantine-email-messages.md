---
title: Office 365 中的隔离
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Office 365 中的隔离会保留可能有害或不需要的邮件。 管理员和最终用户可以访问隔离。
ms.openlocfilehash: d3db036210886f7a4607f477bba2cf9f450ed90c
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2020
ms.locfileid: "43230929"
---
# <a name="quarantine-in-office-365"></a>Office 365 中的隔离

如果您是在 Exchange Online 中有邮箱或独立 Exchange Online Protection （EOP）客户但没有 Exchange Online 邮箱的 Office 365 客户，则可以使用隔离来保存可能有害的邮件。

如果发现*任何*附件包含恶意软件，反恶意软件策略将自动隔离邮件。 有关详细信息，请参阅[在 Office 365 中配置反恶意软件策略](configure-anti-malware-policies.md)。

默认情况下，反垃圾邮件策略隔离网络钓鱼邮件，并将垃圾邮件和批量电子邮件传递到用户的 "垃圾邮件" 文件夹。 不过，您还可以创建和自定义反垃圾邮件策略以隔离垃圾邮件和批量电子邮件。 有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

用户和管理员都可以使用隔离邮件：

- 管理员可对所有用户使用所有类型的已隔离邮件。 只有管理员可以处理被隔离为恶意软件、高可信度网络钓鱼的邮件或邮件流规则（也称为传输规则）的结果。 有关详细信息，请参阅[在 Office 365 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。

- 如果邮件被隔离为垃圾邮件、批量电子邮件或（从2020年4月，）的网络钓鱼，则用户可以使用它们作为收件人的隔离邮件。 有关详细信息，请参阅[在 Office 365 中查找并以用户的方式释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。

  为了防止用户管理自己的隔离网络钓鱼邮件，管理员可以为反垃圾邮件策略中的**网络钓鱼电子邮件**筛选判定功能配置不同的操作。 有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

- 管理员和用户可以向在隔离中的 Microsoft 报告误报。

有关隔离的详细信息，请参阅[隔离 FAQ](quarantine-faq.md)。
