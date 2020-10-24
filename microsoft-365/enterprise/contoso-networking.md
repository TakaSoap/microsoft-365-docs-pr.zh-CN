---
title: Contoso Corporation 网络
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 网络基础结构，以及公司如何使用其 SD WAN 技术实现最佳网络性能到 Microsoft 365 for enterprise 云服务。
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754010"
---
# <a name="networking-for-the-contoso-corporation"></a>Contoso Corporation 网络

为了采用云包容的基础结构，Contoso 为云服务的网络通信的传播方式设计了一个根本性的转变。除了将网络连接和通信集中在 office 层次结构的下一级的内部中心辐射型模型中，它们还将用户位置映射到 internet 上最近的 Microsoft 365 网络位置的本地 internet 出口和本地连接。

## <a name="networking-infrastructure"></a>网络基础结构

以下是链接到全球各地的 Contoso 办事处的网络元素：

- 多协议标签交换 (MPLS) WAN 网络

  MPLS WAN 网络将巴黎总部和区域办事处连接到分支和集线器配置中的卫星办公室。网络使用户能够访问在巴黎总部中组成业务线应用程序的本地服务器。它还会将任何常规 internet 流量路由到巴黎办事处，网络安全设备将擦除请求。在每个办公室中，路由器会将流量传递给有线主机或子网上的无线访问点，这将使用专用 IP 地址空间。

- Microsoft 365 流量的本地直接 internet 访问

  每个 office 都有一个软件定义的 WAN (SD WAN) 设备，该设备具有一个或多个本地 internet ISP 网络电路，通过代理服务器拥有自己的 internet 连接。这通常作为指向本地 ISP 的 WAN 链接实现，同时也提供公用 IP 地址和本地 DNS 服务器。

- Internet 网站

  Contoso 拥有 contoso \. com 公共域名称。Contoso 公共网站订购产品是在巴黎校园中连接到 internet 的数据中心中的一组服务器。Contoso 在 internet 上使用 a/24 公用 IP 地址范围。

图1显示 Contoso 网络基础结构及其与 internet 的连接。

![Contoso 网络](../media/contoso-networking/contoso-networking-fig1.png)
 
**图1： Contoso 网络**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>使用 SD-WAN 与 Microsoft 建立最佳网络连接

Contoso 遵循了 [Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)：

- 标识并区分 Microsoft 365 网络流量
- 实现本地连接出口
- 避免网络发卡
- 绕过重复的网络安全设备

Microsoft 365 的网络流量有三种类别： " *优化*"、" *允许*" 和 " *默认*"。 优化和允许流量是在终结点进行加密和保护的受信任网络流量，它是面向 Microsoft 365 网络的。

Contoso 决定：

- 使用直接 internet 出口以优化和允许类别流量，并将所有默认类别流量转发到基于巴黎的中央 internet 连接。

- 在每个办公室上部署 SD WAN 设备，以一种简单的方式来遵循这些原则，并实现 Microsoft 365 基于云的服务的最佳网络性能。

  SD-WAN 设备具有一个用于本地办事处网络的 LAN 端口和多个 WAN 端口。 一个 WAN 端口连接到其 MPLS 网络。 另一个连接到本地 ISP 电路。 SD-WAN 设备通过 ISP 链接路由“优化”和“允许”类别的网络流量。

## <a name="the-contoso-line-of-business-app-infrastructure"></a>Contoso 业务线应用程序基础结构

Contoso 为以下各项构建业务线应用程序和服务器 intranet 基础结构：

- 附属办事处使用本地缓存服务器来存储经常访问的文档和内部网站。
- 地区中心对地区办事处和附属办事处使用地区应用程序服务器。这些服务器与巴黎总部的服务器同步。
- 巴黎校园数据中心包含为整个组织提供服务的集中式应用程序服务器。

图2显示了跨 Contoso intranet 访问服务器时使用的网络流量容量百分比。

![适用于内部应用程序的 Contoso 基础结构](../media/contoso-networking/contoso-networking-fig2.png)
 
**图2：适用于内部应用程序的 Contoso 基础结构**

对于附属或区域中心办公室，可以通过卫星和区域中心办公室服务器来处理员工所需的60% 的资源。 额外的40% 的资源请求必须通过 WAN 链接进入巴黎校园。

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>适用于企业的 Microsoft 365 的网络分析和准备工作

Contoso 用户成功采用了适用于企业服务的 Microsoft 365，这取决于与 internet 的高可用性和高性能连接，或直接连接到 Microsoft 云服务。 Contoso 采取以下步骤来规划和实施针对企业云服务的 Microsoft 365 的优化连接：

1. 创建公司 WAN 网络图以协助规划

   为了启动其网络规划，Contoso 创建了一个显示其办公室位置、现有网络连接、现有网络外围设备以及在网络上进行管理的服务类别的图表。 他们在规划和实现网络连接的每个后续步骤中使用此图。

2. 为适用于企业网络连接的 Microsoft 365 创建计划

   Contoso 使用 [Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md) 和示例参考网络体系结构，将 SD WAN 标识为 Microsoft 365 连接的首选拓扑。

3. 在每个办公室分析 internet 连接利用率和 MPLS-WAN 带宽，并根据需要增加带宽

   分析了每个 office 的当前使用情况，并增加了电路，以便预测的 Microsoft 365 基于云的流量将使用平均20% 的未使用容量。

4. 优化 Microsoft 网络服务的性能

   Contoso 确定了 Office 365、Intune 和 Azure 终结点集以及 internet 路径中配置的防火墙、安全设备和其他系统，以实现最佳性能。 Office 365 的终结点优化并允许类别流量配置为 SD-WAN 设备，以通过 ISP 电路进行路由。

5. 配置内部 DNS

   DNS 必须能正常运行，才能查找本地 Microsoft 365 流量。

6. 验证网络终结点和端口连接性

   Contoso 已运行 Microsoft 网络连接测试工具，以验证适用于企业云服务的 Microsoft 365 的连接。

7. 优化员工计算机以实现网络连接

   检查了单个计算机以确保安装了最新的操作系统更新，并且所有客户端上的终结点安全监视处于活动状态。

## <a name="next-step"></a>后续步骤

了解 Contoso 如何 [利用云中的本地 Active Directory 域服务](contoso-identity.md) 为员工和联合身份验证针对客户和业务合作伙伴。

## <a name="see-also"></a>另请参阅

[Microsoft 365 的网络路线图](networking-roadmap-microsoft-365.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)
