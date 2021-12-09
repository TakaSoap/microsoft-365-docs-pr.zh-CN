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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 了解如何使用传递池来保护数据中心内电子邮件Microsoft 365信誉。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cbfcb7063f839506b81ee244eadfce622c513c45
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370664"
---
# <a name="outbound-delivery-pools"></a>出站传递池

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

数据中心内的电子邮件Microsoft 365可能暂时没有发送垃圾邮件。 例如，内部部署电子邮件组织中通过邮件发送出站邮件或帐户遭到入侵Microsoft 365恶意软件或恶意Microsoft 365攻击。 攻击者还尝试通过邮件转发来中继邮件，Microsoft 365检测。

这些方案可能导致受影响的数据中心服务器的 IP 地址Microsoft 365第三方阻止列表上出现。 使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件源的电子邮件。

## <a name="high-risk-delivery-pool"></a>高风险传送池
为了防止这种情况，来自 Microsoft 365 数据中心服务器的所有出站邮件（被确定为垃圾邮件或超过服务的发送限制或出站垃圾邮件策略）都 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)通过高风险传送 [](configure-the-outbound-spam-policy.md)池 _发送_。

高风险传递池是出站电子邮件的单独 IP 地址池，仅用于发送"低质量" (例如垃圾邮件和退信[。](backscatter-messages-and-eop.md) 使用高风险传送池有助于防止出站电子邮件的正常 IP 地址池发送垃圾邮件。 出站电子邮件的正常 IP 地址池维护发送"高质量"邮件的信誉，这会降低这些 IP 地址出现在 IP 阻止列表上的可能性。

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

所有这些问题都可能导致服务正在处理的 NDR 数量突然增加。 许多时候，这些NDR 似乎为其他电子邮件服务器和服务的垃圾邮件 (也称为退 _[) 。](backscatter-messages-and-eop.md)_


### <a name="relay-pool"></a>中继池

在某些情况下，通过 Microsoft 365 转发或中继的邮件会使用特殊的中继池发送，因为目标不应Microsoft 365实际发件人。 我们隔离此电子邮件通信非常重要，因为存在用于自动转发或中继来自电子邮件的邮件流的合法和无效Microsoft 365。 与高风险传送池类似，单独的 IP 地址池用于中继邮件。 此地址池未发布，因为它可能会经常更改，并且不是已发布的 SPF 记录的一Microsoft 365。

Microsoft 365验证原始发件人是否合法，以便我们可以放心地传递转发的邮件。

转发/中继邮件应满足以下条件之一，以避免使用中继池：

- 出站发件人位于接受 [域中](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- 当邮件发送到邮件时，SPF Microsoft 365。
- 当邮件发送到发件人域时，发件人域上的 DKIM Microsoft 365。
 
通过查看出站服务器 IP (中继池将位于 40.95.0.0/16 范围) ，或查看出站服务器名称 (的名称将为) ，可以判断邮件是通过中继池发送的。

在我们可以验证发件人的情况下，我们使用发件人重写方案 (SRS) 来帮助收件人电子邮件系统知道转发的邮件来自受信任的来源。 您可以阅读有关工作原理和操作方法的更多信息，以帮助确保发送域通过发件人重写方案中的身份验证 ([SRS](/office365/troubleshoot/antispam/sender-rewriting-scheme)) 中Office 365。

若要使 DKIM 正常工作，请确保为发送域启用 DKIM。 例如，fabrikam.com 是 contoso.com 的一部分，在组织的接受域中定义。 如果邮件发件人 sender@fabrikam.com，需要为邮件发件人启用 DKIM fabrikam.com。 可以在使用 DKIM 验证从自定义域发送的出站电子邮件中阅读如何[启用。](use-dkim-to-validate-outbound-email.md)

若要添加自定义域，请按照将域添加到域[中的步骤Microsoft 365。](../../admin/setup/add-domain.md)

如果域的 MX 记录指向第三方服务或本地电子邮件服务器，则应该使用增强的 [连接器筛选](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。 增强的筛选可确保 SPF 验证对入站邮件正确无误，并避免通过中继池发送电子邮件。

