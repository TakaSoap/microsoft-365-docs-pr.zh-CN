---
title: Microsoft 365 网络路线图
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 实现 Microsoft 365 网络路线图。
ms.openlocfilehash: 2962adf7bdca35d06672696471e0932fd1a7b09c
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787747"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Microsoft 365 网络路线图

Microsoft 365 企业版包括协作和生产力云服务、Microsoft Intune 以及 Microsoft Azure 的许多标识和安全服务。 所有这些基于云的服务都依赖于来自客户端设备通过 Internet 或专用电路的连接的安全性、性能和可靠性。 为了托管这些服务并将其提供给世界各地的客户，Microsoft 设计了一个强调性能和集成的网络基础架构。 

Microsoft 365 载入的一个关键部分是确保网络和 Internet 连接已设置为优化访问。 将本地网络配置为访问全局分布式软件即服务 (SaaS) 云不同于针对到内部部署数据中心的流量和中央 Internet 连接优化的传统网络。 

使用以下文章来理解它们之间的关键区别，并修改你的边缘设备、客户端计算机和内部网络，以为本地用户获得最佳性能。

## <a name="plan"></a>套餐

在网络实施的规划阶段：

- [了解 Microsoft 365 网络的工作原理](microsoft-365-networking-overview.md)
- [评估当前的网络连接](assessing-network-connectivity.md)
- [确定 ExpressRoute 是否适合你的组织](network-planning-with-expressroute.md)
- [规划网络设备](plan-for-network-devices.md)
- [设置网络以用于迁移](network-and-migration-planning.md)

## <a name="deploy"></a>部署

在网络实施的部署阶段：

- [确保企业网络针对 Microsoft 365 连接进行了优化](set-up-network-for-microsoft-365.md)
- [为组织添加 DNS 域](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [优化与 Microsoft 365 终结点的连接](microsoft-365-ip-web-service.md)
- [优化远程工作者的连接](microsoft-365-vpn-split-tunnel.md)
- 如果需要， [请配置 ExpressRoute](azure-expressroute.md)

## <a name="manage"></a>管理

在网络实现的管理阶段：

- [确保网络设备使用的是最新的 Office 365 终结点](microsoft-365-endpoints.md)
- [监视和调整网络性能](network-planning-and-performance.md)
- [监视 ExpressRoute 连接](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>网络设备供应商

如果你是网络设备供应商，请加入 [Microsoft 365 网络合作伙伴计划](microsoft-365-networking-partner-program.md)。 注册该计划以将 Microsoft 365 网络连接原则构建到产品和解决方案中。 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Contoso 如何为 Microsoft 365 建立网络

了解 Contoso Corporation（有代表性的虚构跨国企业）如何针对 Microsoft 365 云服务[优化自己的网络设备和 Internet 连接](contoso-networking.md)。

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>后续步骤

使用 [Microsoft 365 网络连接概述开始网络规划](microsoft-365-networking-overview.md)。
