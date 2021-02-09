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
ms.openlocfilehash: fcce6981369217f21ace5fdf2abbf23ca8606569
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150804"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>安全与合规中心中的出站和入站&见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

安全 [&](https://protection.office.com)**与** 合规中心内邮件流仪表板 [](mail-flow-insights-v2.md)中的出站和入站邮件流见解将连接器报告中的信息和以前的 **TLS** [](view-mail-flow-reports.md#connector-report)概述报告中的信息合并在一处。

小组件在邮件发送到组织或从组织发送邮件时显示用于连接的 TLS 加密。 当 TLS 由双方提供时，TLS 会加密与其他电子邮件服务建立的连接。 小组件提供最后一周的邮件流的快照。

![安全与合规中心的"邮件流"仪表板中的"出站和入站&小组件](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

小部件中的信息与 Microsoft 365 中的连接器和 TLS 邮件保护相关。 有关详细信息，请参阅以下主题：

- [使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Exchange Online 如何使用 TLS 保护电子邮件连接](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [有关 Microsoft 365 中加密的技术参考详细信息](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>在传输过程中受 TLS (保护) 

单击小组件 **上的"** 查看详细信息"时，受 **TLS** (保护的邮件) 显示对进入和离开组织的邮件的 TLS 保护。

![在传输过程中 (由 TLS) 在单击"出站和入站电子邮件"小部件上的"查看详细信息"后出现的) 显示](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

目前，TLS 1.2 是 Microsoft 365 提供的最安全的 TLS 版本。 通常，你需要知道用于合规性审核的 TLS 加密。 你可能与大部分源和目标电子邮件服务器没有直接关系 (而 Microsoft) 也不拥有，因此，你没有很多选项可以改进这些服务器使用的 TLS 加密。

但是，您可以使用 [连接器来确保](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 对电子邮件服务器和 Microsoft 365 之间发送的邮件的最佳 TLS 保护。 Microsoft 365 和属于合作伙伴的您自己的电子邮件服务器之间的邮件流通常比常规邮件更加重要和敏感，因此你需要为这些邮件应用额外的安全性和安全性。

您可以升级或修复自己的电子邮件服务器，以改进所使用的 TLS 加密，或联系合作伙伴以执行相同的操作。 连接器 **报告** 显示使用 Microsoft 365 连接器的邮件的邮件流卷和 TLS 加密。

You can click the **Connector report** link to go to the [Connector report.](view-mail-flow-reports.md#connector-report) 如果检测到关联条件，则连接器报告页面上可能会提供以下见解：

- **入站合作伙伴连接器看到大量 TLS1.0 邮件流**
- **入站 OnPremises 连接器看到大量 TLS1.0 邮件流**

对于 TLS 1.0 连接，你确实需要升级或修复电子邮件服务器或合作伙伴的服务器，以避免在 Microsoft 365 中最终弃用 TLS 1.0 支持时出现任何问题。

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
