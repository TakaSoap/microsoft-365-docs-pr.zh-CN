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
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 EOP Exchange Online Protection (中的出站) ，以及如果您需要发送大量邮件，该怎么办。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 26be514584a8fb2f8c024c0f4db208018d951868
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202389"
---
# <a name="outbound-spam-protection-in-eop"></a>EOP 中的出站垃圾邮件保护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在Microsoft 365邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中Exchange Online，我们非常重视管理出站垃圾邮件。 即使一个客户有意或无意地从组织发送垃圾邮件，该操作也会降低整个服务的信誉，并可能影响其他客户的电子邮件传递。

本文介绍旨在帮助防止出站垃圾邮件的控件和通知，以及如果您需要发送大量邮件，您可以执行哪些操作。

## <a name="what-admins-can-do-to-control-outbound-spam"></a>管理员可以执行哪些操作来控制出站垃圾邮件

- 使用内置通知：当用户超出服务或出站垃圾邮件策略的发送 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)限制并限制 [](configure-the-outbound-spam-policy.md)发送电子邮件时，名为"限制发送电子邮件的用户"的默认警报策略将向 **TenantAdmins** (**全局** 管理员) 组的成员发送电子邮件通知。   若要配置其他接收这些通知的用户，请参阅验证 [受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 此外，名为"电子邮件发送限制"和"检测到可疑电子邮件发送模式"的默认警报策略将电子邮件通知发送到 **TenantAdmins** (**全局** 管理员) 组。 有关警报策略的详细信息，请参阅 [Microsoft 365 中的警报策略](../../compliance/alert-policies.md)。

- 查看来自第三方电子邮件提供商的垃圾邮件投诉：许多电子邮件服务（如 Outlook.com、Yahoo 和 AOL）提供反馈循环，如果其服务中的任意用户将来自 Microsoft 365 的电子邮件标记为垃圾邮件，邮件将打包并发回我们进行审阅。 若要了解有关发件人对 Outlook.com 的支持，请转到 <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> 。

## <a name="how-eop-controls-outbound-spam"></a>EOP 如何控制出站垃圾邮件

- **出站电子邮件流量的** 分离：将扫描通过服务发送的每封出站邮件是否包含垃圾邮件。 如果邮件被确定为垃圾邮件，则从名为高风险传递池的低信誉辅助 IP 地址 _池进行传递_。 有关详细信息，请参阅[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。

- **监视源 IP 地址信誉**：Microsoft 365查询各种第三方 IP 阻止列表。 如果用于出站电子邮件的任何 IP 地址显示在这些列表中，将生成警报。 此监视允许我们在垃圾邮件导致信誉下降时快速做出响应。 生成警报后，我们具有内部文档，概述了如何从阻止列表中 (除名) IP 地址。

- 禁用发送过多垃圾邮件的帐户：尽管我们将出站垃圾邮件隔离到高风险传送池中，但不允许帐户 (，即遭到入侵的帐户) 无限期发送 <sup>\*</sup> 垃圾邮件。 我们监视发送垃圾邮件的帐户，当这些帐户超出限制时，将阻止该帐户发送电子邮件。 单个用户和整个租户有不同的阈值。

- 禁用发送过快的电子邮件的帐户：除了查找标记为垃圾邮件的邮件的限制外，还有一些限制在帐户达到总体出站邮件限制时阻止帐户，而不考虑出站邮件的垃圾邮件筛选裁定。 <sup>\*</sup> 遭到入侵的帐户可能会发送以前无法识别 (垃圾邮件筛选器) 的垃圾邮件的零日通知。 由于很难确定合法的大量邮件活动与垃圾邮件活动，因此这些限制有助于最大限度地减少任何潜在损害。

<sup>\*</sup> 我们不公布确切的限制，因此垃圾邮件制造者无法对系统进行游戏，因此我们可在必要时增加或减少限制。 这些限制足够高，以防止一般商业用户超过它们，而低到足以帮助控制垃圾邮件制造者造成的损坏。

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>推荐通过 EOP 发送大量邮件的客户选择邮件

在想要发送大量电子邮件的客户与保护服务免受损坏的帐户和具有较差收件人获取做法的批量电子邮件发件人之间取得平衡是很难的。 电子邮件源Microsoft 365第三方 IP 阻止列表的成本大于阻止发送过多电子邮件的用户。

如 Exchange Online [Service Description](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)中所述，使用 EOP 发送批量电子邮件不受服务支持，只能在"尽力而为"的基础上使用。 对于想要发送批量电子邮件的客户，我们建议采用以下解决方案：

- **通过本地电子邮件服务器发送** 批量电子邮件：客户维护自己的电子邮件基础结构，用于大量邮件。

- **使用第三方批量电子邮件** 提供商：可以使用多个第三方批量电子邮件解决方案提供商发送大量邮件。 这些公司有兴趣与客户合作，以确保良好的电子邮件发送实践。

MAAWG 消息、移动、恶意软件反滥用 (工作组) 发布其成员身份名单 <https://www.maawg.org/about/roster> 。 列表中列出了多个批量电子邮件提供商，这些提供商已知是负责的 Internet 公民。
