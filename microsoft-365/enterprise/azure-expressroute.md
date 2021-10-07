---
title: 适用于 Office 365 的 Azure ExpressRoute
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: 了解如何将 Azure ExpressRoute 与 Office 365，并规划网络实施项目（如果你要使用它进行部署）。
ms.openlocfilehash: 9a4f4be76751ec03610bd766f51ec91526ca18a4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198537"
---
# <a name="azure-expressroute-for-office-365"></a>适用于 Office 365 的 Azure ExpressRoute

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

了解如何将 Azure ExpressRoute 与 Office 365以及如何规划部署 Azure ExpressRoute 以用于 Office 365 时所需的网络实现项目。 在 Azure 中运行的基础结构和平台服务通常会从解决网络体系结构和性能注意事项中获益。 在这些情况下，我们建议使用 ExpressRoute for Azure。 软件即服务产品（如 Office 365 和 Dynamics 365）已构建为可通过 Internet 安全可靠地访问。 有关 Internet 性能和安全性以及何时可以考虑使用 Azure ExpressRoute for Office 365请参阅文章[Assessing Office 365 network connectivity](assessing-network-connectivity.md)。

> [!NOTE]
> Microsoft Defender for Endpoint 不提供与 Azure ExpressRoute 的集成。 虽然这不会阻止客户定义 ExpressRoute 规则，以便从专用网络连接到适用于 Endpoint 云服务的 Microsoft Defender，但由客户负责在服务或云基础结构不断发展时维护规则。

> [!NOTE]
> 我们不建议使用 ExpressRoute for Microsoft 365因为它在大多数情况下不会为服务提供最佳连接模型。 因此，需要 Microsoft 授权才能使用此连接模型Microsoft 365。 我们查看每个客户请求并授权 ExpressRoute for Microsoft 365仅在极少数情况下才需要。 有关详细信息，请参阅[ExpressRoute for Microsoft 365](https://aka.ms/erguide)指南，并遵循生产力、网络和安全团队对文档的全面审阅，与 Microsoft 帐户团队合作，以根据需要提交例外。 尝试为用户创建路由筛选器的未经授权的Office 365将收到[一条错误消息](https://support.microsoft.com/kb/3181709)。

## <a name="planning-azure-expressroute-for-office-365"></a>规划 Azure ExpressRoute for Office 365

除了 Internet 连接之外，您还可以选择通过直接连接路由其 Office 365 网络流量的子集，该直接连接为 Microsoft 网络组件提供可预测性和 99.95% 正常运行时间 SLA。 Azure ExpressRoute 提供了此专用网络连接，Office 365 Microsoft 云服务。

无论你是否有现有的 MPLS WAN，ExpressRoute 都可以通过以下三种方法之一添加到网络体系结构中;通过支持的云交换共同位置提供程序、以太网点到点连接提供程序，或者通过 MPLS 连接提供程序。 查看 [哪些提供程序在你的区域可用](/azure/expressroute/expressroute-locations)。 直接 ExpressRoute 连接将启用与下面"包括哪些服务Office 365[概述的应用程序的连接](azure-expressroute.md#BKMK_WhatDoIGet)。 所有其他应用程序和服务的网络通信将继续遍历 Internet。

请考虑以下高级网络图，该图显示了一个典型的 Office 365 客户通过 Internet 连接到 Microsoft 数据中心，以访问所有 Microsoft 应用程序，如 Office 365、Windows Update 和 TechNet。 客户无论从本地网络还是从独立 Internet 连接进行连接，都使用类似的网络路径。

![Office 365网络连接。](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

现在，查看更新后的图表，该图Office 365 Internet 和 ExpressRoute 连接到 Office 365。 请注意，某些连接（如公共 DNS 和 内容分发网络 节点）仍然需要公共 Internet 连接。 另请注意，不在 ExpressRoute 连接建筑物中的客户用户正在通过 Internet 进行连接。

![Office 365 ExpressRoute 建立连接。](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

是否仍需要更多信息？ 了解如何使用[Azure ExpressRoute for Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)管理网络流量，并了解如何配置[Azure ExpressRoute for Office 365。](/azure/expressroute/expressroute-faqs) 我们还记录了第 9 频道上的[Azure ExpressRoute for Office 365 培训](https://channel9.msdn.com/series/aer)系列（10 部分）以帮助更详尽地解释概念。

## <a name="what-office-365-services-are-included"></a>包括Office 365服务是什么？
<a name="BKMK_WhatDoIGet"> </a>

下表列出了 ExpressRoute Office 365支持的服务。 请查看 Office 365[终结点](./urls-and-ip-address-ranges.md)文章，了解这些应用程序的哪些网络请求需要 Internet 连接。

| 包含的应用程序 |
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype for BusinessOnline<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePointOnline<sup>1</sup> <br/> OneDrive for Business<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|门户和共享<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD 连接<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup>其中每个应用程序都有不受 ExpressRoute 支持的 Internet 连接要求，请参阅 Office 365[终结点](./urls-and-ip-address-ranges.md)文章了解详细信息。

适用于 Office 365 的 ExpressRoute 中未包含的服务包括 Microsoft 365 企业应用版 客户端下载、本地标识提供商登录和由中国 21 Vianet) 服务运营的 Office 365 (。

## <a name="implementing-expressroute-for-office-365"></a>实现适用于 Office 365 的 ExpressRoute

实现 ExpressRoute 需要网络和应用程序所有者的参与，并且需要仔细规划以确定新的网络路由体系结构[](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)、带宽要求、实现安全性的地方、高可用性等。 若要实现 ExpressRoute，你需要：

1. 完全了解 ExpressRoute 在你的连接规划中满足Office 365需求。 了解哪些应用程序将使用 Internet 或 ExpressRoute，并全面规划网络容量、安全性和高可用性需求，同时使用 Internet 和 ExpressRoute Office 365流量。

2. 确定 Internet 和 ExpressRoute 流量<sup>1</sup>的出口和对等位置。

3. 确定 Internet 和 ExpressRoute 连接所需的容量。

4. 制定实施安全和其他标准外围控件<sup>1 的计划</sup>。

5. 拥有一个有效的Microsoft Azure帐户来订阅 ExpressRoute。

6. 选择连接模型和批准的 [提供程序](/azure/expressroute/expressroute-locations)。 请记住，客户可以选择多个连接模型或合作伙伴，合作伙伴无需与现有的网络提供商相同。

7. 在将流量引导到 ExpressRoute 之前验证部署。

8. （可选 [）实施 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) 和评估区域扩展。

<sup>1</sup> 重要的性能注意事项。 此处的决策会显著影响延迟，延迟对于应用程序（如应用程序）Skype for Business。

有关其他参考，请使用我们的 [路由指南](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) 以及 [ExpressRoute 文档](/azure/expressroute/expressroute-introduction)。

若要购买 ExpressRoute for Office 365，你需要与一个或多个批准的提供商合作，通过[](/azure/expressroute/expressroute-locations)ExpressRoute 订阅预配所需数量和高级版电路。 无需从用户那里购买其他Office 365。

以下是可以用于返回的简短链接：[https://aka.ms/expressrouteoffice365]()

准备好注册[ExpressRoute for Office 365？](https://aka.ms/ert)

## <a name="related-topics"></a>相关主题

[评估 Office 365 网络连接](assessing-network-connectivity.md)

[管理 ExpressRoute for Office 365 连接](managing-expressroute-for-connectivity.md)

[使用 ExpressRoute for Office 365 路由](routing-with-expressroute.md)

[ExpressRoute for Office 365 网络计划](network-planning-with-expressroute.md)

[实现 ExpressRoute for Office 365](implementing-expressroute.md)

[在 ExpressRoute 中将 BGP 社区用于Office 365方案](bgp-communities-in-expressroute.md)

[Skype for Business Online 中的媒体质量和网络连接性能](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[使用基线和性能历史记录优化 Office 365 性能](performance-tuning-using-baselines-and-history.md)

[Office 365 性能疑难解答计划](performance-troubleshooting-plan.md)

[Office 365 URL 和 IP 地址范围](urls-and-ip-address-ranges.md)

[Office 365 网络和性能优化](network-planning-and-performance.md)

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版概述](microsoft-365-overview.md)
