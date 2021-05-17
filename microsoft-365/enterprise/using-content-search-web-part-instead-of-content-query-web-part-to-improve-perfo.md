---
title: 使用内容搜索Web 部件而不是内容Web 部件来改进 SharePoint Online 中的性能
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
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
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: 了解如何在 SharePoint Server 2013 和 SharePoint Online 中将内容查询Web 部件替换为内容搜索Web 部件来提高性能。
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688187"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="3209e-103">使用内容搜索Web 部件而不是内容Web 部件来改进 SharePoint Online 中的性能</span><span class="sxs-lookup"><span data-stu-id="3209e-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="3209e-104">本文介绍如何在 SharePoint Server 2013 和 SharePoint Online 中将内容查询Web 部件替换为内容搜索 Web 部件 来提高性能。</span><span class="sxs-lookup"><span data-stu-id="3209e-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="3209e-105">SharePoint Server 2013 和 SharePoint Online 最强大的新功能之一是内容搜索 Web 部件 (CSWP) 。</span><span class="sxs-lookup"><span data-stu-id="3209e-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="3209e-106">This Web 部件 uses the search index to quickly retrieve results which are shown to the user.</span><span class="sxs-lookup"><span data-stu-id="3209e-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="3209e-107">在页面中Web 部件内容搜索功能，Web 部件 (CQWP) 内容查询功能，为用户提高性能。</span><span class="sxs-lookup"><span data-stu-id="3209e-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="3209e-108">通过内容查询Web 部件内容搜索Web 部件几乎总是可以显著提高 SharePoint Online 上的页面加载性能。</span><span class="sxs-lookup"><span data-stu-id="3209e-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="3209e-109">有一些额外的配置可获取正确的查询，但奖励是改进性能和提高用户业绩。</span><span class="sxs-lookup"><span data-stu-id="3209e-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="3209e-110">比较使用内容搜索功能而非内容Web 部件搜索功能获得的性能Web 部件</span><span class="sxs-lookup"><span data-stu-id="3209e-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="3209e-111">以下示例显示使用内容搜索服务（而不是内容查询搜索Web 部件可能会获得的相对性能Web 部件。</span><span class="sxs-lookup"><span data-stu-id="3209e-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="3209e-112">对于复杂的网站结构和非常广泛的内容查询，效果更为明显。</span><span class="sxs-lookup"><span data-stu-id="3209e-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="3209e-113">此示例网站具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="3209e-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="3209e-114">8 级子网站。</span><span class="sxs-lookup"><span data-stu-id="3209e-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="3209e-115">使用自定义"菜"内容类型的列表。</span><span class="sxs-lookup"><span data-stu-id="3209e-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="3209e-116">在Web 部件中，内容查询很广泛，返回内容类型为"fruit"的所有项。</span><span class="sxs-lookup"><span data-stu-id="3209e-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="3209e-117">此示例在 8 个网站中仅使用 50 个项目。</span><span class="sxs-lookup"><span data-stu-id="3209e-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="3209e-118">对于内容更多的网站，效果将更加明显。</span><span class="sxs-lookup"><span data-stu-id="3209e-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="3209e-119">下面是内容查询查询结果的屏幕截图Web 部件。</span><span class="sxs-lookup"><span data-stu-id="3209e-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![显示 Web 部件的内容查询的图形](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="3209e-121">在Internet Explorer中，使用 F12 开发人员工具的"网络"选项卡查看响应标头的详细信息。 </span><span class="sxs-lookup"><span data-stu-id="3209e-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="3209e-122">在下面的屏幕截图中， **此页面加载的 SPRequestDuration** 的值为 924 毫秒。</span><span class="sxs-lookup"><span data-stu-id="3209e-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![显示请求持续时间为 924 的屏幕截图](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="3209e-124">**SPRequestDuration** 指示服务器上为准备页面而完成的工作量。</span><span class="sxs-lookup"><span data-stu-id="3209e-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="3209e-125">通过按查询Web 部件内容与搜索功能Web 部件可大大减少呈现页面所花的时间。</span><span class="sxs-lookup"><span data-stu-id="3209e-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="3209e-126">相比之下，具有等效内容搜索Web 部件返回相同数量的结果的页面的 **SPRequestDuration** 值为 106 毫秒，如以下屏幕截图中所示：</span><span class="sxs-lookup"><span data-stu-id="3209e-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![显示请求持续时间为 106 的屏幕截图](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="3209e-128">在 Web 部件 Online SharePoint内容搜索</span><span class="sxs-lookup"><span data-stu-id="3209e-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="3209e-129">添加内容搜索Web 部件与常规内容查询查询Web 部件。</span><span class="sxs-lookup"><span data-stu-id="3209e-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="3209e-130">请参阅 Configure *a Content Search Web 部件* in Web 部件 in SharePoint 中的"添加内容 [搜索SharePoint"](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)</span><span class="sxs-lookup"><span data-stu-id="3209e-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="3209e-131">为内容搜索服务创建正确的搜索Web 部件</span><span class="sxs-lookup"><span data-stu-id="3209e-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="3209e-132">添加内容搜索Web 部件，您可以优化搜索并返回您需要的项目。</span><span class="sxs-lookup"><span data-stu-id="3209e-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="3209e-133">有关如何执行此操作的详细说明，请参阅在 SharePoint 中配置内容搜索Web 部件中的"在内容搜索 *Web 部件* 中配置高级查询来显示 [内容SharePoint。](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)</span><span class="sxs-lookup"><span data-stu-id="3209e-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="3209e-134">查询生成和测试工具</span><span class="sxs-lookup"><span data-stu-id="3209e-134">Query building and testing tool</span></span>

<span data-ttu-id="3209e-135">有关生成和测试复杂查询的工具，请参阅 Codeplex 上的 [搜索](https://sp2013searchtool.codeplex.com/) 查询工具。</span><span class="sxs-lookup"><span data-stu-id="3209e-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  

