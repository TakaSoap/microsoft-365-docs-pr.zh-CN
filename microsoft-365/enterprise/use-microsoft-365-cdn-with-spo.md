---
title: 将 Office 365 内容分发网络 (CDN) 与 SharePoint Online 一同使用
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
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
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: 了解如何使用 Office 365 内容分发网络 (CDN) 来加快你的 SharePoint Online 资产的交付。
ms.openlocfilehash: 5e9ed00462b7073c7e03f62a5de6bf26f1e586af
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289447"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="637ab-103">结合使用 Office 365 内容分发网络和 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="637ab-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="637ab-104">可以使用内置的 Office 365 内容分发网络 (CDN) 来托管静态资产，以便提高 SharePoint Online 页面的性能。</span><span class="sxs-lookup"><span data-stu-id="637ab-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="637ab-105">Office 365 CDN 将静态资产缓存到距离请求这些资产的浏览器更近的位置，这样可以加快下载速度并减少延迟，进而提高性能。</span><span class="sxs-lookup"><span data-stu-id="637ab-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="637ab-106">此外，Office 365 CDN[使用 HTTP/2](https://en.wikipedia.org/wiki/HTTP/2)协议改进压缩和 HTTP 管道传输。</span><span class="sxs-lookup"><span data-stu-id="637ab-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="637ab-107">Office 365 CDN 服务被归入 SharePoint Online 订阅。</span><span class="sxs-lookup"><span data-stu-id="637ab-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="637ab-108">此Office 365 CDN仅适用于全球云中的 **生产 (租户**) 租户。</span><span class="sxs-lookup"><span data-stu-id="637ab-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="637ab-109">美国政府、中国德国云中的租户当前不支持Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="637ab-110">Office 365 CDN 由多个 CDN 组成，用户可以在多个位置（即 _源_）托管静态资产，并从全局高速网络提供这些资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="637ab-111">可以添加 **公共** 源、**私有** 源或同时添加这两种源，具体取决于想要托管在 Office 365 CDN 中的内容种类。</span><span class="sxs-lookup"><span data-stu-id="637ab-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="637ab-112">有关 [公用源和专用](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) 源之间区别的信息，请参阅选择每个源是公共源还是私有源。</span><span class="sxs-lookup"><span data-stu-id="637ab-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="637ab-113">![Office 365 CDN概念图](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN概念图")</span><span class="sxs-lookup"><span data-stu-id="637ab-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="637ab-114">如果你已熟悉 CDN 的运行方式，则只需完成几个步骤，为租户Office 365 CDN启用 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="637ab-115">本主题介绍如何。</span><span class="sxs-lookup"><span data-stu-id="637ab-115">This topic describes how.</span></span> <span data-ttu-id="637ab-116">请继续阅读，了解如何开始托管静态资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="637ab-117">还有一些 Microsoft 托管的 CDN 可以与 Office 365 一起用于专用使用方案，但是本主题中未讨论这些 CDN，因为它们不在 Office 365 CDN 范围内。</span><span class="sxs-lookup"><span data-stu-id="637ab-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="637ab-118">有关详细信息，请参阅其他[Microsoft CDN。](content-delivery-networks.md#other-microsoft-cdns)</span><span class="sxs-lookup"><span data-stu-id="637ab-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="637ab-119">**返回到适用于网络 [的网络规划和性能Office 365。](./network-planning-and-performance.md)**</span><span class="sxs-lookup"><span data-stu-id="637ab-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="637ab-120">在 Office 365 CDN Online SharePoint概述</span><span class="sxs-lookup"><span data-stu-id="637ab-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="637ab-121">若要为Office 365 CDN设置服务，请按照以下基本步骤操作：</span><span class="sxs-lookup"><span data-stu-id="637ab-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="637ab-122">规划部署Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="637ab-123">[确定要托管在应用程序上的静态CDN。](use-microsoft-365-cdn-with-spo.md#CDNAssets)</span><span class="sxs-lookup"><span data-stu-id="637ab-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="637ab-124">[确定要存储资产的位置](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)。</span><span class="sxs-lookup"><span data-stu-id="637ab-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="637ab-125">此位置可以是网站SharePoint库或文件夹，_称为源_。</span><span class="sxs-lookup"><span data-stu-id="637ab-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="637ab-126">[选择每个源应为公共源还是私有源](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。</span><span class="sxs-lookup"><span data-stu-id="637ab-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="637ab-127">你可以添加公共和私有类型的多个源。</span><span class="sxs-lookup"><span data-stu-id="637ab-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="637ab-128">使用 PowerShell 或 CDN Online CLI 设置和配置SharePoint客户端</span><span class="sxs-lookup"><span data-stu-id="637ab-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="637ab-129">使用 CDN Online 命令行管理程序设置和配置SharePoint命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="637ab-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="637ab-130">使用 PnP PowerShell CDN和配置应用程序</span><span class="sxs-lookup"><span data-stu-id="637ab-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="637ab-131">使用 CDN CLI 设置和配置Office 365</span><span class="sxs-lookup"><span data-stu-id="637ab-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="637ab-132">完成此步骤后，您将具有：</span><span class="sxs-lookup"><span data-stu-id="637ab-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="637ab-133">为CDN启用策略。</span><span class="sxs-lookup"><span data-stu-id="637ab-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="637ab-134">添加了源，将每个源标识为公用或私有。</span><span class="sxs-lookup"><span data-stu-id="637ab-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="637ab-135">完成设置后，可以按[以下](use-microsoft-365-cdn-with-spo.md#CDNManage)方式Office 365 CDN管理安装程序：</span><span class="sxs-lookup"><span data-stu-id="637ab-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>

+ <span data-ttu-id="637ab-136">添加、更新和删除资源</span><span class="sxs-lookup"><span data-stu-id="637ab-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="637ab-137">添加和删除源</span><span class="sxs-lookup"><span data-stu-id="637ab-137">Adding and removing origins</span></span>
+ <span data-ttu-id="637ab-138">配置CDN策略</span><span class="sxs-lookup"><span data-stu-id="637ab-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="637ab-139">如有必要，禁用CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="637ab-140">最后，[请参阅使用CDN资源](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets)，了解如何从公用CDN源访问你的资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="637ab-141">请参阅[Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues。</span><span class="sxs-lookup"><span data-stu-id="637ab-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="637ab-142">规划部署Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="637ab-143">在部署 Office 365 CDN 租户Office 365，在规划过程中应考虑以下因素。</span><span class="sxs-lookup"><span data-stu-id="637ab-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="637ab-144">确定要托管在应用程序上的静态CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="637ab-145">确定要存储资产的位置</span><span class="sxs-lookup"><span data-stu-id="637ab-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="637ab-146">选择每个源应为公共源还是专用源</span><span class="sxs-lookup"><span data-stu-id="637ab-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="637ab-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="637ab-148">确定要托管在应用程序上的静态CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="637ab-149">通常，CDN 最适用于托管静态 _资产_ 或不经常更改的资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="637ab-150">一个很好的经验法则是标识满足以下部分或所有条件的文件：</span><span class="sxs-lookup"><span data-stu-id="637ab-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="637ab-151">嵌入页面的静态文件 (脚本和图像) 会对页面加载时间产生显著增量影响</span><span class="sxs-lookup"><span data-stu-id="637ab-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="637ab-152">大型文件，如可执行文件和安装文件</span><span class="sxs-lookup"><span data-stu-id="637ab-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="637ab-153">支持客户端代码的资源库</span><span class="sxs-lookup"><span data-stu-id="637ab-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="637ab-154">例如，在将 SharePoint Online 网站添加到 CDN 源时，重复请求的小文件（如网站图像和脚本）可以显著提高网站呈现性能并逐步减少 SharePoint Online 网站的负载。</span><span class="sxs-lookup"><span data-stu-id="637ab-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="637ab-155">可以从 CDN 下载安装可执行文件等较大的文件，从而对性能产生积极的影响，并随后减少 SharePoint Online 网站的负载，即使它们未经常访问。</span><span class="sxs-lookup"><span data-stu-id="637ab-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="637ab-156">基于每个文件的性能改进取决于许多因素，包括客户端与最近的 CDN 终结点的邻近度、本地网络上暂时的情况等等。</span><span class="sxs-lookup"><span data-stu-id="637ab-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="637ab-157">许多静态文件非常小，可以在不到Office 365从文件下载。</span><span class="sxs-lookup"><span data-stu-id="637ab-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="637ab-158">但是，网页可能包含许多嵌入式文件，其累积下载时间为几秒。</span><span class="sxs-lookup"><span data-stu-id="637ab-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="637ab-159">从网站中CDN可显著缩短整个页面加载时间。</span><span class="sxs-lookup"><span data-stu-id="637ab-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="637ab-160">有关[示例，请参阅CDN性能](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide)提升？</span><span class="sxs-lookup"><span data-stu-id="637ab-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="637ab-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="637ab-162">确定要存储资产的位置</span><span class="sxs-lookup"><span data-stu-id="637ab-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="637ab-163">the CDN fetches your assets from a location called an _origin_.</span><span class="sxs-lookup"><span data-stu-id="637ab-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="637ab-164">源可以是 URL SharePoint访问的文档网站、文档库或文件夹。</span><span class="sxs-lookup"><span data-stu-id="637ab-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="637ab-165">当你为组织指定来源时，你具有极大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="637ab-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="637ab-166">例如，可以指定多个源或一个要放入所有源资源CDN源。</span><span class="sxs-lookup"><span data-stu-id="637ab-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="637ab-167">你可以选择同时为组织提供公共源或专用源。</span><span class="sxs-lookup"><span data-stu-id="637ab-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="637ab-168">大多数组织都将选择实施这两者的组合。</span><span class="sxs-lookup"><span data-stu-id="637ab-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="637ab-169">你可以为源（如文件夹或文档库）创建新容器，并添加想要从文档库CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="637ab-170">如果你希望从 CDN 获得一组特定的资产，并且希望将 CDN 资产集限制为容器中的这些文件，则这是一个不错的方法。</span><span class="sxs-lookup"><span data-stu-id="637ab-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="637ab-171">您还可以将现有网站集、网站、库或文件夹配置为源，这样容器中的所有符合条件的资产均可从 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="637ab-172">在将现有容器添加为源之前，请务必确保了解其内容和权限，以便不会无意中向匿名访问或未经授权的用户公开资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="637ab-173">你可以定义 _CDN_ 策略以从源中排除CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="637ab-174">CDN按文件类型和网站分类等属性排除公用源或专用源中的资产，并应用于在策略中指定的 CdnType (private 或 public) 的所有源。</span><span class="sxs-lookup"><span data-stu-id="637ab-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="637ab-175">例如，如果添加由包含多个子网站的网站组成的专用源，您可以定义一个策略来排除标记为"机密"的网站，以便不会从 CDN提供应用了该分类的网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="637ab-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="637ab-176">该策略将应用于已 _添加到_ 策略的所有私有源CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>

<span data-ttu-id="637ab-177">请记住，源数量越大，对服务处理请求CDN的影响越大。</span><span class="sxs-lookup"><span data-stu-id="637ab-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="637ab-178">我们建议你尽可能限制源的数量。</span><span class="sxs-lookup"><span data-stu-id="637ab-178">We recommend that you limit the number of origins as much as possible.</span></span>

<span data-ttu-id="637ab-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="637ab-180">选择每个源应为公共源还是专用源</span><span class="sxs-lookup"><span data-stu-id="637ab-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="637ab-181">标识源时，指定应公开 _还是私有。_ </span><span class="sxs-lookup"><span data-stu-id="637ab-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="637ab-182">对CDN源中资产的访问权限是匿名的，并且CDN源中的内容受动态生成的令牌保护，从而获得更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="637ab-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="637ab-183">无论你选择哪个选项，Microsoft 都会在管理用户本身时，CDN繁重的工作。</span><span class="sxs-lookup"><span data-stu-id="637ab-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="637ab-184">此外，在设置帐户并识别CDN之后，你可以改变主意。</span><span class="sxs-lookup"><span data-stu-id="637ab-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="637ab-185">公共和专用选项都提供相似的性能提升，但每个选项都有独特的属性和优点。</span><span class="sxs-lookup"><span data-stu-id="637ab-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="637ab-186">**可** 匿名访问Office 365 CDN内部的公共源，并且拥有资产 URL 的任何人都可以访问托管资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="637ab-187">由于对公共源中内容的访问属于匿名访问，因此只能使用它们缓存非敏感的常规内容，如 JavaScript 文件、脚本、图标和图片。</span><span class="sxs-lookup"><span data-stu-id="637ab-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as JavaScript files, scripts, icons and images.</span></span>

<span data-ttu-id="637ab-188">**应用程序** 内的专用源Office 365 CDN用户内容（如 SharePoint Online 文档库、网站和专有图像）的专用访问权限。</span><span class="sxs-lookup"><span data-stu-id="637ab-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="637ab-189">对专用源中内容的访问受动态生成的令牌保护，因此只有对原始文档库或存储位置具有权限的用户才能访问它。</span><span class="sxs-lookup"><span data-stu-id="637ab-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="637ab-190">Office 365 CDN中的专用源只能用于 SharePoint Online 内容，并且你仅可以通过从 SharePoint Online 租户重定向来访问专用源中的资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="637ab-191">可以在使用私有源中的CDN中阅读有关对私有源中资产的访问权限[的工作方式。](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)</span><span class="sxs-lookup"><span data-stu-id="637ab-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="637ab-192">在公共源中托管资产的属性和优点</span><span class="sxs-lookup"><span data-stu-id="637ab-192">Attributes and advantages of hosting assets in public origins</span></span>

+ <span data-ttu-id="637ab-193">每个人都能匿名访问公用源中公开的资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="637ab-194">不应将包含用户信息或被视为对组织敏感的资源放在公共源中。</span><span class="sxs-lookup"><span data-stu-id="637ab-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

+ <span data-ttu-id="637ab-195">如果从公用源中删除某资产，缓存会继续保留此资产最多 30 天；但此 CDN 资产的链接会在 15 分钟内失效。</span><span class="sxs-lookup"><span data-stu-id="637ab-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>

+ <span data-ttu-id="637ab-196">如果将样式表（CSS 文件）托管到公用源，可以在代码内使用相对路径和 URI。</span><span class="sxs-lookup"><span data-stu-id="637ab-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="637ab-197">也就是说，可以引用背景图像和其他对象相对于调用它的资产的位置。</span><span class="sxs-lookup"><span data-stu-id="637ab-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>

+ <span data-ttu-id="637ab-198">虽然可以构造公用源的 URL，但应谨慎操作，并确保利用页面上下文属性并按照指南执行此操作。</span><span class="sxs-lookup"><span data-stu-id="637ab-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="637ab-199">这是因为，如果无法访问 CDN，URL 就不会在 SharePoint Online 中自动解析为相应组织，进而可能会导致链接失效和其他错误抛出。</span><span class="sxs-lookup"><span data-stu-id="637ab-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="637ab-200">URL 也可能会更改，这就是为什么它不应只硬编码为当前值的原因。</span><span class="sxs-lookup"><span data-stu-id="637ab-200">The URL is also subject to change which is why it should not just be hard coded to its current value.</span></span>

+ <span data-ttu-id="637ab-201">公共源包括的默认文件类型为 .css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff 和 .woff2。</span><span class="sxs-lookup"><span data-stu-id="637ab-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="637ab-202">可以指定其他文件类型。</span><span class="sxs-lookup"><span data-stu-id="637ab-202">You can specify additional file types.</span></span>

+ <span data-ttu-id="637ab-203">您可以配置策略以排除由您指定的网站分类标识的资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="637ab-204">例如，可以选择排除所有标记为“机密”或“受限”的资产，即使它们的文件类型受支持且位于公用源中，也不例外。</span><span class="sxs-lookup"><span data-stu-id="637ab-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="637ab-205">在专用源中托管资产的属性和优点</span><span class="sxs-lookup"><span data-stu-id="637ab-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="637ab-206">专用源只能用于 SharePoint Online 资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-206">Private origins can only be used for SharePoint Online assets.</span></span>

+ <span data-ttu-id="637ab-207">只有用户有权访问容器，他们才能访问专用源中的资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="637ab-208">禁止匿名访问这些资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-208">Anonymous access to these assets is prevented.</span></span>

+ <span data-ttu-id="637ab-209">专用源中的资产必须从 SharePoint Online 租户引用。</span><span class="sxs-lookup"><span data-stu-id="637ab-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="637ab-210">直接访问私有CDN资产不起作用。</span><span class="sxs-lookup"><span data-stu-id="637ab-210">Direct access to private CDN assets does not work.</span></span>

+ <span data-ttu-id="637ab-211">如果从专用源中删除资产，资产在缓存中可能仍可用一小时;但是，在资产删除后 15 分钟内，CDN中资产的链接失效。</span><span class="sxs-lookup"><span data-stu-id="637ab-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>

+ <span data-ttu-id="637ab-212">默认情况下，支持为专用源添加下列类型的文件：.gif、.ico、.jpeg、.jpg、.js 和 .png。</span><span class="sxs-lookup"><span data-stu-id="637ab-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="637ab-213">可以指定其他文件类型。</span><span class="sxs-lookup"><span data-stu-id="637ab-213">You can specify additional file types.</span></span>

+ <span data-ttu-id="637ab-214">与公用源一样，您可以配置策略以排除由您指定的网站分类标识的资产，即使您使用通配符将文件夹或文档库内的所有资产都包括其中。</span><span class="sxs-lookup"><span data-stu-id="637ab-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="637ab-215">有关为什么使用 Office 365 CDN、常规 CDN 概念和其他可用于 Office 365 租户的 Microsoft CDN 的信息，请参阅内容交付[网络](content-delivery-networks.md)。</span><span class="sxs-lookup"><span data-stu-id="637ab-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="637ab-216">默认CDN源</span><span class="sxs-lookup"><span data-stu-id="637ab-216">Default CDN origins</span></span>

<span data-ttu-id="637ab-217">除非另行指定，否则Office 365启用该设置时，将设置一些默认Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="637ab-218">如果你最初选择不预配它们，可以在完成设置后添加这些源。</span><span class="sxs-lookup"><span data-stu-id="637ab-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="637ab-219">除非您了解跳过默认源设置的后果，并且有这样做的特定原因，否则在启用默认源时，应允许创建CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>

<span data-ttu-id="637ab-220">默认专用CDN源：</span><span class="sxs-lookup"><span data-stu-id="637ab-220">Default private CDN origins:</span></span>

+ <span data-ttu-id="637ab-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="637ab-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="637ab-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="637ab-222">\*/siteassets</span></span>

<span data-ttu-id="637ab-223">默认公用CDN源：</span><span class="sxs-lookup"><span data-stu-id="637ab-223">Default public CDN origins:</span></span>

+ <span data-ttu-id="637ab-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="637ab-224">\*/masterpage</span></span>
+ <span data-ttu-id="637ab-225">\*/style 库</span><span class="sxs-lookup"><span data-stu-id="637ab-225">\*/style library</span></span>
+ <span data-ttu-id="637ab-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="637ab-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="637ab-227">_clientsideassets_ 是 2017 年 12 月添加到 Office 365 CDN 服务的默认公用源。</span><span class="sxs-lookup"><span data-stu-id="637ab-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="637ab-228">此源必须存在，以便SharePoint 框架解决方案CDN工作。</span><span class="sxs-lookup"><span data-stu-id="637ab-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="637ab-229">如果在 2017 年 12 Office 365 CDN之前启用了该设置，或者如果在启用默认源时跳过了默认源CDN，可以手动添加此源。</span><span class="sxs-lookup"><span data-stu-id="637ab-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="637ab-230">有关详细信息，请参阅[我的客户端 Web 部件或SharePoint 框架解决方案无法工作](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)。</span><span class="sxs-lookup"><span data-stu-id="637ab-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="637ab-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="637ab-232">使用 Office 365 CDN Online 命令行管理程序设置和配置SharePoint命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="637ab-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="637ab-233">本节中的过程要求使用 SharePoint Online 命令行管理程序连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="637ab-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="637ab-234">有关说明，请参阅[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="637ab-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

<span data-ttu-id="637ab-235">完成这些步骤以设置和配置 CDN 以使用 SharePoint Online 命令行管理程序在 SharePoint Online 中托管资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="637ab-236">单击展开</span><span class="sxs-lookup"><span data-stu-id="637ab-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="637ab-237">使组织能够使用Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="637ab-238">在更改租户策略设置CDN，应先检索租户中专用CDN配置Office 365状态。</span><span class="sxs-lookup"><span data-stu-id="637ab-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="637ab-239">连接命令行管理程序SharePoint租户：</span><span class="sxs-lookup"><span data-stu-id="637ab-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="637ab-240">现在，使用 **Get-SPOTenantCdnEnabled** cmdlet 从租户CDN状态设置：</span><span class="sxs-lookup"><span data-stu-id="637ab-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="637ab-241">指定 CdnType CDN状态将输出到屏幕。</span><span class="sxs-lookup"><span data-stu-id="637ab-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="637ab-242">使用 **Set-SPOTenantCdnEnabled** cmdlet 可让组织使用 Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="637ab-243">你可以使组织同时使用公用源和/或私有源。</span><span class="sxs-lookup"><span data-stu-id="637ab-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="637ab-244">还可以配置CDN以在启用默认源时跳过其设置。</span><span class="sxs-lookup"><span data-stu-id="637ab-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="637ab-245">稍后始终可以添加这些源，如本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="637ab-245">You can always add these origins later as described in this topic.</span></span>

<span data-ttu-id="637ab-246">在 Windows PowerShell SharePoint Online 中：</span><span class="sxs-lookup"><span data-stu-id="637ab-246">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="637ab-247">例如，若要使组织同时使用公用源和专用源，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="637ab-248">若要使组织能够同时使用公用源和专用源，但跳过设置默认源，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="637ab-249">请参阅[默认](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)CDN源，了解启用 Office 365 CDN 时默认预配的源，以及跳过默认源设置的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="637ab-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="637ab-250">若要使组织能够使用公用源，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-250">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="637ab-251">若要使组织能够使用专用源，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-251">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="637ab-252">有关此 cmdlet 详细信息，请参阅 [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。</span><span class="sxs-lookup"><span data-stu-id="637ab-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="637ab-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="637ab-254">更改要包括在可选列表中的文件类型Office 365 CDN (可选) </span><span class="sxs-lookup"><span data-stu-id="637ab-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="637ab-255">使用 **Set-SPOTenantCdnPolicy** cmdlet 定义文件类型时，将覆盖当前定义的列表。</span><span class="sxs-lookup"><span data-stu-id="637ab-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="637ab-256">如果要向列表中添加其他文件类型，请首先使用 cmdlet 了解已允许的文件类型，将它们与新文件类型一起包括在列表中。</span><span class="sxs-lookup"><span data-stu-id="637ab-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>

<span data-ttu-id="637ab-257">使用 **Set-SPOTenantCdnPolicy** cmdlet 可定义静态文件类型，这些静态文件类型可通过公共源和专用源在 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="637ab-258">默认情况下，允许使用常见资源类型，例如 .css、.gif、.jpg 和 .js。</span><span class="sxs-lookup"><span data-stu-id="637ab-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="637ab-259">在 Windows PowerShell SharePoint Online 中：</span><span class="sxs-lookup"><span data-stu-id="637ab-259">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="637ab-260">例如，若要使CDN .css 和 .png文件，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="637ab-261">To see what file types are currently allowed by the CDN， use the **Get-SPOTenantCdnPolicies** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="637ab-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="637ab-262">有关这些 cmdlet 的信息，请参阅[Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/)和[Get-SPOTenantCdnPolicies。](/powershell/module/sharepoint-online/)</span><span class="sxs-lookup"><span data-stu-id="637ab-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="637ab-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="637ab-264">更改网站分类列表，以从"可选"Office 365 CDN (排除) </span><span class="sxs-lookup"><span data-stu-id="637ab-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="637ab-265">使用 **Set-SPOTenantCdnPolicy** cmdlet 排除网站分类时，将覆盖当前定义的列表。</span><span class="sxs-lookup"><span data-stu-id="637ab-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="637ab-266">如果要排除其他网站分类，请首先使用 cmdlet 了解已排除的分类，然后将它们与新分类一起添加。</span><span class="sxs-lookup"><span data-stu-id="637ab-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="637ab-267">运行 **Set-SPOTenantCdnPolicy** cmdlet 可以排除不想通过 CDN 提供的网站分类。</span><span class="sxs-lookup"><span data-stu-id="637ab-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="637ab-268">默认情况下，不排除任何网站分类。</span><span class="sxs-lookup"><span data-stu-id="637ab-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="637ab-269">在 Windows PowerShell SharePoint Online 中：</span><span class="sxs-lookup"><span data-stu-id="637ab-269">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="637ab-270">若要了解当前限制的网站分类，请使用 **Get-SPOTenantCdnPolicies** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="637ab-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="637ab-271">将返回的属性包括 _IncludeFileExtensions_、 _ExcludeRestrictedSiteClassifications_ 和 _ExcludeIfNoScriptDisabled_。</span><span class="sxs-lookup"><span data-stu-id="637ab-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="637ab-272">_IncludeFileExtensions_ 属性包含文件扩展名的列表，该文件扩展名将CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="637ab-273">默认文件扩展名在公用和专用之间有所不同。</span><span class="sxs-lookup"><span data-stu-id="637ab-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="637ab-274">_ExcludeRestrictedSiteClassifications_ 属性包含您希望从网站列表中排除CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="637ab-275">例如，您可以排除标记为"机密"的网站，以便网站中应用了该分类的内容不会从网站CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="637ab-276">_ExcludeIfNoScriptDisabled_ 属性根据网站级别的 _NoScript_ 属性CDN排除网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="637ab-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="637ab-277">默认情况下 _，NoScript_ 属性设置为"为新式 **网站** 启用"和"**对经典** 网站 _禁用_"。</span><span class="sxs-lookup"><span data-stu-id="637ab-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="637ab-278">这取决于你的租户设置。</span><span class="sxs-lookup"><span data-stu-id="637ab-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="637ab-279">有关这些 cmdlet 的信息，请参阅[Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/)和[Get-SPOTenantCdnPolicies。](/powershell/module/sharepoint-online/)</span><span class="sxs-lookup"><span data-stu-id="637ab-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="637ab-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="637ab-281">为资产添加来源</span><span class="sxs-lookup"><span data-stu-id="637ab-281">Add an origin for your assets</span></span>

<span data-ttu-id="637ab-282">使用 **Add-SPOTenantCdnOrigin** cmdlet 定义源。</span><span class="sxs-lookup"><span data-stu-id="637ab-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="637ab-283">可以定义多个源。</span><span class="sxs-lookup"><span data-stu-id="637ab-283">You can define multiple origins.</span></span> <span data-ttu-id="637ab-284">源是 SharePoint 库或文件夹的 URL，其中包含要由 CDN 托管的资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="637ab-285">不应将包含用户信息或被视为对组织敏感的资源放在公共源中。</span><span class="sxs-lookup"><span data-stu-id="637ab-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="637ab-286">path _的值是_ 包含资产的库或文件夹的相对路径。</span><span class="sxs-lookup"><span data-stu-id="637ab-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="637ab-287">除了相对路径之外，还可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="637ab-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="637ab-288">源支持在 URL 前加通配符。</span><span class="sxs-lookup"><span data-stu-id="637ab-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="637ab-289">这允许你创建跨多个站点的来源。</span><span class="sxs-lookup"><span data-stu-id="637ab-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="637ab-290">例如，若要将所有网站的 masterpages 文件夹中的所有资产作为公共源包含到 CDN，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="637ab-291">通配符修饰符 \* 只能在路径的开头使用，并且将匹配指定 URL 下 **/** 的所有 URL 段。</span><span class="sxs-lookup"><span data-stu-id="637ab-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="637ab-292">该路径可以指向文档库、文件夹或网站。</span><span class="sxs-lookup"><span data-stu-id="637ab-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="637ab-293">例如，路径 _\*/site1_ 将匹配网站下的所有文档库。</span><span class="sxs-lookup"><span data-stu-id="637ab-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="637ab-294">你可以添加具有特定相对路径的原点。</span><span class="sxs-lookup"><span data-stu-id="637ab-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="637ab-295">不能使用完整路径添加原点。</span><span class="sxs-lookup"><span data-stu-id="637ab-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="637ab-296">此示例将网站集库的私有源添加到特定网站上：</span><span class="sxs-lookup"><span data-stu-id="637ab-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="637ab-297">此示例在网站集的网站资产库中添加 _folder1_ 文件夹的私有源：</span><span class="sxs-lookup"><span data-stu-id="637ab-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="637ab-298">如果路径中具有空格，可以使用双引号将路径括起来，或者将空格替换为 URL 编码 %20。</span><span class="sxs-lookup"><span data-stu-id="637ab-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="637ab-299">以下示例在网站集的网站资产库中添加文件夹 _1_ 文件夹的私有源：</span><span class="sxs-lookup"><span data-stu-id="637ab-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="637ab-300">有关此命令及其语法的信息，请参阅 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="637ab-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="637ab-301">在专用源中，从源共享的资产必须具有发布的主要版本，然后才能从源CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>

<span data-ttu-id="637ab-302">运行命令后，系统将跨数据中心同步配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="637ab-303">这最多可能需要 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="637ab-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="637ab-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="637ab-305">示例：为母版页和适用于 SharePoint Online 的样式库配置公共源</span><span class="sxs-lookup"><span data-stu-id="637ab-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="637ab-306">正常情况下，当你启用这些源时，默认情况下会Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="637ab-307">但是，如果要手动启用它们，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="637ab-307">However, if you want to enable them manually, follow these steps.</span></span>

+ <span data-ttu-id="637ab-308">使用 **Add-SPOTenantCdnOrigin** cmdlet 可以将样式库定义为公共源。</span><span class="sxs-lookup"><span data-stu-id="637ab-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="637ab-309">使用 **Add-SPOTenantCdnOrigin** cmdlet 可以将母版页定义为公用源。</span><span class="sxs-lookup"><span data-stu-id="637ab-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="637ab-310">有关此命令及其语法的信息，请参阅 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="637ab-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="637ab-311">运行命令后，系统将跨数据中心同步配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="637ab-312">这最多可能需要 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="637ab-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="637ab-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="637ab-314">示例：为 SharePoint Online 的网站资产、网站页面和发布图像配置专用源</span><span class="sxs-lookup"><span data-stu-id="637ab-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="637ab-315">使用 **Add-SPOTenantCdnOrigin** cmdlet 将网站资产文件夹定义为专用源。</span><span class="sxs-lookup"><span data-stu-id="637ab-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="637ab-316">使用 **Add-SPOTenantCdnOrigin** cmdlet 可以将网站页面文件夹定义为专用源。</span><span class="sxs-lookup"><span data-stu-id="637ab-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="637ab-317">使用 **Add-SPOTenantCdnOrigin** cmdlet 将发布图像文件夹定义为私有源。</span><span class="sxs-lookup"><span data-stu-id="637ab-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="637ab-318">有关此命令及其语法的信息，请参阅 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="637ab-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="637ab-319">运行命令后，系统将跨数据中心同步配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="637ab-320">这最多可能需要 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="637ab-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="637ab-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="637ab-322">示例：为 SharePoint Online 的网站集配置专用源</span><span class="sxs-lookup"><span data-stu-id="637ab-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="637ab-323">使用 **Add-SPOTenantCdnOrigin** cmdlet 将网站集定义为专用源。</span><span class="sxs-lookup"><span data-stu-id="637ab-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="637ab-324">例如：</span><span class="sxs-lookup"><span data-stu-id="637ab-324">For example:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="637ab-325">有关此命令及其语法的信息，请参阅 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="637ab-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="637ab-326">运行命令后，系统将跨数据中心同步配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="637ab-327">你可能会看到"_配置挂起_"消息，预计 SharePoint Online 租户连接到 CDN 服务。</span><span class="sxs-lookup"><span data-stu-id="637ab-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="637ab-328">这最多可能需要 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="637ab-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="637ab-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="637ab-330">管理Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="637ab-331">设置网站集后CDN，可以在更新内容或更改需求时更改配置，如本节中所述。</span><span class="sxs-lookup"><span data-stu-id="637ab-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>

<span data-ttu-id="637ab-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="637ab-333">添加、更新或删除资源Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="637ab-334">完成设置步骤后，可以随时添加新资产，并更新或删除现有资源。</span><span class="sxs-lookup"><span data-stu-id="637ab-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="637ab-335">只需对标识为源的文件夹或SharePoint库中的资产进行更改。</span><span class="sxs-lookup"><span data-stu-id="637ab-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="637ab-336">如果添加新资产，它将立即通过CDN可用。</span><span class="sxs-lookup"><span data-stu-id="637ab-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="637ab-337">但是，如果更新资源，则新副本最多需要 15 分钟才能传播，并可在 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>

<span data-ttu-id="637ab-338">如果需要检索源的位置，可以使用 **Get-SPOTenantCdnOrigins** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="637ab-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="637ab-339">有关如何使用此 cmdlet 的信息，请参阅 [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)。</span><span class="sxs-lookup"><span data-stu-id="637ab-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="637ab-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="637ab-341">从源中删除Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="637ab-342">你可以删除对标识为SharePoint的文件夹或库的访问权限。</span><span class="sxs-lookup"><span data-stu-id="637ab-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="637ab-343">为此，请使用 **Remove-SPOTenantCdnOrigin** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="637ab-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="637ab-344">有关如何使用此 cmdlet 的信息，请参阅 [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="637ab-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="637ab-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="637ab-346">修改源中的Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="637ab-347">无法修改已创建的源。</span><span class="sxs-lookup"><span data-stu-id="637ab-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="637ab-348">请删除原点，然后添加新源。</span><span class="sxs-lookup"><span data-stu-id="637ab-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="637ab-349">有关详细信息，请参阅从资源[中删除Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh)[和为资产添加源](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)。</span><span class="sxs-lookup"><span data-stu-id="637ab-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="637ab-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="637ab-351">禁用Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="637ab-352">使用 **Set-SPOTenantCdnEnabled** cmdlet 可禁用CDN配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="637ab-353">如果同时为 cmdlet 启用了公用源CDN源，则需要运行 cmdlet 两次，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="637ab-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>

<span data-ttu-id="637ab-354">若要在命令行中禁止使用公用CDN，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-354">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="637ab-355">若要在应用程序内禁止使用专用CDN，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="637ab-356">有关此 cmdlet 详细信息，请参阅 [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。</span><span class="sxs-lookup"><span data-stu-id="637ab-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="637ab-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="637ab-358">使用 PnP PowerShell Office 365 CDN和配置应用程序</span><span class="sxs-lookup"><span data-stu-id="637ab-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="637ab-359">本节中的过程要求使用 PnP PowerShell 连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="637ab-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="637ab-360">有关说明，请参阅 [PnP PowerShell 入门](https://github.com/SharePoint/PnP-PowerShell#getting-started)。</span><span class="sxs-lookup"><span data-stu-id="637ab-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="637ab-361">完成这些步骤以设置和配置CDN PnP PowerShell 在 SharePoint Online 中托管资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="637ab-362">单击展开</span><span class="sxs-lookup"><span data-stu-id="637ab-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="637ab-363">使组织能够使用Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="637ab-364">在更改租户策略设置CDN，应先检索租户中专用CDN配置Office 365状态。</span><span class="sxs-lookup"><span data-stu-id="637ab-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="637ab-365">连接 PnP PowerShell 访问租户：</span><span class="sxs-lookup"><span data-stu-id="637ab-365">Connect to your tenant using PnP PowerShell:</span></span>

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="637ab-366">现在，使用 **Get-PnPTenantCdnEnabled** cmdlet 从租户CDN状态设置：</span><span class="sxs-lookup"><span data-stu-id="637ab-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="637ab-367">指定 CdnType CDN状态将输出到屏幕。</span><span class="sxs-lookup"><span data-stu-id="637ab-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="637ab-368">使用 **Set-PnPTenantCdnEnabled** cmdlet 可让组织使用 Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="637ab-369">你可以使组织同时使用公用源和/或私有源。</span><span class="sxs-lookup"><span data-stu-id="637ab-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="637ab-370">还可以配置CDN以在启用默认源时跳过其设置。</span><span class="sxs-lookup"><span data-stu-id="637ab-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="637ab-371">稍后始终可以添加这些源，如本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="637ab-371">You can always add these origins later as described in this topic.</span></span>

<span data-ttu-id="637ab-372">在 PnP PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="637ab-372">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="637ab-373">例如，若要使组织同时使用公用源和专用源，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="637ab-374">若要使组织能够同时使用公用源和专用源，但跳过设置默认源，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="637ab-375">请参阅[默认](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)CDN源，了解启用 Office 365 CDN 时默认预配的源，以及跳过默认源设置的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="637ab-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="637ab-376">若要使组织能够使用公用源，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-376">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="637ab-377">若要使组织能够使用专用源，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-377">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="637ab-378">有关此 cmdlet 详细信息，请参阅 [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。</span><span class="sxs-lookup"><span data-stu-id="637ab-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="637ab-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="637ab-380">更改要包括在可选列表中的文件类型Office 365 CDN (可选) </span><span class="sxs-lookup"><span data-stu-id="637ab-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="637ab-381">使用 **Set-PnPTenantCdnPolicy** cmdlet 定义文件类型时，将覆盖当前定义的列表。</span><span class="sxs-lookup"><span data-stu-id="637ab-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="637ab-382">如果要向列表中添加其他文件类型，请首先使用 cmdlet 了解已允许的文件类型，将它们与新文件类型一起包括在列表中。</span><span class="sxs-lookup"><span data-stu-id="637ab-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>

<span data-ttu-id="637ab-383">使用 **Set-PnPTenantCdnPolicy** cmdlet 可定义静态文件类型，这些静态文件类型可通过公共源和专用源在 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="637ab-384">默认情况下，允许使用常见资源类型，例如 .css、.gif、.jpg 和 .js。</span><span class="sxs-lookup"><span data-stu-id="637ab-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="637ab-385">在 PnP PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="637ab-385">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="637ab-386">例如，若要使CDN .css 和 .png文件，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="637ab-387">To see what file types are currently allowed by the CDN， use the **Get-PnPTenantCdnPolicies** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="637ab-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="637ab-388">有关这些 cmdlet 的信息，请参阅[Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy)和[Get-PnPTenantCdnPolicies。](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="637ab-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="637ab-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="637ab-390">更改网站分类列表，以从"可选"Office 365 CDN (排除) </span><span class="sxs-lookup"><span data-stu-id="637ab-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="637ab-391">使用 **Set-PnPTenantCdnPolicy** cmdlet 排除网站分类时，将覆盖当前定义的列表。</span><span class="sxs-lookup"><span data-stu-id="637ab-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="637ab-392">如果要排除其他网站分类，请首先使用 cmdlet 了解已排除的分类，然后将它们与新分类一起添加。</span><span class="sxs-lookup"><span data-stu-id="637ab-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="637ab-393">使用 **Set-PnPTenantCdnPolicy** cmdlet 可以排除不希望通过网站集CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="637ab-394">默认情况下，不排除任何网站分类。</span><span class="sxs-lookup"><span data-stu-id="637ab-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="637ab-395">在 PnP PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="637ab-395">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="637ab-396">若要了解当前限制哪些网站分类，请使用 **Get-PnPTenantCdnPolicies** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="637ab-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="637ab-397">将返回的属性包括 _IncludeFileExtensions_、 _ExcludeRestrictedSiteClassifications_ 和 _ExcludeIfNoScriptDisabled_。</span><span class="sxs-lookup"><span data-stu-id="637ab-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="637ab-398">_IncludeFileExtensions_ 属性包含文件扩展名的列表，该文件扩展名将CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="637ab-399">默认文件扩展名在公用和专用之间有所不同。</span><span class="sxs-lookup"><span data-stu-id="637ab-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="637ab-400">_ExcludeRestrictedSiteClassifications_ 属性包含您希望从网站列表中排除CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="637ab-401">例如，您可以排除标记为"机密"的网站，以便网站中应用了该分类的内容不会从网站CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="637ab-402">_ExcludeIfNoScriptDisabled_ 属性根据网站级别的 _NoScript_ 属性CDN排除网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="637ab-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="637ab-403">默认情况下 _，NoScript_ 属性设置为"为新式 **网站** 启用"和"**对经典** 网站 _禁用_"。</span><span class="sxs-lookup"><span data-stu-id="637ab-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="637ab-404">这取决于你的租户设置。</span><span class="sxs-lookup"><span data-stu-id="637ab-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="637ab-405">有关这些 cmdlet 的信息，请参阅[Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy)和[Get-PnPTenantCdnPolicies。](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="637ab-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="637ab-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="637ab-407">为资产添加来源</span><span class="sxs-lookup"><span data-stu-id="637ab-407">Add an origin for your assets</span></span>

<span data-ttu-id="637ab-408">使用 **Add-PnPTenantCdnOrigin** cmdlet 定义源。</span><span class="sxs-lookup"><span data-stu-id="637ab-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="637ab-409">可以定义多个源。</span><span class="sxs-lookup"><span data-stu-id="637ab-409">You can define multiple origins.</span></span> <span data-ttu-id="637ab-410">源是 SharePoint 库或文件夹的 URL，其中包含要由 CDN 托管的资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="637ab-411">不应将包含用户信息或被视为对组织敏感的资源放在公共源中。</span><span class="sxs-lookup"><span data-stu-id="637ab-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="637ab-412">path _的值是_ 包含资产的库或文件夹的相对路径。</span><span class="sxs-lookup"><span data-stu-id="637ab-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="637ab-413">除了相对路径之外，还可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="637ab-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="637ab-414">源支持在 URL 前加通配符。</span><span class="sxs-lookup"><span data-stu-id="637ab-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="637ab-415">这允许你创建跨多个站点的来源。</span><span class="sxs-lookup"><span data-stu-id="637ab-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="637ab-416">例如，若要将所有网站的 masterpages 文件夹中的所有资产作为公共源包含到 CDN，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="637ab-417">通配符修饰符 \* 只能在路径的开头使用，并且将匹配指定 URL 下 **/** 的所有 URL 段。</span><span class="sxs-lookup"><span data-stu-id="637ab-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="637ab-418">该路径可以指向文档库、文件夹或网站。</span><span class="sxs-lookup"><span data-stu-id="637ab-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="637ab-419">例如，路径 _\*/site1_ 将匹配网站下的所有文档库。</span><span class="sxs-lookup"><span data-stu-id="637ab-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="637ab-420">你可以添加具有特定相对路径的原点。</span><span class="sxs-lookup"><span data-stu-id="637ab-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="637ab-421">不能使用完整路径添加原点。</span><span class="sxs-lookup"><span data-stu-id="637ab-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="637ab-422">此示例将网站资产库的私有源添加到特定网站上：</span><span class="sxs-lookup"><span data-stu-id="637ab-422">This example adds a private origin of the site assets library on a specific site:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="637ab-423">此示例在网站集的网站资产库中添加 _folder1_ 文件夹的私有源：</span><span class="sxs-lookup"><span data-stu-id="637ab-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="637ab-424">如果路径中具有空格，可以使用双引号将路径括起来，或者将空格替换为 URL 编码 %20。</span><span class="sxs-lookup"><span data-stu-id="637ab-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="637ab-425">以下示例在网站集的网站资产库中添加文件夹 _1_ 文件夹的私有源：</span><span class="sxs-lookup"><span data-stu-id="637ab-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="637ab-426">有关此命令及其语法的信息，请参阅 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="637ab-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="637ab-427">在专用源中，从源共享的资产必须具有发布的主要版本，然后才能从源CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>

<span data-ttu-id="637ab-428">运行命令后，系统将跨数据中心同步配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="637ab-429">这最多可能需要 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="637ab-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="637ab-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="637ab-431">示例：为母版页和适用于 SharePoint Online 的样式库配置公共源</span><span class="sxs-lookup"><span data-stu-id="637ab-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="637ab-432">正常情况下，当你启用这些源时，默认情况下会Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="637ab-433">但是，如果要手动启用它们，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="637ab-433">However, if you want to enable them manually, follow these steps.</span></span>

+ <span data-ttu-id="637ab-434">使用 **Add-PnPTenantCdnOrigin** cmdlet 可以将样式库定义为公共源。</span><span class="sxs-lookup"><span data-stu-id="637ab-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="637ab-435">使用 **Add-PnPTenantCdnOrigin** cmdlet 可以将母版页定义为公用源。</span><span class="sxs-lookup"><span data-stu-id="637ab-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="637ab-436">有关此命令及其语法的信息，请参阅 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="637ab-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="637ab-437">运行命令后，系统将跨数据中心同步配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="637ab-438">这最多可能需要 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="637ab-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="637ab-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="637ab-440">示例：为 SharePoint Online 的网站资产、网站页面和发布图像配置专用源</span><span class="sxs-lookup"><span data-stu-id="637ab-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="637ab-441">使用 **Add-PnPTenantCdnOrigin** cmdlet 将网站资产文件夹定义为专用源。</span><span class="sxs-lookup"><span data-stu-id="637ab-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="637ab-442">使用 **Add-PnPTenantCdnOrigin** cmdlet 将网站页面文件夹定义为专用源。</span><span class="sxs-lookup"><span data-stu-id="637ab-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="637ab-443">使用 **Add-PnPTenantCdnOrigin** cmdlet 将发布图像文件夹定义为私有源。</span><span class="sxs-lookup"><span data-stu-id="637ab-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="637ab-444">有关此命令及其语法的信息，请参阅 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="637ab-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="637ab-445">运行命令后，系统将跨数据中心同步配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="637ab-446">这最多可能需要 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="637ab-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="637ab-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="637ab-448">示例：为 SharePoint Online 的网站集配置专用源</span><span class="sxs-lookup"><span data-stu-id="637ab-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="637ab-449">使用 **Add-PnPTenantCdnOrigin** cmdlet 将网站集定义为专用源。</span><span class="sxs-lookup"><span data-stu-id="637ab-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="637ab-450">例如：</span><span class="sxs-lookup"><span data-stu-id="637ab-450">For example:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="637ab-451">有关此命令及其语法的信息，请参阅 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="637ab-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="637ab-452">运行命令后，系统将跨数据中心同步配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="637ab-453">你可能会看到"_配置挂起_"消息，预计 SharePoint Online 租户连接到 CDN 服务。</span><span class="sxs-lookup"><span data-stu-id="637ab-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="637ab-454">这最多可能需要 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="637ab-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="637ab-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="637ab-456">管理Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="637ab-457">设置网站集后CDN，可以在更新内容或更改需求时更改配置，如本节中所述。</span><span class="sxs-lookup"><span data-stu-id="637ab-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>

<span data-ttu-id="637ab-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="637ab-459">添加、更新或删除资源Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="637ab-460">完成设置步骤后，可以随时添加新资产，并更新或删除现有资源。</span><span class="sxs-lookup"><span data-stu-id="637ab-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="637ab-461">只需对标识为源的文件夹或SharePoint库中的资产进行更改。</span><span class="sxs-lookup"><span data-stu-id="637ab-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="637ab-462">如果添加新资产，它将立即通过CDN可用。</span><span class="sxs-lookup"><span data-stu-id="637ab-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="637ab-463">但是，如果更新资源，则新副本最多需要 15 分钟才能传播，并可在 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>

<span data-ttu-id="637ab-464">如果需要检索源的位置，可以使用 **Get-PnPTenantCdnOrigin** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="637ab-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="637ab-465">有关如何使用此 cmdlet 的信息，请参阅 [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="637ab-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="637ab-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="637ab-467">从源中删除Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="637ab-468">你可以删除对标识为SharePoint的文件夹或库的访问权限。</span><span class="sxs-lookup"><span data-stu-id="637ab-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="637ab-469">为此，请使用 **Remove-PnPTenantCdnOrigin** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="637ab-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="637ab-470">有关如何使用此 cmdlet 的信息，请参阅 [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="637ab-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="637ab-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="637ab-472">修改源中的Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="637ab-473">无法修改已创建的源。</span><span class="sxs-lookup"><span data-stu-id="637ab-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="637ab-474">请删除原点，然后添加新源。</span><span class="sxs-lookup"><span data-stu-id="637ab-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="637ab-475">有关详细信息，请参阅从资源[中删除Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh)[和为资产添加源](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)。</span><span class="sxs-lookup"><span data-stu-id="637ab-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="637ab-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="637ab-477">禁用Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="637ab-478">使用 **Set-PnPTenantCdnEnabled** cmdlet 可禁用CDN配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="637ab-479">如果同时为 cmdlet 启用了公用源CDN源，则需要运行 cmdlet 两次，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="637ab-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>

<span data-ttu-id="637ab-480">若要在命令行中禁止使用公用CDN，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-480">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="637ab-481">若要在应用程序内禁止使用专用CDN，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="637ab-482">有关此 cmdlet 详细信息，请参阅 [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。</span><span class="sxs-lookup"><span data-stu-id="637ab-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="637ab-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="637ab-484">使用 Office 365 CLI 设置和配置 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="637ab-485">本节中的过程要求你已安装 Office 365 [CLI。](https://aka.ms/o365cli)</span><span class="sxs-lookup"><span data-stu-id="637ab-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="637ab-486">接下来，使用登录Office 365连接到你的[租户](https://pnp.github.io/office365-cli/cmd/login/)。</span><span class="sxs-lookup"><span data-stu-id="637ab-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="637ab-487">完成这些步骤以设置和配置CDN CLI 在 SharePoint Online 中Office 365资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="637ab-488">单击展开</span><span class="sxs-lookup"><span data-stu-id="637ab-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="637ab-489">启用Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="637ab-490">可以运行 [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) 命令，在租户中管理 Office 365 CDN 的状态。</span><span class="sxs-lookup"><span data-stu-id="637ab-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="637ab-491">若要在租户中启用 Office 365 公用 CDN，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```cli
spo cdn set --type Public --enabled true
```

<span data-ttu-id="637ab-492">若要启用Office 365 SharePoint CDN，请执行：</span><span class="sxs-lookup"><span data-stu-id="637ab-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="637ab-493">查看 Office 365 CDN 的当前状态</span><span class="sxs-lookup"><span data-stu-id="637ab-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="637ab-494">若要检查特定类型 Office 365 CDN是否已启用，请使用[spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)命令。</span><span class="sxs-lookup"><span data-stu-id="637ab-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="637ab-495">若要检查 Office 365 公用 CDN 是否已启用，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="637ab-496">查看Office 365 CDN源</span><span class="sxs-lookup"><span data-stu-id="637ab-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="637ab-497">若要查看当前配置的 Office 365 公用 CDN 源，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```cli
spo cdn origin list --type Public
```

<span data-ttu-id="637ab-498">请参阅[默认CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)源，了解在启用默认设置时预配Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="637ab-499">添加Office 365 CDN源</span><span class="sxs-lookup"><span data-stu-id="637ab-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="637ab-500">您永远不应将组织的敏感资源放在配置为SharePoint源的文档库中。</span><span class="sxs-lookup"><span data-stu-id="637ab-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="637ab-501">运行 [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) 命令可以定义 CDN 源。</span><span class="sxs-lookup"><span data-stu-id="637ab-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="637ab-502">可以定义多个源。</span><span class="sxs-lookup"><span data-stu-id="637ab-502">You can define multiple origins.</span></span> <span data-ttu-id="637ab-503">源是 SharePoint 库或文件夹的 URL，其中包含要由 CDN 托管的资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="637ab-504">`path`其中 是包含资产的文件夹的相对路径。</span><span class="sxs-lookup"><span data-stu-id="637ab-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="637ab-505">除了相对路径之外，还可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="637ab-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="637ab-506">若要将所有网站的母版页 **样式库中** 的所有资产作为公共源包含，请执行：</span><span class="sxs-lookup"><span data-stu-id="637ab-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```cli
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="637ab-507">若要配置特定网站集的专用源，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="637ab-507">To configure a private origin for a specific site collection, execute:</span></span>

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="637ab-508">添加 CDN 源后，最长可能需要 15 分钟，才能通过 CDN 服务检索文件。</span><span class="sxs-lookup"><span data-stu-id="637ab-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="637ab-509">可以运行 [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 命令，验证特定源是否已启用。</span><span class="sxs-lookup"><span data-stu-id="637ab-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="637ab-510">删除Office 365 CDN源</span><span class="sxs-lookup"><span data-stu-id="637ab-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="637ab-511">运行 [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) 命令可以删除指定类型 CDN 的 CDN 源。</span><span class="sxs-lookup"><span data-stu-id="637ab-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="637ab-512">要从配置中删除公用源CDN，请执行：</span><span class="sxs-lookup"><span data-stu-id="637ab-512">To remove a public origin from the CDN configuration, execute:</span></span>

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="637ab-513">删除CDN源不会影响存储在任何与源匹配的文档库中的文件。</span><span class="sxs-lookup"><span data-stu-id="637ab-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="637ab-514">如果已使用它们的 URL 引用SharePoint，SharePoint将自动切换回指向文档库的原始 URL。</span><span class="sxs-lookup"><span data-stu-id="637ab-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="637ab-515">但是，如果已使用公用 url 引用CDN，则删除源将断开链接，并且你需要手动更改它们。</span><span class="sxs-lookup"><span data-stu-id="637ab-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="637ab-516">修改Office 365 CDN源</span><span class="sxs-lookup"><span data-stu-id="637ab-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="637ab-517">无法修改现有 CDN 源。</span><span class="sxs-lookup"><span data-stu-id="637ab-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="637ab-518">而应运行 `spo cdn origin remove` 命令删除以前定义的 CDN 源，并运行 `spo cdn origin add` 命令添加新源。</span><span class="sxs-lookup"><span data-stu-id="637ab-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="637ab-519">更改要包括在文件Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="637ab-520">默认情况下，CDN 中包含以下文件类型 _：.css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff 和 .woff2。_</span><span class="sxs-lookup"><span data-stu-id="637ab-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="637ab-521">如果需要在 CDN 中添加其他类型的文件，可以运行 [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) 命令更改 CDN 配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="637ab-522">如果更改文件类型列表，也就是覆盖当前定义的列表。</span><span class="sxs-lookup"><span data-stu-id="637ab-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="637ab-523">若要添加其他文件类型，请先运行 [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 命令，确定当前配置的文件类型。</span><span class="sxs-lookup"><span data-stu-id="637ab-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="637ab-524">若要将 _JSON_ 文件类型添加到公共文件中包含的文件类型的默认列表中，CDN：</span><span class="sxs-lookup"><span data-stu-id="637ab-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="637ab-525">更改要从 Office 365 CDN 中排除的网站分类列表</span><span class="sxs-lookup"><span data-stu-id="637ab-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="637ab-526">运行 [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) 命令可以排除不想通过 CDN 提供的网站分类。</span><span class="sxs-lookup"><span data-stu-id="637ab-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="637ab-527">默认情况下，不排除任何网站分类。</span><span class="sxs-lookup"><span data-stu-id="637ab-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="637ab-528">如果更改已排除的网站分类列表，也就是覆盖当前定义的列表。</span><span class="sxs-lookup"><span data-stu-id="637ab-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="637ab-529">若要排除其他分类，请先运行 [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) 命令，确定当前配置的分类。</span><span class="sxs-lookup"><span data-stu-id="637ab-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="637ab-530">若要从公共网站中排除分类为 _HBI_ CDN，请执行</span><span class="sxs-lookup"><span data-stu-id="637ab-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="637ab-531">禁用Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="637ab-532">若要禁用 Office 365 CDN，请运行 `spo cdn set` 命令。例如：</span><span class="sxs-lookup"><span data-stu-id="637ab-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="637ab-533">使用CDN资产</span><span class="sxs-lookup"><span data-stu-id="637ab-533">Using your CDN assets</span></span>

<span data-ttu-id="637ab-534">现在，你已启用CDN配置的来源和策略，可以开始使用CDN资源。</span><span class="sxs-lookup"><span data-stu-id="637ab-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="637ab-535">本节将帮助您了解如何在 SharePoint 页面和内容中使用 CDN URL，以便 SharePoint 将公用源和专用源中的资产请求重定向到 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="637ab-536">更新指向资产CDN的链接</span><span class="sxs-lookup"><span data-stu-id="637ab-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="637ab-537">使用公共源中的资产</span><span class="sxs-lookup"><span data-stu-id="637ab-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="637ab-538">使用专用源中的资产</span><span class="sxs-lookup"><span data-stu-id="637ab-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="637ab-539">有关如何使用 CDN 托管客户端 Web 部件的信息，请参阅主题从 hello World 第 4 部分Office 365 CDN (托管客户端[web) 。 ](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)</span><span class="sxs-lookup"><span data-stu-id="637ab-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="637ab-540">如果将 _ClientSideAssets_ 文件夹添加到专用CDN源列表中，CDN托管的自定义 Web 部件将无法呈现。</span><span class="sxs-lookup"><span data-stu-id="637ab-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="637ab-541">SPFX Web 部件使用的文件只能使用公共CDN ClientSideAssets 文件夹是公用文件夹的默认CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span>

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="637ab-542">更新指向资产CDN的链接</span><span class="sxs-lookup"><span data-stu-id="637ab-542">Updating links to CDN assets</span></span>

<span data-ttu-id="637ab-543">若要使用已添加到源中的资源，只需使用指向原始文件的路径更新指向原始文件的链接。</span><span class="sxs-lookup"><span data-stu-id="637ab-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="637ab-544">编辑包含已添加到源中的资产的链接的页面或内容。</span><span class="sxs-lookup"><span data-stu-id="637ab-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="637ab-545">如果要将链接更新到给定资产出现的任何位置，您还可以使用多种方法之一在输入站点或网站集中进行全局搜索和替换链接。</span><span class="sxs-lookup"><span data-stu-id="637ab-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="637ab-546">对于指向源中资产的每个链接，请将路径替换为源中文件CDN路径。</span><span class="sxs-lookup"><span data-stu-id="637ab-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="637ab-547">可以使用相对路径。</span><span class="sxs-lookup"><span data-stu-id="637ab-547">You can use relative paths.</span></span>
+ <span data-ttu-id="637ab-548">保存页面或内容。</span><span class="sxs-lookup"><span data-stu-id="637ab-548">Save the page or content.</span></span>

<span data-ttu-id="637ab-549">例如，考虑已复制到文档库 _文件夹 /site/CDN_origins/public/ 的图像 /site/SiteAssets/images/image.png_ 。</span><span class="sxs-lookup"><span data-stu-id="637ab-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="637ab-550">若要使用CDN资源，请将图像文件位置的原始路径替换为原点的路径，使新的 URL _/site/CDN_origins/public/image.png_。</span><span class="sxs-lookup"><span data-stu-id="637ab-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="637ab-551">如果要使用资产的完整 URL 而不是相对路径，请构建如下所示的链接：</span><span class="sxs-lookup"><span data-stu-id="637ab-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="637ab-552">通常，不应将 URL 直接硬编码到资源CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="637ab-553">但是，如果需要，你可以手动为公用源中的资产构建 URL。</span><span class="sxs-lookup"><span data-stu-id="637ab-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="637ab-554">有关详细信息，请参阅[Hardcoding CDN URL for public assets](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)。</span><span class="sxs-lookup"><span data-stu-id="637ab-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="637ab-555">若要了解如何验证资产是否正在从 CDN 中提供，请参阅疑难解答中的如何确认 CDN[正在](use-microsoft-365-cdn-with-spo.md#CDNConfirm)为资产[Office 365 CDN。](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="637ab-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="637ab-556">使用公共源中的资产</span><span class="sxs-lookup"><span data-stu-id="637ab-556">Using assets in public origins</span></span>

<span data-ttu-id="637ab-557">SharePoint  Online 中的发布功能会自动将存储在公共源中的资产的 URL 重写为 CDN 等效项，以便资产从 CDN 服务而不是 SharePoint 提供。</span><span class="sxs-lookup"><span data-stu-id="637ab-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="637ab-558">如果你的源位于启用了发布功能的网站中，并且你想要卸载到 CDN 的资产位于以下类别之一，SharePoint 将自动重写源中资产的 URL，只要 CDN 策略未排除该资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="637ab-559">下面概述了 SharePoint 发布功能自动重写的链接：</span><span class="sxs-lookup"><span data-stu-id="637ab-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="637ab-560">经典发布页面 HTML 响应中的 IMG/LINK/CSS URL</span><span class="sxs-lookup"><span data-stu-id="637ab-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="637ab-561">这包括作者在页面的 HTML 内容中添加的图像</span><span class="sxs-lookup"><span data-stu-id="637ab-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="637ab-562">图片库幻灯片 Web 部件图像 URL</span><span class="sxs-lookup"><span data-stu-id="637ab-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="637ab-563">SPList REST API (RenderListDataAsStream) 结果中的图像字段</span><span class="sxs-lookup"><span data-stu-id="637ab-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="637ab-564">使用新属性 _ImageFieldsToTryRewriteToCdnUrls_ 提供以逗号分隔的字段列表</span><span class="sxs-lookup"><span data-stu-id="637ab-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="637ab-565">支持超链接字段和 PublishingImage 字段</span><span class="sxs-lookup"><span data-stu-id="637ab-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="637ab-566">SharePoint图像再现</span><span class="sxs-lookup"><span data-stu-id="637ab-566">SharePoint image renditions</span></span>

<span data-ttu-id="637ab-567">下图说明了当用户收到SharePoint包含来自公共源的资产的页面的请求时，工作流。</span><span class="sxs-lookup"><span data-stu-id="637ab-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="637ab-568">![工作流图：从Office 365 CDN检索资源](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "工作流：从Office 365 CDN检索资源")</span><span class="sxs-lookup"><span data-stu-id="637ab-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="637ab-569">如果要禁用页面上特定 URL 的自动重写，可以签出页面并添加查询字符串参数 **？NoAutoReWrites=true** 到要禁用的每个链接的末尾。</span><span class="sxs-lookup"><span data-stu-id="637ab-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="637ab-570">为CDN构建 URL</span><span class="sxs-lookup"><span data-stu-id="637ab-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="637ab-571">如果未为公共源启用发布功能，或者资产不是 CDN 服务的自动重写功能支持的链接类型之一，您可以手动构造指向资产的 CDN 位置的 URL，并在你的内容中使用这些 URL。</span><span class="sxs-lookup"><span data-stu-id="637ab-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="637ab-572">无法硬编码或构造CDN源中的资产的 URL，因为生成形成 URL 最后一节所需的访问令牌是在请求资源时生成的。</span><span class="sxs-lookup"><span data-stu-id="637ab-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="637ab-573">您可以构造公用网站的 URL CDN URL 不应硬编码，因为它可能会更改。</span><span class="sxs-lookup"><span data-stu-id="637ab-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="637ab-574">对于CDN资源，URL 格式将如下所示：</span><span class="sxs-lookup"><span data-stu-id="637ab-574">For public CDN assets, the URL format will look like the following:</span></span>

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="637ab-575">将 **TenantHostName** 替换为租户名称。</span><span class="sxs-lookup"><span data-stu-id="637ab-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="637ab-576">示例：</span><span class="sxs-lookup"><span data-stu-id="637ab-576">Example:</span></span>

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> <span data-ttu-id="637ab-577">页面上下文属性应该用于构造前缀，而不是硬编码 https://publiccdn.sharepointonline.com " "。</span><span class="sxs-lookup"><span data-stu-id="637ab-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="637ab-578">URL 可能会更改，不应进行硬编码。</span><span class="sxs-lookup"><span data-stu-id="637ab-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="637ab-579">如果将显示模板与 Classic SharePoint Online 一同使用，可以在显示模板中将属性"window._spPageContextInfo.publicCdnBaseUrl"用于 URL 的前缀。</span><span class="sxs-lookup"><span data-stu-id="637ab-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="637ab-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span><span class="sxs-lookup"><span data-stu-id="637ab-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="637ab-581">这将提供前缀，以便如果更改，则你的实现将更新它。</span><span class="sxs-lookup"><span data-stu-id="637ab-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="637ab-582">例如，SPFx，可以使用属性"this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item"构建 URL。</span><span class="sxs-lookup"><span data-stu-id="637ab-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="637ab-583">请参阅[在客户端CDN](https://youtu.be/IH1RbQlbhIA) 1 性能系列的一部分[使用客户端代码](https://aka.ms/sppnp-perfvideos)</span><span class="sxs-lookup"><span data-stu-id="637ab-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="637ab-584">使用专用源中的资产</span><span class="sxs-lookup"><span data-stu-id="637ab-584">Using assets in private origins</span></span>

<span data-ttu-id="637ab-585">使用专用源中的资产不需要其他配置。</span><span class="sxs-lookup"><span data-stu-id="637ab-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="637ab-586">SharePoint联机自动重写专用源中资产的 URL，因此将始终从应用程序服务CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="637ab-587">无法手动生成 URL CDN私有源中的资产，因为这些 URL 包含的令牌必须由 SharePoint Online 在请求资产时自动生成。</span><span class="sxs-lookup"><span data-stu-id="637ab-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="637ab-588">对专用源中的资产的访问权限受基于用户对源权限的动态生成的令牌的保护，以下各节介绍了一些注意事项。</span><span class="sxs-lookup"><span data-stu-id="637ab-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="637ab-589">用户必须至少具有 **对源** 的读取访问权限，CDN内容。</span><span class="sxs-lookup"><span data-stu-id="637ab-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="637ab-590">下图说明了当用户收到包含SharePoint源中的资产的页面的请求时，工作流。</span><span class="sxs-lookup"><span data-stu-id="637ab-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="637ab-591">![工作流图：从Office 365 CDN检索资源](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "工作流：从Office 365 CDN源检索资源")</span><span class="sxs-lookup"><span data-stu-id="637ab-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="637ab-592">私有源中基于令牌的授权</span><span class="sxs-lookup"><span data-stu-id="637ab-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="637ab-593">对专用源中资产的访问权限Office 365 CDN由 SharePoint Online 生成的令牌授予。</span><span class="sxs-lookup"><span data-stu-id="637ab-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="637ab-594">对于已有权访问由源指定的文件夹或库的用户，系统会自动授予允许用户基于其权限级别访问文件的令牌。</span><span class="sxs-lookup"><span data-stu-id="637ab-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="637ab-595">这些访问令牌在生成后 30 到 90 分钟内有效，以帮助防止令牌重播攻击。</span><span class="sxs-lookup"><span data-stu-id="637ab-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="637ab-596">生成访问令牌后，SharePoint Online 会向包含两个授权参数的客户端返回自定义 URI， (边缘授权令牌) 和 _oat_ (源授权令牌) 。</span><span class="sxs-lookup"><span data-stu-id="637ab-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="637ab-597">每个令牌的结构以<格式的过期时间>__<_安全签名>。_</span><span class="sxs-lookup"><span data-stu-id="637ab-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="637ab-598">例如：</span><span class="sxs-lookup"><span data-stu-id="637ab-598">For example:</span></span>

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="637ab-599">拥有令牌的任何人都可以访问 CDN。</span><span class="sxs-lookup"><span data-stu-id="637ab-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="637ab-600">但是，包含这些访问令牌的 URL 仅通过 HTTPS 共享，因此除非 URL 在令牌过期之前由最终用户显式共享，否则未经授权的用户无法访问资产。</span><span class="sxs-lookup"><span data-stu-id="637ab-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="637ab-601">私有源中的资产不支持项目级权限</span><span class="sxs-lookup"><span data-stu-id="637ab-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="637ab-602">需要注意的是，SharePoint Online 不支持私有源中的资产的项目级权限。</span><span class="sxs-lookup"><span data-stu-id="637ab-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="637ab-603">例如，对于位于 的文件，在 满足以下条件的情况下，用户 `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` 具有对文件的有效访问权限：</span><span class="sxs-lookup"><span data-stu-id="637ab-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="637ab-604">User</span><span class="sxs-lookup"><span data-stu-id="637ab-604">User</span></span>  |<span data-ttu-id="637ab-605">权限</span><span class="sxs-lookup"><span data-stu-id="637ab-605">Permissions</span></span>  |<span data-ttu-id="637ab-606">有效访问</span><span class="sxs-lookup"><span data-stu-id="637ab-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="637ab-607">用户 1</span><span class="sxs-lookup"><span data-stu-id="637ab-607">User 1</span></span>     |<span data-ttu-id="637ab-608">有权访问 folder1</span><span class="sxs-lookup"><span data-stu-id="637ab-608">Has access to folder1</span></span>         |<span data-ttu-id="637ab-609">可以从image1.jpg访问CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="637ab-610">用户 2</span><span class="sxs-lookup"><span data-stu-id="637ab-610">User 2</span></span>     |<span data-ttu-id="637ab-611">无法访问 folder1</span><span class="sxs-lookup"><span data-stu-id="637ab-611">Does not have access to folder1</span></span>         |<span data-ttu-id="637ab-612">无法从image1.jpg访问CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="637ab-613">用户 3</span><span class="sxs-lookup"><span data-stu-id="637ab-613">User 3</span></span>     |<span data-ttu-id="637ab-614">无权访问 folder1，但被授予了访问 image1.jpg Online SharePoint权限</span><span class="sxs-lookup"><span data-stu-id="637ab-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="637ab-615">可以直接从 image1.jpg Online 访问资产SharePoint，但不能从 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="637ab-616">用户 4</span><span class="sxs-lookup"><span data-stu-id="637ab-616">User 4</span></span>     |<span data-ttu-id="637ab-617">具有对 folder1 的访问权限，但已明确拒绝image1.jpg SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="637ab-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="637ab-618">无法从 SharePoint Online 访问资产，但可以从 CDN 访问资产，尽管被拒绝访问 SharePoint Online 中的文件</span><span class="sxs-lookup"><span data-stu-id="637ab-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="637ab-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="637ab-620">疑难解答Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="637ab-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="637ab-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="637ab-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="637ab-622">如何确认资产由组织CDN？</span><span class="sxs-lookup"><span data-stu-id="637ab-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="637ab-623">向页面添加指向 CDN 资产的链接后，您可以通过浏览到该页面、在图像呈现并查看图像 URL 后右键单击图像来确认资产是否从 CDN 提供。</span><span class="sxs-lookup"><span data-stu-id="637ab-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="637ab-624">您还可以使用浏览器的开发人员工具查看页面上每个资产的 URL，或使用第三方网络跟踪工具。</span><span class="sxs-lookup"><span data-stu-id="637ab-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="637ab-625">如果使用网络工具（如 Fiddler）在从 SharePoint 页面呈现资产外测试资产，则必须手动将引用器标头"Referer： "添加到 GET 请求，其中 URL 是 SharePoint Online 租户的根 `https://yourdomain.sharepoint.com` URL。</span><span class="sxs-lookup"><span data-stu-id="637ab-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="637ab-626">无法直接CDN Web 浏览器中测试 URL，因为必须有来自 SharePoint Online 的参考程序。</span><span class="sxs-lookup"><span data-stu-id="637ab-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="637ab-627">但是，如果您将CDN资源 URL 添加到 SharePoint 页面，然后在浏览器中打开该页面，则会看到页面上呈现的 CDN 资源。</span><span class="sxs-lookup"><span data-stu-id="637ab-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="637ab-628">有关在浏览器浏览器中使用开发人员工具Microsoft Edge，请参阅Microsoft Edge[工具。](/microsoft-edge/devtools-guide)</span><span class="sxs-lookup"><span data-stu-id="637ab-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="637ab-629">若要观看 SharePoint 开发人员模式和做法[YouTube](https://aka.ms/sppnp-videos)频道中托管的简短视频，演示如何验证 CDN 是否正常工作，请参阅验证[CDN 使用情况](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)并确保最佳网络连接。</span><span class="sxs-lookup"><span data-stu-id="637ab-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="637ab-630">为什么新源中的资产不可用？</span><span class="sxs-lookup"><span data-stu-id="637ab-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="637ab-631">新源中的资产不会立即可供使用，因为注册需要一段时间才能传遍 CDN 并且需要将资产从源上载到 CDN 存储。</span><span class="sxs-lookup"><span data-stu-id="637ab-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="637ab-632">资源在文件中可用CDN取决于资产数量和文件大小。</span><span class="sxs-lookup"><span data-stu-id="637ab-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="637ab-633">我的客户端 Web 部件或SharePoint 框架解决方案无法工作</span><span class="sxs-lookup"><span data-stu-id="637ab-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="637ab-634">为公用源Office 365 CDN时，CDN服务会自动创建这些默认源：</span><span class="sxs-lookup"><span data-stu-id="637ab-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="637ab-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="637ab-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="637ab-636">\*/STYLE 库</span><span class="sxs-lookup"><span data-stu-id="637ab-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="637ab-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="637ab-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="637ab-638">如果缺少 \*/clientsideassets 源，SharePoint 框架解决方案将失败，并且不会生成警告或错误消息。</span><span class="sxs-lookup"><span data-stu-id="637ab-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="637ab-639">此源可能丢失，原因是CDN _-NoDefaultOrigins_ 参数设置为 **$true** 启用该源，或者因为已手动删除源。</span><span class="sxs-lookup"><span data-stu-id="637ab-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="637ab-640">可以通过以下 PowerShell 命令查看存在哪些源：</span><span class="sxs-lookup"><span data-stu-id="637ab-640">You can check to see which origins are present with the following PowerShell command:</span></span>

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="637ab-641">或者，你可以检查以下Office 365 CLI：</span><span class="sxs-lookup"><span data-stu-id="637ab-641">Or you can check with the Office 365 CLI:</span></span>

```cli
spo cdn origin list
```

<span data-ttu-id="637ab-642">若要在 PowerShell 中添加源：：</span><span class="sxs-lookup"><span data-stu-id="637ab-642">To add the origin in PowerShell:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="637ab-643">若要在 CLI 中添加Office 365 CLI：</span><span class="sxs-lookup"><span data-stu-id="637ab-643">To add the origin in the Office 365 CLI:</span></span>

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="637ab-644">我需要使用哪些 PowerShell 模块和 CLI shell 来使用Office 365 CDN？</span><span class="sxs-lookup"><span data-stu-id="637ab-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="637ab-645">可以选择使用 Office 365 CDN **Online 命令行** 管理程序 PowerShell 模块SharePoint或 OFFICE 365 **CLI。**</span><span class="sxs-lookup"><span data-stu-id="637ab-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="637ab-646">SharePoint Online 命令行管理程序入门</span><span class="sxs-lookup"><span data-stu-id="637ab-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
+ [<span data-ttu-id="637ab-647">安装 Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="637ab-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="637ab-648">另请参阅</span><span class="sxs-lookup"><span data-stu-id="637ab-648">See also</span></span>

[<span data-ttu-id="637ab-649">内容分发网络</span><span class="sxs-lookup"><span data-stu-id="637ab-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="637ab-650">Office 365 网络计划和性能优化</span><span class="sxs-lookup"><span data-stu-id="637ab-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="637ab-651">SharePoint性能系列 - Office 365 CDN视频系列</span><span class="sxs-lookup"><span data-stu-id="637ab-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
