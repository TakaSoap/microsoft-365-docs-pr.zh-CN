---
title: 为用户设置Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 查找指向文章的链接，其中的信息可帮助你设置Microsoft 365，包括网络连接概述和终结点列表。
ms.openlocfilehash: c21a7a09e43957c806bca9dd64d425fcef2415fc
ms.sourcegitcommit: 59b1b0abfde30a8f2d8210b696aac3dc9183544e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/18/2021
ms.locfileid: "61566623"
---
# <a name="set-up-your-network-for-microsoft-365"></a>为用户设置Microsoft 365

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

载入的一Microsoft 365一部分是为了确保网络和 Internet 连接已设置为优化访问。 将本地网络配置为访问全局分布式软件即服务 (SaaS) 云不同于针对到本地数据中心的流量和中央 Internet 连接优化的传统网络。 

使用以下文章来理解它们之间的关键区别，并修改你的边缘设备、客户端计算机和内部网络，以为本地用户获得最佳性能。

## <a name="how-microsoft-365-networking-works"></a>网络Microsoft 365的工作原理

请参阅以下文章，大致了解Microsoft 365：

- [Microsoft 365 网络连接概述](microsoft-365-networking-overview.md)
- [Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)
- [评估 Microsoft 365 网络连接](assessing-network-connectivity.md)

有关增强性能的建议，请参阅 Network [planning and performance tuning for Microsoft 365](network-planning-and-performance.md)。

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a>作为Microsoft 365供应商支持网络

如果你是网络设备供应商，请加入 [Office 365 网络合作伙伴计划](microsoft-365-networking-partner-program.md)。加入该计划即可在你的产品和解决方案中构建 Office 365 网络连接原则。 

## <a name="office-365-endpoints"></a>Office 365 端点

端点是 Internet 上 Office 365 流量的目的 IP 地址、DNS 域名和 URL 的集合。 

若要优化基于 Office 365 云的服务的性能，需要使用你的客户端浏览器和边缘网络中的设备对某些端点进行特殊处理。这些设备包括防火墙设备、SSL 中断与检查设备、数据包检查设备以及数据丢失防护系统。

有关详细信息，请参阅[管理 Office 365 端点](managing-office-365-endpoints.md)。

目前有五个不同的 Office 365 云。此表将转到每个端点的列表。

| 终结点 | 说明 |
|:-------|:-----|
| [全球终结点](urls-and-ip-address-ranges.md) | 针对全球 Office 365 订阅的端点，其中包括美国政府社区云 (GCC) 订阅。 |
| [美国政府 DoD 端点](microsoft-365-u-s-government-dod-endpoints.md) | 针对美国国防部 (DoD) 订阅的端点。 |
| [美国政府 GCC 高端点](microsoft-365-u-s-government-gcc-high-endpoints.md) | 针对美国政府社区云高（GCC 高）订阅的端点。 |
| [由世纪互联运营的 Office 365 端点](urls-and-ip-address-ranges-21vianet.md) | 由世纪互联运营的 Office 365 的端点，旨在满足中国境内对 Office 365 的需求。 |
|||

若要自动获取 Office 365 云的最新端点列表，请参阅 [Office 365 IP 地址和 URL Web 服务](microsoft-365-ip-web-service.md)。

有关额外的端点，请参阅以下文章：

- [Web 服务中未包含的其他端点](additional-office365-ip-addresses-and-urls.md)
- [Office 2016 for Mac 中的网络请求](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a>有关网络Microsoft 365主题

请参阅以下文章，了解Microsoft 365主题：

- [内容分发网络](content-delivery-networks.md)
- [Office 365 服务中的 IPv6 支持](ipv6-support.md)
- [Office 365 随附的 NAT 支持](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a>适用于 Microsoft 365 的 ExpressRoute

请参阅以下文章，了解适用于 Office 365 的 ExpressRoute 的流量使用：

- [适用于 Office 365 的 Azure ExpressRoute](azure-expressroute.md)
- [实现 ExpressRoute for Office 365](implementing-expressroute.md)
- [ExpressRoute for Office 365 网络计划](network-planning-with-expressroute.md)
- [通过适用于 Office 365 的 ExpressRoute 进行路由](routing-with-expressroute.md)
