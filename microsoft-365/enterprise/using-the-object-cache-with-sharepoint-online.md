---
title: 在 SharePoint Online 中使用对象缓存
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: 本文介绍了在 SharePoint Server 2013 内部部署和 SharePoint Online 中使用对象缓存的区别。
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695507"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="68b67-103">在 SharePoint Online 中使用对象缓存</span><span class="sxs-lookup"><span data-stu-id="68b67-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="68b67-104">本文介绍了在 SharePoint Server 2013 内部部署和 SharePoint Online 中使用对象缓存的区别。</span><span class="sxs-lookup"><span data-stu-id="68b67-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="68b67-105">在 SharePoint Online 部署中依赖对象缓存SharePoint负面影响。</span><span class="sxs-lookup"><span data-stu-id="68b67-105">There is significant negative impact of relying on the object cache in SharePoint Online deployment.</span></span> <span data-ttu-id="68b67-106">对 SharePoint Online 中对象缓存的任何依赖都将降低页面的可靠性。</span><span class="sxs-lookup"><span data-stu-id="68b67-106">Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="68b67-107">SharePoint Online 和 SharePoint Server 2013 对象缓存的工作原理</span><span class="sxs-lookup"><span data-stu-id="68b67-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="68b67-108">当 SharePoint Server 2013 在本地托管时，客户具有承载对象缓存的专用前端 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="68b67-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="68b67-109">这意味着缓存专用于一个客户，并且仅受可用内存量和分配给对象缓存的内存量限制。</span><span class="sxs-lookup"><span data-stu-id="68b67-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="68b67-110">由于在本地方案中仅服务于一个客户，因此前端 Web 服务器通常让用户不断向同一网站提出请求。</span><span class="sxs-lookup"><span data-stu-id="68b67-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="68b67-111">这意味着缓存可以快速已满，并保留完整的列表查询结果SharePoint用户定期请求的对象。</span><span class="sxs-lookup"><span data-stu-id="68b67-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![显示内部部署前端 Web 服务器的流量和负载](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="68b67-113">因此，用户第二次访问页面时，页面加载时间会改进。</span><span class="sxs-lookup"><span data-stu-id="68b67-113">As a result, the second time a user visits a page, the page load time improves.</span></span> <span data-ttu-id="68b67-114">同一页面至少加载四次后，该页面将缓存在所有前端 Web 服务器上。</span><span class="sxs-lookup"><span data-stu-id="68b67-114">After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="68b67-115">相比之下，SharePoint Online 中，服务器更多，站点也更多。</span><span class="sxs-lookup"><span data-stu-id="68b67-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="68b67-116">每个用户可能连接到未填充缓存的不同前端 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="68b67-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="68b67-117">或者，缓存可能确实为服务器填充，但该前端 Web 服务器的下一个用户从另一个网站请求页面。</span><span class="sxs-lookup"><span data-stu-id="68b67-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="68b67-118">或者，即使下一位用户请求与上次访问时相同的页面，他们也可以负载平衡到缓存中没有该页面的不同前端 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="68b67-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="68b67-119">在上一种情况下，缓存对用户没有帮助。</span><span class="sxs-lookup"><span data-stu-id="68b67-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="68b67-120">在下图中，每个点表示用户正在请求的页面及其缓存位置。</span><span class="sxs-lookup"><span data-stu-id="68b67-120">In the following figure, each dot represents a page that a user is requesting and where it cached.</span></span> <span data-ttu-id="68b67-121">不同的颜色表示共享使用 SaaS 基础结构的不同客户。</span><span class="sxs-lookup"><span data-stu-id="68b67-121">Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![显示 SharePoint Online 中的对象缓存结果](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="68b67-123">从图中可以看到，任何给定用户使用其页面的缓存版本命中服务器的可能性是一种希望。</span><span class="sxs-lookup"><span data-stu-id="68b67-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="68b67-124">此外，由于吞吐量较大，并且服务器在许多网站之间共享，缓存不会持续很长时间，因为缓存的空间不足，</span><span class="sxs-lookup"><span data-stu-id="68b67-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="68b67-125">出于所有这些原因，依赖用户获取缓存对象不是确保 SharePoint Online 中用户体验和页面加载时间的有效方法。</span><span class="sxs-lookup"><span data-stu-id="68b67-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="68b67-126">如果无法依赖对象缓存来提高 SharePoint Online 中的性能，我们改为使用什么？</span><span class="sxs-lookup"><span data-stu-id="68b67-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="68b67-127">由于不应依赖 SharePoint Online 中的缓存，因此应该评估使用对象缓存SharePoint自定义项的替代设计方法。</span><span class="sxs-lookup"><span data-stu-id="68b67-127">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache.</span></span> <span data-ttu-id="68b67-128">这意味着使用不依赖于对象缓存的性能问题的方法，以便为用户提供良好的结果。</span><span class="sxs-lookup"><span data-stu-id="68b67-128">This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users.</span></span> <span data-ttu-id="68b67-129">本系列的一些其他文章中对此进行了介绍，其中包括：</span><span class="sxs-lookup"><span data-stu-id="68b67-129">This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="68b67-130">SharePoint Online 的导航选项</span><span class="sxs-lookup"><span data-stu-id="68b67-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="68b67-131">SharePoint Online 中的缩小和捆绑</span><span class="sxs-lookup"><span data-stu-id="68b67-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="68b67-132">结合使用 Office 365 内容分发网络和 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68b67-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="68b67-133">在 SharePoint Online 中延迟加载图像和 JavaScript</span><span class="sxs-lookup"><span data-stu-id="68b67-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

