---
title: 从其他保护服务切换到 EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您将了解如何从内部部署电子邮件清理 (或基于云的保护服务切换到 EOP) EOP。
ms.openlocfilehash: a6405411a130abf8369b312f553060caf0bf3855
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827793"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>从 Google Postini、Barracuda 垃圾邮件和病毒防火墙或 Cisco IronPort 切换到 EOP

 本主题的目的是帮助您了解从内部部署电子邮件卫生设备或基于云的保护服务切换到 Exchange Online Protection (EOP) 的过程，然后为您提供开始操作的帮助资源。有许多垃圾邮件筛选解决方案，但是在大多数情况下切换到 EOP 的过程是相似的。

如果您不开始使用 EOP 且想在决定切换之前阅读其功能的概述，请从 [Exchange Online Protection 概述主题开始](exchange-online-protection-overview.md) 入门。

在切换到 EOP 之前，有必要考虑是要在云中、Exchange Online、内部部署还是在混合方案中托管 EOP 保护的邮箱。（混合方案意味着某些邮箱在内部部署中托管，其他一些邮箱使用 Exchange Online 托管。）各托管方案：可能是云、内部部署和混合，但安装步骤可能有所不同。有一些考虑事项可帮助您选择合适的部署：

- **使用内部部署邮箱的 EOP 保护**：如果您有要使用的现有邮件托管基础结构或者有在内部部署中保留邮箱的业务需要，并且您想要使用 EOP 作为基于云的电子邮件保护，则适合选择此方案。 [独立切换到 EOP](#switch-to-eop-standalone)详细描述了此方案。

- **使用 Exchange Online 邮箱的 EOP 保护**：如果您希望使用 EOP 保护且在云中托管所有邮箱，则适合选择此方案。 它可以帮助您降低复杂性，因为您不必维护内部部署邮件传递服务器。 [切换到 Exchange Online](#switch-to-exchange-online) 描述了此方案。

- **使用混合邮箱的 EOP**保护：可能您要使用云邮箱，但是你需要在内部部署中为某些用户保留邮箱。 如果您希望在内部部署中托管某些邮箱并使用 Exchange Online 托管其他邮箱，则选择此方案。 [切换到混合解决方案](#switch-to-a-hybrid-solution)描述了此方案。

## <a name="switch-to-eop-standalone"></a>独立切换到 EOP

如果当前在内部部署中托管邮箱，并使用内部部署保护设备或云邮件传递保护服务，则可以切换到 EOP 以利用其保护功能和可用性。要在独立方案中设置 EOP（这意味着在内部部署中托管邮箱并使用 EOP 提供电子邮件保护），可以按照[设置 EOP 服务](set-up-your-eop-service.md)中所述的步骤执行操作。该主题概述了设置 EOP 保护的步骤，包括注册、添加域和使用连接器设置邮件流。

## <a name="switch-to-exchange-online"></a>切换到 Exchange Online

也许您具有由内部部署设备保护的内部部署邮箱，并且您希望跳转到 Exchange Online 云托管的邮箱和 EOP 保护，以利用 Microsoft 365 云邮件和保护功能。 若要开始使用，你可以注册 Microsoft 365 并添加域。 此方案不需要您设置连接器，因为没有任何路由到本地邮箱。 从 [获取使用 Microsoft 365 的](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) 最新高级功能进行注册并熟悉其功能。

在 Microsoft 365 设置过程中，将创建基于云的邮箱用户。

## <a name="switch-to-a-hybrid-solution"></a>切换到混合解决方案

出于业务需要或法规考虑，您可能希望仅将一部分邮箱移动到云。当部署混合方案时，可以根据业务需要指示，将邮箱移动到云。迁移到具有 EOP 保护的混合方案比移动到全云方案更复杂，但是 Microsoft 提供了完全的混合支持和广泛的资源以使移动到混合方案更加简便。

如果您考虑混合部署，则最好 [Exchange Server是最佳选择](https://docs.microsoft.com/exchange/exchange-hybrid)。 另外，有几种不同的在混合方案中路由邮件的方式需要重点了解。 [Exchange 混合部署中的传输路由对](https://docs.microsoft.com/exchange/transport-routing) 每种类型都进行了说明，因此您可以根据业务需求选择最佳路由方案。

## <a name="migration-planning"></a>迁移计划

当决定切换到 EOP 时，请确保特别留意下列几个方面：

- **自定义筛选规则**：如果您有自定义筛选或业务策略规则来克克特定垃圾邮件，建议您在迁移规则前尝试一段时间内使用默认设置的 EOP。 EOP 提供了具有默认设置的企业级垃圾邮件保护，这可能表示您不需要将某些规则迁移到 EOP。 当然，如果您有现成的强制特定自定义业务策略的规则，则可以创建这些规则。 [通过 Exchange Online Protection (传输规则) 邮件流规则，](mail-flow-rules-transport-rules-0.md) 并提供了有关在 EOP 中创建邮件流规则的详细说明。

- **IP 允许列表和 IP 阻止列表**：如果您有每个用户的允许列表和阻止列表，请在设置过程中，有时间将这些列表复制到 EOP。 有关 IP 允许列表和 IP 阻止列表的详细信息，请参阅配置 [连接筛选器策略](configure-the-connection-filter-policy.md)。

- **安全通信**：如果您的合作伙伴需要加密邮件传递，我们建议在 Exchange 管理中心进行该设置。 若要配置此方案，请参阅 [设置连接器以实现与合作伙伴组织一起的安全邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)。

> [!TIP]
> 从内部部署设备切换到 EOP 时，可以就地离开执行业务规则检查的设备或服务器。 例如，如果您的设备对出站邮件执行自定义筛选，您希望它继续这一操作，则您可以配置 EOP 将邮件直接发送到设备以进行额外筛选，然后再路由到 Internet。
