---
title: Office 365 内容分发网络 (CDN) 快速入门
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 内容分发网络 (CDN) 快速入门
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921590"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="4ff45-103">Office 365 内容分发网络 (CDN) 快速入门</span><span class="sxs-lookup"><span data-stu-id="4ff45-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="4ff45-104">可以使用内置 Office 365 内容分发网络 (CDN) 托管静态资产 (图像、JavaScript、样式表、WOFF) ，以提升 SharePoint Online 页面的性能。</span><span class="sxs-lookup"><span data-stu-id="4ff45-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="4ff45-105">Office 365 CDN 将静态资产缓存到距离请求这些资产的浏览器更近的位置，这样可以加快下载速度并减少延迟，进而提高性能。</span><span class="sxs-lookup"><span data-stu-id="4ff45-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="4ff45-106">此外，Office 365 CDN使用 HTTP/2 协议改进压缩和 HTTP 管道传输。</span><span class="sxs-lookup"><span data-stu-id="4ff45-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="4ff45-107">Office 365 CDN 服务被归入 SharePoint Online 订阅。</span><span class="sxs-lookup"><span data-stu-id="4ff45-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="4ff45-108">有关更详细的信息指南，请参阅[将 Office 365 内容分发网络 (CDN) 与 SharePoint Online 一起](use-microsoft-365-cdn-with-spo.md)使用。</span><span class="sxs-lookup"><span data-stu-id="4ff45-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="4ff45-109">此Office 365 CDN仅适用于全球云中生产 (租户) 租户。</span><span class="sxs-lookup"><span data-stu-id="4ff45-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="4ff45-110">美国政府、中国德国云中的租户当前不支持Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="4ff45-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="4ff45-111">使用页面诊断 for SharePoint 工具识别不在CDN</span><span class="sxs-lookup"><span data-stu-id="4ff45-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="4ff45-112">您可以使用 SharePoint工具浏览器扩展的页面诊断轻松列出 SharePoint Online 页面中可添加到 CDN 资源。</span><span class="sxs-lookup"><span data-stu-id="4ff45-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="4ff45-113">适用于 **SharePoint** 的页面诊断工具是新的 Microsoft Edge (和 Chrome 浏览器的浏览器扩展，可分析 SharePoint Online 新式门户和 https://www.microsoft.com/edge) 经典发布网站页面。</span><span class="sxs-lookup"><span data-stu-id="4ff45-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="4ff45-114">该工具对已分配的每个页面提供一个报告，其中显示根据一组定义的性能条件得出的页面性能情况。</span><span class="sxs-lookup"><span data-stu-id="4ff45-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="4ff45-115">要安装和了解适用于 SharePoint 的页面诊断工具，请参阅[使用适用于 SharePoint Online 的页面诊断工具](./page-diagnostics-for-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="4ff45-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](./page-diagnostics-for-spo.md).</span></span>

<span data-ttu-id="4ff45-116">当您在 SharePoint Online 页面上运行 SharePoint 页面诊断工具时，可以单击"诊断测试"选项卡以查看未由 CDN 托管的资产列表。</span><span class="sxs-lookup"><span data-stu-id="4ff45-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="4ff45-117">这些资产将列在标题"内容分发网络 (CDN) **检查"** 下，如下面的屏幕截图所示。</span><span class="sxs-lookup"><span data-stu-id="4ff45-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![页面诊断](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="4ff45-119">页面诊断工具仅适用于 SharePoint Online，无法用于 SharePoint 系统页面。</span><span class="sxs-lookup"><span data-stu-id="4ff45-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="4ff45-120">CDN概述</span><span class="sxs-lookup"><span data-stu-id="4ff45-120">CDN Overview</span></span>

<span data-ttu-id="4ff45-121">Office 365 CDN 旨在通过在高速全局网络中分发经常访问的对象（如图像和 javascript 文件）来优化用户性能，从而减少页面加载时间，并尽可能为用户提供对托管对象的访问。</span><span class="sxs-lookup"><span data-stu-id="4ff45-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="4ff45-122">the CDN fetches your assets from a location called an _origin_.</span><span class="sxs-lookup"><span data-stu-id="4ff45-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="4ff45-123">源可以是 URL SharePoint访问的文档网站、文档库或文件夹。</span><span class="sxs-lookup"><span data-stu-id="4ff45-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="4ff45-124">该Office 365 CDN分为两种基本类型：</span><span class="sxs-lookup"><span data-stu-id="4ff45-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="4ff45-125">**公共 CDN** 旨在用于 JS (JavaScript) 、CSS (StyleSheets) 、Web 字体文件 (WOFF、WOFF2) 以及公司徽标等非专有图像。</span><span class="sxs-lookup"><span data-stu-id="4ff45-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="4ff45-126">**专用CDN** 用于 PNG (JPG、JPEG 等图像) 。</span><span class="sxs-lookup"><span data-stu-id="4ff45-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="4ff45-127">你可以选择同时为组织提供公共源或专用源。</span><span class="sxs-lookup"><span data-stu-id="4ff45-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="4ff45-128">大多数组织都将选择实施这两者的组合。</span><span class="sxs-lookup"><span data-stu-id="4ff45-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="4ff45-129">公共和专用选项都提供相似的性能提升，但每个选项都有独特的属性和优点。</span><span class="sxs-lookup"><span data-stu-id="4ff45-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="4ff45-130">有关公用源和专用源CDN，请参阅选择每个源[是公共源还是私有源](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。</span><span class="sxs-lookup"><span data-stu-id="4ff45-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="4ff45-131">如何使用默认配置CDN公用和专用服务器</span><span class="sxs-lookup"><span data-stu-id="4ff45-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="4ff45-132">在更改租户策略设置CDN，应验证它是否符合组织的合规性、安全性和隐私策略。</span><span class="sxs-lookup"><span data-stu-id="4ff45-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="4ff45-133">有关更详细的配置设置，或者如果你已启用 CDN并且想要添加其他位置 (源) ，请参阅使用[SharePoint Online](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)命令行管理程序设置和配置 Office 365 CDN 部分</span><span class="sxs-lookup"><span data-stu-id="4ff45-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="4ff45-134">连接命令行管理程序SharePoint租户：</span><span class="sxs-lookup"><span data-stu-id="4ff45-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="4ff45-135">若要使组织能够将公用源和专用源与默认配置一同使用，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="4ff45-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="4ff45-136">这些 cmdlet 的输出应如下所示：</span><span class="sxs-lookup"><span data-stu-id="4ff45-136">Output of these cmdlets should look like the following:</span></span>

![输出Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="4ff45-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ff45-138">See also</span></span>

[<span data-ttu-id="4ff45-139">使用适用于 SharePoint Online 的页面诊断工具</span><span class="sxs-lookup"><span data-stu-id="4ff45-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](./page-diagnostics-for-spo.md)

[<span data-ttu-id="4ff45-140">结合使用 Office 365 内容分发网络和 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4ff45-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="4ff45-141">内容分发网络</span><span class="sxs-lookup"><span data-stu-id="4ff45-141">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="4ff45-142">Office 365 网络计划和性能优化</span><span class="sxs-lookup"><span data-stu-id="4ff45-142">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="4ff45-143">SharePoint性能系列 - Office 365 CDN视频系列</span><span class="sxs-lookup"><span data-stu-id="4ff45-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)