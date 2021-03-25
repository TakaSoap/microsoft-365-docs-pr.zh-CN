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
ms.openlocfilehash: 788bdb45fe2d3c8a01315aac0db371b57577aeb8
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164981"
---
# <a name="azure-expressroute-for-office-365"></a><span data-ttu-id="1e338-103">适用于 Office 365 的 Azure ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="1e338-103">Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="1e338-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="1e338-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1e338-105">了解如何将 Azure ExpressRoute 与 Office 365 一同使用，以及如何规划部署 Azure ExpressRoute 以用于 Office 365 时所需的网络实施项目。</span><span class="sxs-lookup"><span data-stu-id="1e338-105">Learn how Azure ExpressRoute is used with Office 365 and how to plan the network implementation project that will be required if you are deploying Azure ExpressRoute for use with Office 365.</span></span> <span data-ttu-id="1e338-106">在 Azure 中运行的基础结构和平台服务通常会从解决网络体系结构和性能注意事项中获益。</span><span class="sxs-lookup"><span data-stu-id="1e338-106">Infrastructure and platform services running in Azure will often benefit by addressing network architecture and performance considerations.</span></span> <span data-ttu-id="1e338-107">在这些情况下，我们建议使用 ExpressRoute for Azure。</span><span class="sxs-lookup"><span data-stu-id="1e338-107">We recommend ExpressRoute for Azure in these cases.</span></span> <span data-ttu-id="1e338-108">Office 365 和 Dynamics 365 等软件即服务产品已构建为可通过 Internet 安全可靠地访问。</span><span class="sxs-lookup"><span data-stu-id="1e338-108">Software as a Service offerings like Office 365 and Dynamics 365 have been built to be accessed securely and reliably via the Internet.</span></span> <span data-ttu-id="1e338-109">可以在评估 [Office 365](assessing-network-connectivity.md)网络连接一文阅读有关 Internet 性能和安全性以及何时考虑使用适用于 Office 365 的 Azure ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="1e338-109">You can read about Internet performance and security and when you might consider Azure ExpressRoute for Office 365 in the article [Assessing Office 365 network connectivity](assessing-network-connectivity.md).</span></span>

>[!NOTE]
><span data-ttu-id="1e338-110">Microsoft 不建议使用适用于 Microsoft 365 的 ExpressRoute，也不在几乎所有情况下都为该服务提供最佳连接模型。</span><span class="sxs-lookup"><span data-stu-id="1e338-110">Microsoft does not recommend ExpressRoute for Microsoft 365, nor does it provide the best connectivity model for the service in almost all circumstances.</span></span> <span data-ttu-id="1e338-111">因此，需要 Microsoft 授权才能对此服务使用此连接模型。</span><span class="sxs-lookup"><span data-stu-id="1e338-111">As such, Microsoft authorization is required to use this connectivity model for the service.</span></span> <span data-ttu-id="1e338-112">Microsoft 仅在必要时审查每个客户请求并授权 ExpressRoute for Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="1e338-112">Microsoft reviews every customer request and authorizes ExpressRoute for Microsoft 365 only in the rare scenarios where it is necessary.</span></span> <span data-ttu-id="1e338-113">有关详细信息，请阅读 [ExpressRoute for Microsoft 365](https://aka.ms/erguide) 指南，并遵循本指南的全面审阅，与 Microsoft 帐户团队合作提交例外。</span><span class="sxs-lookup"><span data-stu-id="1e338-113">Please read the [ExpressRoute for Microsoft 365 guide](https://aka.ms/erguide) for more information and work with your Microsoft account team to submit an exception should you require, following comprehensive review of the guide.</span></span>
<span data-ttu-id="1e338-114">尝试为 Microsoft 365 创建路由筛选器的未经授权的订阅将收到 [一条错误消息](https://support.microsoft.com/kb/3181709)。</span><span class="sxs-lookup"><span data-stu-id="1e338-114">Unauthorized subscriptions trying to create route filters for Microsoft 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>

<span data-ttu-id="1e338-115">现在，您可以为选定的 Office 365 网络流量向 Office 365 添加直接网络连接。</span><span class="sxs-lookup"><span data-stu-id="1e338-115">You can now add a direct network connection to Office 365 for selected Office 365 network traffic.</span></span> <span data-ttu-id="1e338-116">Azure ExpressRoute 提供直接连接、可预测的性能，并附带 99.95% 的 Microsoft 网络组件的运行时间 SLA。</span><span class="sxs-lookup"><span data-stu-id="1e338-116">Azure ExpressRoute offers a direct connection, predictable performance, and comes with an uptime SLA of 99.95% for the Microsoft networking components.</span></span> <span data-ttu-id="1e338-117">对于 Azure ExpressRoute 不支持的服务，你仍然需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="1e338-117">You'll still require an internet connection for services that aren't supported over Azure ExpressRoute.</span></span>

## <a name="planning-azure-expressroute-for-office-365"></a><span data-ttu-id="1e338-118">规划 Office 365 的 Azure ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="1e338-118">Planning Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="1e338-119">除了 Internet 连接之外，您还可以选择通过直接连接路由 Office 365 网络流量的子集，该直接连接为 Microsoft 网络组件提供可预测性和 99.95% 正常运行时间 SLA。</span><span class="sxs-lookup"><span data-stu-id="1e338-119">In addition to internet connectivity, you may choose to route a subset of their Office 365 network traffic over a direct connection that offers predictability and a 99.95% uptime SLA for the Microsoft networking components.</span></span> <span data-ttu-id="1e338-120">Azure ExpressRoute 为您提供到 Office 365 和其他 Microsoft 云服务的专用网络连接。</span><span class="sxs-lookup"><span data-stu-id="1e338-120">Azure ExpressRoute provides you with this dedicated network connection to Office 365 and other Microsoft cloud services.</span></span>

<span data-ttu-id="1e338-121">无论你是否有现有的 MPLS WAN，ExpressRoute 都可以通过以下三种方式之一添加到网络体系结构中;通过支持的云交换共同位置提供程序、以太网点到点连接提供程序，或者通过 MPLS 连接提供程序。</span><span class="sxs-lookup"><span data-stu-id="1e338-121">Regardless of whether you have an existing MPLS WAN, ExpressRoute can be added to your network architecture in one of three ways; through a supported cloud exchange co-location provider, an Ethernet point-to-point connection provider, or through an MPLS connection provider.</span></span> <span data-ttu-id="1e338-122">查看 [哪些提供程序在你的区域可用](/azure/expressroute/expressroute-locations)。</span><span class="sxs-lookup"><span data-stu-id="1e338-122">See what [providers are available in your region](/azure/expressroute/expressroute-locations).</span></span> <span data-ttu-id="1e338-123">直接 ExpressRoute 连接将启用与下面包含哪些 [Office 365](azure-expressroute.md#BKMK_WhatDoIGet) 服务？中概述的应用程序的连接。</span><span class="sxs-lookup"><span data-stu-id="1e338-123">The direct ExpressRoute connection will enable connectivity to the applications outlined in [What Office 365 services are included?](azure-expressroute.md#BKMK_WhatDoIGet) below.</span></span> <span data-ttu-id="1e338-124">所有其他应用程序和服务的网络通信将继续遍历 Internet。</span><span class="sxs-lookup"><span data-stu-id="1e338-124">Network traffic for all other applications and services will continue to traverse the internet.</span></span>

<span data-ttu-id="1e338-125">请考虑以下高级网络图，该图显示了通过 Internet 连接到 Microsoft 数据中心以访问所有 Microsoft 应用程序（如 Office 365、Windows 更新和 TechNet）的典型 Office 365 客户。</span><span class="sxs-lookup"><span data-stu-id="1e338-125">Consider the following high level network diagram which shows a typical Office 365 customer connecting to Microsoft's datacenters over the internet for access to all Microsoft applications such as Office 365, Windows Update, and TechNet.</span></span> <span data-ttu-id="1e338-126">无论客户是从本地网络还是从独立的 Internet 连接进行连接，他们都会使用类似的网络路径。</span><span class="sxs-lookup"><span data-stu-id="1e338-126">Customers use a similar network path regardless of whether they're connecting from an on-premises network or from an independent internet connection.</span></span>

![Office 365 网络连接](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

<span data-ttu-id="1e338-128">现在查看更新后的图表，其中描述了同时使用 Internet 和 ExpressRoute 连接到 Office 365 的 Office 365 客户。</span><span class="sxs-lookup"><span data-stu-id="1e338-128">Now look at the updated diagram which depicts an Office 365 customer who uses both the internet and ExpressRoute to connect to Office 365.</span></span> <span data-ttu-id="1e338-129">请注意，某些连接（如公共 DNS 和内容传递网络节点）仍然需要公共 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="1e338-129">Notice that some connections such as Public DNS and Content Delivery Network nodes still require the public internet connection.</span></span> <span data-ttu-id="1e338-130">另请注意，不在 ExpressRoute 连接建筑物中的客户用户正在通过 Internet 进行连接。</span><span class="sxs-lookup"><span data-stu-id="1e338-130">Also notice the customer's users who are not located in their ExpressRoute connected building are connecting over the Internet.</span></span>

![与 ExpressRoute 的 Office 365 连接](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

<span data-ttu-id="1e338-132">是否仍需要更多信息？</span><span class="sxs-lookup"><span data-stu-id="1e338-132">Still want more information?</span></span> <span data-ttu-id="1e338-133">了解如何使用[适用于 Office 365 的 Azure ExpressRoute](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)管理网络流量，以及如何为 Office [365 配置 Azure ExpressRoute。](/azure/expressroute/expressroute-faqs)</span><span class="sxs-lookup"><span data-stu-id="1e338-133">Learn how to [manage your network traffic with Azure ExpressRoute for Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) and learn how to [configure Azure ExpressRoute for Office 365](/azure/expressroute/expressroute-faqs).</span></span> <span data-ttu-id="1e338-134">我们还在 Channel 9 上记录了一个 10 部分 [Azure ExpressRoute for Office 365 培训](https://channel9.msdn.com/series/aer) 系列，以帮助更详尽地解释概念。</span><span class="sxs-lookup"><span data-stu-id="1e338-134">We've also recorded a 10 part [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) series on Channel 9 to help explain the concepts more thoroughly.</span></span>

## <a name="what-office-365-services-are-included"></a><span data-ttu-id="1e338-135">包含哪些 Office 365 服务？</span><span class="sxs-lookup"><span data-stu-id="1e338-135">What Office 365 services are included?</span></span>
<span data-ttu-id="1e338-136"><a name="BKMK_WhatDoIGet"> </a></span><span class="sxs-lookup"><span data-stu-id="1e338-136"><a name="BKMK_WhatDoIGet"> </a></span></span>

<span data-ttu-id="1e338-137">下表列出了通过 ExpressRoute 支持的 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="1e338-137">The following table lists the Office 365 services that are supported over ExpressRoute.</span></span> <span data-ttu-id="1e338-138">请查看 [Office 365](./urls-and-ip-address-ranges.md) 终结点文章，了解这些应用程序的哪些网络请求需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="1e338-138">Please review the [Office 365 endpoints article](./urls-and-ip-address-ranges.md) to understand which network requests for these applications require internet connectivity.</span></span>

|<span data-ttu-id="1e338-139">**包含的应用程序**</span><span class="sxs-lookup"><span data-stu-id="1e338-139">**Applications included**</span></span>|
|:-----|
|<span data-ttu-id="1e338-140">Exchange Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-140">Exchange Online<sup>1</sup></span></span> <br/> <span data-ttu-id="1e338-141">Exchange Online Protection<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-141">Exchange Online Protection<sup>1</sup></span></span> <br/> <span data-ttu-id="1e338-142">Delve<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-142">Delve<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="1e338-143">Skype for Business Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-143">Skype for Business Online<sup>1</sup></span></span> <br/> <span data-ttu-id="1e338-144">Microsoft Teams <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-144">Microsoft Teams <sup>1</sup></span></span> <br/> |
|<span data-ttu-id="1e338-145">SharePoint Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-145">SharePoint Online<sup>1</sup></span></span> <br/> <span data-ttu-id="1e338-146">OneDrive for Business<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-146">OneDrive for Business<sup>1</sup></span></span> <br/> <span data-ttu-id="1e338-147">Project Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-147">Project Online<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="1e338-148">门户和共享<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-148">Portal and shared<sup>1</sup></span></span> <br/> <span data-ttu-id="1e338-149">Azure Active Directory (Azure AD) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-149">Azure Active Directory (Azure AD) <sup>1</sup></span></span> <br/> <span data-ttu-id="1e338-150">Azure AD Connect<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-150">Azure AD Connect<sup>1</sup></span></span> <br/> <span data-ttu-id="1e338-151">Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e338-151">Office<sup>1</sup></span></span> <br/> |

<span data-ttu-id="1e338-152"><sup>1</sup> 其中每个应用程序都有不受 ExpressRoute 支持的 Internet 连接要求，有关详细信息，请参阅 [Office 365](./urls-and-ip-address-ranges.md) 终结点文章。</span><span class="sxs-lookup"><span data-stu-id="1e338-152"><sup>1</sup> Each of these applications have internet connectivity requirements not supported over ExpressRoute, see the [Office 365 endpoints article](./urls-and-ip-address-ranges.md) for more information.</span></span>

<span data-ttu-id="1e338-153">ExpressRoute for Office 365 中未包含的服务包括 Microsoft 365 企业应用版客户端下载、本地标识提供商登录和由中国世纪通) 服务运营的 Office 365 (。</span><span class="sxs-lookup"><span data-stu-id="1e338-153">The services that aren't included with ExpressRoute for Office 365 are Microsoft 365 Apps for enterprise client downloads, On-premises Identity Provider Sign-In, and Office 365 (operated by 21 Vianet) service in China.</span></span>

## <a name="implementing-expressroute-for-office-365"></a><span data-ttu-id="1e338-154">实现适用于 Office 365 的 ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="1e338-154">Implementing ExpressRoute for Office 365</span></span>

<span data-ttu-id="1e338-155">实现 ExpressRoute 需要网络和应用程序所有者的参与，并且需要仔细规划以确定新的网络路由体系结构[](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)、带宽要求、实现安全性的地方、高可用性等。</span><span class="sxs-lookup"><span data-stu-id="1e338-155">Implementing ExpressRoute requires the involvement of network and application owners and requires careful planning to determine the new [network routing architecture](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), bandwidth requirements, where security will be implemented, high availability, and so on.</span></span> <span data-ttu-id="1e338-156">若要实现 ExpressRoute，你需要：</span><span class="sxs-lookup"><span data-stu-id="1e338-156">To implement ExpressRoute, you'll need to:</span></span>

1. <span data-ttu-id="1e338-157">完全了解在 Office 365 连接规划中 ExpressRoute 满足需求。</span><span class="sxs-lookup"><span data-stu-id="1e338-157">Fully understand the need ExpressRoute satisfies in your Office 365 connectivity planning.</span></span> <span data-ttu-id="1e338-158">了解哪些应用程序将使用 Internet 或 ExpressRoute，并针对 Office 365 流量使用 Internet 和 ExpressRoute，全面规划网络容量、安全性和高可用性需求。</span><span class="sxs-lookup"><span data-stu-id="1e338-158">Understand what applications will use the internet or ExpressRoute and fully plan your network capacity, security, and high availability needs in the context of using both the internet and ExpressRoute for Office 365 traffic.</span></span>

2. <span data-ttu-id="1e338-159">确定 Internet 和 ExpressRoute 流量<sup>1</sup>的出口和对等位置。</span><span class="sxs-lookup"><span data-stu-id="1e338-159">Determine the egress and peering locations for both internet and ExpressRoute traffic<sup>1</sup>.</span></span>

3. <span data-ttu-id="1e338-160">确定 Internet 和 ExpressRoute 连接所需的容量。</span><span class="sxs-lookup"><span data-stu-id="1e338-160">Determine the capacity required on the internet and ExpressRoute connections.</span></span>

4. <span data-ttu-id="1e338-161">制定实施安全和其他标准外围控件<sup>1 的计划</sup>。</span><span class="sxs-lookup"><span data-stu-id="1e338-161">Have a plan in place for implementing security and other standard perimeter controls<sup>1</sup>.</span></span>

5. <span data-ttu-id="1e338-162">拥有有效的 Microsoft Azure 帐户以订阅 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="1e338-162">Have a valid Microsoft Azure account to subscribe to ExpressRoute.</span></span>

6. <span data-ttu-id="1e338-163">选择连接模型和批准的 [提供程序](/azure/expressroute/expressroute-locations)。</span><span class="sxs-lookup"><span data-stu-id="1e338-163">Select a connectivity model and an [approved provider](/azure/expressroute/expressroute-locations).</span></span> <span data-ttu-id="1e338-164">请记住，客户可以选择多个连接模型或合作伙伴，合作伙伴无需与现有的网络提供商相同。</span><span class="sxs-lookup"><span data-stu-id="1e338-164">Keep in mind, customers can select multiple connectivity models or partners and the partner doesn't need to be the same as your existing network provider.</span></span>

7. <span data-ttu-id="1e338-165">在将流量引导到 ExpressRoute 之前验证部署。</span><span class="sxs-lookup"><span data-stu-id="1e338-165">Validate deployment prior to directing traffic to ExpressRoute.</span></span>

8. <span data-ttu-id="1e338-166">（可选 [）实施 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) 和评估区域扩展。</span><span class="sxs-lookup"><span data-stu-id="1e338-166">Optionally [implement QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) and evaluate regional expansion.</span></span>

<span data-ttu-id="1e338-167"><sup>1</sup> 重要的性能注意事项。</span><span class="sxs-lookup"><span data-stu-id="1e338-167"><sup>1</sup> Important performance considerations.</span></span> <span data-ttu-id="1e338-168">此处的决策会显著影响延迟，延迟对于 Skype for Business 等应用程序至关重要。</span><span class="sxs-lookup"><span data-stu-id="1e338-168">Decisions here can dramatically impact latency which is a critical for applications such as Skype for Business.</span></span>

<span data-ttu-id="1e338-169">有关其他参考，请使用我们的 [路由指南](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) 以及 [ExpressRoute 文档](/azure/expressroute/expressroute-introduction)。</span><span class="sxs-lookup"><span data-stu-id="1e338-169">For additional references, use our [routing guide](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) in addition to the [ExpressRoute documentation](/azure/expressroute/expressroute-introduction).</span></span>

<span data-ttu-id="1e338-170">若要购买适用于 Office 365 的 ExpressRoute，需要与一个或多个批准的[](/azure/expressroute/expressroute-locations)提供商合作，通过 ExpressRoute Premium 订阅预配所需数量和大小的电路。</span><span class="sxs-lookup"><span data-stu-id="1e338-170">To purchase ExpressRoute for Office 365, you'll need to work with one or more [approved providers](/azure/expressroute/expressroute-locations) to provision the desired number and size circuits with an ExpressRoute Premium subscription.</span></span> <span data-ttu-id="1e338-171">无需从 Office 365 购买其他许可证。</span><span class="sxs-lookup"><span data-stu-id="1e338-171">There are no additional licenses to purchase from Office 365.</span></span>

<span data-ttu-id="1e338-172">以下是可以用于返回的简短链接：[https://aka.ms/expressrouteoffice365]()</span><span class="sxs-lookup"><span data-stu-id="1e338-172">Here's a short link you can use to come back: [https://aka.ms/expressrouteoffice365]()</span></span>

<span data-ttu-id="1e338-173">准备好注册适用于 Office [365 的 ExpressRoute 了吗](https://aka.ms/ert)？</span><span class="sxs-lookup"><span data-stu-id="1e338-173">Ready to sign-up for [ExpressRoute for Office 365](https://aka.ms/ert)?</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e338-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="1e338-174">Related Topics</span></span>

[<span data-ttu-id="1e338-175">评估 Office 365 网络连接</span><span class="sxs-lookup"><span data-stu-id="1e338-175">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)

[<span data-ttu-id="1e338-176">管理 ExpressRoute for Office 365 连接</span><span class="sxs-lookup"><span data-stu-id="1e338-176">Managing ExpressRoute for Office 365 connectivity</span></span>](managing-expressroute-for-connectivity.md)

[<span data-ttu-id="1e338-177">使用 ExpressRoute for Office 365 路由</span><span class="sxs-lookup"><span data-stu-id="1e338-177">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)

[<span data-ttu-id="1e338-178">ExpressRoute for Office 365 网络计划</span><span class="sxs-lookup"><span data-stu-id="1e338-178">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)

[<span data-ttu-id="1e338-179">实现 ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="1e338-179">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)

[<span data-ttu-id="1e338-180">在 ExpressRoute for Office 365 方案中使用 BGP 社区</span><span class="sxs-lookup"><span data-stu-id="1e338-180">Using BGP communities in ExpressRoute for Office 365 scenarios</span></span>](bgp-communities-in-expressroute.md)

[<span data-ttu-id="1e338-181">Skype for Business Online 中的媒体质量和网络连接性能</span><span class="sxs-lookup"><span data-stu-id="1e338-181">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[<span data-ttu-id="1e338-182">使用基线和性能历史记录优化 Office 365 性能</span><span class="sxs-lookup"><span data-stu-id="1e338-182">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)

[<span data-ttu-id="1e338-183">Office 365 性能疑难解答计划</span><span class="sxs-lookup"><span data-stu-id="1e338-183">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)

[<span data-ttu-id="1e338-184">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="1e338-184">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="1e338-185">Office 365 网络和性能优化</span><span class="sxs-lookup"><span data-stu-id="1e338-185">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

## <a name="see-also"></a><span data-ttu-id="1e338-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e338-186">See also</span></span>

[<span data-ttu-id="1e338-187">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="1e338-187">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
