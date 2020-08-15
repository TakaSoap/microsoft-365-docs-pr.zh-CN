---
title: Microsoft 365 的网络路线图
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
description: 实施 Microsoft 365 网络的路线图。
ms.openlocfilehash: 93d0f253e098815139b431a826f7e5e7a0410b37
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687880"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="1dbe3-103">Microsoft 365 的网络路线图</span><span class="sxs-lookup"><span data-stu-id="1dbe3-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="1dbe3-104">适用于企业的 microsoft 365 包括协作和生产率云服务、Microsoft Intune 以及 Microsoft Azure 的许多标识和安全服务。</span><span class="sxs-lookup"><span data-stu-id="1dbe3-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="1dbe3-105">所有这些基于云的服务都依赖于来自客户端设备通过 Internet 或专用电路的连接的安全性、性能和可靠性。</span><span class="sxs-lookup"><span data-stu-id="1dbe3-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="1dbe3-106">为了托管这些服务并将其提供给世界各地的客户，Microsoft 设计了一个强调性能和集成的网络基础架构。</span><span class="sxs-lookup"><span data-stu-id="1dbe3-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="1dbe3-107">你的 Microsoft 365 的重要部分是确保设置了你的网络和 Internet 连接以实现优化的访问。</span><span class="sxs-lookup"><span data-stu-id="1dbe3-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="1dbe3-108">配置您的本地网络以访问全局分布式软件即服务 (SaaS) 云不同于针对本地数据中心和中心 Internet 连接进行了优化的传统网络。</span><span class="sxs-lookup"><span data-stu-id="1dbe3-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="1dbe3-109">使用以下文章来理解它们之间的关键区别，并修改你的边缘设备、客户端计算机和内部网络，以为本地用户获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="1dbe3-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="1dbe3-110">套餐</span><span class="sxs-lookup"><span data-stu-id="1dbe3-110">Plan</span></span>

<span data-ttu-id="1dbe3-111">在网络实施的规划阶段：</span><span class="sxs-lookup"><span data-stu-id="1dbe3-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="1dbe3-112">了解 Microsoft 365 网络的工作原理</span><span class="sxs-lookup"><span data-stu-id="1dbe3-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="1dbe3-113">评估当前的网络连接</span><span class="sxs-lookup"><span data-stu-id="1dbe3-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="1dbe3-114">确定 ExpressRoute 是否适合你的组织</span><span class="sxs-lookup"><span data-stu-id="1dbe3-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="1dbe3-115">规划网络设备</span><span class="sxs-lookup"><span data-stu-id="1dbe3-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="1dbe3-116">获取用于迁移的网络设置</span><span class="sxs-lookup"><span data-stu-id="1dbe3-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="1dbe3-117">部署</span><span class="sxs-lookup"><span data-stu-id="1dbe3-117">Deploy</span></span>

<span data-ttu-id="1dbe3-118">在网络实施的部署阶段：</span><span class="sxs-lookup"><span data-stu-id="1dbe3-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="1dbe3-119">确保企业网络已针对 Microsoft 365 连接进行了优化</span><span class="sxs-lookup"><span data-stu-id="1dbe3-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="1dbe3-120">为您的组织添加 DNS 域</span><span class="sxs-lookup"><span data-stu-id="1dbe3-120">Add the DNS domains for your organization</span></span>](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [<span data-ttu-id="1dbe3-121">优化与 Microsoft 365 终结点的连接</span><span class="sxs-lookup"><span data-stu-id="1dbe3-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="1dbe3-122">优化远程工作人员的连接</span><span class="sxs-lookup"><span data-stu-id="1dbe3-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="1dbe3-123">如果需要，请 [配置 ExpressRoute](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="1dbe3-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="1dbe3-124">管理</span><span class="sxs-lookup"><span data-stu-id="1dbe3-124">Manage</span></span>

<span data-ttu-id="1dbe3-125">在网络实施的管理阶段：</span><span class="sxs-lookup"><span data-stu-id="1dbe3-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="1dbe3-126">确保你的网络设备使用最新的 Office 365 终结点</span><span class="sxs-lookup"><span data-stu-id="1dbe3-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="1dbe3-127">监视和调整网络性能</span><span class="sxs-lookup"><span data-stu-id="1dbe3-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="1dbe3-128">监视您的 ExpressRoute 连接</span><span class="sxs-lookup"><span data-stu-id="1dbe3-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="1dbe3-129">网络设备供应商</span><span class="sxs-lookup"><span data-stu-id="1dbe3-129">Network equipment vendors</span></span>

<span data-ttu-id="1dbe3-130">如果你是网络设备供应商，请加入 [Microsoft 365 网络合作伙伴计划](microsoft-365-networking-partner-program.md)。</span><span class="sxs-lookup"><span data-stu-id="1dbe3-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="1dbe3-131">注册程序以将 Microsoft 365 网络连接原则构建到你的产品和解决方案中。</span><span class="sxs-lookup"><span data-stu-id="1dbe3-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="1dbe3-132">Contoso 如何为 Microsoft 365 进行网络连接</span><span class="sxs-lookup"><span data-stu-id="1dbe3-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="1dbe3-133">了解 Contoso Corporation（有代表性的虚构跨国企业）如何针对 Microsoft 365 云服务[优化自己的网络设备和 Internet 连接](contoso-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="1dbe3-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="1dbe3-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1dbe3-135">Next step</span></span>

<span data-ttu-id="1dbe3-136">使用 [Microsoft 365 网络连接概述](microsoft-365-networking-overview.md)启动网络规划。</span><span class="sxs-lookup"><span data-stu-id="1dbe3-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>
