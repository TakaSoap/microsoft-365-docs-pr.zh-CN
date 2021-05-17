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
description: 了解如何使用传递池来保护数据中心中电子邮件Microsoft 365信誉。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599907"
---
# <a name="outbound-delivery-pools"></a>出站传递池

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

数据中心内的电子邮件Microsoft 365可能暂时没有发送垃圾邮件。 例如，内部部署电子邮件组织中通过邮件发送出站邮件或帐户遭到入侵Microsoft 365恶意软件或Microsoft 365攻击。 攻击者还尝试通过邮件转发来中继邮件，Microsoft 365检测。

这些方案可能导致受影响的数据中心服务器的 IP 地址Microsoft 365第三方阻止列表上出现。 使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件源的电子邮件。

## <a name="high-risk-delivery-pool"></a>高风险传送池
为了防止这种情况，来自 Microsoft 365 数据中心服务器的所有出站邮件（被确定为垃圾邮件或超过服务或出站垃圾邮件策略的发送限制）[](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)都通过高风险 [](configure-the-outbound-spam-policy.md)传递池 _发送_。

高风险传递池是出站电子邮件的单独 IP 地址池，仅用于发送"低质量" (例如垃圾邮件和退信) 。 [](backscatter-messages-and-eop.md) 使用高风险传送池有助于防止出站电子邮件的正常 IP 地址池发送垃圾邮件。 出站电子邮件的正常 IP 地址池维护发送"高质量"邮件的信誉，这会降低这些 IP 地址出现在 IP 阻止列表上的可能性。

将高风险传送池中的 IP 地址置于 IP 阻止列表的可能性仍然很高，但这是设计使的。 不保证向目标收件人传递邮件，因为许多电子邮件组织不接受来自高风险传递池的邮件。

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
