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
ms.service: O365-seccomp
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
description: 管理员可以了解 Exchange Online Protection (EOP) 包含潜在危险或不需要的邮件的隔离。
ms.openlocfilehash: 8a978ece029de06bcb7b434de730b0baea33a5e1
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794324"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP 中的隔离电子邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在具有 Exchange Online 邮箱的 Microsoft 365 组织或独立 Exchange Online Protection (EOP) 组织中，可以使用隔离来保留潜在危险或不需要的邮件。

如果发现任何附件包含恶意软件，反恶意软件策略将自动隔离邮件。 有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

默认情况下，反垃圾邮件策略隔离网络钓鱼邮件，将垃圾邮件和批量电子邮件发送到用户的"垃圾邮件"文件夹。 但是，您还可以创建和自定义反垃圾邮件策略以隔离垃圾邮件和批量电子邮件。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

用户和管理员可以使用隔离邮件：

- 管理员可以为所有用户使用所有类型的隔离邮件。 只有管理员才能处理被隔离为恶意软件、高可信度网络钓鱼的邮件，或者由于邮件流规则 (也称为传输规则) 。 有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。

- 如果自 2020 年 4 月网络钓鱼起，邮件被隔离为垃圾邮件、批量电子邮件或 (，用户可以处理作为收件人的隔离邮件) 邮件。 有关详细信息，请参阅在 EOP 中查找并释放作为 [用户隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。

  为了防止用户管理自己的隔离网络钓鱼邮件，管理员可以为反垃圾邮件策略中的网络钓鱼电子邮件筛选裁定配置不同的操作。  有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

- 管理员和用户可以在隔离时向 Microsoft 报告误报。

有关隔离功能详细信息，请参阅隔离 [常见问题解答](quarantine-faq.md)。
