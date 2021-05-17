---
title: 为用户设置Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
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
description: 查找指向文章的链接，这些文章包含可帮助您为 Microsoft 365设置网络的信息，包括网络连接概述和终结点列表。
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687644"
---
# <a name="set-up-your-network-for-microsoft-365"></a><span data-ttu-id="2672a-103">为用户设置Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2672a-103">Set up your network for Microsoft 365</span></span>

<span data-ttu-id="2672a-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="2672a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2672a-105">载入的一Microsoft 365一部分是为了确保网络和 Internet 连接已设置为优化访问。</span><span class="sxs-lookup"><span data-stu-id="2672a-105">An important part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="2672a-106">将本地网络配置为访问全局分布式软件即服务 (SaaS) 云与针对到内部部署数据中心的流量和中央 Internet 连接进行了优化的传统网络不同。</span><span class="sxs-lookup"><span data-stu-id="2672a-106">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="2672a-107">使用以下文章来理解它们之间的关键区别，并修改你的边缘设备、客户端计算机和内部网络，以为本地用户获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="2672a-107">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="how-microsoft-365-networking-works"></a><span data-ttu-id="2672a-108">网络Microsoft 365工作原理</span><span class="sxs-lookup"><span data-stu-id="2672a-108">How Microsoft 365 networking works</span></span>

<span data-ttu-id="2672a-109">请参阅以下文章，大致了解Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="2672a-109">See these articles for an overview of connectivity for Microsoft 365:</span></span>

- [<span data-ttu-id="2672a-110">Microsoft 365 网络连接概述</span><span class="sxs-lookup"><span data-stu-id="2672a-110">Microsoft 365 networking connectivity overview</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="2672a-111">Microsoft 365 网络连接原则</span><span class="sxs-lookup"><span data-stu-id="2672a-111">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)
- [<span data-ttu-id="2672a-112">评估 Microsoft 365 网络连接</span><span class="sxs-lookup"><span data-stu-id="2672a-112">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

<span data-ttu-id="2672a-113">有关增强性能的建议，请参阅 Network [planning and performance tuning for Microsoft 365](network-planning-and-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="2672a-113">For advice on enhancing performance, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a><span data-ttu-id="2672a-114">作为Microsoft 365供应商支持网络</span><span class="sxs-lookup"><span data-stu-id="2672a-114">Support Microsoft 365 networking as a network equipment vendor</span></span>

<span data-ttu-id="2672a-p102">如果你是网络设备供应商，请加入 [Office 365 网络合作伙伴计划](microsoft-365-networking-partner-program.md)。加入该计划即可在你的产品和解决方案中构建 Office 365 网络连接原则。</span><span class="sxs-lookup"><span data-stu-id="2672a-p102">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md). Enroll in the program to build Office 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="office-365-endpoints"></a><span data-ttu-id="2672a-117">Office 365 端点</span><span class="sxs-lookup"><span data-stu-id="2672a-117">Office 365 endpoints</span></span>

<span data-ttu-id="2672a-118">端点是 Internet 上 Office 365 流量的目的 IP 地址、DNS 域名和 URL 的集合。</span><span class="sxs-lookup"><span data-stu-id="2672a-118">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Office 365 traffic on the Internet.</span></span> 

<span data-ttu-id="2672a-p103">若要优化基于 Office 365 云的服务的性能，需要使用你的客户端浏览器和边缘网络中的设备对某些端点进行特殊处理。这些设备包括防火墙设备、SSL 中断与检查设备、数据包检查设备以及数据丢失防护系统。</span><span class="sxs-lookup"><span data-stu-id="2672a-p103">To optimize performance to Office 365 cloud-based services, some endpoints need special handling by your client browsers and the devices in your edge network. These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="2672a-121">有关详细信息，请参阅[管理 Office 365 端点](managing-office-365-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="2672a-121">See [Managing Office 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="2672a-p104">目前有五个不同的 Office 365 云。此表将转到每个端点的列表。</span><span class="sxs-lookup"><span data-stu-id="2672a-p104">There are currently five different Office 365 clouds. This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="2672a-124">终结点</span><span class="sxs-lookup"><span data-stu-id="2672a-124">Endpoints</span></span> | <span data-ttu-id="2672a-125">说明</span><span class="sxs-lookup"><span data-stu-id="2672a-125">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="2672a-126">全球终结点</span><span class="sxs-lookup"><span data-stu-id="2672a-126">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="2672a-127">针对全球 Office 365 订阅的端点，其中包括美国政府社区云 (GCC) 订阅。</span><span class="sxs-lookup"><span data-stu-id="2672a-127">The endpoints for worldwide Office 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="2672a-128">美国政府 DoD 端点</span><span class="sxs-lookup"><span data-stu-id="2672a-128">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="2672a-129">针对美国国防部 (DoD) 订阅的端点。</span><span class="sxs-lookup"><span data-stu-id="2672a-129">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="2672a-130">美国政府 GCC 高端点</span><span class="sxs-lookup"><span data-stu-id="2672a-130">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="2672a-131">针对美国政府社区云高（GCC 高）订阅的端点。</span><span class="sxs-lookup"><span data-stu-id="2672a-131">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="2672a-132">由世纪互联运营的 Office 365 端点</span><span class="sxs-lookup"><span data-stu-id="2672a-132">Office 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="2672a-133">由世纪互联运营的 Office 365 的端点，旨在满足中国境内对 Office 365 的需求。</span><span class="sxs-lookup"><span data-stu-id="2672a-133">The endpoints for Office 365 operated by 21Vianet, which is designed to meet the needs for Office 365 in China.</span></span> |
| [<span data-ttu-id="2672a-134">Office 365 Germany 端点</span><span class="sxs-lookup"><span data-stu-id="2672a-134">Office 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="2672a-135">为德国、欧盟 (EU) 和欧洲自由贸易协会 (EFTA) 中监管最严格的客户在欧洲建立的独立云的端点。</span><span class="sxs-lookup"><span data-stu-id="2672a-135">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="2672a-136">若要自动获取 Office 365 云的最新端点列表，请参阅 [Office 365 IP 地址和 URL Web 服务](microsoft-365-ip-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="2672a-136">To automate getting the latest list of endpoints for your Office 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="2672a-137">有关额外的端点，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="2672a-137">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="2672a-138">Web 服务中未包含的其他端点</span><span class="sxs-lookup"><span data-stu-id="2672a-138">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="2672a-139">Office 2016 for Mac 中的网络请求</span><span class="sxs-lookup"><span data-stu-id="2672a-139">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a><span data-ttu-id="2672a-140">有关网络Microsoft 365主题</span><span class="sxs-lookup"><span data-stu-id="2672a-140">Additional topics for Microsoft 365 networking</span></span>

<span data-ttu-id="2672a-141">请参阅以下文章，了解Microsoft 365主题：</span><span class="sxs-lookup"><span data-stu-id="2672a-141">See these articles for specialized topics in Microsoft 365 networking:</span></span>

- [<span data-ttu-id="2672a-142">内容分发网络</span><span class="sxs-lookup"><span data-stu-id="2672a-142">Content delivery networks</span></span>](content-delivery-networks.md)
- [<span data-ttu-id="2672a-143">Office 365 服务中的 IPv6 支持</span><span class="sxs-lookup"><span data-stu-id="2672a-143">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
- [<span data-ttu-id="2672a-144">Office 365 随附的 NAT 支持</span><span class="sxs-lookup"><span data-stu-id="2672a-144">NAT support with Office 365</span></span>](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a><span data-ttu-id="2672a-145">适用于 Microsoft 365 的 ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="2672a-145">ExpressRoute for Microsoft 365</span></span>

<span data-ttu-id="2672a-146">请参阅以下文章，了解适用于 Office 365 的 ExpressRoute 的流量使用：</span><span class="sxs-lookup"><span data-stu-id="2672a-146">See these articles for information on the use of ExpressRoute for Office 365 traffic:</span></span>

- [<span data-ttu-id="2672a-147">适用于 Office 365 的 Azure ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="2672a-147">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
- [<span data-ttu-id="2672a-148">实现 ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="2672a-148">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)
- [<span data-ttu-id="2672a-149">ExpressRoute for Office 365 网络计划</span><span class="sxs-lookup"><span data-stu-id="2672a-149">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="2672a-150">通过适用于 Office 365 的 ExpressRoute 进行路由</span><span class="sxs-lookup"><span data-stu-id="2672a-150">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
