---
title: 已隔离的电子邮件
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
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP 服务器中) 保存潜在危险或不需要的邮件的隔离。
ms.openlocfilehash: d2ccf174ae929c6db14f2a5319e9594495c0778e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826797"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP 中的已隔离电子邮件

在具有 Exchange Online 邮箱的 Microsoft 365 组织中或在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能可用于保存潜在危险或不需要的邮件。

如果发现任何附件包含恶意软件，反 *恶意软件策略会自动* 隔离邮件。 有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

默认情况下，反垃圾邮件策略会隔离网络钓鱼邮件，并将垃圾邮件和批量电子邮件传递到用户的"垃圾邮件"文件夹。 但是，您还可以创建和自定义反垃圾邮件策略来隔离垃圾邮件和批量电子邮件。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

用户和管理员均可以使用隔离邮件：

- 管理员可以处理所有用户的全部类型的隔离邮件。 只有管理员可以处理被隔离为恶意软件或高可信度网络钓鱼的邮件，或者邮件流规则 (也称为传输规则) 。 有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。

- 用户可以处理自 2020 年 4 月起将邮件隔离为垃圾邮件、批量电子邮件或从 2020 年 4 月起作为垃圾邮件、批量电子邮件或 (的邮件隔离在哪) 个隔离邮件中。 有关详细信息，请参阅在 [EOP 中以用户身份查找和释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。

  若要防止用户管理自己的隔离网络钓鱼邮件，管理员可以在反垃圾邮件策略中为钓鱼 **电子邮件** 筛选裁定配置不同的操作。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

- 管理员和用户可以隔离为 Microsoft 报告误报。

有关隔离的详细信息，请参阅"隔离[常见问题解答"。](quarantine-faq.md)
