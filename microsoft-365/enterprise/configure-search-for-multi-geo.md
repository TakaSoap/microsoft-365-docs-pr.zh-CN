---
title: 为 Microsoft 365 多地理位置配置搜索
ms.reviewer: adwood
ms.author: tlarsen
author: tklarsen
manager: arnek
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: 了解如何在多地理位置环境中配置搜索。 只有某些客户端（如 OneDrive for Business）可以在多地理位置环境中返回结果。
ms.openlocfilehash: b3a96b1d0652cb954c58ae410583befa078460d9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911158"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a><span data-ttu-id="a2d54-104">为 Microsoft 365 多地理位置配置搜索</span><span class="sxs-lookup"><span data-stu-id="a2d54-104">Configure Search for Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="a2d54-105">在多地理位置环境中，每个地理位置都有自己的搜索索引和搜索中心。</span><span class="sxs-lookup"><span data-stu-id="a2d54-105">In a multi-geo environment, each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="a2d54-106">在用户搜索时，查询会扇出以覆盖所有索引，并合并返回的结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-106">When a user searches, the query is fanned out to all the indexes, and the returned results are merged.</span></span>

<span data-ttu-id="a2d54-107">例如，位于一个地理位置的用户可以搜索在另一个地理位置中存储的内容，也可以搜索只限不同地理位置的 SharePoint 网站内容。</span><span class="sxs-lookup"><span data-stu-id="a2d54-107">For example, a user in one geo location can search for content stored in another geo location, or for content on a SharePoint site that's restricted to a different geo location.</span></span> <span data-ttu-id="a2d54-108">如果用户有权访问此内容，便会看到搜索结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-108">If the user has access to this content, search will show the result.</span></span>

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a><span data-ttu-id="a2d54-109">在多地理位置环境中可以运行哪些搜索客户端？</span><span class="sxs-lookup"><span data-stu-id="a2d54-109">Which search clients work in a multi-geo environment?</span></span>

<span data-ttu-id="a2d54-110">这些客户端可以返回来自所有地理位置的结果：</span><span class="sxs-lookup"><span data-stu-id="a2d54-110">These clients can return results from all geo locations:</span></span>

- <span data-ttu-id="a2d54-111">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a2d54-111">OneDrive for Business</span></span>
- <span data-ttu-id="a2d54-112">Delve</span><span class="sxs-lookup"><span data-stu-id="a2d54-112">Delve</span></span>
- <span data-ttu-id="a2d54-113">SharePoint 主页</span><span class="sxs-lookup"><span data-stu-id="a2d54-113">The SharePoint home page</span></span>
- <span data-ttu-id="a2d54-114">搜索中心</span><span class="sxs-lookup"><span data-stu-id="a2d54-114">The Search Center</span></span>
- <span data-ttu-id="a2d54-115">使用 SharePoint 搜索 API 的自定义搜索应用程序</span><span class="sxs-lookup"><span data-stu-id="a2d54-115">Custom search applications that use the SharePoint Search API</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="a2d54-116">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a2d54-116">OneDrive for Business</span></span>

<span data-ttu-id="a2d54-117">多地理位置环境一旦设置，在 OneDrive 中搜索的用户即可获得来自所有地理位置的结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-117">As soon as the multi-geo environment has been set up, users that search in OneDrive get results from all geo locations.</span></span>

### <a name="delve"></a><span data-ttu-id="a2d54-118">Delve</span><span class="sxs-lookup"><span data-stu-id="a2d54-118">Delve</span></span>

<span data-ttu-id="a2d54-119">多地理位置环境一旦设置，在 Delve 中搜索的用户即可获得来自所有地理位置的结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-119">As soon as the multi-geo environment has been set up, users that search in Delve get results from all geo locations.</span></span>

<span data-ttu-id="a2d54-120">Delve 源和个人资料卡仅显示存储在中心位置的文件的预览。</span><span class="sxs-lookup"><span data-stu-id="a2d54-120">The Delve feed and the profile card only show previews of files that are stored in the central location.</span></span> <span data-ttu-id="a2d54-121">对于存储在附属位置的文件，则会显示文件类型的图标。</span><span class="sxs-lookup"><span data-stu-id="a2d54-121">For files that are stored in satellite locations, the icon for the file type is shown instead.</span></span>

### <a name="the-sharepoint-home-page"></a><span data-ttu-id="a2d54-122">SharePoint 主页</span><span class="sxs-lookup"><span data-stu-id="a2d54-122">The SharePoint home page</span></span>

<span data-ttu-id="a2d54-p105">多地理位置环境一旦设置，用户即可在其 SharePoint 主页上看到来自多地理位置的资讯、最近访问和关注的网站。如果他们使用 SharePoint 主页上的搜索框，则他们将获得来自多地理位置的合并结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-p105">As soon as the multi-geo environment has been set up, users will see news, recent and followed sites from multiple geo locations on their SharePoint home page. If they use the search box on the SharePoint home page, they'll get merged results from multiple geo locations.</span></span>

### <a name="the-search-center"></a><span data-ttu-id="a2d54-125">搜索中心</span><span class="sxs-lookup"><span data-stu-id="a2d54-125">The Search Center</span></span>

<span data-ttu-id="a2d54-p106">多地理位置环境设置后，每个搜索中心将继续仅显示来自其各自地理位置的结果。管理员必须[更改每个搜索中心的设置](#_Set_up_a_1)，以获取来自所有地理位置的结果。之后，在搜索中心搜索的用户将获得来自所有地理位置的结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-p106">After the multi-geo environment has been set up, each Search Center continues to only show results from their own geo location. Admins must [change the settings of each Search Center](#_Set_up_a_1) to get results from all geo locations. Afterwards, users that search in the Search Center get results from all geo locations.</span></span>

### <a name="custom-search-applications"></a><span data-ttu-id="a2d54-129">自定义搜索应用程序</span><span class="sxs-lookup"><span data-stu-id="a2d54-129">Custom search applications</span></span>

<span data-ttu-id="a2d54-p107">同样，自定义搜索应用程序使用现有 SharePoint Search REST API 与搜索索引进行交互。若要获取来自所有（或部分）地理位置的结果，应用程序必须在请求中[调用 API 并包含新的多地理位置查询参数](#_Get_custom_search)。这将触发对所有地理位置的查询扇出。</span><span class="sxs-lookup"><span data-stu-id="a2d54-p107">As usual, custom search applications interact with the search indexes by using the existing SharePoint Search REST APIs. To get results from all, or some geo locations, the application must [call the API and include the new Multi-Geo query parameters](#_Get_custom_search) in the request. This triggers a fan out of the query to all geo locations.</span></span>

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a><span data-ttu-id="a2d54-133">在多地理位置环境中搜索有什么不同之处？</span><span class="sxs-lookup"><span data-stu-id="a2d54-133">What's different about search in a multi-geo environment?</span></span>

<span data-ttu-id="a2d54-134">你所熟悉的某些搜索功能在多地理位置环境中的工作方式可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="a2d54-134">Some search features you might be familiar with, work differently in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a2d54-135"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="a2d54-135"><strong>Feature</strong></span></span></th>
<th align="left"><span data-ttu-id="a2d54-136"><strong>工作原理</strong></span><span class="sxs-lookup"><span data-stu-id="a2d54-136"><strong>How it works</strong></span></span></th>
<th align="left"><span data-ttu-id="a2d54-137"><strong>解决方法</strong></span><span class="sxs-lookup"><span data-stu-id="a2d54-137"><strong>Workaround</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="a2d54-138">升级的结果</span><span class="sxs-lookup"><span data-stu-id="a2d54-138">Promoted results</span></span></td>
<td align="left"><span data-ttu-id="a2d54-139">您可以在不同级别创建具有升级的结果的查询规则：整个租户、网站集或网站。</span><span class="sxs-lookup"><span data-stu-id="a2d54-139">You can create query rules with promoted results at different levels: for the whole tenant, for a site collection, or for a site.</span></span> <span data-ttu-id="a2d54-140">在多地理位置环境中的租户级别定义升级的结果，以便将结果升级到所有地理位置中的搜索中心。</span><span class="sxs-lookup"><span data-stu-id="a2d54-140">In a multi-geo environment, define promoted results at the tenant level to promote the results to the Search Centers in all geo locations.</span></span> <span data-ttu-id="a2d54-141">如果只想升级位于站点集或站点的搜索中心中的结果，请在站点集或站点级别定义升级的结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-141">If you only want to promote results in the Search Center that's in the geo location of the site collection or site, define the promoted results at the site collection or site level.</span></span> <span data-ttu-id="a2d54-142">不会升级位于其他地理位置的结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-142">These results are not promoted in other geo locations.</span></span></td>
<td align="left"><span data-ttu-id="a2d54-143">如果不需要对每个地理位置使用不同的升级结果（例如，在出差时使用不同的规则），我们建议在租户级别定义升级的结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-143">If you don't need different promoted results per geo location, for example different rules for traveling, we recommend defining promoted results at the tenant level.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="a2d54-144">搜索精简</span><span class="sxs-lookup"><span data-stu-id="a2d54-144">Search refiners</span></span></td>
<td align="left"><span data-ttu-id="a2d54-p109">搜索将返回来自租户的所有地理位置的精简内容，然后对其进行聚合。聚合是最佳做法，意味着精简计数可能并非 100% 准确。对于大部分搜索驱动的方案，此准确度已足够。 </span><span class="sxs-lookup"><span data-stu-id="a2d54-p109">Search returns refiners from all the geo locations of a tenant and then aggregates them. The aggregation is a best effort, meaning that the refiner counts might not be 100% accurate. For most search-driven scenarios, this accuracy is sufficient. </span></span></td>
<td align="left"><span data-ttu-id="a2d54-148">对于依赖于精简完整度的搜索驱动的应用程序，请单独查询每个地理位置。</span><span class="sxs-lookup"><span data-stu-id="a2d54-148">For search-driven applications that depend on refiner completeness, query each geo location independently.</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="a2d54-149">多地理位置搜索不支持数值精简的动态存储桶。</span><span class="sxs-lookup"><span data-stu-id="a2d54-149">Multi-geo search doesn't support dynamic bucketing for numerical refiners.</span></span></td>
<td align="left"><span data-ttu-id="a2d54-150">对 <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">数字精简条件使用"Discretize"</a> 参数。</span><span class="sxs-lookup"><span data-stu-id="a2d54-150">Use the <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">"Discretize" parameter</a> for numerical refiners.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="a2d54-151">文档 ID</span><span class="sxs-lookup"><span data-stu-id="a2d54-151">Document IDs</span></span></td>
<td align="left"><span data-ttu-id="a2d54-152">如果正在开发依赖于文档 ID 的搜索驱动的应用程序，请注意，多地理位置环境中的文档 ID 对所有地理位置来说并不是唯一的，它们只对每个地理位置来说是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a2d54-152">If you're developing a search-driven application that depends on document IDs, note that document IDs in a multi-geo environment aren't unique across geo locations, they are unique per geo location.</span></span></td>
<td align="left"><span data-ttu-id="a2d54-153">我们添加了用于标识地理位置的列。</span><span class="sxs-lookup"><span data-stu-id="a2d54-153">We've added a column that identifies the geo location.</span></span> <span data-ttu-id="a2d54-154">使用此列来实现唯一性。</span><span class="sxs-lookup"><span data-stu-id="a2d54-154">Use this column to achieve uniqueness.</span></span> <span data-ttu-id="a2d54-155">此列名为"GeoLocationSource"。</span><span class="sxs-lookup"><span data-stu-id="a2d54-155">This column is named "GeoLocationSource".</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="a2d54-156">结果数</span><span class="sxs-lookup"><span data-stu-id="a2d54-156">Number of results</span></span></td>
<td align="left"><span data-ttu-id="a2d54-157">搜索结果页将显示来自地理位置的组合结果，但该页显示的结果不能超过 500 个。</span><span class="sxs-lookup"><span data-stu-id="a2d54-157">The search results page shows combined results from the geo locations, but it's not possible to page beyond 500 results.</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="a2d54-158">混合搜索</span><span class="sxs-lookup"><span data-stu-id="a2d54-158">Hybrid search</span></span></td>
<td align="left"><span data-ttu-id="a2d54-159">在具有<a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">云混合搜索</a>的混合 SharePoint 环境中，本地内容将添加到中心位置的 Microsoft 365 索引。</span><span class="sxs-lookup"><span data-stu-id="a2d54-159">In a hybrid SharePoint environment with <a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">cloud hybrid search</a>,  on-premises content is added to the Microsoft 365 index of the central location.</span></span></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a><span data-ttu-id="a2d54-160">在多地理位置环境中不支持的搜索有哪些？</span><span class="sxs-lookup"><span data-stu-id="a2d54-160">What's not supported for search in a multi-geo environment?</span></span>

<span data-ttu-id="a2d54-161">你所熟悉的某些搜索功能在多地理位置环境中可能不受支持。</span><span class="sxs-lookup"><span data-stu-id="a2d54-161">Some of the search features you might be familiar with, aren't supported in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a2d54-162"><strong>搜索功能</strong></span><span class="sxs-lookup"><span data-stu-id="a2d54-162"><strong>Search feature</strong></span></span></th>
<th align="left"><span data-ttu-id="a2d54-163"><strong>注意</strong></span><span class="sxs-lookup"><span data-stu-id="a2d54-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="a2d54-164">仅应用身份验证</span><span class="sxs-lookup"><span data-stu-id="a2d54-164">App-only authentication</span></span></td>
<td align="left"><span data-ttu-id="a2d54-165">在多地理位置搜索中不支持仅应用身份验证（来自服务的特权访问）。</span><span class="sxs-lookup"><span data-stu-id="a2d54-165">App-only authentication (privileged access from services) isn't supported in multi-geo search.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="a2d54-166">来宾用户</span><span class="sxs-lookup"><span data-stu-id="a2d54-166">Guest users</span></span></td>
<td align="left"><span data-ttu-id="a2d54-167">来宾用户仅获得其搜索的地理位置中的结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-167">Guest users only get results from the geo location that they're searching from.</span></span></td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a><span data-ttu-id="a2d54-168">如何在多地理位置环境中进行搜索？</span><span class="sxs-lookup"><span data-stu-id="a2d54-168">How does search work in a multi-geo environment?</span></span>

<span data-ttu-id="a2d54-169">所有搜索客户端均使用现有 SharePoint Search REST API 与搜索索引进行交互。</span><span class="sxs-lookup"><span data-stu-id="a2d54-169">All the search clients use the existing SharePoint Search REST APIs to interact with the search indexes.</span></span>

![显示 SharePoint 搜索 REST API 如何与搜索索引交互的关系图](../media/configure-search-for-multi-geo-image1-1.png)

1. <span data-ttu-id="a2d54-171">搜索客户端使用查询属性 EnableMultiGeoSearch= true 来调用搜索 REST 终结点。</span><span class="sxs-lookup"><span data-stu-id="a2d54-171">A search client calls the Search REST endpoint with the query property EnableMultiGeoSearch= true.</span></span>
2. <span data-ttu-id="a2d54-172">查询将被发送到租户中的所有地理位置。</span><span class="sxs-lookup"><span data-stu-id="a2d54-172">The query is sent to all geo locations in the tenant.</span></span>
3. <span data-ttu-id="a2d54-173">将对来自每个地理位置的搜索结果进行合并和排名。</span><span class="sxs-lookup"><span data-stu-id="a2d54-173">Search results from each geo location are merged and ranked.</span></span>
4. <span data-ttu-id="a2d54-174">客户端将获得统一的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-174">The client gets unified search results.</span></span>

<span data-ttu-id="a2d54-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>请注意，在收到来自所有地理位置的结果之前，我们不会合并搜索结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Notice that we don't merge the search results until we've received results from all the geo locations.</span></span> <span data-ttu-id="a2d54-176">这意味着，与仅包含一个地理位置的环境中的搜索相比，多地理位置搜索会有额外的延迟。</span><span class="sxs-lookup"><span data-stu-id="a2d54-176">This means that multi-geo searches have additional latency compared to searches in an environment with only one geo location.</span></span>

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a><span data-ttu-id="a2d54-177">获取搜索中心以显示来自所有地理位置的结果</span><span class="sxs-lookup"><span data-stu-id="a2d54-177">Get a Search Center to show results from all geo locations</span></span>

<span data-ttu-id="a2d54-178">每个搜索中心具有多个类别，必须单独设置每个类别。</span><span class="sxs-lookup"><span data-stu-id="a2d54-178">Each Search Center has several verticals and you have to set up each vertical individually.</span></span>

1. <span data-ttu-id="a2d54-179">请确保执行这些步骤所使用的帐户具有编辑搜索结果页和搜索结果 Web 部件的权限。</span><span class="sxs-lookup"><span data-stu-id="a2d54-179">Ensure that you perform these steps with an account that has permission to edit the search results page and the Search Result Web Part.</span></span>

2. <span data-ttu-id="a2d54-180">导航到搜索结果页（请参阅搜索结果页的[列表](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213)）</span><span class="sxs-lookup"><span data-stu-id="a2d54-180">Navigate to the search results page (see the [list](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) of search results pages)</span></span>

3. <span data-ttu-id="a2d54-p112">选择要设置的类别，单击右上角的 **“设置”** 齿轮图标，然后单击 **“编辑页面”**。搜索结果页将在编辑模式下打开。</span><span class="sxs-lookup"><span data-stu-id="a2d54-p112">Select the vertical to set up, click **Settings** gear icon in the upper, right corner, and then click **Edit Page**. The search results page opens in Edit mode.</span></span>

   ![在"设置"中编辑页面选择](../media/configure-search-for-multi-geo-image2.png)

4. <span data-ttu-id="a2d54-184">在搜索结果 Web 部件中，将鼠标指针移动到 Web 部件的右上角，单击箭头，然后单击菜单上的“**编辑 Web 部件** ”。</span><span class="sxs-lookup"><span data-stu-id="a2d54-184">In the Search Results Web Part, move the pointer to the upper, right corner of the web part, click the arrow, and then click **Edit Web Part** on the menu.</span></span> <span data-ttu-id="a2d54-185">搜索结果 Web 部件工具窗格在页面右上角的功能区下方打开。</span><span class="sxs-lookup"><span data-stu-id="a2d54-185">The Search Results Web Part tool pane opens under the ribbon in the top right of the page.</span></span>

   ![编辑Web 部件选择](../media/configure-search-for-multi-geo-image3.png)

5. <span data-ttu-id="a2d54-187">在 Web 部件工具窗格中的 **“设置”** 部分，在 **“结果控制设置”** 下，选择 **“显示多地理位置结果”**，获取搜索结果 Web 部件，以显示来自所有地理位置的结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-187">In the Web Part tool pane, in the **Settings** section, under **Results control settings**, select **Show Multi-Geo results** to get the Search Results Web Part to show results from all geo locations.</span></span>

6. <span data-ttu-id="a2d54-188">单击 **“确定”**，以保存更改并关闭 Web 部件工具窗格。</span><span class="sxs-lookup"><span data-stu-id="a2d54-188">Click **OK** to save your change and close the Web Part tool pane.</span></span>

7. <span data-ttu-id="a2d54-189">单击主菜单 **“页面”选项卡上的“签入”**，查看对搜索结果 Web 部件所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a2d54-189">Check your changes to the Search Results Web Part by clicking **Check-In** on the Page tab of the main menu.</span></span>

8. <span data-ttu-id="a2d54-190">使用页面顶部的注释中提供的链接来发布更改。</span><span class="sxs-lookup"><span data-stu-id="a2d54-190">Publish the changes by using the link provided in the note at the top of the page.</span></span>

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a><span data-ttu-id="a2d54-191">获取自定义搜索应用程序，以显示来自所有（或部分）地理位置的结果</span><span class="sxs-lookup"><span data-stu-id="a2d54-191">Get custom search applications to show results from all or some geo locations</span></span>

<span data-ttu-id="a2d54-192">自定义搜索应用程序通过使用对 SharePoint 搜索 REST API 的请求指定查询参数，从所有或部分地理位置获取结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-192">Custom search applications get results from all, or some, geo locations by specifying query parameters with the request to the SharePoint Search REST API.</span></span> <span data-ttu-id="a2d54-193">根据查询参数，查询会扇出到所有地理位置或某些地理位置。</span><span class="sxs-lookup"><span data-stu-id="a2d54-193">Depending on the query parameters, the query is fanned out to all geo locations, or to some geo locations.</span></span> <span data-ttu-id="a2d54-194">例如，如果只需要查询地理位置的子集以查找相关信息，你可以仅控制扇出到这些地理位置。</span><span class="sxs-lookup"><span data-stu-id="a2d54-194">For example, if you only need to query a subset of geo locations to find relevant information, you can control the fan out to only these.</span></span> <span data-ttu-id="a2d54-195">如果请求成功，SharePoint 搜索 REST API 将返回响应数据。</span><span class="sxs-lookup"><span data-stu-id="a2d54-195">If the request succeeds, the SharePoint Search REST API returns response data.</span></span>

### <a name="requirement"></a><span data-ttu-id="a2d54-196">要求</span><span class="sxs-lookup"><span data-stu-id="a2d54-196">Requirement</span></span>

<span data-ttu-id="a2d54-p115">对于每个地理位置，必须确保组织中的所有用户都已授予根网站（例如 contoso **APAC**.sharepoint.com/ and contoso **EU**.sharepoint.com/）的 **读取** 权限级别。[了解权限](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848)。</span><span class="sxs-lookup"><span data-stu-id="a2d54-p115">For each geo location, you must ensure that all users in the organization have been granted the **Read** permission level for the root website (for example contoso **APAC**.sharepoint.com/ and contoso **EU**.sharepoint.com/). [Learn about permissions](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span></span>

### <a name="query-parameters"></a><span data-ttu-id="a2d54-199">查询参数</span><span class="sxs-lookup"><span data-stu-id="a2d54-199">Query parameters</span></span>

<span data-ttu-id="a2d54-200">EnableMultiGeoSearch - 此布尔值指定是否应将查询扇出到多地理位置租户的其他地理位置的索引。</span><span class="sxs-lookup"><span data-stu-id="a2d54-200">EnableMultiGeoSearch - This is a Boolean value that specifies whether the query shall be fanned out to the indexes of other geo locations of the multi-geo tenant.</span></span> <span data-ttu-id="a2d54-201">将其设置为 **true** 以扇出查询；设置为 **false** 则不扇出查询。</span><span class="sxs-lookup"><span data-stu-id="a2d54-201">Set it to **true** to fan out the query; **false** to not fan out the query.</span></span> <span data-ttu-id="a2d54-202">如果不包含此参数，则默认值为 **false**（除非针对使用企业搜索中心模板的网站执行 REST API 调用，在这种情况下，默认值为 **true**）。</span><span class="sxs-lookup"><span data-stu-id="a2d54-202">If you don't include this parameter, the default value is **false**, except when making a REST API call against a site which uses the Enterprise Search Center template, in this case the default value is **true**.</span></span> <span data-ttu-id="a2d54-203">如果在非多地理位置环境中使用该参数，则会忽略该参数。</span><span class="sxs-lookup"><span data-stu-id="a2d54-203">If you use the parameter in an environment that isn't multi-geo, the parameter is ignored.</span></span>

<span data-ttu-id="a2d54-204">ClientType - 此参数为字符串。</span><span class="sxs-lookup"><span data-stu-id="a2d54-204">ClientType - This is a string.</span></span> <span data-ttu-id="a2d54-205">输入每个搜索应用程序的唯一客户端名称。</span><span class="sxs-lookup"><span data-stu-id="a2d54-205">Enter a unique client name for each search application.</span></span> <span data-ttu-id="a2d54-206">如果不包括此参数，则不会将查询扇出到其他地理位置。</span><span class="sxs-lookup"><span data-stu-id="a2d54-206">If you don't include this parameter, the query is not fanned out to other geo locations.</span></span>

<span data-ttu-id="a2d54-207">MultiGeoSearchConfiguration - 这是一个可选列表，其中包含多地理位置租户中的一些地理位置，当 **EnableMultiGeoSearch** 为 **true** 时，会将查询扇出到这些地理位置。</span><span class="sxs-lookup"><span data-stu-id="a2d54-207">MultiGeoSearchConfiguration - This is an optional list of which geo locations in the multi-geo tenant to fan the query out to when **EnableMultiGeoSearch** is **true**.</span></span> <span data-ttu-id="a2d54-208">如果不包括此参数，或将其保留为空白，则会将查询扇出到所有地理位置。</span><span class="sxs-lookup"><span data-stu-id="a2d54-208">If you don't include this parameter, or leave it blank, the query is fanned out to all geo locations.</span></span> <span data-ttu-id="a2d54-209">对于每个地理位置，请以 JSON 格式输入以下各项：</span><span class="sxs-lookup"><span data-stu-id="a2d54-209">For each geo location, enter the following items, in JSON format:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a2d54-210">项目</span><span class="sxs-lookup"><span data-stu-id="a2d54-210">Item</span></span></th>
<th align="left"><span data-ttu-id="a2d54-211">说明</span><span class="sxs-lookup"><span data-stu-id="a2d54-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="a2d54-212">DataLocation</span><span class="sxs-lookup"><span data-stu-id="a2d54-212">DataLocation</span></span></td>
<td align="left"><span data-ttu-id="a2d54-213">地理位置，例如 NAM。</span><span class="sxs-lookup"><span data-stu-id="a2d54-213">The geo location, for example NAM.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="a2d54-214">终结点</span><span class="sxs-lookup"><span data-stu-id="a2d54-214">EndPoint</span></span></td>
<td align="left"><span data-ttu-id="a2d54-215">要连接到的终结点，例如 https://contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="a2d54-215">The endpoint to connect to, for example https://contoso.sharepoint.com</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="a2d54-216">SourceId</span><span class="sxs-lookup"><span data-stu-id="a2d54-216">SourceId</span></span></td>
<td align="left"><span data-ttu-id="a2d54-217">结果源的 GUID，例如 B81EAB55-3140-4312-B0F4-9459D1B4FFEE。</span><span class="sxs-lookup"><span data-stu-id="a2d54-217">The GUID of the result source, for example B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a2d54-p119">如果省略 DataLocation 或终结点，或如果 DataLocation 是重复的，则请求将会失败。[可以使用 Microsoft Graph 获取有关租户地理位置终结点的信息](/sharepoint/dev/solution-guidance/multigeo-discovery)。</span><span class="sxs-lookup"><span data-stu-id="a2d54-p119">If you omit DataLocation or EndPoint, or if a DataLocation is duplicated, the request fails. [You can get information about the endpoint of a tenant's geo locations by using Microsoft Graph](/sharepoint/dev/solution-guidance/multigeo-discovery).</span></span>

### <a name="response-data"></a><span data-ttu-id="a2d54-220">响应数据</span><span class="sxs-lookup"><span data-stu-id="a2d54-220">Response data</span></span>

<span data-ttu-id="a2d54-p120">MultiGeoSearchStatus - 这是 SharePoint Search API 响应请求返回的属性。该属性的值是一个字符串，提供有关 SharePoint Search API 所返回结果的以下信息：</span><span class="sxs-lookup"><span data-stu-id="a2d54-p120">MultiGeoSearchStatus – This is a property that the SharePoint Search API returns in response to a request. The value of the property is a string and gives the following information about the results that the SharePoint Search API returns:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a2d54-223">值</span><span class="sxs-lookup"><span data-stu-id="a2d54-223">Value</span></span></th>
<th align="left"><span data-ttu-id="a2d54-224">说明</span><span class="sxs-lookup"><span data-stu-id="a2d54-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="a2d54-225">完整</span><span class="sxs-lookup"><span data-stu-id="a2d54-225">Full</span></span></td>
<td align="left"><span data-ttu-id="a2d54-226">来自<strong>所有</strong>地理位置的完整结果。</span><span class="sxs-lookup"><span data-stu-id="a2d54-226">Full results from <strong>all</strong> the geo locations.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="a2d54-227">部分</span><span class="sxs-lookup"><span data-stu-id="a2d54-227">Partial</span></span></td>
<td align="left"><span data-ttu-id="a2d54-p121">来自一个或多个地理位置的部分结果。由于暂时性错误，该结果不完整。</span><span class="sxs-lookup"><span data-stu-id="a2d54-p121">Partial results from one or more geo locations. The results are incomplete due to a transient error.</span></span></td>
</tr>
</tbody>
</table>

### <a name="query-using-the-rest-service"></a><span data-ttu-id="a2d54-230">使用 REST 服务查询</span><span class="sxs-lookup"><span data-stu-id="a2d54-230">Query using the REST service</span></span>

<span data-ttu-id="a2d54-p122">使用 GET 请求，指定 URL 中的查询参数。使用 POST 请求，在正文中以 JavaScript 对象表示法 (JSON) 格式传递查询参数。</span><span class="sxs-lookup"><span data-stu-id="a2d54-p122">With a GET request, you specify the query parameters in the URL. With a POST request, you pass the query parameters in the body in JavaScript Object Notation (JSON) format.</span></span>

#### <a name="request-headers"></a><span data-ttu-id="a2d54-233">请求标头</span><span class="sxs-lookup"><span data-stu-id="a2d54-233">Request headers</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a2d54-234">名称</span><span class="sxs-lookup"><span data-stu-id="a2d54-234">Name</span></span></th>
<th align="left"><span data-ttu-id="a2d54-235">值</span><span class="sxs-lookup"><span data-stu-id="a2d54-235">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="a2d54-236">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a2d54-236">Content-Type</span></span></td>
<td align="left"><span data-ttu-id="a2d54-237">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="a2d54-237">application/json;odata=verbose</span></span></td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="a2d54-238">扇出到 **所有** 地理位置的示例 GET 请求</span><span class="sxs-lookup"><span data-stu-id="a2d54-238">Sample GET request that's fanned out to **all** geo locations</span></span>

<span data-ttu-id="a2d54-239"> https:// \<tenant\> / \_ api/search/query？querytext='sharepoint'&Properties='EnableMultiGeoSearch：true'&ClientType='my \_ client \_ id'</span><span class="sxs-lookup"><span data-stu-id="a2d54-239">https:// \<tenant\>/\_api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my\_client\_id'</span></span>

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a><span data-ttu-id="a2d54-240">扇出部分地理位置的示例 GET 请求</span><span class="sxs-lookup"><span data-stu-id="a2d54-240">Sample GET request to fan out to **some** geo locations</span></span>

<span data-ttu-id="a2d54-241"> https:// \<tenant\> / \_ api/search/query？querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch：true， MultiGeoSearchConfiguration：[{DataLocation \\ ："NAM" \\ ，Endpoint \\ ："https \\ ：//contosoNAM.sharepoint.com" \\ ，SourceId \\ ："B81EAB55-3140-4312-B0F4-9459D1B4FFEE"} \\ ，{DataLocation \\ ："CAN" \\ ，Endpoint \\ ："https \\ ：//contosoCAN.sharepoint-df.com"}]'</span><span class="sxs-lookup"><span data-stu-id="a2d54-241">https:// \<tenant\>/\_api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation\\:"NAM"\\,Endpoint\\:"https\\://contosoNAM.sharepoint.com"\\,SourceId\\:"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"}\\,{DataLocation\\:"CAN"\\,Endpoint\\:"https\\://contosoCAN.sharepoint-df.com"}]'</span></span>

> [!NOTE]
> <span data-ttu-id="a2d54-242">MultiGeoSearchConfiguration 属性的地理位置列表中的逗号和冒号前面带有 **反斜杠** 字符。</span><span class="sxs-lookup"><span data-stu-id="a2d54-242">Commas and colons in the list of geo locations for the MultiGeoSearchConfiguration property are preceded by the **backslash** character.</span></span> <span data-ttu-id="a2d54-243">这是因为 GET 请求使用冒号分隔属性，并使用逗号分隔属性的参数。</span><span class="sxs-lookup"><span data-stu-id="a2d54-243">This is because GET requests use colons to separate properties and commas to separate arguments of properties.</span></span> <span data-ttu-id="a2d54-244">如果不使用反斜杠作为转义字符，则 MultiGeoSearchConfiguration 属性会被错误解读。</span><span class="sxs-lookup"><span data-stu-id="a2d54-244">Without the backslash as an escape character, the MultiGeoSearchConfiguration property is interpreted wrongly.</span></span>

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="a2d54-245">扇出到 **所有** 地理位置的示例 POST 请求</span><span class="sxs-lookup"><span data-stu-id="a2d54-245">Sample POST request that's fanned out to **all** geo locations</span></span>

```text
    {
    "request": {
            "__metadata": {
            "type": "Microsoft.Office.Server.Search.REST.SearchRequest"
        },
        "Querytext": "sharepoint",
        "Properties": {
            "results": [
                {
                    "Name": "EnableMultiGeoSearch",
                    "Value": {
                        "QueryPropertyValueTypeIndex": 3,
                        "BoolVal": true
                    }
                }
            ]
        },
        "ClientType": "my_client_id"
        }
    }
```

#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a><span data-ttu-id="a2d54-246">扇出到 **部分** 地理位置的示例 POST 请求</span><span class="sxs-lookup"><span data-stu-id="a2d54-246">Sample POST request that's fanned out to **some** geo locations</span></span>

```text
    {
        "request": {
            "Querytext": "SharePoint",
            "ClientType": "my_client_id",
            "Properties": {
                "results": [
                    {
                        "Name": "EnableMultiGeoSearch",
                        "Value": {
                            "QueryPropertyValueTypeIndex": 3,
                            "BoolVal": true
                        }
                    },
                    {
                        "Name": "MultiGeoSearchConfiguration",
                        "Value": {
                        "StrVal": "[{\"DataLocation\":\"NAM\",\"Endpoint\":\"https://contoso.sharepoint.com\",\"SourceId\":\"B81EAB55-3140-4312-B0F4-9459D1B4FFEE\"},{\"DataLocation\":\"CAN\",\"Endpoint\":\"https://contosoCAN.sharepoint.com\"}]",
                            "QueryPropertyValueTypeIndex": 1
                        }
                    }
                ]
            }
        }
    }
```

### <a name="query-using-csom"></a><span data-ttu-id="a2d54-247">使用 CSOM 查询</span><span class="sxs-lookup"><span data-stu-id="a2d54-247">Query using CSOM</span></span>

<span data-ttu-id="a2d54-248">以下是扇出到 **所有** 地理位置的示例 CSOM 请求：</span><span class="sxs-lookup"><span data-stu-id="a2d54-248">Here's a sample CSOM query that's fanned out to **all** geo locations:</span></span>

```text
var keywordQuery = new KeywordQuery(ctx);
keywordQuery.QueryText = query.SearchQueryText;
keywordQuery.ClientType = <enter a string here>;
keywordQuery["EnableMultiGeoSearch"] = true;
```