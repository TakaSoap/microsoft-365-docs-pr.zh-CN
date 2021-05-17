---
title: SharePoint Online 的导航选项
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: 本文介绍在 SharePoint Online 中启用了 SharePoint Publishing 的导航SharePoint网站。
ms.openlocfilehash: b5989bf26ebf7bb1452f983af89a6e6739821d53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923620"
---
# <a name="navigation-options-for-sharepoint-online"></a><span data-ttu-id="15c80-103">SharePoint Online 的导航选项</span><span class="sxs-lookup"><span data-stu-id="15c80-103">Navigation options for SharePoint Online</span></span>

<span data-ttu-id="15c80-104">本文介绍在 SharePoint Online 中启用了 SharePoint Publishing 的导航SharePoint网站。</span><span class="sxs-lookup"><span data-stu-id="15c80-104">This article describes navigation options sites with SharePoint Publishing enabled in SharePoint Online.</span></span> <span data-ttu-id="15c80-105">导航的选择和配置会显著影响 SharePoint Online 中的网站的性能和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="15c80-105">The choice and configuration of navigation significantly impacts the performance and scalability of sites in SharePoint Online.</span></span> <span data-ttu-id="15c80-106">只有在SharePoint门户需要时，才应使用"发布网站模板"，并且发布功能应仅在特定网站上启用，并且仅在绝对需要时使用，因为它在错误使用时可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="15c80-106">The SharePoint Publishing site template should only be used if required for a centralized portal and the publishing feature should only be enabled on specific sites and only when absolutely required as it can impact performance when used incorrectly.</span></span>

>[!NOTE]
><span data-ttu-id="15c80-107">如果你使用的是新式导航导航SharePoint如大型菜单、级联导航或中心导航，本文不适用于你的网站。</span><span class="sxs-lookup"><span data-stu-id="15c80-107">If you're using modern SharePoint navigation options like mega menu, cascading navigation, or hub navigation, this article does not apply to your site.</span></span> <span data-ttu-id="15c80-108">新式SharePoint网站体系结构利用更平展的网站层次结构和中心分支模型。</span><span class="sxs-lookup"><span data-stu-id="15c80-108">Modern SharePoint site architectures leverage a more flattened site hierarchy and a hub-and-spoke model.</span></span> <span data-ttu-id="15c80-109">这可以实现许多不需要使用"发布"功能SharePoint方案。</span><span class="sxs-lookup"><span data-stu-id="15c80-109">This allows many scenarios to be achieved that do NOT require use of the SharePoint Publishing feature.</span></span>

## <a name="overview-of-navigation-options"></a><span data-ttu-id="15c80-110">导航选项概述</span><span class="sxs-lookup"><span data-stu-id="15c80-110">Overview of navigation options</span></span>

<span data-ttu-id="15c80-111">导航提供程序配置会显著影响整个网站的性能，必须仔细考虑如何选择可有效扩展的导航提供程序和配置，从而满足网站SharePoint要求。</span><span class="sxs-lookup"><span data-stu-id="15c80-111">Navigation provider configuration can significantly impact performance for the entire site, and careful consideration must be taken to pick a navigation provider and configuration that scales effectively for the requirements of a SharePoint site.</span></span> <span data-ttu-id="15c80-112">有两个开箱即用导航提供程序以及自定义导航实现。</span><span class="sxs-lookup"><span data-stu-id="15c80-112">There are two out-of-the-box navigation providers, as well as custom navigation implementations.</span></span>

<span data-ttu-id="15c80-113">如果为网站启用 [](#using-structural-navigation-in-sharepoint-online)结构导航缓存，则第一个选项"结构导航"是 SharePoint Online 中推荐用于经典 Sharepoint 网站的 **导航选项**。</span><span class="sxs-lookup"><span data-stu-id="15c80-113">The first option, [**Structural navigation**](#using-structural-navigation-in-sharepoint-online), is the recommended navigation option in SharePoint Online for classic Sharepoint sites, **if you turn on structural navigation caching for your site**.</span></span> <span data-ttu-id="15c80-114">此导航提供程序显示当前网站下方的导航项目，也可以选择显示当前网站及其同级网站。</span><span class="sxs-lookup"><span data-stu-id="15c80-114">This navigation provider displays the navigation items below the current site, and optionally the current site and its siblings.</span></span> <span data-ttu-id="15c80-115">它提供其他功能，如安全修整和网站结构枚举。</span><span class="sxs-lookup"><span data-stu-id="15c80-115">It provides additional capabilities such as security trimming and site structure enumeration.</span></span> <span data-ttu-id="15c80-116">如果禁用缓存，这将对性能和可伸缩性产生负面影响，并且可能会受到限制。</span><span class="sxs-lookup"><span data-stu-id="15c80-116">If caching is disabled, this will negatively impact performance and scalability, and may be subject to throttling.</span></span>

<span data-ttu-id="15c80-117">第二个选项 Managed [**(Metadata) 表示**](#using-managed-navigation-and-metadata-in-sharepoint-online)使用托管元数据术语集的导航项。</span><span class="sxs-lookup"><span data-stu-id="15c80-117">The second option, [**Managed (Metadata) navigation**](#using-managed-navigation-and-metadata-in-sharepoint-online), represents navigation items using a Managed Metadata term set.</span></span> <span data-ttu-id="15c80-118">建议禁用安全修整，除非需要。</span><span class="sxs-lookup"><span data-stu-id="15c80-118">We recommend that security trimming be disabled unless required.</span></span> <span data-ttu-id="15c80-119">安全修整作为此导航提供程序的默认设置启用;但是，许多网站不需要安全修整开销，因为导航元素对于网站的所有用户通常都是一致的。</span><span class="sxs-lookup"><span data-stu-id="15c80-119">Security trimming is enabled as a secure-by-default setting for this navigation provider; however, many sites do not require the overhead of security trimming since navigation elements often are consistent for all users of the site.</span></span> <span data-ttu-id="15c80-120">使用禁用安全修整的建议配置，此导航提供程序不需要枚举网站结构，并且可扩展性高，并且对性能产生可接受的影响。</span><span class="sxs-lookup"><span data-stu-id="15c80-120">With the recommended configuration to disable security trimming, this navigation provider does not require enumerating site structure and is highly scalable with acceptable performance impact.</span></span>

<span data-ttu-id="15c80-121">除了开箱即用导航提供程序之外，许多客户还成功实现了替代自定义导航实现。</span><span class="sxs-lookup"><span data-stu-id="15c80-121">In addition to the out-of-the-box navigation providers, many customers have successfully implemented alternative custom navigation implementations.</span></span> <span data-ttu-id="15c80-122">请参阅 [本文中的搜索驱动](#using-search-driven-client-side-scripting) 客户端脚本。</span><span class="sxs-lookup"><span data-stu-id="15c80-122">See [Search-driven client-side scripting](#using-search-driven-client-side-scripting) in this article.</span></span>
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a><span data-ttu-id="15c80-123">联机导航选项SharePoint优缺点</span><span class="sxs-lookup"><span data-stu-id="15c80-123">Pros and Cons of SharePoint Online navigation options</span></span>

<span data-ttu-id="15c80-124">下表总结了每个选项的优缺点。</span><span class="sxs-lookup"><span data-stu-id="15c80-124">The following table summarizes the pros and cons of each option.</span></span>

|<span data-ttu-id="15c80-125">结构导航</span><span class="sxs-lookup"><span data-stu-id="15c80-125">Structural navigation</span></span>  |<span data-ttu-id="15c80-126">托管导航</span><span class="sxs-lookup"><span data-stu-id="15c80-126">Managed navigation</span></span>  |<span data-ttu-id="15c80-127">搜索驱动的导航</span><span class="sxs-lookup"><span data-stu-id="15c80-127">Search-driven navigation</span></span>  |<span data-ttu-id="15c80-128">自定义导航提供程序</span><span class="sxs-lookup"><span data-stu-id="15c80-128">Custom-navigation provider</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="15c80-129">优点：</span><span class="sxs-lookup"><span data-stu-id="15c80-129">Pros:</span></span><br/><br/><span data-ttu-id="15c80-130">易于维护</span><span class="sxs-lookup"><span data-stu-id="15c80-130">Easy to maintain</span></span><br/><span data-ttu-id="15c80-131">经过安全修整</span><span class="sxs-lookup"><span data-stu-id="15c80-131">Security trimmed</span></span><br/><span data-ttu-id="15c80-132">内容更改后 24 小时内自动更新</span><span class="sxs-lookup"><span data-stu-id="15c80-132">Automatically updates within 24 hours when content is changed</span></span><br/>     |<span data-ttu-id="15c80-133">优点：</span><span class="sxs-lookup"><span data-stu-id="15c80-133">Pros:</span></span><br/><br/><span data-ttu-id="15c80-134">易于维护</span><span class="sxs-lookup"><span data-stu-id="15c80-134">Easy to maintain</span></span><br/>|<span data-ttu-id="15c80-135">优点：</span><span class="sxs-lookup"><span data-stu-id="15c80-135">Pros:</span></span><br/><br/><span data-ttu-id="15c80-136">经过安全修整</span><span class="sxs-lookup"><span data-stu-id="15c80-136">Security trimmed</span></span><br/><span data-ttu-id="15c80-137">添加网站时自动更新</span><span class="sxs-lookup"><span data-stu-id="15c80-137">Automatically updates as sites are added</span></span><br/><span data-ttu-id="15c80-138">加载时间和本地缓存的导航结构</span><span class="sxs-lookup"><span data-stu-id="15c80-138">Fast loading time and locally cached navigation structure</span></span><br/>|<span data-ttu-id="15c80-139">优点：</span><span class="sxs-lookup"><span data-stu-id="15c80-139">Pros:</span></span><br/><br/><span data-ttu-id="15c80-140">可用选项的更多选择</span><span class="sxs-lookup"><span data-stu-id="15c80-140">Wider choice of options available</span></span><br/><span data-ttu-id="15c80-141">正确使用缓存时快速加载</span><span class="sxs-lookup"><span data-stu-id="15c80-141">Fast loading when caching is used correctly</span></span><br/><span data-ttu-id="15c80-142">许多选项都很好地用于响应式页面设计</span><span class="sxs-lookup"><span data-stu-id="15c80-142">Many options work well with responsive page design</span></span><br/>|
|<span data-ttu-id="15c80-143">缺点：</span><span class="sxs-lookup"><span data-stu-id="15c80-143">Cons:</span></span><br/><br/><span data-ttu-id="15c80-144">**如果禁用缓存，则影响性能**</span><span class="sxs-lookup"><span data-stu-id="15c80-144">**Impacts performance if caching is disabled**</span></span><br/><span data-ttu-id="15c80-145">受限制</span><span class="sxs-lookup"><span data-stu-id="15c80-145">Subject to throttling</span></span><br/>|<span data-ttu-id="15c80-146">缺点：</span><span class="sxs-lookup"><span data-stu-id="15c80-146">Cons:</span></span><br/><br/><span data-ttu-id="15c80-147">不自动更新以反映网站结构</span><span class="sxs-lookup"><span data-stu-id="15c80-147">Not automatically updated to reflect site structure</span></span><br/><span data-ttu-id="15c80-148">**如果启用安全修整或** 导航结构复杂，则会影响性能</span><span class="sxs-lookup"><span data-stu-id="15c80-148">**Impacts performance if security trimming is enabled** or when navigation structure is complex</span></span><br/>|<span data-ttu-id="15c80-149">缺点：</span><span class="sxs-lookup"><span data-stu-id="15c80-149">Cons:</span></span><br/><br/><span data-ttu-id="15c80-150">无法轻松对网站排序</span><span class="sxs-lookup"><span data-stu-id="15c80-150">No ability to easily order sites</span></span><br/><span data-ttu-id="15c80-151">需要自定义母版页 (所需的技术) </span><span class="sxs-lookup"><span data-stu-id="15c80-151">Requires customization of the master page (technical skills required)</span></span><br/>|<span data-ttu-id="15c80-152">缺点：</span><span class="sxs-lookup"><span data-stu-id="15c80-152">Cons:</span></span><br/><br/><span data-ttu-id="15c80-153">需要自定义开发</span><span class="sxs-lookup"><span data-stu-id="15c80-153">Custom development is required</span></span><br/><span data-ttu-id="15c80-154">需要存储的外部数据源/缓存，例如 Azure</span><span class="sxs-lookup"><span data-stu-id="15c80-154">External data source / cache stored is needed e.g. Azure</span></span><br/>|

<span data-ttu-id="15c80-155">网站最适合的选项将取决于网站要求和您的技术功能。</span><span class="sxs-lookup"><span data-stu-id="15c80-155">The most appropriate option for your site will depend on your site requirements and on your technical capability.</span></span> <span data-ttu-id="15c80-156">如果需要一个易于配置的导航提供程序，该提供程序在内容更改时自动更新，则启用缓存 [的结构](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) 导航是一个不错的选择。</span><span class="sxs-lookup"><span data-stu-id="15c80-156">If you want an easy-to-configure navigation provider that automatically updates when content is changed, then structural navigation [with caching enabled](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) is a good option.</span></span>

>[!NOTE]
><span data-ttu-id="15c80-157">通过简化整体网站结构SharePoint简单化的非分层结构，应用与新式网站相同的原则可提高性能并简化向新式SharePoint迁移。</span><span class="sxs-lookup"><span data-stu-id="15c80-157">Applying the same principle as modern SharePoint sites by simplifying the overall site structure to a flatter, non-hierarchical structure improves performance and simplifies moving to modern SharePoint sites.</span></span> <span data-ttu-id="15c80-158">这意味着，一个包含数百个网站的网站集 (子网站) ，更好的方法是让许多网站集具有非常少的子网站 (子网站) 。</span><span class="sxs-lookup"><span data-stu-id="15c80-158">What this means is that instead of having a single site collection with hundreds of sites (subwebs), a better approach is to have many site collections with very few subsites (subwebs).</span></span>

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a><span data-ttu-id="15c80-159">分析 SharePoint Online 中的导航性能</span><span class="sxs-lookup"><span data-stu-id="15c80-159">Analyzing navigation performance in SharePoint Online</span></span>

<span data-ttu-id="15c80-160">适用于[SharePoint](./page-diagnostics-for-spo.md)的页面诊断工具是 Microsoft Edge 和 Chrome 浏览器的浏览器扩展，可分析 SharePoint Online 新式门户和经典发布网站页面。</span><span class="sxs-lookup"><span data-stu-id="15c80-160">The [Page Diagnostics for SharePoint tool](./page-diagnostics-for-spo.md) is a browser extension for Microsoft Edge and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="15c80-161">此工具仅适用于 SharePoint Online，不能用于 SharePoint 系统页面。</span><span class="sxs-lookup"><span data-stu-id="15c80-161">This tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="15c80-162">该工具将针对每个分析的页面生成一个报告，其中显示页面如何针对预定义的规则集执行，并显示测试的结果超出基线值时的详细信息。</span><span class="sxs-lookup"><span data-stu-id="15c80-162">The tool generates a report for each analyzed page showing how the page performs against a pre-defined set of rules and displays detailed information when results for a test fall outside the baseline value.</span></span> <span data-ttu-id="15c80-163">SharePoint联机管理员和设计人员可以使用该工具解决性能问题，以确保新页面在发布之前已经过优化。</span><span class="sxs-lookup"><span data-stu-id="15c80-163">SharePoint Online administrators and designers can use the tool to troubleshoot performance issues to ensure that new pages are optimized prior to publishing.</span></span>

<span data-ttu-id="15c80-164">**SPRequestDuration** 尤其需要一段时间SharePoint处理页面。</span><span class="sxs-lookup"><span data-stu-id="15c80-164">**SPRequestDuration** in particular is the time it takes for SharePoint to process the page.</span></span> <span data-ttu-id="15c80-165">导航 (包括导航) 、复杂网站层次结构以及其他配置和拓扑选项等大量导航功能都可能会显著延长持续时间。</span><span class="sxs-lookup"><span data-stu-id="15c80-165">Heavy navigation (like including pages in navigation), complex site hierarchies, and other configuration and topology options can all dramatically contribute to longer durations.</span></span>

## <a name="using-structural-navigation-in-sharepoint-online"></a><span data-ttu-id="15c80-166">在 SharePoint Online SharePoint导航</span><span class="sxs-lookup"><span data-stu-id="15c80-166">Using structural navigation in SharePoint Online</span></span>

<span data-ttu-id="15c80-167">这是默认情况下使用的开箱即用导航，是最直接的解决方案。</span><span class="sxs-lookup"><span data-stu-id="15c80-167">This is the out-of-the-box navigation used by default and is the most straightforward solution.</span></span> <span data-ttu-id="15c80-168">它不需要任何自定义，非技术用户还可以轻松添加项目、隐藏项目以及从设置页管理导航。</span><span class="sxs-lookup"><span data-stu-id="15c80-168">It does not require any customization and a non-technical user can also easily add items, hide items, and manage the navigation from the settings page.</span></span> <span data-ttu-id="15c80-169">我们建议 [启用缓存 ，](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)否则会进行代价高昂的性能选择。</span><span class="sxs-lookup"><span data-stu-id="15c80-169">We recommend [enabling caching](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), otherwise there is an expensive performance trade-off.</span></span>

### <a name="how-to-implement-structural-navigation-caching"></a><span data-ttu-id="15c80-170">如何实现结构导航缓存</span><span class="sxs-lookup"><span data-stu-id="15c80-170">How to implement structural navigation caching</span></span>

<span data-ttu-id="15c80-171">在 **"设置** 外观导航"下，可以验证是否选择了全局导航或当前导航  >    >  的结构导航。</span><span class="sxs-lookup"><span data-stu-id="15c80-171">Under **Site Settings** > **Look and Feel** > **Navigation**, you can validate if structural navigation is selected for either global navigation or current navigation.</span></span> <span data-ttu-id="15c80-172">选择 **"显示** 页面"将对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="15c80-172">Selecting **Show pages** will have negative impact on performance.</span></span>

![选择"显示子网站"的结构导航](../media/SPONavOptionsStructuredShowSubsites.png)

<span data-ttu-id="15c80-174">Caching网站集级别和网站级别启用或禁用网站集，并且默认情况下启用这两者。</span><span class="sxs-lookup"><span data-stu-id="15c80-174">Caching can be enabled or disabled at the site collection level and at the site level, and is enabled for both by default.</span></span> <span data-ttu-id="15c80-175">若要在网站集级别启用，请在"网站集管理设置""网站集导航"下，选中"  >    >  **启用缓存"框**。</span><span class="sxs-lookup"><span data-stu-id="15c80-175">To enable at the site collection level, under **Site Settings** > **Site Collection Administration** > **Site Collection Navigation**, check the box for **Enable caching**.</span></span>

![在网站级别启用缓存](../media/structural-nav/structural-nav-caching-site-coll.png)

<span data-ttu-id="15c80-177">若要在网站级别启用，**请在"网站** 设置  >  **导航"下** 选中"**启用缓存"框**。</span><span class="sxs-lookup"><span data-stu-id="15c80-177">To enable at the site level, under **Site Settings** > **Navigation**, check the box for **Enable caching**.</span></span>

![在网站级别启用缓存](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a><span data-ttu-id="15c80-179">在 SharePoint Online 中SharePoint导航和元数据</span><span class="sxs-lookup"><span data-stu-id="15c80-179">Using managed navigation and metadata in SharePoint Online</span></span>

<span data-ttu-id="15c80-180">托管导航是另一个开箱即用选项，可用于重新创建与结构导航相同的大部分功能。</span><span class="sxs-lookup"><span data-stu-id="15c80-180">Managed navigation is another out-of-the-box option that you can use to recreate most of the same functionality as structural navigation.</span></span> <span data-ttu-id="15c80-181">托管元数据可以配置为启用或禁用安全修整。</span><span class="sxs-lookup"><span data-stu-id="15c80-181">Managed metadata can be configured to have security trimming enabled or disabled.</span></span> <span data-ttu-id="15c80-182">在禁用安全修整的情况下配置后，托管导航会相当高效，因为它加载具有固定数量的服务器调用的所有导航链接。</span><span class="sxs-lookup"><span data-stu-id="15c80-182">When configured with security trimming disabled, managed navigation is fairly efficient as it loads all the navigation links with a constant number of server calls.</span></span> <span data-ttu-id="15c80-183">但是，启用安全修整会否定托管导航的一些性能优势。</span><span class="sxs-lookup"><span data-stu-id="15c80-183">Enabling security trimming, however, negates some of the performance advantages of managed navigation.</span></span>

<span data-ttu-id="15c80-184">如果您需要启用安全修整，我们建议您：</span><span class="sxs-lookup"><span data-stu-id="15c80-184">If you need to enable security trimming, we recommend that you:</span></span>

- <span data-ttu-id="15c80-185">将所有友好 URL 链接更新为简单链接</span><span class="sxs-lookup"><span data-stu-id="15c80-185">Update all friendly URL links to simple links</span></span>
- <span data-ttu-id="15c80-186">将所需的安全修整节点添加为友好 URL</span><span class="sxs-lookup"><span data-stu-id="15c80-186">Add required security trimming nodes as friendly URLs</span></span>
- <span data-ttu-id="15c80-187">将导航项数限制为不超过 100 个且深度不超过 3 个级别</span><span class="sxs-lookup"><span data-stu-id="15c80-187">Limit the number of navigation items to no more than 100 and no more than 3 levels deep</span></span>

<span data-ttu-id="15c80-188">许多网站不需要安全修整，因为导航结构对于网站的所有用户来说通常是一致的。</span><span class="sxs-lookup"><span data-stu-id="15c80-188">Many sites do not require security trimming, as the navigation structure is often consistent for all users of the site.</span></span> <span data-ttu-id="15c80-189">如果禁用安全修整，并且向导航添加了一个链接，但并非所有用户都有权访问该链接，该链接仍将显示，但会导致出现拒绝访问的消息。</span><span class="sxs-lookup"><span data-stu-id="15c80-189">If security trimming is disabled and a link is added to navigation that not all users have access to, the link will still show but will lead to an access denied message.</span></span> <span data-ttu-id="15c80-190">不存在意外访问内容的风险。</span><span class="sxs-lookup"><span data-stu-id="15c80-190">There is no risk of inadvertent access to the content.</span></span>

### <a name="how-to-implement-managed-navigation-and-the-results"></a><span data-ttu-id="15c80-191">如何实现托管导航和结果</span><span class="sxs-lookup"><span data-stu-id="15c80-191">How to implement managed navigation and the results</span></span>

<span data-ttu-id="15c80-192">关于托管导航的详细信息，docs.microsoft.com 文章。</span><span class="sxs-lookup"><span data-stu-id="15c80-192">There are several articles on docs.microsoft.com about the details of managed navigation.</span></span> <span data-ttu-id="15c80-193">例如，请参阅[Overview of managed navigation in SharePoint Server](/sharepoint/administration/overview-of-managed-navigation)。</span><span class="sxs-lookup"><span data-stu-id="15c80-193">For example, see [Overview of managed navigation in SharePoint Server](/sharepoint/administration/overview-of-managed-navigation).</span></span>

<span data-ttu-id="15c80-194">为了实现托管导航，您可以使用与网站的导航结构对应的 URL 设置术语。</span><span class="sxs-lookup"><span data-stu-id="15c80-194">In order to implement managed navigation, you set up terms with URLs corresponding to the navigation structure of the site.</span></span> <span data-ttu-id="15c80-195">在许多情况下，甚至可以手动选择托管导航来替换结构导航。</span><span class="sxs-lookup"><span data-stu-id="15c80-195">Managed navigation can even be manually curated to replace structural navigation in many cases.</span></span> <span data-ttu-id="15c80-196">例如：</span><span class="sxs-lookup"><span data-stu-id="15c80-196">For example:</span></span>

![SharePoint联机网站结构](../media/SPONavOptionsListOfSites.png)<span data-ttu-id="15c80-198">)</span><span class="sxs-lookup"><span data-stu-id="15c80-198">)</span></span>

## <a name="using-search-driven-client-side-scripting"></a><span data-ttu-id="15c80-199">使用搜索驱动的客户端脚本</span><span class="sxs-lookup"><span data-stu-id="15c80-199">Using Search-driven client-side scripting</span></span>

<span data-ttu-id="15c80-200">一种常见的自定义导航实现类采用客户端呈现的设计模式，该模式存储导航节点的本地缓存。</span><span class="sxs-lookup"><span data-stu-id="15c80-200">One common class of custom navigation implementations embraces client-rendered design patterns that store a local cache of navigation nodes.</span></span>

<span data-ttu-id="15c80-201">这些导航提供程序具有一些关键优势：</span><span class="sxs-lookup"><span data-stu-id="15c80-201">These navigation providers have a couple of key advantages:</span></span>

- <span data-ttu-id="15c80-202">它们通常与响应式页面设计很好地工作。</span><span class="sxs-lookup"><span data-stu-id="15c80-202">They generally work well with responsive page designs.</span></span>
- <span data-ttu-id="15c80-203">它们非常可扩展且性能高，因为它们无需任何资源成本 (超时后在后台刷新) 。</span><span class="sxs-lookup"><span data-stu-id="15c80-203">They are extremely scalable and performant because they can render with no resource cost (and refresh in the background after a timeout).</span></span>
- <span data-ttu-id="15c80-204">这些导航提供程序可以使用各种策略检索导航数据，范围从简单的静态配置到各种动态数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="15c80-204">These navigation providers can retrieve navigation data using various strategies, ranging from simple static configurations to various dynamic data providers.</span></span>

<span data-ttu-id="15c80-205">数据提供程序的一个示例是使用 **搜索驱动的** 导航，该导航可灵活地枚举导航节点并高效处理安全修整。</span><span class="sxs-lookup"><span data-stu-id="15c80-205">An example of a data provider is to use a **Search-driven navigation**, which allows flexibility for enumerating navigation nodes and handling security trimming efficiently.</span></span>

<span data-ttu-id="15c80-206">还有其他一些常用选项可生成 **自定义导航提供程序**。</span><span class="sxs-lookup"><span data-stu-id="15c80-206">There are other popular options to build **Custom navigation providers**.</span></span> <span data-ttu-id="15c80-207">请查看[适用于 SharePoint Online](/sharepoint/dev/solution-guidance/portal-navigation)门户的导航解决方案，获取有关构建自定义导航提供程序的进一步指导。</span><span class="sxs-lookup"><span data-stu-id="15c80-207">Please review [Navigation solutions for SharePoint Online portals](/sharepoint/dev/solution-guidance/portal-navigation) for further guidance on building a Custom navigation provider.</span></span>

<span data-ttu-id="15c80-208">使用搜索，可以使用连续爬网利用在后台构建的索引。</span><span class="sxs-lookup"><span data-stu-id="15c80-208">Using search you can leverage the indexes that are built up in the background using continuous crawl.</span></span> <span data-ttu-id="15c80-209">搜索结果从搜索索引中拉取，并且结果经过安全修整。</span><span class="sxs-lookup"><span data-stu-id="15c80-209">The search results are pulled from the search index and the results are security-trimmed.</span></span> <span data-ttu-id="15c80-210">当需要安全修整时，这通常比开箱即用导航提供程序快。</span><span class="sxs-lookup"><span data-stu-id="15c80-210">This is generally faster than out-of-the-box navigation providers when security trimming is required.</span></span> <span data-ttu-id="15c80-211">使用搜索结构导航（尤其是在网站结构复杂时）将极大地加快页面加载速度。</span><span class="sxs-lookup"><span data-stu-id="15c80-211">Using search for structural navigation, especially if you have a complex site structure, will speed up page loading time considerably.</span></span> <span data-ttu-id="15c80-212">与托管导航不同，这一点的主要优点是，您受益于安全修整。</span><span class="sxs-lookup"><span data-stu-id="15c80-212">The main advantage of this over managed navigation is that you benefit from security trimming.</span></span>

<span data-ttu-id="15c80-213">此方法涉及创建自定义母版页，将开箱即用导航代码替换为自定义 HTML。</span><span class="sxs-lookup"><span data-stu-id="15c80-213">This approach involves creating a custom master page and replacing the out-of-the-box navigation code with custom HTML.</span></span> <span data-ttu-id="15c80-214">按照以下示例中概述的过程替换文件 中的导航代码 `seattle.html` 。</span><span class="sxs-lookup"><span data-stu-id="15c80-214">Follow this procedure outlined in the following example to replace the navigation code in the file `seattle.html`.</span></span> <span data-ttu-id="15c80-215">本示例中，您将打开 `seattle.html` 文件，将整个 元素 `id="DeltaTopNavigation"` 替换为自定义 HTML 代码。</span><span class="sxs-lookup"><span data-stu-id="15c80-215">In this example, you will open the `seattle.html` file and replace the whole element `id="DeltaTopNavigation"` with custom HTML code.</span></span>

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a><span data-ttu-id="15c80-216">示例：替换母版页中的开箱用导航代码</span><span class="sxs-lookup"><span data-stu-id="15c80-216">Example: Replace the out-of-the-box navigation code in a master page</span></span>

1. <span data-ttu-id="15c80-217">导航到"网站设置页。</span><span class="sxs-lookup"><span data-stu-id="15c80-217">Navigate to the Site Settings page.</span></span>
2. <span data-ttu-id="15c80-218">通过单击"母版页"打开 **母版页样式库**。</span><span class="sxs-lookup"><span data-stu-id="15c80-218">Open the master page gallery by clicking **Master Pages**.</span></span>
3. <span data-ttu-id="15c80-219">你可以在此处浏览库并下载文件 `seattle.master` 。</span><span class="sxs-lookup"><span data-stu-id="15c80-219">From here you can navigate through the library and download the file `seattle.master`.</span></span>
4. <span data-ttu-id="15c80-220">使用文本编辑器编辑代码，并删除以下屏幕截图中的代码块。</span><span class="sxs-lookup"><span data-stu-id="15c80-220">Edit the code using a text editor and delete the code block in the following screen shot.</span></span><br/>![删除显示的代码块](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. <span data-ttu-id="15c80-222">删除 和 标记 `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` 之间的代码，并将其替换为以下代码段：</span><span class="sxs-lookup"><span data-stu-id="15c80-222">Remove the code between the `<SharePoint:AjaxDelta id="DeltaTopNavigation">` and `<\SharePoint:AjaxDelta>` tags and replace it with the following snippet:</span></span><br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. <span data-ttu-id="15c80-223">将开始加载图像定位标记中的 URL 替换为指向网站集中的加载图像的链接。</span><span class="sxs-lookup"><span data-stu-id="15c80-223">Replace the URL in the loading image anchor tag at the beginning, with a link to a loading image in your site collection.</span></span> <span data-ttu-id="15c80-224">进行更改后，重命名该文件，然后将它上载到母版页样式库。</span><span class="sxs-lookup"><span data-stu-id="15c80-224">After you have made the changes, rename the file and then upload it to the master page gallery.</span></span> <span data-ttu-id="15c80-225">这将生成一个新的 .master 文件。</span><span class="sxs-lookup"><span data-stu-id="15c80-225">This generates a new .master file.</span></span><br/>
7. <span data-ttu-id="15c80-226">此 HTML 是由 JavaScript 代码返回的搜索结果填充的基本标记。</span><span class="sxs-lookup"><span data-stu-id="15c80-226">This HTML is the basic markup that will be populated by the search results returned from JavaScript code.</span></span> <span data-ttu-id="15c80-227">您需要编辑代码以更改 var root = "site collection URL" 的值，如以下代码片段所示：</span><span class="sxs-lookup"><span data-stu-id="15c80-227">You will need to edit the code to change the value for var root = "site collection URL" as demonstrated in the following snippet:</span></span><br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. <span data-ttu-id="15c80-228">结果将分配给 self.nodes 数组，并且通过使用将输出分配给数组 self.hierarchy linq.js对象构建层次结构。</span><span class="sxs-lookup"><span data-stu-id="15c80-228">The results are assigned to the self.nodes array and a hierarchy is built out of the objects using linq.js assigning the output to an array self.hierarchy.</span></span> <span data-ttu-id="15c80-229">此数组是绑定到 HTML 的对象。</span><span class="sxs-lookup"><span data-stu-id="15c80-229">This array is the object that is bound to the HTML.</span></span> <span data-ttu-id="15c80-230">这是通过向 ko.applyBinding () 函数传递 self 对象在 toggleView () 函数中完成。</span><span class="sxs-lookup"><span data-stu-id="15c80-230">This is done in the toggleView() function by passing the self object to the ko.applyBinding() function.</span></span><br/><span data-ttu-id="15c80-231">这样，层次结构数组将绑定到以下 HTML：</span><span class="sxs-lookup"><span data-stu-id="15c80-231">This then causes the hierarchy array to be bound to the following HTML:</span></span><br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

<span data-ttu-id="15c80-232">和 的事件处理程序将添加到顶级导航以处理在 函数中完成的子网站 `mouseenter` `mouseexit` 下拉菜单 `addEventsToElements()` 。</span><span class="sxs-lookup"><span data-stu-id="15c80-232">The event handlers for `mouseenter` and `mouseexit` are added to the top-level navigation to handle the subsite drop-down menus which is done in the `addEventsToElements()` function.</span></span>

<span data-ttu-id="15c80-233">在我们的复杂导航示例中，没有本地缓存的新页面负载显示服务器所花费的时间已从基准结构导航中缩减，以获得与托管导航方法类似的结果。</span><span class="sxs-lookup"><span data-stu-id="15c80-233">In our complex navigation example, a fresh page load without the local caching shows the time spent on the server has been cut down from the benchmark structural navigation to get a similar result as the managed navigation approach.</span></span>

### <a name="about-the-javascript-file"></a><span data-ttu-id="15c80-234">关于 JavaScript 文件...</span><span class="sxs-lookup"><span data-stu-id="15c80-234">About the JavaScript file...</span></span>

>[!NOTE]
><span data-ttu-id="15c80-235">如果使用自定义 JavaScript，请确保CDN启用公用文件，并且文件位于CDN位置。</span><span class="sxs-lookup"><span data-stu-id="15c80-235">If using custom JavaScript, ensure that public CDN is enabled and the file is in a CDN location.</span></span>

<span data-ttu-id="15c80-236">整个 JavaScript 文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="15c80-236">The entire JavaScript file is as follows:</span></span>

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

<span data-ttu-id="15c80-237">为了汇总函数中以上所示的代码，创建了 一个 `jQuery $(document).ready` `viewModel object` ，然后 `loadNavigationNodes()` 调用该对象上的 函数。</span><span class="sxs-lookup"><span data-stu-id="15c80-237">To summarize the code shown above in the `jQuery $(document).ready` function there is a `viewModel object` created and then the `loadNavigationNodes()` function on that object is called.</span></span> <span data-ttu-id="15c80-238">此函数加载之前构建的导航层次结构，该层次结构存储在客户端浏览器的 HTML5 本地存储中，或者调用 函数 `queryRemoteInterface()` 。</span><span class="sxs-lookup"><span data-stu-id="15c80-238">This function either loads the previously built navigation hierarchy stored in the HTML5 local storage of the client browser or it calls the function `queryRemoteInterface()`.</span></span>

<span data-ttu-id="15c80-239">`QueryRemoteInterface()` 使用 函数和脚本前面定义的 查询参数生成请求， `getRequest()` 然后从服务器返回数据。</span><span class="sxs-lookup"><span data-stu-id="15c80-239">`QueryRemoteInterface()` builds a request using the `getRequest()` function with the query parameter defined earlier in the script and then returns data from the server.</span></span> <span data-ttu-id="15c80-240">此数据实质上是网站集中所有网站的数组，表示为具有各种属性的数据传输对象。</span><span class="sxs-lookup"><span data-stu-id="15c80-240">This data is essentially an array of all the sites in the site collection represented as data transfer objects with various properties.</span></span>

<span data-ttu-id="15c80-241">然后，此数据被解析为之前定义的对象，这些对象用于创建可观察属性，以用于将值绑定到我们之前定义的 `SPO.Models.NavigationNode` `Knockout.js` HTML 的数据。</span><span class="sxs-lookup"><span data-stu-id="15c80-241">This data is then parsed into the previously defined `SPO.Models.NavigationNode` objects which use `Knockout.js` to create observable properties for use by data binding the values into the HTML that we defined earlier.</span></span>

<span data-ttu-id="15c80-242">然后，将对象放入结果数组中。</span><span class="sxs-lookup"><span data-stu-id="15c80-242">The objects are then put into a results array.</span></span> <span data-ttu-id="15c80-243">此数组使用 Knockout 解析为 JSON，并存储在本地浏览器存储中，以在将来页面加载时提高性能。</span><span class="sxs-lookup"><span data-stu-id="15c80-243">This array is parsed into JSON using Knockout and stored in the local browser storage for improved performance on future page loads.</span></span>

### <a name="benefits-of-this-approach"></a><span data-ttu-id="15c80-244">此方法的好处</span><span class="sxs-lookup"><span data-stu-id="15c80-244">Benefits of this approach</span></span>

<span data-ttu-id="15c80-245">此方法的主要 [好处是](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) ，通过使用 HTML5 本地存储，导航在用户下次加载页面时本地存储。</span><span class="sxs-lookup"><span data-stu-id="15c80-245">One major benefit of [this approach](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is that by using HTML5 local storage, the navigation is stored locally for the user the next time they load the page.</span></span> <span data-ttu-id="15c80-246">我们将搜索 API 用于结构导航，获得重大性能改进;但是，执行和自定义此功能需要一些技术功能。</span><span class="sxs-lookup"><span data-stu-id="15c80-246">We get major performance improvements from using the search API for structural navigation; however, it takes some technical capability to execute and customize this functionality.</span></span>

<span data-ttu-id="15c80-247">在 [示例实现中](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)，网站按与开箱用结构导航相同的方式排序;字母顺序。</span><span class="sxs-lookup"><span data-stu-id="15c80-247">In the [example implementation](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), the sites are ordered in the same way as the out-of-the-box structural navigation; alphabetical order.</span></span> <span data-ttu-id="15c80-248">如果要偏离此顺序，开发和维护会更加复杂。</span><span class="sxs-lookup"><span data-stu-id="15c80-248">If you wanted to deviate from this order, it would be more complicated to develop and maintain.</span></span> <span data-ttu-id="15c80-249">此外，此方法还要求您偏离受支持的母版页。</span><span class="sxs-lookup"><span data-stu-id="15c80-249">Also, this approach requires you to deviate from the supported master pages.</span></span> <span data-ttu-id="15c80-250">如果未维护自定义母版页，您的网站将错过 Microsoft 对母版页的更新和改进。</span><span class="sxs-lookup"><span data-stu-id="15c80-250">If the custom master page is not maintained, your site will miss out on updates and improvements that Microsoft makes to the master pages.</span></span>

<span data-ttu-id="15c80-251">上述 [代码](#about-the-javascript-file) 具有以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="15c80-251">The [above code](#about-the-javascript-file) has the following dependencies:</span></span>

- <span data-ttu-id="15c80-252">jQuery - https://jquery.com/</span><span class="sxs-lookup"><span data-stu-id="15c80-252">jQuery - https://jquery.com/</span></span>
- <span data-ttu-id="15c80-253">KnockoutJS - https://knockoutjs.com/</span><span class="sxs-lookup"><span data-stu-id="15c80-253">KnockoutJS - https://knockoutjs.com/</span></span>
- <span data-ttu-id="15c80-254">Linq.js - https://linqjs.codeplex.com/ 或 github.com/neuecc/linq.js</span><span class="sxs-lookup"><span data-stu-id="15c80-254">Linq.js - https://linqjs.codeplex.com/, or github.com/neuecc/linq.js</span></span>

<span data-ttu-id="15c80-255">LinqJS 的当前版本不包含上述代码中使用的 ByHierarchy 方法，将中断导航代码。</span><span class="sxs-lookup"><span data-stu-id="15c80-255">The current version of LinqJS does not contain the ByHierarchy method used in the above code and will break the navigation code.</span></span> <span data-ttu-id="15c80-256">若要解决此问题，将以下方法添加到 Linq.js 文件行之前 `Flatten: function ()` 。</span><span class="sxs-lookup"><span data-stu-id="15c80-256">To fix this, add the following method to the Linq.js file before the line `Flatten: function ()`.</span></span>

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a><span data-ttu-id="15c80-257">相关主题</span><span class="sxs-lookup"><span data-stu-id="15c80-257">Related topics</span></span>

[<span data-ttu-id="15c80-258">SharePoint Server 中的托管导航概述</span><span class="sxs-lookup"><span data-stu-id="15c80-258">Overview of managed navigation in SharePoint Server</span></span>](/sharepoint/administration/overview-of-managed-navigation)

[<span data-ttu-id="15c80-259">结构导航缓存和性能</span><span class="sxs-lookup"><span data-stu-id="15c80-259">Structural navigation caching and performance</span></span>](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)