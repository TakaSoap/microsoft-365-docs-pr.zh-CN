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
description: 管理员可以了解 Exchange Online Protection 邮箱中隔离邮件的最终用户 (垃圾邮件) 。
ms.openlocfilehash: 9e9c95fafe3610e0ad945f18aa85ff13342d8d65
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827357"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>使用用户垃圾邮件通知释放和报告隔离邮件

无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。 有关详细信息，请参阅 [EOP 中隔离的邮件](quarantine-email-messages.md)。

默认情况下，在反垃圾邮件策略中禁用最终用户垃圾邮件通知。 当管理员 [启用最终用户垃圾邮件通知时](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)，收件人 (（包括启用了自动映射的共享邮箱) ）将定期收到有关自 2020) 年 4 月起作为垃圾邮件、批量电子邮件或网络钓鱼 (的邮件相关的定期通知。

对于共享邮箱，仅对授予共享邮箱完全访问权限的用户支持最终用户垃圾邮件通知。 有关详细信息，请参阅使用 [EAC 编辑共享邮箱委派](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)。

组不支持最终用户垃圾邮件通知。

> [!NOTE]
> 只有管理员才能使用被隔离为高可信度钓鱼邮件、恶意软件或邮件流规则 (也称为传输规则) ）的邮件。 有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。

最终用户垃圾邮件通知包含每封隔离邮件的以下信息：

- **发件人**：隔离邮件的发送名称和电子邮件地址。

- **主题**：隔离邮件的主题行文本。

- **日期**：以 UTC (时表示邮件隔离) 时间和时间格式。

- **"阻止**发件人：单击此链接"将发件人添加到"阻止的发件人"列表中。 有关详细信息，请参阅"[阻止邮件发件人"。](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)

- **释**放：对于 (邮件而) 邮件，你可以在此处释放邮件，而无需隔离安全&合规性中心。

- **查看**：单击此链接转到安全 & 合规中心内的"隔离"，你可在其中 (转到其中的地址，具体取决于邮件被隔离的) 查看、释放、删除或报告隔离邮件的原因。 有关详细信息，请参阅在 [EOP 中以用户身份查找和释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。

![示例最终用户垃圾邮件通知](../../media/end-user-spam-notification.png)
