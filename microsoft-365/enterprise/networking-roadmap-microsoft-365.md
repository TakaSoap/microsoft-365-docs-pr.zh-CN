---
title: Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 03/03/2022
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 规划、实施和管理网络Microsoft 365路线图。
ms.openlocfilehash: cfefd668f91eb074259d056b3b573b9c0f636bb6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325189"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Microsoft 365

Microsoft 365包括协作和生产力云服务、Microsoft Intune以及许多企业标识和安全服务Microsoft Azure。 所有这些基于云的服务都依赖于来自客户端设备通过 Internet 或专用电路的连接的安全性、性能和可靠性。 为了托管这些服务并将其提供给世界各地的客户，Microsoft 设计了一个强调性能和集成的网络基础架构。

入门的一个关键Microsoft 365是确保网络和 Internet 连接已设置为优化访问。 将本地网络配置为访问全局分布式软件即服务 (SaaS) 云与针对到本地数据中心的流量和中央 Internet 连接进行了优化的传统网络不同。

使用以下文章来理解它们之间的关键区别，并修改你的边缘设备、客户端计算机和内部网络，以为本地用户获得最佳性能。

## <a name="plan"></a>计划

在网络实施的规划阶段：

- [了解Microsoft 365的工作原理](microsoft-365-networking-overview.md)
- [了解网络连接原则](microsoft-365-network-connectivity-principles.md)
- [评估当前的网络连接](assessing-network-connectivity.md)
- [确定 ExpressRoute 是否适合你的组织](network-planning-with-expressroute.md)
- [规划网络设备](plan-for-network-devices.md)
- [设置网络以用于迁移](network-and-migration-planning.md)

## <a name="deploy"></a>部署

在网络实施的部署阶段：

- [确保企业网络已针对连接Microsoft 365优化](set-up-network-for-microsoft-365.md)
- [为组织添加 DNS 域](../admin/setup/add-domain.md)
- [使用 VPN 拆分隧道优化远程工作者的连接](microsoft-365-vpn-split-tunnel.md)
- [配置CDN以提高网络性能](office-365-cdn-quickstart.md)
- [优化与 Microsoft 365 的连接](microsoft-365-ip-web-service.md)
- 如果需要， [请配置 ExpressRoute](azure-expressroute.md)

## <a name="manage"></a>管理

在网络实现的管理阶段：

- [使用 Microsoft 365 网络连接测试工具进行测试和优化](office-365-network-mac-perf-onboarding-tool.md)
- [确保你的网络设备使用的是最新的 Office 365 终结点](microsoft-365-endpoints.md)
- [监视和调整网络性能](network-planning-and-performance.md)
- [监视Microsoft 365连接](monitor-connectivity.md)

## <a name="network-equipment-vendors"></a>网络设备供应商

如果您是网络设备供应商，[请加入Microsoft 365 网络合作伙伴计划](microsoft-365-networking-partner-program.md)。 注册该计划，在产品和解决方案中构建 Microsoft 365 网络连接原则。

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Contoso 如何建立Microsoft 365

了解 Contoso Corporation（有代表性的虚构跨国企业）如何针对 Microsoft 365 云服务[优化自己的网络设备和 Internet 连接](contoso-networking.md)。

![Contoso Corporation。](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>后续步骤

使用网络连接概述Microsoft 365[网络规划](microsoft-365-networking-overview.md)。
