---
title: 邮件流仪表板中的出站和入站邮件流见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理员可在安全与合规中心的"邮件流"仪表板中了解出站和&见解。
ms.openlocfilehash: 920c1212f4d6dee508704c93272e48140e199710
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826889"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>安全电子邮件合规中心中的出站和&入站邮件

安全 & **合规中心的** 邮件流仪表板中的 [出站和](mail-flow-insights-v2.md) 入站邮件流见解将 [来自连接器报表](view-mail-flow-reports.md#connector-report) 的信息和以前 **的 TLS 概述报告** 组合在一个位置。

小部件显示在向组织和从组织发送邮件时用于连接的 TLS 加密。 当这两端提供 TLS 时，TLS 与其他电子邮件服务建立的连接都由 TLS 加密。 小部件提供邮件流的最后一周的快照。

![安全与合规中心的邮件流仪表板中的"出站和出站&小部件](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

小部件中的信息与 Microsoft 365 中的连接器和 TLS 邮件保护相关。 有关详细信息，请参阅以下主题：

- [使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Exchange Online 如何使用 TLS 保护电子邮件连接](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [有关 Microsoft 365 加密的技术参考详细信息](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>由 TLS 管理员在传输中 (保护) 

当单击 **小部件上的** "查看详细信息"时 **，TLS () ** 浮出控件中受保护的邮件) 出发，以及如何为进入和离开组织的邮件提供 TLS 保护。

![在"出站和 (" (中) 单击"查看详细信息"后，由 TLS 管理中保护的邮件，传输中受 TLS 保护的浮出控件](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

目前，TLS 1.2 是 Microsoft 365 提供的最安全的 TLS 版本。 通常，您需要了解用于合规性审核的 TLS 加密。 您可能没有与它们所拥有的大多数源和目标电子邮件服务器 (没有直接关系，也没有 Microsoft) ，因此您没有多项选项来改进这些服务器使用的 TLS 加密。

但是，你可以 [使用连接器，](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 以确保对您电子邮件服务器和 Microsoft 365 之间发送的邮件实现最佳的 TLS 保护。 Microsoft 365 和你自己的属于合作伙伴的电子邮件服务器或服务器之间的邮件流通常比常规邮件更加重要和更敏感，因此您需要对这些邮件应用额外的安全性和漏性。

您可以升级或修复您自己的电子邮件服务器，以改进正在使用的 TLS 加密，或联系合作伙伴执行相同操作。 连接器 **报告显示** 使用 Microsoft 365 连接器的邮件的邮件流卷和 TLS 加密。

您可以单击连接器 **报告链接** 以转到连接器 [报告](view-mail-flow-reports.md#connector-report)。 如果检测到关联条件，"连接器报告 **"** 页上可能提供了以下见解：

- **显示重要 TLS1.0 邮件流的入站合作伙伴连接器**
- **显示重要 TLS1.0 邮件流的入站 OnPremises 连接器**

对于 TLS 1.0 连接，你确实需要升级电子邮件服务器或您的合作伙伴的服务器，以避免当 Microsoft 365 最终弃用 TLS 1.0 支持时出现任何问题。

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。
