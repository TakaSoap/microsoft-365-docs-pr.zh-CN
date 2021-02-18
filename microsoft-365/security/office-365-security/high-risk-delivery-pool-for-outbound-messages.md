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
ms.openlocfilehash: 89aac1478d3e5840df4379b9f49832b79d0e133a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289801"
---
# <a name="outbound-delivery-pools"></a>出站传递池

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft 365 数据中心中的电子邮件服务器可能暂时有发送垃圾邮件的念念。 例如，内部部署电子邮件组织中通过 Microsoft 365 发送出站邮件或遭到入侵的 Microsoft 365 帐户的恶意软件或恶意垃圾邮件攻击。 攻击者还尝试通过 Microsoft 365 转发中继邮件来避免检测。

这些方案可能会导致受影响的 Microsoft 365 数据中心服务器的 IP 地址显示在第三方阻止列表中。 使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件源的电子邮件。

## <a name="high-risk-delivery-pool"></a>高风险传递池
为了防止这种情况，来自 Microsoft 365 数据中心服务器的所有出站邮件被确定为垃圾邮件或超出服务发送限制或出站垃圾邮件 [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)策略的所有出 [](configure-the-outbound-spam-policy.md)站邮件都通过高风险传递池 _发送_。

高风险传递池是出站电子邮件的单独 IP 地址池，仅用于发送"低质量"邮件 (例如垃圾邮件和退信) 。 [](backscatter-messages-and-eop.md) 使用高风险传递池有助于防止出站电子邮件的正常 IP 地址池发送垃圾邮件。 出站电子邮件的正常 IP 地址池维护发送"高质量"邮件的信誉，这会降低这些 IP 地址出现在 IP 阻止列表上的可能性。

高风险传递池中的 IP 地址将保留在 IP 阻止列表上的可能性非常真实，但这是设计使的。 不保证向目标收件人传递邮件，因为许多电子邮件组织不接受来自高风险传递池的邮件。

有关详细信息，请参阅"[控制出站垃圾邮件"。](outbound-spam-controls.md)

> [!NOTE]
> 源电子邮件域没有 A 记录且在公共 DNS 中未定义 MX 记录的邮件始终通过高风险传递池路由，无论其垃圾邮件或发送限制处置如何。

### <a name="bounce-messages"></a>退回邮件

出站高风险传递池管理所有未送达报告（也称为 (、退回邮件、传递状态通知或 DSN）的) 。

NDR 中激增的可能原因包括：

- 影响使用该服务的客户之一的欺骗活动。
- 目录收集攻击。
- 垃圾邮件攻击。
- 未授权电子邮件服务器。

所有这些问题都可能导致服务正在处理的 NDR 数量突然增加。 许多时候，这些 NDR 对于其他电子邮件服务器和服务 (_[也称为退退垃圾邮件](backscatter-messages-and-eop.md)_) 。

## <a name="relay-pool"></a>中继池

转发或中继自 Microsoft 365 的邮件使用特殊的中继池发送，因为最终目标不应将 Microsoft 365 视为实际发件人。 隔离此流量也很重要，因为存在从 Microsoft 365 自动转发或中继电子邮件的合法和无效方案。 与高风险传递池类似，单独的 IP 地址池用于中继邮件。 此地址池不会发布，因为它可能会经常更改。

Microsoft 365 需要验证原始发件人是否合法，以便我们可以放心地传递转发的邮件。 为此，需要在邮件 (SPF、DKIM 和 DMARC) 传递电子邮件身份验证。 在我们可以对发件人进行身份验证的情况下，我们使用发件人重写来帮助收件人知道转发的邮件来自受信任的来源。 您可以阅读有关工作原理以及您可以执行哪些操作来帮助确保发送域通过发件人重写方案 ([SRS ](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)) 。
