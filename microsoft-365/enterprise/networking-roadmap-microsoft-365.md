---
title: Microsoft 365
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
description: 实现网络Microsoft 365路线图。
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923548"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="8f6ce-103">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f6ce-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="8f6ce-104">Microsoft 365包括协作和生产力云服务、Microsoft Intune以及许多企业标识和安全服务Microsoft Azure。</span><span class="sxs-lookup"><span data-stu-id="8f6ce-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="8f6ce-105">所有这些基于云的服务都依赖于来自客户端设备通过 Internet 或专用电路的连接的安全性、性能和可靠性。</span><span class="sxs-lookup"><span data-stu-id="8f6ce-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="8f6ce-106">为了托管这些服务并将其提供给世界各地的客户，Microsoft 设计了一个强调性能和集成的网络基础架构。</span><span class="sxs-lookup"><span data-stu-id="8f6ce-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="8f6ce-107">载入时Microsoft 365一个关键部分是确保网络和 Internet 连接已设置为优化访问。</span><span class="sxs-lookup"><span data-stu-id="8f6ce-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="8f6ce-108">将本地网络配置为访问全局分布式软件即服务 (SaaS) 云与针对到内部部署数据中心的流量和中央 Internet 连接进行了优化的传统网络不同。</span><span class="sxs-lookup"><span data-stu-id="8f6ce-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="8f6ce-109">使用以下文章来理解它们之间的关键区别，并修改你的边缘设备、客户端计算机和内部网络，以为本地用户获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="8f6ce-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="8f6ce-110">计划</span><span class="sxs-lookup"><span data-stu-id="8f6ce-110">Plan</span></span>

<span data-ttu-id="8f6ce-111">在网络实施的规划阶段：</span><span class="sxs-lookup"><span data-stu-id="8f6ce-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="8f6ce-112">了解Microsoft 365的工作原理</span><span class="sxs-lookup"><span data-stu-id="8f6ce-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="8f6ce-113">评估当前的网络连接</span><span class="sxs-lookup"><span data-stu-id="8f6ce-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="8f6ce-114">确定 ExpressRoute 是否适合你的组织</span><span class="sxs-lookup"><span data-stu-id="8f6ce-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="8f6ce-115">规划网络设备</span><span class="sxs-lookup"><span data-stu-id="8f6ce-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="8f6ce-116">设置网络以用于迁移</span><span class="sxs-lookup"><span data-stu-id="8f6ce-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="8f6ce-117">部署</span><span class="sxs-lookup"><span data-stu-id="8f6ce-117">Deploy</span></span>

<span data-ttu-id="8f6ce-118">在网络实施的部署阶段：</span><span class="sxs-lookup"><span data-stu-id="8f6ce-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="8f6ce-119">确保企业网络已针对连接Microsoft 365优化</span><span class="sxs-lookup"><span data-stu-id="8f6ce-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="8f6ce-120">为组织添加 DNS 域</span><span class="sxs-lookup"><span data-stu-id="8f6ce-120">Add the DNS domains for your organization</span></span>](../admin/setup/add-domain.md)
- [<span data-ttu-id="8f6ce-121">优化与终结点Microsoft 365连接</span><span class="sxs-lookup"><span data-stu-id="8f6ce-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="8f6ce-122">优化远程工作者的连接</span><span class="sxs-lookup"><span data-stu-id="8f6ce-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="8f6ce-123">如果需要， [请配置 ExpressRoute](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="8f6ce-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="8f6ce-124">管理</span><span class="sxs-lookup"><span data-stu-id="8f6ce-124">Manage</span></span>

<span data-ttu-id="8f6ce-125">在网络实现的管理阶段：</span><span class="sxs-lookup"><span data-stu-id="8f6ce-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="8f6ce-126">确保你的网络设备使用的是最新的 Office 365 终结点</span><span class="sxs-lookup"><span data-stu-id="8f6ce-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="8f6ce-127">监视和调整网络性能</span><span class="sxs-lookup"><span data-stu-id="8f6ce-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="8f6ce-128">监视 ExpressRoute 连接</span><span class="sxs-lookup"><span data-stu-id="8f6ce-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="8f6ce-129">网络设备供应商</span><span class="sxs-lookup"><span data-stu-id="8f6ce-129">Network equipment vendors</span></span>

<span data-ttu-id="8f6ce-130">如果您是网络设备供应商，请[加入Microsoft 365 网络合作伙伴计划。](microsoft-365-networking-partner-program.md)</span><span class="sxs-lookup"><span data-stu-id="8f6ce-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="8f6ce-131">注册该计划，在产品和解决方案中构建 Microsoft 365 网络连接原则。</span><span class="sxs-lookup"><span data-stu-id="8f6ce-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="8f6ce-132">Contoso 如何建立Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f6ce-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="8f6ce-133">了解 Contoso Corporation（有代表性的虚构跨国企业）如何针对 Microsoft 365 云服务[优化自己的网络设备和 Internet 连接](contoso-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="8f6ce-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="8f6ce-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8f6ce-135">Next step</span></span>

<span data-ttu-id="8f6ce-136">使用网络连接概述 Microsoft 365[网络规划](microsoft-365-networking-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8f6ce-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>