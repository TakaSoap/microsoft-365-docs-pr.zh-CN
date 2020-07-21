---
title: Microsoft 365 中的最终用户垃圾邮件通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以在 Exchange Online Protection （EOP）中了解有关隔离邮件的最终用户垃圾邮件通知。
ms.openlocfilehash: 4c3275b6af1eb452ed420b8eb2f923dfbb1267d6
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200012"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>使用用户垃圾邮件通知释放和报告隔离的邮件

无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。 有关详细信息，请参阅[EOP 中的隔离邮件](quarantine-email-messages.md)。

默认情况下，在反垃圾邮件策略中禁用最终用户垃圾邮件通知。 当管理员[启用最终用户垃圾邮件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)时，收件人（包括启用了自动映射的共享邮箱）将收到有关被隔离为垃圾邮件、批量电子邮件或（截止到4月2020）的网络钓鱼的邮件的定期通知。

> [!NOTE]
> 被隔离为高可信度网络钓鱼、恶意软件或通过邮件流规则（也称为传输规则）的邮件仅适用于管理员。 有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。

最终用户垃圾邮件通知包含每个隔离邮件的以下信息：

- **发件人**：隔离邮件的发送名称和电子邮件地址。

- **Subject**：隔离邮件的主题行文本。

- **日期**：邮件被隔离的日期和时间（以 UTC 为单位）。

- **阻止发件人**：单击此链接可将发件人添加到阻止发件人列表。 有关详细信息，请参阅[阻止邮件发件人](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

- **Release**：对于垃圾邮件（不是网络钓鱼）邮件，您可以在此处释放邮件，而无需隔离安全 & 合规性中心。

- **查看**：单击此链接可转到 Security & 合规性中心中的隔离，可在其中释放、删除或报告隔离邮件。 有关详细信息，请参阅[在 EOP 中以用户的方式查找和释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。

![最终用户垃圾邮件通知示例](../../media/end-user-spam-notification.png)
