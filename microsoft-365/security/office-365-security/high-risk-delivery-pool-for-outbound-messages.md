---
title: 出站邮件的高风险传递池
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 了解如何使用高风险传递池来保护 Microsoft 365 数据中心中的电子邮件服务器的声誉。
ms.openlocfilehash: 190dc3bd7ed2a6cddb23c8bc7c117dee30fd4f13
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209183"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>出站邮件的高风险传递池

Microsoft 365 数据中心中的电子邮件服务器可能暂时 guilty 发送垃圾邮件。 例如，在内部部署电子邮件组织中通过 Microsoft 365 发送出站邮件的恶意软件或恶意垃圾邮件攻击，或者是 Microsoft 365 帐户受到危害。 这些方案可能会导致出现在第三方阻止列表中的受影响的 Microsoft 365 数据中心服务器的 IP 地址。 使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件源的电子邮件。

为防止出现这种情况，通过_高风险传递池_发送来自确定为垃圾邮件的 Microsoft 365 datacenter server 中的所有出站邮件，或超出[服务](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)的发送限制或[出站垃圾邮件策略](configure-the-outbound-spam-policy.md)的所有出站邮件。

高风险传递池是仅用于发送 "低质量" 邮件（例如，垃圾邮件和[退信](backscatter-messages-and-eop.md)）的出站电子邮件的辅助 IP 地址池。 使用高风险传递池有助于阻止出站电子邮件的常规 IP 地址池发送垃圾邮件。 出站电子邮件的常规 IP 地址池维护发送 "高质量" 邮件的信誉，从而降低了这些 IP 地址在 IP 阻止列表中出现的可能性。

高风险传递池中的 IP 地址可能会保留在 IP 阻止列表中，但这是设计的。 无法保证传递给预期的收件人，因为很多电子邮件组织不接受来自高风险传递池的邮件。

有关详细信息，请参阅[控制出站垃圾邮件](outbound-spam-controls.md)。

> [!NOTE]
> 源电子邮件域没有记录且在公用 DNS 中定义的任何 MX 记录都不会通过高风险传递池路由（无论其垃圾邮件或发送限制处置）的邮件。

## <a name="bounce-messages"></a>退回邮件

出站高风险传递池管理所有未送达报告（也称为 Ndr、弹跳邮件、传递状态通知或 Dsn）的传递。

Ndr 中的电涌可能的原因包括：

- 对使用服务的客户之一产生影响的欺骗活动。
- 目录搜集攻击。
- 垃圾邮件攻击。
- 一个欺诈性电子邮件服务器。

所有这些问题都会导致服务处理的 Ndr 数量突然增加。 许多情况下，这些 Ndr 似乎是垃圾邮件发送给其他电子邮件服务器和服务（也称为_[退信](backscatter-messages-and-eop.md)_）。
