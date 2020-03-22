---
title: Office 36 中的最终用户垃圾邮件通知
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
description: 当管理员在反垃圾邮件策略中启用最终用户垃圾邮件通知后，邮件收件人将收到有关其隔离邮件的定期通知。
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895055"
---
# <a name="end-user-spam-notifications-in-office-365"></a>Office 365 中的最终用户垃圾邮件通知

在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online Protection （EOP）组织中，隔离会在 Office 365 组织中保留可能有害或不需要的邮件。 有关详细信息，请参阅[Office 365 中的隔离](quarantine-email-messages.md)。

默认情况下，在反垃圾邮件策略中禁用最终用户垃圾邮件通知。 当管理员[启用最终用户垃圾邮件通知](configure-your-spam-filter-policies.md)后，邮件收件人将收到有关被隔离为垃圾邮件、批量电子邮件或（截止到4月，2020）的网络钓鱼的邮件的定期通知。

> [!NOTE]
> 在10月2019，我们删除了直接从最终用户的垃圾邮件通知中释放隔离邮件的功能。 相反，用户现在可以转到 Office 365 安全 & 合规中心来释放隔离邮件（直接或通过单击通知中的 "**查看**"）。 有关详细信息，请参阅[在 Office 365 中查找并以用户的方式释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。 <br/><br/> 被隔离为高可信度网络钓鱼、恶意软件或通过邮件流规则（也称为传输规则）的邮件仅适用于管理员。 有关详细信息，请参阅[在 Office 365 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。

最终用户垃圾邮件通知包含每个隔离邮件的以下信息：

- **发件人**：隔离邮件的发送名称和电子邮件地址。

- **Subject**：隔离邮件的主题行文本。

- **日期**：邮件被隔离的日期和时间（以 UTC 为单位）。

- **阻止发件人**：单击此链接可将发件人添加到阻止发件人列表。

- **查看**：单击此链接可转到 Security & 合规性中心中的隔离，您可以在其中释放、删除或报告隔离邮件。

![最终用户垃圾邮件通知示例](../../media/end-user-spam-notification.png)
