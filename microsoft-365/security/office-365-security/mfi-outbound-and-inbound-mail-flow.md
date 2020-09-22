---
title: 邮件流仪表板中的出站和入站邮件流洞察力
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
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中的出站和入站邮件流洞察力。
ms.openlocfilehash: 33bfe3882c274fa655d17c80aba007e8d246b250
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199297"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>安全 & 合规中心中的出站和入站邮件流洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Security & 合规中心](https://protection.office.com)的[邮件流仪表板](mail-flow-insights-v2.md)中的**出站和入站邮件流**洞察力将[连接器报告](view-mail-flow-reports.md#connector-report)中的信息和以前的**TLS 概述报告**合并到一个位置。

当邮件传递到组织或从组织中传递时，该小组件将显示用于连接的 TLS 加密。 当双方提供 TLS 时，使用其他电子邮件服务建立的连接将由 TLS 进行加密。 小组件提供邮件流的最后一周的快照。

![Security & 合规中心的邮件流仪表板中的出站和入站邮件流小组件](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

小组件中的信息与 Microsoft 365 中的连接器和 TLS 邮件保护有关。 有关详细信息，请参阅以下主题：

- [使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Exchange Online 如何使用 TLS 保护电子邮件连接](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [有关 Microsoft 365 中的加密的技术参考详细信息](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>TLS 在 (传输中保护的邮件) 

当您单击小部件上的 " **查看详细信息** " 时， **受 TLS 保护的邮件 (由 TLS) ** 浮出控件向您显示进入和离开组织的邮件的 TLS 保护。

![在单击 "出站和入站电子邮件" 小组件上的 "查看详细信息" 之后，在传输 (由 TLS) 浮出的邮件](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

目前，TLS 1.2 是 Microsoft 365 提供的最安全的 TLS 版本。 通常，您需要知道正在用于合规性审核的 TLS 加密。 您可能没有与源和目标电子邮件服务器的直接关系 (你不拥有它们，也不会) Microsoft。因此，Microsoft 不，因此不会有许多选项可用于改进这些服务器所使用的 TLS 加密。

不过，您可以使用 [连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 来确保在电子邮件服务器和 Microsoft 365 之间发送的邮件的最佳可用 TLS 保护。 在 Microsoft 365 与您自己的电子邮件服务器或属于您的合作伙伴的服务器之间流动的邮件通常比常规邮件更重要且敏感，因此您需要对这些邮件应用额外的安全和 vigilance。

您可以升级或修复自己的电子邮件服务器，以改进正在使用的 TLS 加密，或与您的合作伙伴进行相同的操作。 **连接器报告**为使用 Microsoft 365 连接器的邮件显示邮件流卷和 TLS 加密。

您可以单击 " **连接器报告** " 链接以转到 [连接器报告](view-mail-flow-reports.md#connector-report)。 如果检测到相关的条件， **连接器报告** 页上可能会提供以下见解：

- **入站合作伙伴连接器查看有效的 TLS 1.0 邮件流**
- **入站 OnPremises 连接器查看有效的 TLS 1.0 邮件流**

对于 TLS 1.0 连接，确实需要将您的电子邮件服务器或合作伙伴的服务器升级或修复，以避免在 Microsoft 365 中最终弃用 TLS 1.0 支持时出现的任何问题。

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
