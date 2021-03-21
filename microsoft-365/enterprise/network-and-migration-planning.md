---
title: Office 365 的网络和迁移规划
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
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
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: 本文包含指向有关网络规划、测试和迁移到 Office 365 的信息的链接。
ms.openlocfilehash: 99bcc1bd0447b192860fc0bcc67fc18d87c2d5fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923584"
---
# <a name="network-and-migration-planning-for-office-365"></a><span data-ttu-id="4922e-103">Office 365 的网络和迁移规划</span><span class="sxs-lookup"><span data-stu-id="4922e-103">Network and migration planning for Office 365</span></span>

<span data-ttu-id="4922e-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="4922e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4922e-105">本文包含指向有关网络规划和测试以及迁移到 Office 365 的信息的链接。</span><span class="sxs-lookup"><span data-stu-id="4922e-105">This article contains links to information about network planning and testing, and migration to Office 365.</span></span>
  
<span data-ttu-id="4922e-106">首次部署或迁移到 Office 365 之前，可以使用这些主题中的信息估计所需的带宽，然后测试和验证是否有足够的带宽来部署或迁移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4922e-106">Before you deploy for the first time or migrate to Office 365, you can use the information in these topics to estimate the bandwidth you need and then to test and verify that you have enough bandwidth to deploy or migrate to Office 365.</span></span>

<span data-ttu-id="4922e-107">本文是 Office [365 的网络规划和性能调整的一部分](./network-planning-and-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="4922e-107">This article is part of [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).</span></span>

<span data-ttu-id="4922e-108">有关针对 Microsoft 365 和其他 Microsoft 云平台和服务优化网络的步骤，请参阅适用于企业架构师的 [Microsoft 云网络](../solutions/cloud-architecture-models.md) 海报。</span><span class="sxs-lookup"><span data-stu-id="4922e-108">For the steps to optimize your network for Microsoft 365 and other Microsoft cloud platforms and services, see the [Microsoft Cloud Networking for Enterprise Architects](../solutions/cloud-architecture-models.md) poster.</span></span>
   
## <a name="estimate-network-bandwidth-requirements"></a><span data-ttu-id="4922e-109">估计网络带宽要求</span><span class="sxs-lookup"><span data-stu-id="4922e-109">Estimate network bandwidth requirements</span></span>
<span data-ttu-id="4922e-110"><a name="EstimateBandwidthRequirements"> </a></span><span class="sxs-lookup"><span data-stu-id="4922e-110"><a name="EstimateBandwidthRequirements"> </a></span></span>

<span data-ttu-id="4922e-111">使用 Office 365 可能会增加组织的 Internet 线路的利用率。</span><span class="sxs-lookup"><span data-stu-id="4922e-111">Using Office 365 may increase the utilization of your organization's internet circuit.</span></span> <span data-ttu-id="4922e-112">一旦完全部署 Office 365，同时至少保留 20% 的容量来处理最忙碌的天数，则确定当前可用的带宽量是否足以处理估计的增加量，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="4922e-112">It's important to determine if the amount of bandwidth currently available is enough to handle the estimated increase once Office 365 is fully deployed while leaving at least 20% capacity to handle the busiest of days.</span></span>
  
<span data-ttu-id="4922e-113">若要估计带宽，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4922e-113">To estimate the bandwidth, use the following steps:</span></span>
  
1. <span data-ttu-id="4922e-114">评估将使用每个 Internet 出口的客户端数量。</span><span class="sxs-lookup"><span data-stu-id="4922e-114">Assess the number of clients that will use each Internet egress.</span></span> <span data-ttu-id="4922e-115">让我们的多 TB 网络处理尽可能多的连接。</span><span class="sxs-lookup"><span data-stu-id="4922e-115">Let our multi-terabit network handle as much of the connection as possible.</span></span> 
    
2. <span data-ttu-id="4922e-116">确定可供客户端使用的 Office 365 服务和功能。</span><span class="sxs-lookup"><span data-stu-id="4922e-116">Determine which Office 365 services and features will be available for clients to use.</span></span> <span data-ttu-id="4922e-117">您可能拥有一组具有不同的服务或使用率配置文件的用户组。</span><span class="sxs-lookup"><span data-stu-id="4922e-117">You will likely have groups of people with different services or usage profiles.</span></span>
    
3. <span data-ttu-id="4922e-118">测量客户端试点组的网络使用。</span><span class="sxs-lookup"><span data-stu-id="4922e-118">Measure the network use for a pilot group of clients.</span></span> <span data-ttu-id="4922e-119">确保试点客户端代表组织中不同人员以及不同地理位置的不同配置文件。</span><span class="sxs-lookup"><span data-stu-id="4922e-119">Ensure the pilot clients are representative of the different profiles of people in the organization as well as the different geographic locations.</span></span> <span data-ttu-id="4922e-120">你可以针对 Exchange 和[Microsoft Teams](/microsoftteams/prepare-network)的旧计算器[](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744)交叉检查结果，也可以交叉[](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)检查我们在自己的网络上执行的案例研究。</span><span class="sxs-lookup"><span data-stu-id="4922e-120">You can cross-check your results against our old calculators for [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) and [Microsoft Teams](/microsoftteams/prepare-network) or the [case study](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) we performed on our own network.</span></span> 
    
4. <span data-ttu-id="4922e-121">使用试点组的测量推断整个组织的需求，然后重新测试以验证估计值，然后再对网络进行更改。</span><span class="sxs-lookup"><span data-stu-id="4922e-121">Use the measurements from the pilot group to extrapolate the entire organization's needs and re-test to validate the estimations before making any changes to your network.</span></span>
    
## <a name="test-your-existing-network"></a><span data-ttu-id="4922e-122">测试现有网络</span><span class="sxs-lookup"><span data-stu-id="4922e-122">Test your existing network</span></span>
<span data-ttu-id="4922e-123"><a name="calculators"> </a></span><span class="sxs-lookup"><span data-stu-id="4922e-123"><a name="calculators"> </a></span></span>

 <span data-ttu-id="4922e-124">**网络工具。**</span><span class="sxs-lookup"><span data-stu-id="4922e-124">**Network tools.**</span></span> <span data-ttu-id="4922e-125">测试和验证 Internet 带宽以确定下载、上载和延迟限制。</span><span class="sxs-lookup"><span data-stu-id="4922e-125">Test and validate your Internet bandwidth to determine download, upload, and latency constraints.</span></span> <span data-ttu-id="4922e-126">这些工具将帮助您确定网络的迁移功能，以及完全部署后的功能。</span><span class="sxs-lookup"><span data-stu-id="4922e-126">These tools will help you determine the capabilities of your network for migration as well as after you're fully deployed.</span></span> 
    
- <span data-ttu-id="4922e-127">[Microsoft Remote Connectivity Analyzer：](https://go.microsoft.com/fwlink/p/?LinkId=517243)测试 Exchange Online 环境中的连接性。</span><span class="sxs-lookup"><span data-stu-id="4922e-127">[Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): Tests connectivity in your Exchange Online environment.</span></span>
    
- <span data-ttu-id="4922e-128">使用 [适用于 Office 365](https://diagnostics.office.com/#/Download?env=SOC) 的 Microsoft 支持和恢复助手修复 Outlook 和 Office 365 问题。</span><span class="sxs-lookup"><span data-stu-id="4922e-128">Use the [Microsoft Support and Recovery Assistant for Office 365](https://diagnostics.office.com/#/Download?env=SOC) to fix Outlook and Office 365 problems.</span></span> 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a><span data-ttu-id="4922e-129">Office 365 的网络规划和提高迁移性能的最佳实践</span><span class="sxs-lookup"><span data-stu-id="4922e-129">Best practices for network planning and improving migration performance for Office 365</span></span>
<span data-ttu-id="4922e-130"><a name="BestPractices"> </a></span><span class="sxs-lookup"><span data-stu-id="4922e-130"><a name="BestPractices"> </a></span></span>

<span data-ttu-id="4922e-131">深入了解这些最佳实践，详细了解如何改善 Office 365 体验。</span><span class="sxs-lookup"><span data-stu-id="4922e-131">Dig a little deeper into these best practices for more information about improving your Office 365 experience.</span></span>
  
1. <span data-ttu-id="4922e-132">想要开始帮助你的用户吗？</span><span class="sxs-lookup"><span data-stu-id="4922e-132">Want to get started helping your users right away?</span></span> <span data-ttu-id="4922e-133">请参阅在慢速网络上使用 [Office 365](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) 的最佳实践，了解在网络未运行时使用 Office 365（包括 SharePoint Online、Exchange Online 和 Lync Online）的提示。</span><span class="sxs-lookup"><span data-stu-id="4922e-133">See [Best practices for using Office 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) for tips on using Office 365, including SharePoint Online, Exchange Online, and Lync Online, when your network just isn't cooperating.</span></span> <span data-ttu-id="4922e-134">本文链接到 TechNet 和 Support.office.com 上用于优化 Office 365 体验的内容加载，并包括有关自定义网页的简便方法以及如何设置 Internet Explorer 设置以获得最佳 Office 365 体验的信息。</span><span class="sxs-lookup"><span data-stu-id="4922e-134">This article links out to loads of content on TechNet and Support.office.com for optimizing your Office 365 experience and includes information on easy ways to customize your web pages and how to set your Internet Explorer settings for the best Office 365 experience.</span></span> 
    
2. <span data-ttu-id="4922e-135">阅读 [Office 365](./microsoft-365-network-connectivity-principles.md) 网络连接原则，了解安全管理 Office 365 流量和获得最佳性能的连接原则。</span><span class="sxs-lookup"><span data-stu-id="4922e-135">Read [Office 365 Network Connectivity Principles](./microsoft-365-network-connectivity-principles.md) to understand the connectivity principles for securely managing Office 365 traffic and getting the best possible performance.</span></span> <span data-ttu-id="4922e-136">本文将帮助你了解有关安全优化 Office 365 网络连接的最新指南。</span><span class="sxs-lookup"><span data-stu-id="4922e-136">This article will help you understand the most recent guidance for securely optimizing Office 365 network connectivity.</span></span> 
    
3. <span data-ttu-id="4922e-137">通过仔细管理 Windows 更新的计划来提高邮件迁移性能。</span><span class="sxs-lookup"><span data-stu-id="4922e-137">Improve mail migration performance by carefully managing the schedule for Windows Updates.</span></span> <span data-ttu-id="4922e-138">可以分批更新客户端计算机，并确保在迁移到 Office 365 之前更新所有客户端计算机，以控制网络带宽的使用。</span><span class="sxs-lookup"><span data-stu-id="4922e-138">You can update your client computers in batches and ensure that all client computers are updated before migrating to Office 365 to regulate the use of network bandwidth.</span></span> <span data-ttu-id="4922e-139">有关详细信息，请参阅 [Manually update and configure desktops for Office 365获取最新更新](https://support.microsoft.com/gp/office-2013-365-update)。</span><span class="sxs-lookup"><span data-stu-id="4922e-139">For more information, see [Manually update and configure desktops for Office 365 for the latest updates](https://support.microsoft.com/gp/office-2013-365-update).</span></span>
    
4. <span data-ttu-id="4922e-140">当 Office 365 网络流量被视为受信任的 Internet 服务并允许绕过大部分传统筛选和扫描（某些组织将网络流量放在不受信任的 Internet 服务上）时，其性能最佳。</span><span class="sxs-lookup"><span data-stu-id="4922e-140">Office 365 network traffic performs best when it's treated as a trusted Internet service and allowed to bypass much of the traditional filtering and scanning that some organizations place on network traffic to untrusted Internet services.</span></span> <span data-ttu-id="4922e-141">这通常包括删除代理用户身份验证和数据包检查等出站处理，以及确保具有正确的网络地址转换 (NAT) 和足够的带宽容量来处理增加的网络请求的本地 Internet 出口。</span><span class="sxs-lookup"><span data-stu-id="4922e-141">This typically includes removing outbound processing such as proxy user authentication and packet inspection, as well as ensuring local egress to the Internet with the proper Network Address Translation (NAT) and enough bandwidth capacity to handle the increased network requests.</span></span> <span data-ttu-id="4922e-142">有关配置网络以将 Office 365 作为网络上受信任的 Internet 服务处理的其他指南，请参阅管理 [Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)终结点。</span><span class="sxs-lookup"><span data-stu-id="4922e-142">Refer to [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)for additional guidance on configuring your network to handle Office 365 as a trusted Internet service on your network.</span></span>
    
1. <span data-ttu-id="4922e-143">确保 [管理 Office 365 终结点](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)。</span><span class="sxs-lookup"><span data-stu-id="4922e-143">Ensure [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span> <span data-ttu-id="4922e-144">进入 Office 365 的额外流量导致出站代理连接增加，通过 TLS/SSL 的安全流量增加。</span><span class="sxs-lookup"><span data-stu-id="4922e-144">The additional traffic going to Office 365 results in an increase of outbound proxy connections as well as an increase in secure traffic over TLS/SSL.</span></span>
    
2. <span data-ttu-id="4922e-145">如果您的出站代理需要用户身份验证，则可能会遇到连接缓慢或功能丢失的问题。</span><span class="sxs-lookup"><span data-stu-id="4922e-145">If your outbound proxies require user authentication you may experience slow connectivity or a loss of functionality.</span></span> <span data-ttu-id="4922e-146">绕过 Office 365 域的身份验证要求可降低此开销。</span><span class="sxs-lookup"><span data-stu-id="4922e-146">Bypassing the authentication requirement for the Office 365 domains can reduce this overhead.</span></span>
    
3. <span data-ttu-id="4922e-147">如果您具有大量共享日历和邮箱，您可能会看到从 Outlook 到 Exchange 的连接数增加。</span><span class="sxs-lookup"><span data-stu-id="4922e-147">If you have a large number of shared calendars and mailboxes, you may see an increase in the number of connections from Outlook to Exchange.</span></span> <span data-ttu-id="4922e-148">例如，Outlook 客户端可能会为使用的每个共享日历打开最多两个附加连接。</span><span class="sxs-lookup"><span data-stu-id="4922e-148">For instance, the Outlook client may open up to two additional connections for each shared calendar in use.</span></span> <span data-ttu-id="4922e-149">在这种情况下，请确保出口代理可以处理连接，或绕过代理连接到 Office 365 for Outlook。</span><span class="sxs-lookup"><span data-stu-id="4922e-149">In this situation, ensure that the egress proxy can handle the connections, or bypass the proxy for connections to Office 365 for Outlook.</span></span>
    
4. <span data-ttu-id="4922e-150">确定公用 IP 地址支持的最大设备数以及如何在多个 IP 地址之间实现负载平衡。</span><span class="sxs-lookup"><span data-stu-id="4922e-150">Determine the maximum number of supported devices for a public IP address and how to load balance across multiple IP addresses.</span></span> <span data-ttu-id="4922e-151">有关详细信息，请参阅[与 Office 365 的 NAT 支持](nat-support-with-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="4922e-151">For more information, see [NAT support with Office 365](nat-support-with-microsoft-365.md).</span></span>
    
5. <span data-ttu-id="4922e-152">如果要检查来自网络上的计算机的出站连接，则绕过此筛选到 Office 365 域将提高连接性和性能。</span><span class="sxs-lookup"><span data-stu-id="4922e-152">If you're inspecting outbound connections from computers on your network, bypassing this filtering to the Office 365 domains will improve connectivity and performance.</span></span> <span data-ttu-id="4922e-153">此外，绕过出站检查通常无需单个 Internet 出口，并启用发往 Office 365 的网络请求的本地 Internet 出口。</span><span class="sxs-lookup"><span data-stu-id="4922e-153">Additionally, bypassing outbound inspection often removes the need for a single Internet egress and enables local Internet egress for Office 365 destined network requests.</span></span>
    
6. <span data-ttu-id="4922e-154">一些客户发现内部网络设置可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="4922e-154">Some customers find internal network settings may affect performance.</span></span> <span data-ttu-id="4922e-155">诸如最大传输单元 (MTU) 大小、网络自动协商或自动检测以及到 Internet 的次最佳路由等设置是常见的查找位置。</span><span class="sxs-lookup"><span data-stu-id="4922e-155">Settings such as maximum transmission unit (MTU) size, network auto-negotiation or auto-detection, and sub-optimal routes to the Internet are common places to look.</span></span>
    
## <a name="network-planning-reference-for-office-365"></a><span data-ttu-id="4922e-156">Office 365 的网络规划参考</span><span class="sxs-lookup"><span data-stu-id="4922e-156">Network planning reference for Office 365</span></span>
<span data-ttu-id="4922e-157"><a name="NetReference"> </a></span><span class="sxs-lookup"><span data-stu-id="4922e-157"><a name="NetReference"> </a></span></span>

<span data-ttu-id="4922e-158">这些主题包含详细的 Office 365 网络参考信息。</span><span class="sxs-lookup"><span data-stu-id="4922e-158">These topics contain detailed Office 365 network reference information.</span></span>
  
- [<span data-ttu-id="4922e-159">管理 Office 365 终结点</span><span class="sxs-lookup"><span data-stu-id="4922e-159">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [<span data-ttu-id="4922e-160">内容分发网络</span><span class="sxs-lookup"><span data-stu-id="4922e-160">Content delivery networks</span></span>](content-delivery-networks.md)
    
- [<span data-ttu-id="4922e-161">Office 365 的外部域名系统记录</span><span class="sxs-lookup"><span data-stu-id="4922e-161">External Domain Name System records for Office 365</span></span>](external-domain-name-system-records.md)
    
- [<span data-ttu-id="4922e-162">Office 365 服务中的 IPv6 支持</span><span class="sxs-lookup"><span data-stu-id="4922e-162">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
    
- [<span data-ttu-id="4922e-163">Office 365 网络连接原则</span><span class="sxs-lookup"><span data-stu-id="4922e-163">Office 365 Network Connectivity Principles</span></span>](./microsoft-365-network-connectivity-principles.md)
    
- [<span data-ttu-id="4922e-164">Office 365 视频网络常见问题解答 (常见问题) </span><span class="sxs-lookup"><span data-stu-id="4922e-164">Office 365 video networking Frequently Asked Questions (FAQ)</span></span>](office-365-video-networking-faq.md)
    
- [<span data-ttu-id="4922e-165">有关连接到 Office 365 服务的网络设备的计划</span><span class="sxs-lookup"><span data-stu-id="4922e-165">Plan for network devices that connect to Office 365 services</span></span>](plan-for-network-devices.md)
    
- [<span data-ttu-id="4922e-166">Office 365 服务的设置指南</span><span class="sxs-lookup"><span data-stu-id="4922e-166">Setup guides for Office 365 services</span></span>](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a><span data-ttu-id="4922e-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4922e-167">See also</span></span>

[<span data-ttu-id="4922e-168">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="4922e-168">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)