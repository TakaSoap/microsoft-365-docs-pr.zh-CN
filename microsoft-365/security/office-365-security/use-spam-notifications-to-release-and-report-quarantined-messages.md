---
title: Microsoft 365 中的最终用户垃圾邮件通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: 管理员可以在 Exchange Online Protection (EOP) 中了解有关隔离邮件的最终用户垃圾邮件通知。
ms.openlocfilehash: 0440056e8e31d24e659f9d0ff6662f86f31a6189
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600293"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>使用用户垃圾邮件通知释放和报告隔离的邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。 有关详细信息，请参阅 [EOP 中的隔离邮件](quarantine-email-messages.md)。

默认情况下，在反垃圾邮件策略中禁用最终用户垃圾邮件通知。 当管理员 [启用最终用户垃圾邮件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)时，收件人 (包括启用了自动映射的共享邮箱) 会收到有关其邮件的定期通知，这些邮件被隔离为垃圾邮件、批量电子邮件或 (2020) 的网络钓鱼。

对于共享邮箱，仅对向其授予了对共享邮箱的 FullAccess 权限的用户才支持最终用户垃圾邮件通知。 有关详细信息，请参阅 [使用 EAC 编辑共享邮箱委派](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)。

组不支持最终用户垃圾邮件通知。

> [!NOTE]
> 被隔离为高可信度网络钓鱼、恶意软件或邮件流规则的邮件 (也称为传输规则) 仅供管理员使用。 有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。

最终用户垃圾邮件通知包含每个隔离邮件的以下信息：

- **发件人**：隔离邮件的发送名称和电子邮件地址。

- **Subject**：隔离邮件的主题行文本。

- **日期**：) 邮件被隔离的日期和时间 (（UTC）。

- **阻止发件人**：单击此链接可将发件人添加到阻止发件人列表。 有关详细信息，请参阅 [阻止邮件发件人](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

- **Release**：对于垃圾邮件 (不会) 邮件的网络钓鱼，您可以在此处释放邮件，而无需隔离安全 & 合规性中心。

- **查看**：单击此链接可转到 Security & 合规性中心中的隔离，在此 (可以根据邮件被隔离的原因) 查看、释放、删除或报告隔离邮件。 有关详细信息，请参阅 [在 EOP 中以用户的方式查找和释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。

![最终用户垃圾邮件通知示例](../../media/end-user-spam-notification.png)

> [!NOTE]
> 被阻止的发件人仍可向你发送邮件。 从该发件人将其发送到邮箱的任何邮件都将立即移动到 "垃圾邮件" 文件夹。 今后来自此发件人的邮件将转到 "垃圾邮件" 文件夹或最终用户隔离。 如果要在到达时删除这些邮件而不是隔离这些邮件，请使用 [邮件流规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (也称为传输规则) 以在到达时删除邮件。
