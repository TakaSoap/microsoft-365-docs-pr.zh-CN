---
title: SharePoint Online 性能调整简介
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: 本文介绍了在 SharePoint Online 中设计页面时需要考虑的特定方面。
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909734"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="a2957-103">SharePoint Online 性能优化简介</span><span class="sxs-lookup"><span data-stu-id="a2957-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="a2957-104">本文介绍了在 SharePoint Online 中设计页面时需要考虑的特定方面。</span><span class="sxs-lookup"><span data-stu-id="a2957-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="a2957-105">SharePoint联机指标</span><span class="sxs-lookup"><span data-stu-id="a2957-105">SharePoint Online metrics</span></span>

<span data-ttu-id="a2957-106">以下适用于 SharePoint Online 的广泛指标提供有关性能的真实数据：</span><span class="sxs-lookup"><span data-stu-id="a2957-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="a2957-107">页面加载速度</span><span class="sxs-lookup"><span data-stu-id="a2957-107">How fast pages load</span></span>
    
- <span data-ttu-id="a2957-108">每页需要多少个往返行程</span><span class="sxs-lookup"><span data-stu-id="a2957-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="a2957-109">服务问题</span><span class="sxs-lookup"><span data-stu-id="a2957-109">Issues with the service</span></span>
    
- <span data-ttu-id="a2957-110">导致性能降低的其他情况</span><span class="sxs-lookup"><span data-stu-id="a2957-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="a2957-111">由于数据而得出结论</span><span class="sxs-lookup"><span data-stu-id="a2957-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="a2957-112">数据告诉我们：</span><span class="sxs-lookup"><span data-stu-id="a2957-112">The data tells us:</span></span>
  
- <span data-ttu-id="a2957-113">大多数页面在 SharePoint Online 上运行良好。</span><span class="sxs-lookup"><span data-stu-id="a2957-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="a2957-114">非自定义页面加载速度非常快。</span><span class="sxs-lookup"><span data-stu-id="a2957-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="a2957-115">OneDrive for Business、工作组网站和系统页面（_layouts等）都可以快速加载。</span><span class="sxs-lookup"><span data-stu-id="a2957-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="a2957-116">最慢的 1% SharePoint Online 页面的加载时间超过 5，000 毫秒。</span><span class="sxs-lookup"><span data-stu-id="a2957-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="a2957-117">可以使用的一个简单的基准测试是，通过将您自己的门户的加载时间与 OneDrive for Business 主页的加载时间进行比较来测量性能，因为它使用很少的自定义功能。</span><span class="sxs-lookup"><span data-stu-id="a2957-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="a2957-118">这通常是在解决网络性能问题时支持会要求你完成的第一步。</span><span class="sxs-lookup"><span data-stu-id="a2957-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="a2957-119">检查性能时使用标准用户帐户</span><span class="sxs-lookup"><span data-stu-id="a2957-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="a2957-120">网站集管理员、网站所有者、编辑者或参与者属于其他安全组，具有其他权限，因此具有可SharePoint加载的其他元素。</span><span class="sxs-lookup"><span data-stu-id="a2957-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="a2957-121">这适用于本地SharePoint和 SharePoint Online，但在本地方案中，差异不会像 SharePoint Online 中一样容易注意到。</span><span class="sxs-lookup"><span data-stu-id="a2957-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="a2957-122">为了正确评估页面将如何为用户执行，您应该使用标准用户帐户，以避免加载创作控件和安全组相关的其他通信。</span><span class="sxs-lookup"><span data-stu-id="a2957-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="a2957-123">用于性能调整的连接类别</span><span class="sxs-lookup"><span data-stu-id="a2957-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="a2957-124">可以将服务器和用户之间的连接分为三个主要组件。</span><span class="sxs-lookup"><span data-stu-id="a2957-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="a2957-125">在设计联机页面时SharePoint这些页面，以深入了解加载时间。</span><span class="sxs-lookup"><span data-stu-id="a2957-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="a2957-126">**服务器** Microsoft 在数据中心托管的服务器。</span><span class="sxs-lookup"><span data-stu-id="a2957-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="a2957-127">**网络** 数据中心和用户之间的 Microsoft 网络、Internet 和本地网络。</span><span class="sxs-lookup"><span data-stu-id="a2957-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="a2957-128">**浏览器** 页面的加载位置。</span><span class="sxs-lookup"><span data-stu-id="a2957-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="a2957-129">在这三个连接中，通常有五个原因会导致 95% 的页面变慢。</span><span class="sxs-lookup"><span data-stu-id="a2957-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="a2957-130">本文将讨论其中每个原因：</span><span class="sxs-lookup"><span data-stu-id="a2957-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="a2957-131">导航问题</span><span class="sxs-lookup"><span data-stu-id="a2957-131">Navigation issues</span></span>
    
- <span data-ttu-id="a2957-132">内容汇总</span><span class="sxs-lookup"><span data-stu-id="a2957-132">Content roll up</span></span>
    
- <span data-ttu-id="a2957-133">大文件</span><span class="sxs-lookup"><span data-stu-id="a2957-133">Large files</span></span>
    
- <span data-ttu-id="a2957-134">对服务器的许多请求</span><span class="sxs-lookup"><span data-stu-id="a2957-134">Many requests to the server</span></span>
    
- <span data-ttu-id="a2957-135">Web 部件处理</span><span class="sxs-lookup"><span data-stu-id="a2957-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="a2957-136">服务器连接</span><span class="sxs-lookup"><span data-stu-id="a2957-136">Server connection</span></span>

<span data-ttu-id="a2957-137">影响本地部署SharePoint的很多问题也适用于 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="a2957-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="a2957-138">正如您预期，您可以更加控制服务器使用本地部署SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a2957-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="a2957-139">使用 SharePoint Online，内容会有所不同。</span><span class="sxs-lookup"><span data-stu-id="a2957-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="a2957-140">服务器执行的工作越多，呈现页面所花的时间越长。</span><span class="sxs-lookup"><span data-stu-id="a2957-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="a2957-141">使用SharePoint，这一方面的最大原因就是包含多个 Web 部件的复杂页面。</span><span class="sxs-lookup"><span data-stu-id="a2957-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="a2957-142">SharePoint服务器本地</span><span class="sxs-lookup"><span data-stu-id="a2957-142">SharePoint Server on-premises</span></span>
  
![内部部署服务器的屏幕截图](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="a2957-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a2957-144">SharePoint Online</span></span>
  
![联机服务器的屏幕截图](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="a2957-146">使用 SharePoint Online，某些页面请求可能最终调用多个服务器。</span><span class="sxs-lookup"><span data-stu-id="a2957-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="a2957-147">最终，您可以为单个请求在服务器之间创建一个请求矩阵。</span><span class="sxs-lookup"><span data-stu-id="a2957-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="a2957-148">从页面加载的角度来看，这些交互成本很高，并且会使情况变慢。</span><span class="sxs-lookup"><span data-stu-id="a2957-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="a2957-149">这些服务器与服务器交互的示例包括：</span><span class="sxs-lookup"><span data-stu-id="a2957-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="a2957-150">Web 到 SQL 服务器</span><span class="sxs-lookup"><span data-stu-id="a2957-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="a2957-151">Web 到应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="a2957-151">Web to application servers</span></span>
    
<span data-ttu-id="a2957-152">另一个会降低服务器交互速度的方面是缓存丢失。</span><span class="sxs-lookup"><span data-stu-id="a2957-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="a2957-153">与本地SharePoint不同，您命中之前访问的页面的同一服务器的可能性非常小;这使得对象缓存过时。</span><span class="sxs-lookup"><span data-stu-id="a2957-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="a2957-154">网络连接</span><span class="sxs-lookup"><span data-stu-id="a2957-154">Network connection</span></span>

<span data-ttu-id="a2957-155">对于不使用 WAN SharePoint本地服务器，您可以在数据中心和最终用户之间使用高速连接。</span><span class="sxs-lookup"><span data-stu-id="a2957-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="a2957-156">通常，从网络角度来说，操作很容易管理。</span><span class="sxs-lookup"><span data-stu-id="a2957-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="a2957-157">对于 SharePoint Online，还有一些要考虑的因素;例如：</span><span class="sxs-lookup"><span data-stu-id="a2957-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="a2957-158">Microsoft 网络</span><span class="sxs-lookup"><span data-stu-id="a2957-158">The Microsoft network</span></span>
    
- <span data-ttu-id="a2957-159">The Internet</span><span class="sxs-lookup"><span data-stu-id="a2957-159">The Internet</span></span>
    
- <span data-ttu-id="a2957-160">The ISP</span><span class="sxs-lookup"><span data-stu-id="a2957-160">The ISP</span></span>
    
<span data-ttu-id="a2957-161">无论使用哪个SharePoint (以及) 网络，通常会导致网络繁忙的事情包括：</span><span class="sxs-lookup"><span data-stu-id="a2957-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="a2957-162">大型负载</span><span class="sxs-lookup"><span data-stu-id="a2957-162">Large payload</span></span>
    
- <span data-ttu-id="a2957-163">许多文件</span><span class="sxs-lookup"><span data-stu-id="a2957-163">Many files</span></span>
    
- <span data-ttu-id="a2957-164">与服务器的物理距离较大</span><span class="sxs-lookup"><span data-stu-id="a2957-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="a2957-165">Microsoft SharePoint Online 中可以利用的一CDN (内容分发网络) 。</span><span class="sxs-lookup"><span data-stu-id="a2957-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="a2957-166">一CDN基本上是跨多个数据中心部署的服务器的分布式集合。</span><span class="sxs-lookup"><span data-stu-id="a2957-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="a2957-167">使用 CDN，即使客户端与原始 SharePoint 服务器距离非常远，页面上的内容也可以托管在靠近客户端的服务器上。</span><span class="sxs-lookup"><span data-stu-id="a2957-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="a2957-168">Microsoft 将在将来使用此功能来存储无法自定义的页面的本地实例，例如 SharePoint Online 管理员主页。</span><span class="sxs-lookup"><span data-stu-id="a2957-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="a2957-169">有关 CDN 的信息，请参阅内容 [交付网络](content-delivery-networks.md)。</span><span class="sxs-lookup"><span data-stu-id="a2957-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="a2957-170">需要注意但可能无法执行很多工作的是 ISP 的连接速度。</span><span class="sxs-lookup"><span data-stu-id="a2957-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="a2957-171">简单的速度测试工具将告知你连接速度。</span><span class="sxs-lookup"><span data-stu-id="a2957-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="a2957-172">浏览器连接</span><span class="sxs-lookup"><span data-stu-id="a2957-172">Browser connection</span></span>

<span data-ttu-id="a2957-173">从性能角度考虑 Web 浏览器有几个因素。</span><span class="sxs-lookup"><span data-stu-id="a2957-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="a2957-174">访问复杂页面会影响性能。</span><span class="sxs-lookup"><span data-stu-id="a2957-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="a2957-175">大多数浏览器只有一个小型缓存 (大约 90 MB) ，而平均网页通常约为 1.6 MB。</span><span class="sxs-lookup"><span data-stu-id="a2957-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="a2957-176">这不会花很长时间就用不上。</span><span class="sxs-lookup"><span data-stu-id="a2957-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="a2957-177">带宽也可能成为问题。</span><span class="sxs-lookup"><span data-stu-id="a2957-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="a2957-178">例如，如果用户在另一个会话中观看视频，这将影响你的SharePoint性能。</span><span class="sxs-lookup"><span data-stu-id="a2957-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="a2957-179">虽然无法阻止用户流式传输媒体，但可以控制页面加载用户的方式。</span><span class="sxs-lookup"><span data-stu-id="a2957-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="a2957-180">请查看以下文章，了解不同的 SharePoint Online 页面自定义技术和其他最佳做法，以帮助你实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="a2957-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="a2957-181">SharePoint Online 的导航选项</span><span class="sxs-lookup"><span data-stu-id="a2957-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="a2957-182">使用适用于 SharePoint Online 的页面诊断工具</span><span class="sxs-lookup"><span data-stu-id="a2957-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="a2957-183">SharePoint Online 的图像优化</span><span class="sxs-lookup"><span data-stu-id="a2957-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="a2957-184">在 SharePoint Online 中延迟加载图像和 JavaScript</span><span class="sxs-lookup"><span data-stu-id="a2957-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="a2957-185">SharePoint Online 中的缩小和捆绑</span><span class="sxs-lookup"><span data-stu-id="a2957-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="a2957-186">结合使用 Office 365 内容分发网络和 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a2957-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="a2957-187">使用内容搜索Web 部件而不是内容Web 部件来改进 SharePoint Online 中的性能</span><span class="sxs-lookup"><span data-stu-id="a2957-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="a2957-188">容量规划和负载测试 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a2957-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="a2957-189">诊断 SharePoint Online 性能问题</span><span class="sxs-lookup"><span data-stu-id="a2957-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="a2957-190">在 SharePoint Online 中使用对象缓存</span><span class="sxs-lookup"><span data-stu-id="a2957-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="a2957-191">如何：避免在 SharePoint Online 中受限制或被阻止</span><span class="sxs-lookup"><span data-stu-id="a2957-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
