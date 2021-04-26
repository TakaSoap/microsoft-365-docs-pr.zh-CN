---
title: 适用于 Office 365 的 Azure ExpressRoute
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: 了解如何将 Azure ExpressRoute 与 Office 365 一同使用，并规划网络实施项目（如果随其一起部署）。
ms.openlocfilehash: d4c14d97cff2952f5f7052a8aa2940f05d644737
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023721"
---
# <a name="azure-expressroute-for-office-365"></a>适用于 Office 365 的 Azure ExpressRoute

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

了解如何将 Azure ExpressRoute 与 Office 365 一同使用，以及如何规划部署 Azure ExpressRoute 以用于 Office 365 时所需的网络实施项目。 在 Azure 中运行的基础结构和平台服务通常会从解决网络体系结构和性能注意事项中获益。 在这些情况下，我们建议使用 ExpressRoute for Azure。 Office 365 和 Dynamics 365 等软件即服务产品已构建为可通过 Internet 安全可靠地访问。 可以在评估 [Office 365](assessing-network-connectivity.md)网络连接一文阅读有关 Internet 性能和安全性以及何时考虑使用适用于 Office 365 的 Azure ExpressRoute。

> [!NOTE]
> Microsoft Defender for Endpoint 在 Azure Express 路由中不受支持。

> [!NOTE]
> 需要 Microsoft 授权才能使用适用于 Office 365 的 ExpressRoute。 当客户的法规要求需要直接连接时，Microsoft 会审查每个客户请求并授权 ExpressRoute for Office 365 使用。 如果你有此类要求，请联系你的 Microsoft 客户代表开始 Microsoft 审查。 尝试为 Office 365 创建路由筛选器的未经授权的订阅将收到 [一条错误消息](https://support.microsoft.com/kb/3181709)。

现在，您可以为选定的 Office 365 网络流量向 Office 365 添加直接网络连接。 Azure ExpressRoute 提供直接连接、可预测的性能，并附带 99.95% 的 Microsoft 网络组件的运行时间 SLA。 对于 Azure ExpressRoute 不支持的服务，你仍然需要 Internet 连接。

## <a name="planning-azure-expressroute-for-office-365"></a>规划 Office 365 的 Azure ExpressRoute

除了 Internet 连接之外，您还可以选择通过直接连接路由 Office 365 网络流量的子集，该直接连接为 Microsoft 网络组件提供可预测性和 99.95% 正常运行时间 SLA。 Azure ExpressRoute 为您提供到 Office 365 和其他 Microsoft 云服务的专用网络连接。

无论你是否有现有的 MPLS WAN，ExpressRoute 都可以通过以下三种方式之一添加到网络体系结构中;通过支持的云交换共同位置提供程序、以太网点到点连接提供程序，或者通过 MPLS 连接提供程序。 查看 [哪些提供程序在你的区域可用](/azure/expressroute/expressroute-locations)。 直接 ExpressRoute 连接将启用与下面包含哪些 [Office 365](azure-expressroute.md#BKMK_WhatDoIGet) 服务？中概述的应用程序的连接。 所有其他应用程序和服务的网络通信将继续遍历 Internet。

请考虑以下高级网络图，该图显示了通过 Internet 连接到 Microsoft 数据中心以访问所有 Microsoft 应用程序（如 Office 365、Windows 更新和 TechNet）的典型 Office 365 客户。 无论客户是从本地网络还是从独立的 Internet 连接进行连接，他们都会使用类似的网络路径。

![Office 365 网络连接](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

现在查看更新后的图表，其中描述了同时使用 Internet 和 ExpressRoute 连接到 Office 365 的 Office 365 客户。 请注意，某些连接（如公共 DNS 和内容传递网络节点）仍然需要公共 Internet 连接。 另请注意，不在 ExpressRoute 连接建筑物中的客户用户正在通过 Internet 进行连接。

![与 ExpressRoute 的 Office 365 连接](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

是否仍需要更多信息？ 了解如何使用[适用于 Office 365 的 Azure ExpressRoute](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)管理网络流量，以及如何为 Office [365 配置 Azure ExpressRoute。](/azure/expressroute/expressroute-faqs) 我们还在 Channel 9 上记录了一个 10 部分 [Azure ExpressRoute for Office 365 培训](https://channel9.msdn.com/series/aer) 系列，以帮助更详尽地解释概念。

## <a name="what-office-365-services-are-included"></a>包含哪些 Office 365 服务？
<a name="BKMK_WhatDoIGet"> </a>

下表列出了通过 ExpressRoute 支持的 Office 365 服务。 请查看 [Office 365](./urls-and-ip-address-ranges.md) 终结点文章，了解这些应用程序的哪些网络请求需要 Internet 连接。

|**包含的应用程序**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype for Business Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive for Business<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|门户和共享<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> 其中每个应用程序都有不受 ExpressRoute 支持的 Internet 连接要求，有关详细信息，请参阅 [Office 365](./urls-and-ip-address-ranges.md) 终结点文章。

ExpressRoute for Office 365 中未包含的服务包括 Microsoft 365 企业应用版客户端下载、本地标识提供商登录和由中国世纪通) 服务运营的 Office 365 (。

## <a name="implementing-expressroute-for-office-365"></a>实现适用于 Office 365 的 ExpressRoute

实现 ExpressRoute 需要网络和应用程序所有者的参与，并且需要仔细规划以确定新的网络路由体系结构[](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)、带宽要求、实现安全性的地方、高可用性等。 若要实现 ExpressRoute，你需要：

1. 完全了解在 Office 365 连接规划中 ExpressRoute 满足需求。 了解哪些应用程序将使用 Internet 或 ExpressRoute，并针对 Office 365 流量使用 Internet 和 ExpressRoute，全面规划网络容量、安全性和高可用性需求。

2. 确定 Internet 和 ExpressRoute 流量<sup>1</sup>的出口和对等位置。

3. 确定 Internet 和 ExpressRoute 连接所需的容量。

4. 制定实施安全和其他标准外围控件<sup>1 的计划</sup>。

5. 拥有有效的 Microsoft Azure 帐户以订阅 ExpressRoute。

6. 选择连接模型和批准的 [提供程序](/azure/expressroute/expressroute-locations)。 请记住，客户可以选择多个连接模型或合作伙伴，合作伙伴无需与现有的网络提供商相同。

7. 在将流量引导到 ExpressRoute 之前验证部署。

8. （可选 [）实施 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) 和评估区域扩展。

<sup>1</sup> 重要的性能注意事项。 此处的决策会显著影响延迟，延迟对于 Skype for Business 等应用程序至关重要。

有关其他参考，请使用我们的 [路由指南](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) 以及 [ExpressRoute 文档](/azure/expressroute/expressroute-introduction)。

若要购买适用于 Office 365 的 ExpressRoute，需要与一个或多个批准的[](/azure/expressroute/expressroute-locations)提供商合作，通过 ExpressRoute Premium 订阅预配所需数量和大小的电路。 无需从 Office 365 购买其他许可证。

以下是可以用于返回的简短链接：[https://aka.ms/expressrouteoffice365]()

准备好注册适用于 Office [365 的 ExpressRoute 了吗](https://aka.ms/ert)？

## <a name="related-topics"></a>相关主题

[评估 Office 365 网络连接](assessing-network-connectivity.md)

[管理 ExpressRoute for Office 365 连接](managing-expressroute-for-connectivity.md)

[使用 ExpressRoute for Office 365 路由](routing-with-expressroute.md)

[ExpressRoute for Office 365 网络计划](network-planning-with-expressroute.md)

[实现 ExpressRoute for Office 365](implementing-expressroute.md)

[在 ExpressRoute for Office 365 方案中使用 BGP 社区](bgp-communities-in-expressroute.md)

[Skype for Business Online 中的媒体质量和网络连接性能](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[使用基线和性能历史记录优化 Office 365 性能](performance-tuning-using-baselines-and-history.md)

[Office 365 性能疑难解答计划](performance-troubleshooting-plan.md)

[Office 365 URL 和 IP 地址范围](urls-and-ip-address-ranges.md)

[Office 365 网络和性能优化](network-planning-and-performance.md)

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版概述](microsoft-365-overview.md)
