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
description: 了解如何将 Azure ExpressRoute 与 Office 365，并规划网络实施项目（如果你要使用它进行部署）。
ms.openlocfilehash: c43957435272e1a3b6f738d33a2dd12e81dfc013
ms.sourcegitcommit: aff2331f9a3f22591f8ace1a646809969d28c120
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52464413"
---
# <a name="azure-expressroute-for-office-365"></a><span data-ttu-id="5d661-103">适用于 Office 365 的 Azure ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="5d661-103">Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="5d661-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="5d661-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5d661-105">了解如何将 Azure ExpressRoute 与 Office 365 以及如何规划在部署 Azure ExpressRoute 以用于 Office 365 时所需的网络实现项目。</span><span class="sxs-lookup"><span data-stu-id="5d661-105">Learn how Azure ExpressRoute is used with Office 365 and how to plan the network implementation project that will be required if you are deploying Azure ExpressRoute for use with Office 365.</span></span> <span data-ttu-id="5d661-106">在 Azure 中运行的基础结构和平台服务通常会从解决网络体系结构和性能注意事项中获益。</span><span class="sxs-lookup"><span data-stu-id="5d661-106">Infrastructure and platform services running in Azure will often benefit by addressing network architecture and performance considerations.</span></span> <span data-ttu-id="5d661-107">在这些情况下，我们建议使用 ExpressRoute for Azure。</span><span class="sxs-lookup"><span data-stu-id="5d661-107">We recommend ExpressRoute for Azure in these cases.</span></span> <span data-ttu-id="5d661-108">软件即服务产品（如 Office 365 和 Dynamics 365）已构建为可通过 Internet 安全可靠地访问。</span><span class="sxs-lookup"><span data-stu-id="5d661-108">Software as a Service offerings like Office 365 and Dynamics 365 have been built to be accessed securely and reliably via the Internet.</span></span> <span data-ttu-id="5d661-109">有关 Internet 性能和安全性以及何时可以考虑使用 Azure ExpressRoute for Office 365请参阅文章[Assessing Office 365 network connectivity](assessing-network-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="5d661-109">You can read about Internet performance and security and when you might consider Azure ExpressRoute for Office 365 in the article [Assessing Office 365 network connectivity](assessing-network-connectivity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5d661-110">Microsoft Defender for Endpoint 不提供与 Azure ExpressRoute 的集成。</span><span class="sxs-lookup"><span data-stu-id="5d661-110">Microsoft Defender for Endpoint does not provide integration with Azure ExpressRoute.</span></span> <span data-ttu-id="5d661-111">虽然这不会阻止客户定义 ExpressRoute 规则，以便从专用网络连接到适用于 Endpoint 云服务的 Microsoft Defender，但由客户负责在服务或云基础结构不断发展时维护规则。</span><span class="sxs-lookup"><span data-stu-id="5d661-111">While this does not stop customers from defining ExpressRoute rules that enable connectivity from a private network to Microsoft Defender for Endpoint cloud services, it is up to the customer to maintain rules as the service or cloud infrastructure evolves.</span></span>

> [!NOTE]
> <span data-ttu-id="5d661-112">我们不建议使用 ExpressRoute for Microsoft 365因为它在大多数情况下不会为服务提供最佳连接模型。</span><span class="sxs-lookup"><span data-stu-id="5d661-112">We do not recommend ExpressRoute for Microsoft 365 because it does not provide the best connectivity model for the service in most circumstances.</span></span> <span data-ttu-id="5d661-113">因此，需要 Microsoft 授权才能使用此连接模型Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5d661-113">As such, Microsoft authorization is required to use this connectivity model for Microsoft 365.</span></span> <span data-ttu-id="5d661-114">我们查看每个客户请求，并授权 ExpressRoute for Microsoft 365仅在极少数情况下才有必要使用 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="5d661-114">We review every customer request and authorize ExpressRoute for Microsoft 365 only in the rare scenarios where it is necessary.</span></span> <span data-ttu-id="5d661-115">有关详细信息，请参阅[ExpressRoute for Microsoft 365](https://aka.ms/erguide)指南，并遵循生产力、网络和安全团队对文档的全面审阅，与 Microsoft 帐户团队合作以根据需要提交例外。</span><span class="sxs-lookup"><span data-stu-id="5d661-115">Please read the [ExpressRoute for Microsoft 365 guide](https://aka.ms/erguide) for more information and following a comprehensive review of the document with your productivity, network, and security teams, work with your Microsoft account team to submit an exception if needed.</span></span> <span data-ttu-id="5d661-116">尝试为用户创建路由筛选器Office 365订阅将收到[一条错误消息](https://support.microsoft.com/kb/3181709)。</span><span class="sxs-lookup"><span data-stu-id="5d661-116">Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>

## <a name="planning-azure-expressroute-for-office-365"></a><span data-ttu-id="5d661-117">规划 Azure ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="5d661-117">Planning Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="5d661-118">除了 Internet 连接之外，您还可以选择通过直接连接路由其 Office 365 网络流量的子集，该直接连接为 Microsoft 网络组件提供可预测性和 99.95% 正常运行时间 SLA。</span><span class="sxs-lookup"><span data-stu-id="5d661-118">In addition to internet connectivity, you may choose to route a subset of their Office 365 network traffic over a direct connection that offers predictability and a 99.95% uptime SLA for the Microsoft networking components.</span></span> <span data-ttu-id="5d661-119">Azure ExpressRoute 提供了此专用网络连接，Office 365 Microsoft 云服务。</span><span class="sxs-lookup"><span data-stu-id="5d661-119">Azure ExpressRoute provides you with this dedicated network connection to Office 365 and other Microsoft cloud services.</span></span>

<span data-ttu-id="5d661-120">无论你是否有现有的 MPLS WAN，ExpressRoute 都可以通过以下三种方式之一添加到网络体系结构中;通过支持的云交换共同位置提供程序、以太网点到点连接提供程序，或者通过 MPLS 连接提供程序。</span><span class="sxs-lookup"><span data-stu-id="5d661-120">Regardless of whether you have an existing MPLS WAN, ExpressRoute can be added to your network architecture in one of three ways; through a supported cloud exchange co-location provider, an Ethernet point-to-point connection provider, or through an MPLS connection provider.</span></span> <span data-ttu-id="5d661-121">查看 [哪些提供程序在你的区域可用](/azure/expressroute/expressroute-locations)。</span><span class="sxs-lookup"><span data-stu-id="5d661-121">See what [providers are available in your region](/azure/expressroute/expressroute-locations).</span></span> <span data-ttu-id="5d661-122">直接 ExpressRoute 连接将启用与下面"包括哪些服务Office 365[概述的应用程序的连接](azure-expressroute.md#BKMK_WhatDoIGet)。</span><span class="sxs-lookup"><span data-stu-id="5d661-122">The direct ExpressRoute connection will enable connectivity to the applications outlined in [What Office 365 services are included?](azure-expressroute.md#BKMK_WhatDoIGet) below.</span></span> <span data-ttu-id="5d661-123">所有其他应用程序和服务的网络通信将继续遍历 Internet。</span><span class="sxs-lookup"><span data-stu-id="5d661-123">Network traffic for all other applications and services will continue to traverse the internet.</span></span>

<span data-ttu-id="5d661-124">请考虑以下高级网络图，该图显示了一个典型的 Office 365 客户通过 Internet 连接到 Microsoft 数据中心，以访问所有 Microsoft 应用程序，如 Office 365、Windows Update 和 TechNet。</span><span class="sxs-lookup"><span data-stu-id="5d661-124">Consider the following high level network diagram which shows a typical Office 365 customer connecting to Microsoft's datacenters over the internet for access to all Microsoft applications such as Office 365, Windows Update, and TechNet.</span></span> <span data-ttu-id="5d661-125">无论客户是从本地网络还是从独立的 Internet 连接进行连接，他们都会使用类似的网络路径。</span><span class="sxs-lookup"><span data-stu-id="5d661-125">Customers use a similar network path regardless of whether they're connecting from an on-premises network or from an independent internet connection.</span></span>

![Office 365网络连接](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

<span data-ttu-id="5d661-127">现在，查看更新的图表，该图Office 365 Internet 和 ExpressRoute 连接到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="5d661-127">Now look at the updated diagram which depicts an Office 365 customer who uses both the internet and ExpressRoute to connect to Office 365.</span></span> <span data-ttu-id="5d661-128">请注意，某些连接（如公共 DNS 和 内容分发网络 节点）仍然需要公共 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="5d661-128">Notice that some connections such as Public DNS and Content Delivery Network nodes still require the public internet connection.</span></span> <span data-ttu-id="5d661-129">另请注意，不在 ExpressRoute 连接建筑物中的客户用户正在通过 Internet 进行连接。</span><span class="sxs-lookup"><span data-stu-id="5d661-129">Also notice the customer's users who are not located in their ExpressRoute connected building are connecting over the Internet.</span></span>

![Office 365 ExpressRoute 建立连接](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

<span data-ttu-id="5d661-131">是否仍需要更多信息？</span><span class="sxs-lookup"><span data-stu-id="5d661-131">Still want more information?</span></span> <span data-ttu-id="5d661-132">了解如何使用[Azure ExpressRoute for Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)管理网络流量，并了解如何为 Office 365 配置[Azure ExpressRoute。](/azure/expressroute/expressroute-faqs)</span><span class="sxs-lookup"><span data-stu-id="5d661-132">Learn how to [manage your network traffic with Azure ExpressRoute for Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) and learn how to [configure Azure ExpressRoute for Office 365](/azure/expressroute/expressroute-faqs).</span></span> <span data-ttu-id="5d661-133">我们还记录了第 9 频道上的[Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer)系列（10 部分）以帮助更详尽地解释概念。</span><span class="sxs-lookup"><span data-stu-id="5d661-133">We've also recorded a 10 part [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) series on Channel 9 to help explain the concepts more thoroughly.</span></span>

## <a name="what-office-365-services-are-included"></a><span data-ttu-id="5d661-134">包括Office 365服务是什么？</span><span class="sxs-lookup"><span data-stu-id="5d661-134">What Office 365 services are included?</span></span>
<span data-ttu-id="5d661-135"><a name="BKMK_WhatDoIGet"> </a></span><span class="sxs-lookup"><span data-stu-id="5d661-135"><a name="BKMK_WhatDoIGet"> </a></span></span>

<span data-ttu-id="5d661-136">下表列出了 ExpressRoute Office 365支持的服务。</span><span class="sxs-lookup"><span data-stu-id="5d661-136">The following table lists the Office 365 services that are supported over ExpressRoute.</span></span> <span data-ttu-id="5d661-137">请查看 Office 365[终结点](./urls-and-ip-address-ranges.md)文章，了解这些应用程序的哪些网络请求需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="5d661-137">Please review the [Office 365 endpoints article](./urls-and-ip-address-ranges.md) to understand which network requests for these applications require internet connectivity.</span></span>

| <span data-ttu-id="5d661-138">包含的应用程序</span><span class="sxs-lookup"><span data-stu-id="5d661-138">Applications included</span></span> |
|:-----|
|<span data-ttu-id="5d661-139">Exchange Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-139">Exchange Online<sup>1</sup></span></span> <br/> <span data-ttu-id="5d661-140">Exchange Online Protection<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-140">Exchange Online Protection<sup>1</sup></span></span> <br/> <span data-ttu-id="5d661-141">Delve<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-141">Delve<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="5d661-142">Skype for BusinessOnline<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-142">Skype for Business Online<sup>1</sup></span></span> <br/> <span data-ttu-id="5d661-143">Microsoft Teams <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-143">Microsoft Teams <sup>1</sup></span></span> <br/> |
|<span data-ttu-id="5d661-144">SharePointOnline<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-144">SharePoint Online<sup>1</sup></span></span> <br/> <span data-ttu-id="5d661-145">OneDrive for Business<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-145">OneDrive for Business<sup>1</sup></span></span> <br/> <span data-ttu-id="5d661-146">Project Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-146">Project Online<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="5d661-147">门户和共享<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-147">Portal and shared<sup>1</sup></span></span> <br/> <span data-ttu-id="5d661-148">Azure Active Directory (Azure AD) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-148">Azure Active Directory (Azure AD) <sup>1</sup></span></span> <br/> <span data-ttu-id="5d661-149">Azure AD 连接<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-149">Azure AD Connect<sup>1</sup></span></span> <br/> <span data-ttu-id="5d661-150">Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d661-150">Office<sup>1</sup></span></span> <br/> |

<span data-ttu-id="5d661-151"><sup>1</sup>其中每个应用程序都有不受 ExpressRoute 支持的 Internet 连接要求，请参阅 Office 365[终结点](./urls-and-ip-address-ranges.md)文章了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="5d661-151"><sup>1</sup> Each of these applications have internet connectivity requirements not supported over ExpressRoute, see the [Office 365 endpoints article](./urls-and-ip-address-ranges.md) for more information.</span></span>

<span data-ttu-id="5d661-152">ExpressRoute for Office 365 中未包含的服务包括 Microsoft 365 企业应用版 客户端下载、本地标识提供商登录Office 365 (由中国世纪通) 服务运营。</span><span class="sxs-lookup"><span data-stu-id="5d661-152">The services that aren't included with ExpressRoute for Office 365 are Microsoft 365 Apps for enterprise client downloads, On-premises Identity Provider Sign-In, and Office 365 (operated by 21 Vianet) service in China.</span></span>

## <a name="implementing-expressroute-for-office-365"></a><span data-ttu-id="5d661-153">实现适用于 Office 365 的 ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="5d661-153">Implementing ExpressRoute for Office 365</span></span>

<span data-ttu-id="5d661-154">实现 ExpressRoute 需要网络和应用程序所有者的参与，并且需要仔细规划以确定新的网络路由体系结构[](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)、带宽要求、实现安全性的地方、高可用性等。</span><span class="sxs-lookup"><span data-stu-id="5d661-154">Implementing ExpressRoute requires the involvement of network and application owners and requires careful planning to determine the new [network routing architecture](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), bandwidth requirements, where security will be implemented, high availability, and so on.</span></span> <span data-ttu-id="5d661-155">若要实现 ExpressRoute，你需要：</span><span class="sxs-lookup"><span data-stu-id="5d661-155">To implement ExpressRoute, you'll need to:</span></span>

1. <span data-ttu-id="5d661-156">完全了解 ExpressRoute 在连接规划中满足Office 365需求。</span><span class="sxs-lookup"><span data-stu-id="5d661-156">Fully understand the need ExpressRoute satisfies in your Office 365 connectivity planning.</span></span> <span data-ttu-id="5d661-157">了解哪些应用程序将使用 Internet 或 ExpressRoute，并全面规划网络容量、安全性和高可用性需求，同时使用 Internet 和 ExpressRoute Office 365流量。</span><span class="sxs-lookup"><span data-stu-id="5d661-157">Understand what applications will use the internet or ExpressRoute and fully plan your network capacity, security, and high availability needs in the context of using both the internet and ExpressRoute for Office 365 traffic.</span></span>

2. <span data-ttu-id="5d661-158">确定 Internet 和 ExpressRoute 流量<sup>1</sup>的出口和对等位置。</span><span class="sxs-lookup"><span data-stu-id="5d661-158">Determine the egress and peering locations for both internet and ExpressRoute traffic<sup>1</sup>.</span></span>

3. <span data-ttu-id="5d661-159">确定 Internet 和 ExpressRoute 连接所需的容量。</span><span class="sxs-lookup"><span data-stu-id="5d661-159">Determine the capacity required on the internet and ExpressRoute connections.</span></span>

4. <span data-ttu-id="5d661-160">制定实施安全和其他标准外围控件<sup>1 的计划</sup>。</span><span class="sxs-lookup"><span data-stu-id="5d661-160">Have a plan in place for implementing security and other standard perimeter controls<sup>1</sup>.</span></span>

5. <span data-ttu-id="5d661-161">拥有一个有效的Microsoft Azure帐户来订阅 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="5d661-161">Have a valid Microsoft Azure account to subscribe to ExpressRoute.</span></span>

6. <span data-ttu-id="5d661-162">选择连接模型和批准的 [提供程序](/azure/expressroute/expressroute-locations)。</span><span class="sxs-lookup"><span data-stu-id="5d661-162">Select a connectivity model and an [approved provider](/azure/expressroute/expressroute-locations).</span></span> <span data-ttu-id="5d661-163">请记住，客户可以选择多个连接模型或合作伙伴，合作伙伴无需与现有的网络提供商相同。</span><span class="sxs-lookup"><span data-stu-id="5d661-163">Keep in mind, customers can select multiple connectivity models or partners and the partner doesn't need to be the same as your existing network provider.</span></span>

7. <span data-ttu-id="5d661-164">在将流量引导到 ExpressRoute 之前验证部署。</span><span class="sxs-lookup"><span data-stu-id="5d661-164">Validate deployment prior to directing traffic to ExpressRoute.</span></span>

8. <span data-ttu-id="5d661-165">（可选 [）实施 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) 和评估区域扩展。</span><span class="sxs-lookup"><span data-stu-id="5d661-165">Optionally [implement QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) and evaluate regional expansion.</span></span>

<span data-ttu-id="5d661-166"><sup>1</sup> 重要的性能注意事项。</span><span class="sxs-lookup"><span data-stu-id="5d661-166"><sup>1</sup> Important performance considerations.</span></span> <span data-ttu-id="5d661-167">此处的决策会显著影响延迟，这一点对于应用程序（如应用程序）Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="5d661-167">Decisions here can dramatically impact latency which is a critical for applications such as Skype for Business.</span></span>

<span data-ttu-id="5d661-168">有关其他参考，请使用我们的 [路由指南](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) 以及 [ExpressRoute 文档](/azure/expressroute/expressroute-introduction)。</span><span class="sxs-lookup"><span data-stu-id="5d661-168">For additional references, use our [routing guide](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) in addition to the [ExpressRoute documentation](/azure/expressroute/expressroute-introduction).</span></span>

<span data-ttu-id="5d661-169">若要购买 ExpressRoute for Office 365，你需要与一个或多个批准的提供商合作，通过[](/azure/expressroute/expressroute-locations)ExpressRoute 订阅预配所需数量和高级版线路。</span><span class="sxs-lookup"><span data-stu-id="5d661-169">To purchase ExpressRoute for Office 365, you'll need to work with one or more [approved providers](/azure/expressroute/expressroute-locations) to provision the desired number and size circuits with an ExpressRoute Premium subscription.</span></span> <span data-ttu-id="5d661-170">无需从用户那里购买其他Office 365。</span><span class="sxs-lookup"><span data-stu-id="5d661-170">There are no additional licenses to purchase from Office 365.</span></span>

<span data-ttu-id="5d661-171">以下是可以用于返回的简短链接：[https://aka.ms/expressrouteoffice365]()</span><span class="sxs-lookup"><span data-stu-id="5d661-171">Here's a short link you can use to come back: [https://aka.ms/expressrouteoffice365]()</span></span>

<span data-ttu-id="5d661-172">准备好注册[ExpressRoute for Office 365？](https://aka.ms/ert)</span><span class="sxs-lookup"><span data-stu-id="5d661-172">Ready to sign-up for [ExpressRoute for Office 365](https://aka.ms/ert)?</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d661-173">相关主题</span><span class="sxs-lookup"><span data-stu-id="5d661-173">Related Topics</span></span>

[<span data-ttu-id="5d661-174">评估 Office 365 网络连接</span><span class="sxs-lookup"><span data-stu-id="5d661-174">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)

[<span data-ttu-id="5d661-175">管理 ExpressRoute for Office 365 连接</span><span class="sxs-lookup"><span data-stu-id="5d661-175">Managing ExpressRoute for Office 365 connectivity</span></span>](managing-expressroute-for-connectivity.md)

[<span data-ttu-id="5d661-176">使用 ExpressRoute for Office 365 路由</span><span class="sxs-lookup"><span data-stu-id="5d661-176">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)

[<span data-ttu-id="5d661-177">ExpressRoute for Office 365 网络计划</span><span class="sxs-lookup"><span data-stu-id="5d661-177">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)

[<span data-ttu-id="5d661-178">实现 ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="5d661-178">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)

[<span data-ttu-id="5d661-179">在 ExpressRoute 中将 BGP 社区用于Office 365方案</span><span class="sxs-lookup"><span data-stu-id="5d661-179">Using BGP communities in ExpressRoute for Office 365 scenarios</span></span>](bgp-communities-in-expressroute.md)

[<span data-ttu-id="5d661-180">Skype for Business Online 中的媒体质量和网络连接性能</span><span class="sxs-lookup"><span data-stu-id="5d661-180">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[<span data-ttu-id="5d661-181">使用基线和性能历史记录优化 Office 365 性能</span><span class="sxs-lookup"><span data-stu-id="5d661-181">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)

[<span data-ttu-id="5d661-182">Office 365 性能疑难解答计划</span><span class="sxs-lookup"><span data-stu-id="5d661-182">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)

[<span data-ttu-id="5d661-183">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="5d661-183">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="5d661-184">Office 365 网络和性能优化</span><span class="sxs-lookup"><span data-stu-id="5d661-184">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

## <a name="see-also"></a><span data-ttu-id="5d661-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d661-185">See also</span></span>

[<span data-ttu-id="5d661-186">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="5d661-186">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
