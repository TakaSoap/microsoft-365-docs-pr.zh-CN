---
title: 从另一个保护服务切换到 EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: 本文将了解如何从本地电子邮件Exchange Online Protection (安全) 或基于云的保护服务切换到 EOP 服务。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9b1bd7eb869c410ccbda51ad88b105ff0315fadd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60149571"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>从 Google Postini、Barracuda 垃圾邮件和病毒防火墙或 Cisco IronPort 切换到 EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 本主题的目的是帮助您了解从内部部署电子邮件卫生设备或基于云的保护服务切换到 Exchange Online Protection (EOP) 的过程，然后为您提供开始操作的帮助资源。有许多垃圾邮件筛选解决方案，但是在大多数情况下切换到 EOP 的过程是相似的。

如果您不是 EOP 的一位，并且想要在决定切换之前阅读其功能的概述，请从 Exchange Online Protection[概述](exchange-online-protection-overview.md)主题开始。

在切换到 EOP 之前，有必要考虑是要在云中、Exchange Online、内部部署还是在混合方案中托管 EOP 保护的邮箱。（混合方案意味着某些邮箱在内部部署中托管，其他一些邮箱使用 Exchange Online 托管。）各托管方案：可能是云、内部部署和混合，但安装步骤可能有所不同。有一些考虑事项可帮助您选择合适的部署：

- 使用内部部署邮箱的 **EOP** 保护：如果您具有您想要使用的现有邮件托管基础结构，或者您具有将邮箱保留在本地的业务要求，并且您希望使用 EOP 作为基于云的电子邮件保护，则此方案适用。 [独立切换到 EOP](#switch-to-eop-standalone)详细描述了此方案。

- **EOP 保护Exchange Online** 邮箱：如果您需要 EOP 保护以及所有托管在云中的邮箱，则此方案适用。 它可以帮助您降低复杂性，因为您不必维护内部部署邮件传递服务器。 [切换到 Exchange Online](#switch-to-exchange-online) 描述了此方案。

- **混合邮箱的 EOP** 保护：可能希望使用云邮箱，但需要为某些用户保留内部部署邮箱。 如果您希望在内部部署中托管某些邮箱并使用 Exchange Online 托管其他邮箱，则选择此方案。 [切换到混合解决方案](#switch-to-a-hybrid-solution)描述了此方案。

## <a name="switch-to-eop-standalone"></a>独立切换到 EOP

如果当前在内部部署中托管邮箱，并使用内部部署保护设备或云邮件传递保护服务，则可以切换到 EOP 以利用其保护功能和可用性。要在独立方案中设置 EOP（这意味着在内部部署中托管邮箱并使用 EOP 提供电子邮件保护），可以按照[设置 EOP 服务](/exchange/standalone-eop/set-up-your-eop-service)中所述的步骤执行操作。该主题概述了设置 EOP 保护的步骤，包括注册、添加域和使用连接器设置邮件流。

## <a name="switch-to-exchange-online"></a>切换到 Exchange Online

你可能有受本地设备保护的本地邮箱，并且你想要跳转到 Exchange Online 云托管的邮箱和 EOP 保护，以利用 Microsoft 365 云消息和保护功能。 To get started， you can sign up for Microsoft 365 and add your domain. 此方案不需要您设置连接器，因为没有任何路由到内部部署邮箱。 首先[获取最新高级功能，Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)注册并熟悉其功能。

在Microsoft 365过程中，您将创建基于云的邮箱用户。

## <a name="switch-to-a-hybrid-solution"></a>切换到混合解决方案

出于业务需要或法规考虑，您可能希望仅将一部分邮箱移动到云。当部署混合方案时，可以根据业务需要指示，将邮箱移动到云。迁移到具有 EOP 保护的混合方案比移动到全云方案更复杂，但是 Microsoft 提供了完全的混合支持和广泛的资源以使移动到混合方案更加简便。

如果你正在考虑混合部署，最好从混合Exchange Server[开始](/exchange/exchange-hybrid)。 另外，有几种不同的在混合方案中路由邮件的方式需要重点了解。 [混合Exchange](/exchange/transport-routing)中的传输路由将解释每种类型，因此您可以根据您的业务需求选择最佳路由方案。

## <a name="migration-planning"></a>迁移计划

当决定切换到 EOP 时，请确保特别留意下列几个方面：

- **自定义筛选规则**：如果有自定义筛选或业务策略规则来捕获特定垃圾邮件，我们建议您在迁移规则之前先尝试使用默认设置的 EOP 一段时间。 EOP 提供了具有默认设置的企业级垃圾邮件保护，这可能表示您不需要将某些规则迁移到 EOP。 当然，如果您有现成的强制特定自定义业务策略的规则，则可以创建这些规则。 有关详细信息，请参阅邮件[流规则 (中的) 传输Exchange Online。](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

- **IP 允许列表和 IP 阻止列表**：如果您有每用户允许列表和阻止列表，请留出一些时间在设置过程中将列表复制到 EOP。 有关 IP 允许列表和 IP 阻止列表的信息，请参阅 [配置连接筛选器策略](configure-the-connection-filter-policy.md)。

- **安全通信**：如果你有需要加密消息的合作伙伴，我们建议你在管理中心Exchange此操作。 若要配置此方案，请参阅设置 [连接器以确保与合作伙伴组织的安全邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)。

> [!TIP]
> 从内部部署设备切换到 EOP 时，可以就地离开执行业务规则检查的设备或服务器。 例如，如果你的设备对出站邮件执行自定义筛选，并且希望它继续这样做，你可以将 EOP 配置为直接将邮件发送到设备进行其他筛选，然后再将其路由到 Internet。
