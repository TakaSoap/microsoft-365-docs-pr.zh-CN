---
title: 隔离的电子邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 具有潜在危险或不需要的邮件的隔离。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd748871cc09905f9878d5917351b1c185cc1106
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056293"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP 中的隔离电子邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在具有 Exchange Online 邮箱或独立 Exchange Online Protection (EOP) 组织（没有 Exchange Online 邮箱）的 Microsoft 365 组织中，可以使用隔离来保留潜在危险或不需要的邮件。

如果发现任何附件包含 *恶意软件，反* 恶意软件策略将自动隔离邮件。 有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

默认情况下，反垃圾邮件策略会隔离网络钓鱼邮件，将垃圾邮件和批量电子邮件发送到用户的"垃圾邮件"文件夹。 但是，您还可以创建和自定义反垃圾邮件策略以隔离垃圾邮件和批量电子邮件。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

用户和管理员可以使用隔离邮件：

- 管理员可以为所有用户使用所有类型的隔离邮件。 只有管理员才能处理被隔离为恶意软件、高可信度网络钓鱼的邮件，或由于邮件流规则或邮件流规则 (传输规则) 。 有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。

- 从 2020 年 4 月开始，如果邮件被隔离为垃圾邮件、批量电子邮件或 (，用户可以处理作为收件人的隔离) 邮件。 有关详细信息，请参阅在 [EOP](find-and-release-quarantined-messages-as-a-user.md)中以用户模式查找并释放隔离邮件。

  为了防止用户管理自己的隔离网络钓鱼邮件，管理员可以为反垃圾邮件策略中的网络钓鱼电子邮件筛选裁定配置不同的操作。  有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

- 管理员和用户可以在隔离中向 Microsoft 报告误报。

有关隔离功能详细信息，请参阅隔离 [常见问题](quarantine-faq.md)解答。
