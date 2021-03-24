---
title: 出站垃圾邮件保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 中的出站垃圾邮件控件，以及如果您需要发送大量邮件，该怎么办。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e84cd636abee42a03ff8590091542c96714f2d8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055683"
---
# <a name="outbound-spam-protection-in-eop"></a>EOP 中的出站垃圾邮件保护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，我们将认真管理出站垃圾邮件。 有意或无意发送其组织垃圾邮件的客户可能会降低整个服务的信誉，并可能影响其他客户的电子邮件传递。

本主题介绍旨在帮助防止出站垃圾邮件的控件和通知，以及如果您需要发送大量邮件，您可以执行哪些操作。

## <a name="what-admins-can-do-to-control-outbound-spam"></a>管理员可以执行哪些操作来控制出站垃圾邮件

- 使用内置通知：当用户超出服务或出站垃圾邮件策略的发送 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)限制并限制 [](configure-the-outbound-spam-policy.md)发送电子邮件时，名为 **"** 限制发送电子邮件的用户"的默认警报策略将向 **TenantAdmins** (**全局** 管理员) 组的成员发送电子邮件通知。 若要配置其他接收这些通知的用户，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 此外，名为"电子邮件发送限制"和"检测到可疑电子邮件发送模式"的默认警报策略向 **TenantAdmins** (**全局** 管理员组) 发送电子邮件通知。 若要详细了解警报策略，请参阅[安全与合规中心内的警报策略](../../compliance/alert-policies.md)。

- **审阅** 来自第三方电子邮件提供商的垃圾邮件投诉：许多电子邮件服务（如 Outlook.com、Yahoo 和 AOL）提供反馈循环，如果服务中的用户将来自 Microsoft 365 的电子邮件标记为垃圾邮件，邮件将打包并发回我们进行审阅。 若要了解有关发件人对邮件 Outlook.com，请转到 <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> 。

## <a name="how-eop-controls-outbound-spam"></a>EOP 如何控制出站垃圾邮件

- **出站电子邮件流量的分离**：将扫描通过服务发送的每封出站邮件是否包含垃圾邮件。 如果邮件被确定为垃圾邮件，则从名为高风险传递池的低信誉辅助 IP 地址 _池进行传递_。 有关详细信息，请参阅[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。

- **监视源 IP 地址信誉**：Microsoft 365 查询各种第三方 IP 阻止列表。 如果我们用于出站电子邮件的任何 IP 地址显示在这些列表中，将生成警报。 这样，在垃圾邮件导致信誉下降时，我们能够快速做出响应。 生成警报时，我们具有内部文档，概述了如何从阻止列表中 (除名) IP 地址。

- 禁用发送过多垃圾邮件的帐户：尽管我们将出站垃圾邮件隔离到高风险传送池中，但不允许帐户 (，即遭到入侵的帐户) 无限期发送垃圾邮件。 <sup>\*</sup> 我们监视发送垃圾邮件的帐户，当这些帐户超出限制时，将阻止该帐户发送电子邮件。 单个用户和整个租户有不同的阈值。

- 禁用发送过快的电子邮件的帐户：除了查找标记为垃圾邮件的邮件的限制之外，还有一些限制在帐户达到总体出站邮件限制时阻止帐户，而不管出站邮件的垃圾邮件筛选裁定如何。 <sup>\*</sup> 遭到入侵的帐户可能会发送零 (之前无法识别) 垃圾邮件筛选器错过的垃圾邮件。 由于很难确定合法的大量邮件活动与垃圾邮件活动，因此这些限制有助于最大限度地减少任何潜在损害。

<sup>\*</sup> 我们不公布确切的限制，因此垃圾邮件制造者无法对系统进行游戏，因此我们可以在必要时增加或减少限制。 这些限制足够高，以防止一般商业用户超过它们，而低到足以帮助控制垃圾邮件制造者造成的损坏。

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>建议通过 EOP 发送大量邮件的客户

在想要发送大量电子邮件的客户与保护服务免受损坏的帐户和具有较差收件人获取做法的批量电子邮件发件人之间取得平衡非常困难。 Microsoft 365 电子邮件源登录第三方 IP 阻止列表的成本大于阻止发送过多电子邮件的用户。

如 Exchange [Online 服务](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)说明中所述，使用 EOP 发送批量电子邮件不支持使用该服务，仅允许"尽力"使用。 对于想要发送批量电子邮件的客户，我们建议采用以下解决方案：

- **通过本地电子邮件服务器发送** 批量电子邮件：这意味着客户需要维护自己的电子邮件基础结构，用于大量邮件。

- **使用第三方批量电子邮件** 提供商：可以使用多个第三方批量电子邮件解决方案提供商发送大量邮件。 这些公司有兴趣与客户合作，以确保良好的电子邮件发送实践。

MAAWG 消息、移动、恶意软件反滥用工作组 (在) 发布其成员身份名单 <https://www.maawg.org/about/roster> 。 列表中列出了多个批量电子邮件提供商，这些提供商已知是负责的 Internet 公民。