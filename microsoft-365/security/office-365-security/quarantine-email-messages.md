---
title: 隔离的电子邮件
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
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection （EOP）中的隔离，其中包含可能存在危险或不需要的邮件。
ms.openlocfilehash: 71a5f32fe6888d751bf2c4020fca4df671ac96d1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208278"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP 中隔离的电子邮件

在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online 保护（EOP）组织中具有邮箱的 Microsoft 365 组织中，隔离功能可用于保留潜在危险或不需要的邮件。

如果发现*任何*附件包含恶意软件，反恶意软件策略将自动隔离邮件。 有关详细信息，请参阅[在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

默认情况下，反垃圾邮件策略隔离网络钓鱼邮件，并将垃圾邮件和批量电子邮件传递到用户的 "垃圾邮件" 文件夹。 不过，您还可以创建和自定义反垃圾邮件策略以隔离垃圾邮件和批量电子邮件。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

用户和管理员都可以使用隔离邮件：

- 管理员可对所有用户使用所有类型的已隔离邮件。 只有管理员可以处理被隔离为恶意软件、高可信度网络钓鱼的邮件或邮件流规则（也称为传输规则）的结果。 有关详细信息，请参阅[在 EOP 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。

- 如果邮件被隔离为垃圾邮件、批量电子邮件或（到4月2020）的网络钓鱼，则用户可以使用它们作为收件人的隔离邮件。 有关详细信息，请参阅[在 EOP 中以用户的方式查找和释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。

  为了防止用户管理自己的隔离网络钓鱼邮件，管理员可以为反垃圾邮件策略中的**网络钓鱼电子邮件**筛选判定功能配置不同的操作。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

- 管理员和用户可以向在隔离中的 Microsoft 报告误报。

有关隔离的详细信息，请参阅[隔离 FAQ](quarantine-faq.md)。
