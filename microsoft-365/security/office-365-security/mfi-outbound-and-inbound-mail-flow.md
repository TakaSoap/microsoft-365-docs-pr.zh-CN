---
title: 邮件流仪表板中的出站和入站邮件流见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理员可以在安全与合规中心的邮件流仪表板中了解出站和入站&见解。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 87c5bd9ab0d550f50feabbb96176debbe04863e5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289445"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>安全与合规中心中的出站和入站&见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

安全 [&](https://protection.office.com)**与** 合规中心的"邮件流"[](mail-flow-insights-v2.md)仪表板中的出站和入站邮件流见解将连接器报表和以前的 **TLS** [](view-mail-flow-reports.md#connector-report)概述报告中的信息合并在一处。

小组件显示邮件发送到组织或从组织传递邮件时用于连接的 TLS 加密。 如果 TLS 由双方提供，则与其他电子邮件服务建立的连接由 TLS 加密。 小部件提供上一周邮件流的快照。

![安全与合规中心的"邮件流"仪表板中的"出站和入站&小组件](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

小部件中的信息与 Microsoft 365 中的连接器和 TLS 邮件保护相关。 有关详细信息，请参阅以下主题：

- [使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Exchange Online 如何使用 TLS 保护电子邮件连接](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [有关 Microsoft 365 中加密的技术参考详细信息](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>在传输过程中受 TLS (保护) 

单击 **小组件** 上的"查看详细信息"时，受 **TLS** (保护的邮件) 显示进入和离开组织的邮件的 TLS 保护。

![受 TLS (传输) 在单击"出站"和"入站电子邮件"小部件上查看详细信息后出现的) 显示](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

目前，TLS 1.2 是 Microsoft 365 提供的最安全的 TLS 版本。 通常，你需要知道用于合规性审核的 TLS 加密。 你可能与大多数源和目标电子邮件服务器没有直接关系 (而 Microsoft) 也不拥有它们，因此你没有很多选项来改进这些服务器使用的 TLS 加密。

但是，您可以使用 [连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 来确保电子邮件服务器和 Microsoft 365 之间发送的邮件的最佳 TLS 保护。 Microsoft 365 和属于合作伙伴的您自己的电子邮件服务器之间的邮件流通常比常规邮件更加重要和敏感，因此你需要为这些邮件应用额外的安全性和安全性。

您可以升级或修复自己的电子邮件服务器，以改进所使用的 TLS 加密，或联系合作伙伴以执行相同的操作。 连接器 **报告** 显示使用 Microsoft 365 连接器的邮件的邮件流卷和 TLS 加密。

可以单击" **连接器"报告** 链接以转到 ["连接器"报表](view-mail-flow-reports.md#connector-report)。 如果检测到关联条件，则"连接器报告"页上可能提供以下见解：

- **入站合作伙伴连接器看到重要的 TLS1.0 邮件流**
- **入站 OnPremises 连接器看到大量 TLS1.0 邮件流**

对于 TLS 1.0 连接，真正需要升级或修复您的电子邮件服务器或合作伙伴的服务器，以避免在 Microsoft 365 中最终弃用 TLS 1.0 支持时出现任何问题。

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
