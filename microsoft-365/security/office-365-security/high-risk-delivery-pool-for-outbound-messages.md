---
title: 出站传递池
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 了解如何使用传递池保护 Microsoft 365 数据中心中电子邮件服务器的信誉。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 461b5f9aa0407c5115ab84a075c793139a8b4305
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203251"
---
# <a name="outbound-delivery-pools"></a>出站传递池

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 数据中心的电子邮件服务器可能暂时没有发送垃圾邮件。 例如，本地电子邮件组织中通过 Microsoft 365 发送出站邮件或 Microsoft 365 帐户遭到入侵的恶意软件或恶意垃圾邮件攻击。 攻击者还尝试通过 Microsoft 365 转发中继邮件来避免检测。

这些方案可能导致受影响的 Microsoft 365 数据中心服务器的 IP 地址显示在第三方阻止列表中。 使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件源的电子邮件。

## <a name="high-risk-delivery-pool"></a>高风险传送池
为了防止这种情况，来自 Microsoft 365 数据中心服务器的所有出站邮件（被确定为垃圾邮件或超过服务的发送限制或出站 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)垃圾邮件策略）[](configure-the-outbound-spam-policy.md)都通过高风险传送池 _发送_。

高风险传递池是出站电子邮件的单独 IP 地址池，仅用于发送"低质量" (例如垃圾邮件和退信) 。 [](backscatter-messages-and-eop.md) 使用高风险传送池有助于防止出站电子邮件的正常 IP 地址池发送垃圾邮件。 出站电子邮件的正常 IP 地址池维护发送"高质量"邮件的信誉，这会降低这些 IP 地址出现在 IP 阻止列表上的可能性。

高风险传送池中的 IP 地址将保留在 IP 阻止列表上的非常真实的可能性仍然存在，但这是设计使的。 不保证向目标收件人传递邮件，因为许多电子邮件组织不接受来自高风险传递池的邮件。

有关详细信息，请参阅控制 [出站垃圾邮件](outbound-spam-controls.md)。

> [!NOTE]
> 源电子邮件域没有 A 记录且公共 DNS 中未定义 MX 记录的邮件始终通过高风险传送池路由，无论其垃圾邮件或发送限制处置如何。

### <a name="bounce-messages"></a>退回邮件

出站高风险传递池管理所有未送达报告（也称为 (、退回邮件、传递状态通知或 DSN) ）。

NDR 中出现激增的可能原因包括：

- 影响使用该服务的其中一个客户的欺骗活动。
- 目录收集攻击。
- 垃圾邮件攻击。
- 未授权电子邮件服务器。

所有这些问题都可能导致服务正在处理的 NDR 数量突然增加。 在许多情况下，这些 NDR 似乎为其他电子邮件服务器和服务的垃圾邮件 (也称为退 _[) 。](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>中继池

转发或中继出 Microsoft 365 的邮件使用特殊的中继池发送，因为最终目标不应将 Microsoft 365 视为实际发件人。 隔离此流量也很重要，因为存在从 Microsoft 365 自动转发或中继电子邮件的合法和无效方案。 与高风险传送池类似，单独的 IP 地址池用于中继邮件。 此地址池不会发布，因为它可能会经常更改。

Microsoft 365 需要验证原始发件人是否合法，以便我们可以放心地传递转发的邮件。 为此，SPF (DKIM 和 DMARC) 需要在邮件发送到我们时通过。 在我们可以对发件人进行身份验证的情况下，我们使用发件人重写来帮助接收方知道转发的邮件来自受信任的来源。 您可以阅读有关工作原理以及您可以执行哪些操作来帮助确保发送域在 SRS 策略的发件人重写方案中通过 ([身份验证) 。 ](/office365/troubleshoot/antispam/sender-rewriting-scheme)