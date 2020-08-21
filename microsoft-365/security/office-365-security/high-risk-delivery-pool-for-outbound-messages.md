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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 了解如何在 Microsoft 365 数据中心中使用传递池来保护电子邮件服务器的信誉。
ms.openlocfilehash: 83ea21a9230240f1339513efc75587f3d84733cb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827733"
---
# <a name="outbound-delivery-pools"></a>出站传递池

Microsoft 365 数据中心的电子邮件服务器可能暂时会强烈影响发送垃圾邮件。 例如，本地电子邮件组织（通过 Microsoft 365 或 Microsoft 365 帐户入站邮件）中进行的恶意软件或恶意垃圾邮件攻击。 攻击者还通过 Microsoft 365 转发功能中继邮件来避免检测。

这些方案可能会导致受影响的 Microsoft 365 数据中心服务器的 IP 地址出现在第三方阻止列表中。 使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件来源的邮件。

## <a name="high-risk-delivery-pool"></a>高风险传送池
为了防止发生这种限制，来自 Microsoft 365 数据中心服务器（已确定为垃圾邮件或超过服务或出站垃圾邮件策略的发送[限制）](configure-the-outbound-spam-policy.md)的所有出站邮件均将通过_高风险传送池发送_。 [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

高风险传送池是用于出站电子邮件的单独 IP 地址池，它仅用于发送"低质量"邮件 (例如垃圾邮件[和退信) 。](backscatter-messages-and-eop.md) 使用高风险传送池有助于防止出站电子邮件的正常 IP 地址池发送垃圾邮件。 出站电子邮件的正常 IP 地址池维护"高质量"邮件发送信誉，这样可以降低这些 IP 地址出现在 IP 阻止列表中的可能性。

高风险传送池中的 IP 地址将保留在 IP 阻止列表中的可能性，但这是按设计使不可行的。 无法保证传递到预期收件人，因为许多电子邮件组织不会接受来自高风险传送池的邮件。

有关详细信息，请参阅"[控制出站垃圾邮件"。](outbound-spam-controls.md)

> [!NOTE]
> 不管源电子邮件域没有 A 记录也没有公共 DNS 中定义的 MX 记录的邮件，无论其垃圾邮件或发送限制处置如何，都始终会通过高风险传送池路由。

### <a name="bounce-messages"></a>退回邮件

出站高风险传送池管理所有未送达报告 (也称为 NDR、退回邮件、传递状态通知或 DSN) 。

NDR 中可能出现的问题的原因包括：

- 欺骗活动会影响使用该服务之一的客户。
- 帐户收集攻击。
- 垃圾邮件攻击。
- 未创建电子邮件服务器。

所有这些问题都可能会导致服务处理 NDR 的数量显然增加。 在很多情况下，这些 NDR 对其他电子邮件服务器和服务组 (（也称为_[退信式垃圾邮件) 。](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>中继池

通过使用特殊中继池发送转发或中继来自 Microsoft 365 的邮件，因为最终目标不应将 Microsoft 365 视为实际的发件人。 我们根据某些要求，我们也必须隔离此通信，因为 Microsoft 365 的自动转发或中继电子邮件存在合法和无效的方案。 与高风险传送池类似，单独的 IP 地址池用于中继邮件。 该地址库未发布，因为它可能会经常更改。

Microsoft 365 需要验证原始发件人是否为合法邮件，以便我们可以自信地传递转发的邮件。 为此，电子邮件身份验证必须 (符合 SPF、DKIM 和 DMARC) 通过邮件发送给我们时需要通过。 如果我们可以对发件人进行身份验证，我们使用发件人重写来帮助收件人知道转发的邮件来自受信任的来源。 可以详细了解这一如何工作，以及可以如何帮助确保发送域通过 [S) RS 域的发件人 (写入 ](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)。
