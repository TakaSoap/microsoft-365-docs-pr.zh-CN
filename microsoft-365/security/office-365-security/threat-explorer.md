---
title: 威胁资源管理器和实时检测
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 了解如何在安全合规中心中使用 Explorer 和实时检测， &amp; 以有效且高效地对威胁进行调查和响应。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4220c850e5ef7f830f7fc6ec57bb220cca29eaf4
ms.sourcegitcommit: 4ac96855d7c269a0055ca8943000b762a70ca4ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "47322006"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="dd33f-103">威胁资源管理器和实时检测</span><span class="sxs-lookup"><span data-stu-id="dd33f-103">Threat Explorer and real-time detections</span></span>

<span data-ttu-id="dd33f-104">如果您的组织具有 [office 365 高级威胁防护](office-365-atp.md) (OFFICE 365 ATP) ，并且您拥有 [必要的权限](#required-licenses-and-permissions)，则您可以使用 **资源管理器** 或 **实时检测** (以前的 *实时报告* — [请参阅最近更新](#new-features-in-threat-explorer-and-real-time-detections)！ ) 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="dd33f-105">在安全 & 合规性中心中，转到 " **威胁管理**"，然后选择 " **浏览器**" _或_" **实时检测**"。</span><span class="sxs-lookup"><span data-stu-id="dd33f-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

|<span data-ttu-id="dd33f-106">在 ATP 计划2中，您将看到：</span><span class="sxs-lookup"><span data-stu-id="dd33f-106">With ATP Plan 2, you see:</span></span>|<span data-ttu-id="dd33f-107">在 ATP 计划1中，您将看到：</span><span class="sxs-lookup"><span data-stu-id="dd33f-107">With ATP Plan 1, you see:</span></span>|
|---|---|
|![威胁资源管理器](../../media/threatmgmt-explorer.png)|![实时检测](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="dd33f-110">通过资源管理器 (或) 的实时检测功能，您有一个功能强大的报告，使安全操作团队能够有效且高效地调查威胁并对其做出响应。</span><span class="sxs-lookup"><span data-stu-id="dd33f-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently.</span></span> <span data-ttu-id="dd33f-111">该报告类似于以下图像：</span><span class="sxs-lookup"><span data-stu-id="dd33f-111">The report resembles the following image:</span></span>

![转到 "威胁管理 \> 资源管理器"](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="dd33f-113">使用此报告，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dd33f-113">With this report, you can:</span></span>

- [<span data-ttu-id="dd33f-114">查看 Microsoft 365 安全功能检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="dd33f-114">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="dd33f-115">查看有关仿冒 Url 的数据，然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="dd33f-115">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- <span data-ttu-id="dd33f-116">[从资源管理器中的视图启动自动调查和响应过程](#start-automated-investigation-and-response) (ATP 计划2仅) </span><span class="sxs-lookup"><span data-stu-id="dd33f-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="dd33f-117">... [调查恶意电子邮件，](#more-ways-to-use-explorer-or-real-time-detections)等等！</span><span class="sxs-lookup"><span data-stu-id="dd33f-117">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="dd33f-118">对威胁资源管理器和实时检测的改进体验</span><span class="sxs-lookup"><span data-stu-id="dd33f-118">Experience Improvements to Threat Explorer and Real-Time Detections</span></span>

<span data-ttu-id="dd33f-119">在改进搜寻过程的过程中，我们已经对威胁浏览器和实时检测进行了一些更新。</span><span class="sxs-lookup"><span data-stu-id="dd33f-119">As part of improving the hunting process, we have made a few updates to Threat Explorer and Real-Time Detections.</span></span> <span data-ttu-id="dd33f-120">这些是 "体验" 改进，重点是让求职体验更一致。</span><span class="sxs-lookup"><span data-stu-id="dd33f-120">These are ‘experience’ improvements, with the focus on making the hunting experience more consistent.</span></span> <span data-ttu-id="dd33f-121">下面概述了这些更改：</span><span class="sxs-lookup"><span data-stu-id="dd33f-121">These changes are outlined below:</span></span>

- [<span data-ttu-id="dd33f-122">时区改进</span><span class="sxs-lookup"><span data-stu-id="dd33f-122">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="dd33f-123">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="dd33f-123">Update in the Refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="dd33f-124">要添加到筛选器的图表深入分析</span><span class="sxs-lookup"><span data-stu-id="dd33f-124">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="dd33f-125">在产品信息更新中</span><span class="sxs-lookup"><span data-stu-id="dd33f-125">In product information updates</span></span>](#in-product-information-updates)

### <a name="timezone-improvements"></a><span data-ttu-id="dd33f-126">时区改进</span><span class="sxs-lookup"><span data-stu-id="dd33f-126">Timezone improvements</span></span>

<span data-ttu-id="dd33f-127">我们将显示门户中的电子邮件记录的时区以及导出的数据的时区。</span><span class="sxs-lookup"><span data-stu-id="dd33f-127">We will show the timezone for the email records within the Portal, as well as for Exported data.</span></span> <span data-ttu-id="dd33f-128">在电子邮件网格、详细信息浮出控件、电子邮件日程表和类似的电子邮件等体验中，时区将可见，从而使用户可以清楚地了解结果集的时区。</span><span class="sxs-lookup"><span data-stu-id="dd33f-128">The timezone will be visible across experiences like Email Grid, Details Flyout, Email Timeline, and Similar Emails, so that the timezone for the result set is clear to the user.</span></span>

![在资源管理器中查看时区](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="dd33f-130">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="dd33f-130">Update in the Refresh process</span></span>

<span data-ttu-id="dd33f-131">我们已经听说过与自动刷新 (混淆的反馈，例如日期，一旦您更改日期，页面将刷新) 并手动刷新 (其他筛选器) 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-131">We have heard feedback around confusion with automatic refresh (e.g. for date, as soon as you change the date, the page would refresh) and manual refresh (for other filters).</span></span> <span data-ttu-id="dd33f-132">同样，删除筛选器会导致自动刷新，这会导致在修改查询时更改不同的筛选器会导致不一致的搜索体验的情况。</span><span class="sxs-lookup"><span data-stu-id="dd33f-132">Similarly, removing filters leads to automatic refresh, this causes situations where changing the different filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="dd33f-133">若要解决此情况，我们将迁移到手动筛选机制。</span><span class="sxs-lookup"><span data-stu-id="dd33f-133">To solve this, we are moving to a manual filtering mechanism.</span></span>
<span data-ttu-id="dd33f-134">从经验的角度来看，用户可以应用和删除筛选器集 (的不同范围的筛选器，并在日期) ，然后按 "刷新" 按钮，在完成定义查询的情况下筛选结果。</span><span class="sxs-lookup"><span data-stu-id="dd33f-134">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set, and date), and press the refresh button to filter the results once they are done with defining the query.</span></span> <span data-ttu-id="dd33f-135">"刷新" 按钮也已更新，可在屏幕上清楚地调用它。</span><span class="sxs-lookup"><span data-stu-id="dd33f-135">The refresh button has also been updated to call it out clearly on the screen.</span></span> <span data-ttu-id="dd33f-136">我们还提供了有关此更改的更新工具提示和产品内文档。</span><span class="sxs-lookup"><span data-stu-id="dd33f-136">We have also updated tooltips and in-product documentation around this change.</span></span>

![单击 "刷新" 以筛选结果](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="dd33f-138">要添加到筛选器的图表深入分析</span><span class="sxs-lookup"><span data-stu-id="dd33f-138">Chart drilldown to add to filters</span></span>

<span data-ttu-id="dd33f-139">现在，您可以单击 "图表图例" 值，将该值作为筛选器添加。</span><span class="sxs-lookup"><span data-stu-id="dd33f-139">You will now be able to click on the chart legend values to add that value as a filter.</span></span> <span data-ttu-id="dd33f-140">请注意，您仍必须单击 "刷新" 按钮，才能将结果作为上述更改的一部分进行筛选。</span><span class="sxs-lookup"><span data-stu-id="dd33f-140">Note that you will still have to click on the refresh button to filter the results as part of the change described above.</span></span>

![通过要筛选的图表深入分析](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a><span data-ttu-id="dd33f-142">在产品信息更新中</span><span class="sxs-lookup"><span data-stu-id="dd33f-142">In product information updates</span></span>

<span data-ttu-id="dd33f-143">您还应查看产品中的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="dd33f-143">You should also see additional details within the product.</span></span> <span data-ttu-id="dd33f-144">例如，网格中的搜索结果总数) ，以及有关标签、错误消息和工具提示的改进，以提供有关筛选器、搜索体验和结果集的详细信息，请参阅下图所示的 (。</span><span class="sxs-lookup"><span data-stu-id="dd33f-144">For example, the total number of search results within grid (see below), as well as improvements around labels, error messages and tooltips, to give more information around filters, search experience, and result set.</span></span>

![查看产品信息](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="dd33f-146">威胁资源管理器中的扩展功能</span><span class="sxs-lookup"><span data-stu-id="dd33f-146">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="dd33f-147">主要目标用户</span><span class="sxs-lookup"><span data-stu-id="dd33f-147">Top targeted users</span></span>

<span data-ttu-id="dd33f-148">今天，我们在恶意软件的主要部分中公开主要目标用户的列表， (主要恶意软件系列中的电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-148">Today we expose the list of the top targeted users in the Malware View for Emails (within the Top Malware Families section).</span></span> <span data-ttu-id="dd33f-149">我们将在网络钓鱼和所有电子邮件视图中扩展此视图，在该视图中，您将能够查看前五个目标用户以及每个用户对相应 (视图的尝试次数。例如，对于 "网络钓鱼" 视图，您将能够查看) 的网络钓鱼尝试次数。</span><span class="sxs-lookup"><span data-stu-id="dd33f-149">We will be extending this view within Phish and All Email views as well, where you will be able to see the top five targeted users along with the number of attempts for each user for the corresponding view (for example, for Phish view you will be able to see the number of Phish attempts).</span></span>
<span data-ttu-id="dd33f-150">您还可以将目标用户列表导出为3000，并将每个电子邮件视图的脱机分析尝试次数导出到最大值为。</span><span class="sxs-lookup"><span data-stu-id="dd33f-150">You will also be able to export the list of targeted users up to a limit of 3000 along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="dd33f-151">此外，选择 "否"。</span><span class="sxs-lookup"><span data-stu-id="dd33f-151">In addition to that, selecting No.</span></span> <span data-ttu-id="dd33f-152"> (例如，下面的13次) 将在威胁 Explorer 中打开筛选视图，以便您可以在电子邮件和威胁中查看该用户的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="dd33f-152">of attempts (for example, 13 attempts below) would open a filtered view in Threat Explorer, so that you can look at more details across emails and threats for that user.</span></span> 

![主要目标用户](../../media/Top_Targeted_Users.png)


### <a name="exchange-transport-rules"></a><span data-ttu-id="dd33f-154">Exchange 传输规则</span><span class="sxs-lookup"><span data-stu-id="dd33f-154">Exchange transport rules</span></span>
<span data-ttu-id="dd33f-155">作为数据扩充的一部分，您还应该能够查看应用于邮件的所有不同传输规则。</span><span class="sxs-lookup"><span data-stu-id="dd33f-155">As part of data enrichment, you should also be able to see all the different transport rules which were applied to a message.</span></span> <span data-ttu-id="dd33f-156">此信息将显示在电子邮件网格视图中 (查看此内容，请在网格中选择 "列选项"，并在 "网格中的列选项" 中添加 Exchange 传输规则) 以及电子邮件中的 "详细信息" 浮出控件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-156">This information will be present within the Email grid view (to view this, select Column options in the grid and add Exchange Transport Rule from the Column options in the grid) as well as Details flyout in the email.</span></span>
<span data-ttu-id="dd33f-157">你将能够同时查看 GUID 以及应用于邮件的传输规则的名称。</span><span class="sxs-lookup"><span data-stu-id="dd33f-157">You would be able to see both the GUID as well as the name of the transport rules which were applied to the message.</span></span> <span data-ttu-id="dd33f-158">此外，您还可以使用传输规则的名称搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-158">Additionally, you would be able to search for the messages using the name of the transport rule.</span></span> <span data-ttu-id="dd33f-159">这是一个 "包含" 搜索，这意味着您也可以使用部分搜索进行搜索。</span><span class="sxs-lookup"><span data-stu-id="dd33f-159">This would be a ‘Contains’ search which means you will be able to search using partial searches as well.</span></span> 

#### <a name="important-note"></a><span data-ttu-id="dd33f-160">重要说明：</span><span class="sxs-lookup"><span data-stu-id="dd33f-160">Important Note:</span></span> 
<span data-ttu-id="dd33f-161">ETR 搜索和名称可用性取决于已分配给你的特定角色。</span><span class="sxs-lookup"><span data-stu-id="dd33f-161">ETR search and name availability would depend on the specific role that has been assigned to you.</span></span> <span data-ttu-id="dd33f-162">您需要具有以下角色/权限之一才能查看 ETR 名称和搜索。</span><span class="sxs-lookup"><span data-stu-id="dd33f-162">You will need to have one of the following roles/permissions in order to view the ETR names and search.</span></span>  <span data-ttu-id="dd33f-163">如果没有为您分配以下任何角色，您将无法看到传输规则的名称，并使用 ETR 名称搜索邮件的名称。</span><span class="sxs-lookup"><span data-stu-id="dd33f-163">If you do not have any of the following roles assigned to you, you will not be able to see the names of the transport rules, and search for the messages using the ETR names.</span></span> <span data-ttu-id="dd33f-164">不过，你将能够在电子邮件详细信息中看到 ETR 标签和 GUID 信息。</span><span class="sxs-lookup"><span data-stu-id="dd33f-164">However, you will be able to see the ETR label and GUID information within the Email Details.</span></span> <span data-ttu-id="dd33f-165">有关在电子邮件网格、电子邮件 flyouts、筛选器和导出中查看记录的其他体验不受影响。</span><span class="sxs-lookup"><span data-stu-id="dd33f-165">Your other experiences around viewing records in Email Grids, Email flyouts, Filters, and Export are not impacted.</span></span> 
 
- <span data-ttu-id="dd33f-166">仅限 EXO-数据丢失防护：全部</span><span class="sxs-lookup"><span data-stu-id="dd33f-166">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="dd33f-167">仅 EXO-O365SupportViewConfig： All</span><span class="sxs-lookup"><span data-stu-id="dd33f-167">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="dd33f-168">AAD 或 EXO-安全管理员： All</span><span class="sxs-lookup"><span data-stu-id="dd33f-168">AAD or EXO - Security Admin: All</span></span>
- <span data-ttu-id="dd33f-169">AAD 或 EXO-安全读者： All</span><span class="sxs-lookup"><span data-stu-id="dd33f-169">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="dd33f-170">仅限 EXO-传输规则： All</span><span class="sxs-lookup"><span data-stu-id="dd33f-170">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="dd33f-171">仅限 EXO-仅查看配置：全部</span><span class="sxs-lookup"><span data-stu-id="dd33f-171">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="dd33f-172">在电子邮件网格、详细信息浮出控件和导出的 CSV 中，Etr 显示如下所示的名称/GUID。</span><span class="sxs-lookup"><span data-stu-id="dd33f-172">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span> 

![Exchange 传输规则](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a><span data-ttu-id="dd33f-174">入站连接器</span><span class="sxs-lookup"><span data-stu-id="dd33f-174">Inbound connectors</span></span> 

<span data-ttu-id="dd33f-175">连接器是一组说明，可用于自定义电子邮件流动到 Microsoft 365 或 Office 365 组织的方式，并能够应用任何安全限制或控件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-175">Connectors are a collection of instructions that customize the way your email flows to and from your Microsoft 365 or Office 365 organization, with the ability to apply any security restriction or controls.</span></span> <span data-ttu-id="dd33f-176">在威胁资源管理器中，您现在可以查看与电子邮件相关的连接器，也可以使用连接器名称搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-176">Within Threat Explorer, you will now have the ability to view the connectors which are related to an email as well as search for emails using the connector names.</span></span> <span data-ttu-id="dd33f-177">对连接器的搜索是 ' 包含 ' 性质的，这意味着分部关键字搜索也应正常工作。</span><span class="sxs-lookup"><span data-stu-id="dd33f-177">The search for connectors is ‘Contains’ in nature which means partial keyword searches should work as well.</span></span> <span data-ttu-id="dd33f-178">在主网格视图中，"详细信息" 浮出控件和导出的 CSV，连接器以如下所示的名称/GUID 格式显示：</span><span class="sxs-lookup"><span data-stu-id="dd33f-178">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown below:</span></span> 

![连接器详细信息](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="dd33f-180">威胁资源管理器中的新功能和实时检测</span><span class="sxs-lookup"><span data-stu-id="dd33f-180">New features in Threat Explorer and real-time detections</span></span>

<span data-ttu-id="dd33f-181">威胁资源管理器和实时检测添加了三个新功能：</span><span class="sxs-lookup"><span data-stu-id="dd33f-181">Three new features added into Threat Explorer and real-time detections:</span></span>

- [<span data-ttu-id="dd33f-182">预览电子邮件标头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="dd33f-182">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="dd33f-183">电子邮件日程表</span><span class="sxs-lookup"><span data-stu-id="dd33f-183">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="dd33f-184">导出 URL 单击 "数据"</span><span class="sxs-lookup"><span data-stu-id="dd33f-184">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="dd33f-185">下面概述了这些新功能。</span><span class="sxs-lookup"><span data-stu-id="dd33f-185">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="dd33f-186">预览电子邮件标头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="dd33f-186">Preview email header and download email body</span></span>

<span data-ttu-id="dd33f-187">在威胁资源管理器中，预览电子邮件标头和下载电子邮件正文的功能是可用的新功能。</span><span class="sxs-lookup"><span data-stu-id="dd33f-187">The ability to preview an email header and download the email body are new features available in Threat Explorer.</span></span> <span data-ttu-id="dd33f-188">管理员将能够分析下载的邮件头/电子邮件是否有威胁。</span><span class="sxs-lookup"><span data-stu-id="dd33f-188">Admins will be able to analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="dd33f-189">由于下载电子邮件可能会降低信息的暴露风险，因此此过程由基于角色的访问控制 (RBAC) 控制。</span><span class="sxs-lookup"><span data-stu-id="dd33f-189">Because downloading email messages can risk the exposure of information, this process is controlled by roles-based access control (RBAC).</span></span> <span data-ttu-id="dd33f-190">必须向另一个角色 (组中添加一个新的角色、 *预览*，如安全操作或安全管理员) ，以授予在所有电子邮件视图中下载邮件和预览邮件头的能力。</span><span class="sxs-lookup"><span data-stu-id="dd33f-190">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="dd33f-191">但是，资源管理器 (和实时检测) 也会添加新的新字段，旨在为您提供有关电子邮件土地的更完整的信息。</span><span class="sxs-lookup"><span data-stu-id="dd33f-191">But Explorer (and real-time detections) also adds fresh new fields designed to give you a more complete picture of where your email messages land.</span></span> <span data-ttu-id="dd33f-192">此更改的目标部分是使搜索更易于进行安全操作人员，但最终结果是了解问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="dd33f-192">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="dd33f-193">这是如何完成的？</span><span class="sxs-lookup"><span data-stu-id="dd33f-193">How is this done?</span></span> <span data-ttu-id="dd33f-194">传递状态现已分为两列：</span><span class="sxs-lookup"><span data-stu-id="dd33f-194">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="dd33f-195">**传递操作** -此电子邮件的状态是什么？</span><span class="sxs-lookup"><span data-stu-id="dd33f-195">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="dd33f-196">**送达位置** -此电子邮件的路由结果</span><span class="sxs-lookup"><span data-stu-id="dd33f-196">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="dd33f-197">传递操作是由于现有策略或检测而导致对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="dd33f-197">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="dd33f-198">以下是电子邮件可能执行的操作：</span><span class="sxs-lookup"><span data-stu-id="dd33f-198">Here are the possible actions an email can take:</span></span>

|<span data-ttu-id="dd33f-199">附带</span><span class="sxs-lookup"><span data-stu-id="dd33f-199">Delivered</span></span>|<span data-ttu-id="dd33f-200">Junked</span><span class="sxs-lookup"><span data-stu-id="dd33f-200">Junked</span></span>|<span data-ttu-id="dd33f-201">Blocked</span><span class="sxs-lookup"><span data-stu-id="dd33f-201">Blocked</span></span>|<span data-ttu-id="dd33f-202">代替</span><span class="sxs-lookup"><span data-stu-id="dd33f-202">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="dd33f-203">电子邮件已传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="dd33f-203">Email was delivered to Inbox or folder of a user and the user can directly access it.</span></span>|<span data-ttu-id="dd33f-204">电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹，并且用户有权访问这些文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-204">Email was sent to either user’s Junk folder or Deleted folder, and the user has access to emails in those folders.</span></span>|<span data-ttu-id="dd33f-205">隔离的、失败的或已丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-205">Any emails that are quarantined, that  failed, or were dropped.</span></span> <span data-ttu-id="dd33f-206">用户完全无法访问它！</span><span class="sxs-lookup"><span data-stu-id="dd33f-206">This is completely inaccessible by the user!</span></span>|<span data-ttu-id="dd33f-207">所有恶意附件都被替换为 .txt 文件的电子邮件，以表明附件是恶意的。</span><span class="sxs-lookup"><span data-stu-id="dd33f-207">Any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>|

|<span data-ttu-id="dd33f-208">附带</span><span class="sxs-lookup"><span data-stu-id="dd33f-208">Delivered</span></span>|<span data-ttu-id="dd33f-209">Junked</span><span class="sxs-lookup"><span data-stu-id="dd33f-209">Junked</span></span>|<span data-ttu-id="dd33f-210">Blocked</span><span class="sxs-lookup"><span data-stu-id="dd33f-210">Blocked</span></span>|<span data-ttu-id="dd33f-211">代替</span><span class="sxs-lookup"><span data-stu-id="dd33f-211">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="dd33f-212">电子邮件已传递到用户的收件箱或其他文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="dd33f-212">Email was delivered to the user's inbox or another folder, and the user can directly access it.</span></span>|<span data-ttu-id="dd33f-213">电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹，并且用户有权访问这些文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-213">Email was sent to either user's Junk folder or Deleted folder, and the user has access to email messages in those folders.</span></span>|<span data-ttu-id="dd33f-214">隔离的、失败的或已删除的任何电子邮件、以及用户无法访问的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-214">Any email messages that are quarantined, that failed, or were dropped, and are not accessible by the user.</span></span>|<span data-ttu-id="dd33f-215">任何电子邮件，其中恶意附件被替换为 .txt 文件，以表明这些附件是恶意的。</span><span class="sxs-lookup"><span data-stu-id="dd33f-215">Any email messages where malicious attachments were replaced by .txt files that state the attachments were malicious.</span></span>|
|

<span data-ttu-id="dd33f-216">用户可以看到的内容及其不能执行的操作：</span><span class="sxs-lookup"><span data-stu-id="dd33f-216">And here is what the user can see, and what they can't:</span></span>

|<span data-ttu-id="dd33f-217">最终用户可以访问</span><span class="sxs-lookup"><span data-stu-id="dd33f-217">Accessible to end users</span></span>|<span data-ttu-id="dd33f-218">最终用户无法访问</span><span class="sxs-lookup"><span data-stu-id="dd33f-218">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="dd33f-219">附带</span><span class="sxs-lookup"><span data-stu-id="dd33f-219">Delivered</span></span>|<span data-ttu-id="dd33f-220">Blocked</span><span class="sxs-lookup"><span data-stu-id="dd33f-220">Blocked</span></span>|
|<span data-ttu-id="dd33f-221">Junked</span><span class="sxs-lookup"><span data-stu-id="dd33f-221">Junked</span></span>|<span data-ttu-id="dd33f-222">代替</span><span class="sxs-lookup"><span data-stu-id="dd33f-222">Replaced</span></span>|

<span data-ttu-id="dd33f-223">"送达位置" 显示运行送达后的策略和检测结果。</span><span class="sxs-lookup"><span data-stu-id="dd33f-223">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="dd33f-224">它已链接到传递操作。</span><span class="sxs-lookup"><span data-stu-id="dd33f-224">It's linked to a Delivery Action.</span></span> <span data-ttu-id="dd33f-225">添加此字段是为了深入了解在发现问题邮件时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="dd33f-225">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="dd33f-226">以下是送达位置的可能值：</span><span class="sxs-lookup"><span data-stu-id="dd33f-226">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="dd33f-227">**收件箱或文件夹**：电子邮件位于收件箱中或文件夹 (根据您的电子邮件规则) 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-227">**Inbox or folder**: The email is in inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="dd33f-228">**本地或 external**：邮箱在云上不存在，但在本地。</span><span class="sxs-lookup"><span data-stu-id="dd33f-228">**On-prem or external**: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="dd33f-229">**垃圾邮件文件夹**：电子邮件位于用户的 "垃圾邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dd33f-229">**Junk folder**: The email is in the Junk folder of a user.</span></span>
- <span data-ttu-id="dd33f-230">"**已删除**邮件" 文件夹：用户的 "已删除邮件" 文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-230">**Deleted items folder**: The email in the Deleted items folder of a user.</span></span>
- <span data-ttu-id="dd33f-231">**隔离**：隔离中的电子邮件，并且不在用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="dd33f-231">**Quarantine**: The email in quarantine, and is not in a user's mailbox.</span></span>
- <span data-ttu-id="dd33f-232">**失败**：电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="dd33f-232">**Failed**: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="dd33f-233">已**删除**：电子邮件在邮件流中的某处丢失。</span><span class="sxs-lookup"><span data-stu-id="dd33f-233">**Dropped**: The email gets lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="dd33f-234">电子邮件日程表</span><span class="sxs-lookup"><span data-stu-id="dd33f-234">Email timeline</span></span>

<span data-ttu-id="dd33f-235">**电子邮件日程表**是另一个新的浏览器功能，旨在提高管理员的求职体验。</span><span class="sxs-lookup"><span data-stu-id="dd33f-235">The **Email Timeline** is another new Explorer feature aimed at making the hunting experience better for admins.</span></span> <span data-ttu-id="dd33f-236">它会在随机时减少，因为检查不同位置以尝试了解事件的时间较少。</span><span class="sxs-lookup"><span data-stu-id="dd33f-236">It cuts down on randomization because there is less time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="dd33f-237">当电子邮件上的多个事件发生时，或在同一时间结束时，这些事件将显示在 "日程表" 视图中。</span><span class="sxs-lookup"><span data-stu-id="dd33f-237">When multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="dd33f-238">事实上，在传递给邮件的某些事件将在 "特殊操作" 列中捕获。</span><span class="sxs-lookup"><span data-stu-id="dd33f-238">In fact, some events that happen post-delivery to your mail will be captured in the 'Special action' column.</span></span> <span data-ttu-id="dd33f-239">将该邮件的时间线中的信息与邮件投递后执行的特殊操作组合在一起，管理员可以了解其策略的工作方式，即最后路由邮件的位置，在某些情况下，最终评估是什么。</span><span class="sxs-lookup"><span data-stu-id="dd33f-239">Combining the information from the timeline of that mail with the special action taken on the mail post-delivery will give admins insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="dd33f-240">有关调查恶意电子邮件的详细讨论，请参阅 [调查和修正 Office 365 中提供的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)。</span><span class="sxs-lookup"><span data-stu-id="dd33f-240">For more discussion about investigating malicious email messages, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="dd33f-241">导出 URL 单击 "数据"</span><span class="sxs-lookup"><span data-stu-id="dd33f-241">Export URL click data</span></span>

<span data-ttu-id="dd33f-242">此外，您现在可以将 URL 单击的报告导出到 Microsoft Excel 中，以查看其网络消息 ID 和单击结论，从而使了解您的 URL 单击流量更容易的任务。</span><span class="sxs-lookup"><span data-stu-id="dd33f-242">Also, you will now be able to export reports for URL clicks to Microsoft Excel in order to view both their Network Message ID, and their Click Verdict, making the task of understanding where your URL click traffic originated easier.</span></span> <span data-ttu-id="dd33f-243">下面介绍了它的工作原理。</span><span class="sxs-lookup"><span data-stu-id="dd33f-243">Here's how it works.</span></span> <span data-ttu-id="dd33f-244">从 "Office 365 快速启动" 上的 "威胁管理" 开始，依次单击 "通过此链"：</span><span class="sxs-lookup"><span data-stu-id="dd33f-244">Starting in Threat Management on the Office 365 quick-launch, click through this chain:</span></span>

<span data-ttu-id="dd33f-245">**浏览器** \>**查看网络钓鱼** \>**单击** \>**顶部 url 或 URL 顶部单击** \>**单击任意记录以打开 "URL 飞出**"</span><span class="sxs-lookup"><span data-stu-id="dd33f-245">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs or URL Top Clicks** \> **Click on any record to open URL flyout**</span></span>

<span data-ttu-id="dd33f-246">当您单击列表中的某个 URL 时，将会在弹出面板上看到一个新的 "导出" 按钮。</span><span class="sxs-lookup"><span data-stu-id="dd33f-246">When you click on a URL in the list, you'll see a new Export button on the fly-out panel.</span></span> <span data-ttu-id="dd33f-247">使用此按钮可以将数据移动到 Excel 电子表格，以便更轻松地进行报告。</span><span class="sxs-lookup"><span data-stu-id="dd33f-247">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="dd33f-248">您可以在实时检测报告中获取相同的位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dd33f-248">You can get to the same location in the real-time detections report as follows:</span></span>

<span data-ttu-id="dd33f-249">**浏览器** \>**实时检测** \>**查看网络钓鱼** \>**Url** \>**顶部的 url 或顶部的单击** \>**单击任意记录以打开 "URL 飞出** \> "**导航到 "单击" 选项卡。**</span><span class="sxs-lookup"><span data-stu-id="dd33f-249">**Explorer** \> **Real-time Detections** \> **View Phish** \> **URLs** \> **Top URLs or Top Clicks** \> **Click on any record to open URL flyout** \> **Navigate to the Clicks Tab.**</span></span>

> [!TIP]
> <span data-ttu-id="dd33f-250">当您通过网络邮件 ID 搜索浏览器或关联的第三方工具时，网络邮件 ID 会将单击映射回特定邮件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-250">Network Message ID maps the click back to specific mails when you search through Explorer or associated 3rd party tools via Network Message ID.</span></span> <span data-ttu-id="dd33f-251">在网络邮件 ID 中搜索将为管理员提供与单击结果关联的特定电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-251">Searching through the Network Message ID will give admins the specific email associated with a click result.</span></span> <span data-ttu-id="dd33f-252">在有导出功能的情况下，网络邮件 ID 的关联标识将使分析速度更快、更强大。</span><span class="sxs-lookup"><span data-stu-id="dd33f-252">On export having, the correlating identification of Network Message ID makes for quicker and more powerful analysis.</span></span>

![tp_ExportClickResultAndNetworkID.png](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="dd33f-254">查看电子邮件中的技术检测到恶意软件</span><span class="sxs-lookup"><span data-stu-id="dd33f-254">See malware detected in email by technology</span></span>

<span data-ttu-id="dd33f-255">假设您想要查看 Microsoft 365 技术在电子邮件中检测到的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-255">Suppose you want to see malware detected in email, by Microsoft 365 technology.</span></span> <span data-ttu-id="dd33f-256">若要执行此操作，请使用资源管理器 (的 [电子邮件 > 恶意软件](threat-explorer-views.md#email--malware) 视图或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-256">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="dd33f-257">在 "安全性 & 合规性中心 ([https://protection.office.com](https://protection.office.com) ") 中，选择 "**威胁管理**  >  **资源管理器** (" 或 "**实时检测**") 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-257">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="dd33f-258"> (本示例使用 Explorer。 ) </span><span class="sxs-lookup"><span data-stu-id="dd33f-258">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="dd33f-259">在 "**视图**" 菜单中，选择 "**电子邮件**  >  **恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="dd33f-259">In the **View** menu, choose **Email** > **Malware**.</span></span>

   ![浏览器的视图菜单](../../media/ExplorerViewEmailMalwareMenu.png)

3. <span data-ttu-id="dd33f-261">单击 "**发件人**"，然后选择 "**基本**  >  **检测技术**"。</span><span class="sxs-lookup"><span data-stu-id="dd33f-261">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span>

   <span data-ttu-id="dd33f-262">您的检测技术现在可用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="dd33f-262">Your detection technologies are now available as filters for the report.</span></span>

   ![恶意软件检测技术](../../media/ExplorerEmailMalwareDetectionTech.png)

4. <span data-ttu-id="dd33f-264">选择一个选项，然后单击 " **刷新** " 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="dd33f-264">Select an option, and then click the **Refresh** button to apply that filter.</span></span>

   ![选定的检测技术](../../media/ExplorerEmailMalwareDetectionTechATP.png)

<span data-ttu-id="dd33f-266">报告将刷新，以显示使用您选择的技术选项在电子邮件中检测到恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="dd33f-266">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="dd33f-267">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="dd33f-267">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="dd33f-268">查看有关仿冒 Url 的数据，然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="dd33f-268">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="dd33f-269">假定您要查看通过电子邮件中的 Url 进行的网络钓鱼尝试，包括允许、阻止和重写的 Url 的列表。</span><span class="sxs-lookup"><span data-stu-id="dd33f-269">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="dd33f-270">标识所单击的 Url 需要配置 [ATP 安全链接](atp-safe-links.md) 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-270">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="dd33f-271">确保已为单击时的保护设置了 [Atp 安全链接策略](set-up-atp-safe-links-policies.md) ，然后通过 ATP 安全链接单击 "verdicts" 进行日志记录。</span><span class="sxs-lookup"><span data-stu-id="dd33f-271">Make sure that you have set up [ATP Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by ATP Safe Links.</span></span>

<span data-ttu-id="dd33f-272">若要查看邮件中的网络钓鱼 Url 并单击网络钓鱼邮件中的 Url，请使用资源管理器 (的 [电子邮件 > 网络钓鱼](threat-explorer-views.md#email--phish) 视图或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-272">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="dd33f-273">在 "安全性 & 合规性中心 ([https://protection.office.com](https://protection.office.com) ") 中，选择 "**威胁管理**  >  **资源管理器** (" 或 "**实时检测**") 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-273">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="dd33f-274"> (本示例使用 Explorer。 ) </span><span class="sxs-lookup"><span data-stu-id="dd33f-274">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="dd33f-275">在 "**视图**" 菜单中，选择 "**电子邮件**  >  **网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="dd33f-275">In the **View** menu, choose **Email** > **Phish**.</span></span>

   ![浏览器的视图菜单](../../media/ExplorerViewEmailPhishMenu.png)

3. <span data-ttu-id="dd33f-277">单击 "**发件人**"，然后选择 " **url**  >  **" 单击 "判定"**。</span><span class="sxs-lookup"><span data-stu-id="dd33f-277">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="dd33f-278">选择一个或多个选项（如 "已 **阻止** " 和 " **阻止被覆盖**"），然后单击与应用该筛选器的选项位于同一行中的 " **刷新** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="dd33f-278">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="dd33f-279"> (不刷新浏览器窗口。 ) </span><span class="sxs-lookup"><span data-stu-id="dd33f-279">(Don't refresh your browser window.)</span></span>

   ![Url 并单击 "verdicts"](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    <span data-ttu-id="dd33f-281">报告将刷新，以在报告下的 "URL" 选项卡上显示两个不同的 URL 表：</span><span class="sxs-lookup"><span data-stu-id="dd33f-281">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="dd33f-282">**上面的 url** 是您已筛选出的邮件中包含的 url，并且每个 URL 的电子邮件传递操作都会计数。</span><span class="sxs-lookup"><span data-stu-id="dd33f-282">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="dd33f-283">在网络钓鱼电子邮件视图中，此列表通常包含合法的 Url。</span><span class="sxs-lookup"><span data-stu-id="dd33f-283">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="dd33f-284">攻击者在其邮件中加入了好和坏的 Url，以尝试传递它们，但它们会使用户更有趣地单击恶意链接。</span><span class="sxs-lookup"><span data-stu-id="dd33f-284">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="dd33f-285">Url 表按总电子邮件计数进行排序 (但请注意，此列处于隐藏状态，以简化视图) 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-285">The table of URLs is sorted by total email count (but note that this column is hidden to simplify the view).</span></span>

   - <span data-ttu-id="dd33f-286">单击**鼠标顶部**的安全链接包装的 url 已被单击，按总单击次数排序 (此列也不会显示以简化视图) 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-286">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="dd33f-287">"总计计数依据" 列指示安全链接单击每个单击的 URL 的 "已判定计数"。</span><span class="sxs-lookup"><span data-stu-id="dd33f-287">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="dd33f-288">在网络钓鱼电子邮件视图中，这些 Url 更常见或恶意 Url，但可能包括不是威胁但位于网络钓鱼邮件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="dd33f-288">In the phish email view, these are more often suspicious or malicious URLs, but could include URLs that are not threats but are in phish messages.</span></span> <span data-ttu-id="dd33f-289">URL 单击未打开的链接将不会显示在此处。</span><span class="sxs-lookup"><span data-stu-id="dd33f-289">URL clicks on unwrapped links will not show up here.</span></span>

   <span data-ttu-id="dd33f-290">这两个 URL 表通过传递操作和位置显示网络钓鱼电子邮件中的前几个 url，并且它们显示的 URL 单击已被阻止 (或访问被阻止) 的情况，以便您可以了解用户收到的潜在坏链接和用户的交互情况。</span><span class="sxs-lookup"><span data-stu-id="dd33f-290">The two URL tables show top URLs in phishing email messages by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="dd33f-291">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="dd33f-291">From here, you can conduct further analysis.</span></span> <span data-ttu-id="dd33f-292">例如，在图表下方，您可以看到在组织的环境中被阻止的电子邮件中的最高 Url。</span><span class="sxs-lookup"><span data-stu-id="dd33f-292">For example, below the chart, you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   ![阻止的资源管理器 Url](../../media/ExplorerPhishClickVerdictURLs.png)

   <span data-ttu-id="dd33f-294">选择一个 URL 以查看更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="dd33f-294">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dd33f-295">在 "URL 浮出控件" 对话框中，将删除对电子邮件的筛选，以显示您的环境中 URL 公开的完整视图。</span><span class="sxs-lookup"><span data-stu-id="dd33f-295">In the URL flyout dialog, the filtering on email messages is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="dd33f-296">这样，您就可以在资源管理器中筛选出您关注的电子邮件，找出潜在威胁的特定 Url，然后通过 "URL 详细信息") 对话框 (了解您的环境中的 URL 公开情况，而无需向资源管理器视图本身添加 URL 筛选器。</span><span class="sxs-lookup"><span data-stu-id="dd33f-296">This lets you filter down email messages in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>


<span data-ttu-id="dd33f-297">**不同的单击 verdicts 的解释**</span><span class="sxs-lookup"><span data-stu-id="dd33f-297">**Interpretation of different click verdicts**</span></span>

<span data-ttu-id="dd33f-298">在电子邮件或 URL flyouts 中，点击率和在筛选体验中，你将看到不同的 click 值作为你的求职体验的一部分。</span><span class="sxs-lookup"><span data-stu-id="dd33f-298">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you will see different click values as part of your hunting experience.</span></span> <span data-ttu-id="dd33f-299">下面是单击 Verdicts 及其解释的可能值：</span><span class="sxs-lookup"><span data-stu-id="dd33f-299">Below are the possible values of Click Verdicts and their interpretation:</span></span>

- <span data-ttu-id="dd33f-300">**无**：我们无法捕获 URL 的结论。</span><span class="sxs-lookup"><span data-stu-id="dd33f-300">**None**: We were unable to capture the verdict for the URL.</span></span> <span data-ttu-id="dd33f-301">用户可能已通过 URL 单击。</span><span class="sxs-lookup"><span data-stu-id="dd33f-301">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="dd33f-302">**允许**：允许用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="dd33f-302">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="dd33f-303">已**阻止**：阻止用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="dd33f-303">**Blocked**: The User was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="dd33f-304">**挂起的判定**：用户显示沙箱挂起页面。</span><span class="sxs-lookup"><span data-stu-id="dd33f-304">**Pending verdict**: The user was presented with the detonation pending page.</span></span>
- <span data-ttu-id="dd33f-305">**被阻止的被覆盖**：阻止用户导航到 URL;但是，用户 overrode 阻止导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="dd33f-305">**Blocked overridden**: The user was blocked from navigating to the URL; however, the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="dd33f-306">**挂起的判定被绕过**：向用户显示沙箱页面;但是，用户 overrode 页面以导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="dd33f-306">**Pending verdict bypassed**: The user was presented with the detonation page; however, the user overrode the page to navigate to the URL.</span></span>
- <span data-ttu-id="dd33f-307">**错误**：用户显示错误页。</span><span class="sxs-lookup"><span data-stu-id="dd33f-307">**Error**: The user was presented with the error page.</span></span> <span data-ttu-id="dd33f-308">这也意味着捕获判定的错误。</span><span class="sxs-lookup"><span data-stu-id="dd33f-308">This can also mean there was an error in capturing the verdict.</span></span>
- <span data-ttu-id="dd33f-309">**失败**：捕获判定时出现未知异常。</span><span class="sxs-lookup"><span data-stu-id="dd33f-309">**Failure**: There was unknown exception while capturing the verdict.</span></span> <span data-ttu-id="dd33f-310">用户可能已通过 URL 单击。</span><span class="sxs-lookup"><span data-stu-id="dd33f-310">The user might have clicked through the URL.</span></span> 

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="dd33f-311">查看用户报告的电子邮件</span><span class="sxs-lookup"><span data-stu-id="dd33f-311">Review email messages reported by users</span></span>

<span data-ttu-id="dd33f-312">假设您想要查看您的组织中的用户使用 [Outlook 和 web 上的 outlook 的报告邮件外接程序](enable-the-report-message-add-in.md)报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dd33f-312">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="dd33f-313">为此，请使用浏览器 (的 [电子邮件 > 提交](threat-explorer-views.md#email--submissions) 视图或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-313">To do this, use the [Email > Submissions](threat-explorer-views.md#email--submissions) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="dd33f-314">在 "安全性 & 合规性中心 ([https://protection.office.com](https://protection.office.com) ") 中，选择 "**威胁管理**  >  **资源管理器** (" 或 "**实时检测**") 。</span><span class="sxs-lookup"><span data-stu-id="dd33f-314">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="dd33f-315"> (本示例使用 Explorer。 ) </span><span class="sxs-lookup"><span data-stu-id="dd33f-315">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="dd33f-316">在 "**视图**" 菜单中，选择 "**电子邮件**  >  **提交**"。</span><span class="sxs-lookup"><span data-stu-id="dd33f-316">In the **View** menu, choose **Email** > **Submissions**.</span></span>

   ![浏览器的视图菜单](../../media/explorer-view-menu-email-user-reported.png)

3. <span data-ttu-id="dd33f-318">单击 "**发件人**"，然后选择 "**基本**  >  **报告类型**"。</span><span class="sxs-lookup"><span data-stu-id="dd33f-318">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="dd33f-319">选择一个选项，如 " **网络钓鱼**"，然后单击 " **刷新** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="dd33f-319">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span>

   ![用户报告的网络钓鱼](../../media/EmailUserReportedReportType.png)

<span data-ttu-id="dd33f-321">报告将刷新，以显示组织中的人员已报告为网络钓鱼尝试的电子邮件的相关数据。</span><span class="sxs-lookup"><span data-stu-id="dd33f-321">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="dd33f-322">您可以使用此信息进行进一步分析，如有必要，调整您的 [ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="dd33f-322">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="dd33f-323">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="dd33f-323">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="dd33f-324">**Office 365 ATP 计划 2**和**Office 365 E5**中提供了自动调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="dd33f-324">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="dd33f-325"> (NEW！ ) [自动调查和响应](automated-investigation-response-office.md) 可在调查和缓解 cyberattacks 的过程中节省您的安全操作团队时间和精力。</span><span class="sxs-lookup"><span data-stu-id="dd33f-325">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="dd33f-326">除了配置可触发安全行动手册的警报外，还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="dd33f-326">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span>

<span data-ttu-id="dd33f-327">有关此操作的详细信息，请参阅 [示例：安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="dd33f-327">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="dd33f-328">使用资源管理器 (或实时检测) 的更多方法</span><span class="sxs-lookup"><span data-stu-id="dd33f-328">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="dd33f-329">除了本文中介绍的方案，您还可以使用浏览器 (或实时检测) 更多的报告选项。</span><span class="sxs-lookup"><span data-stu-id="dd33f-329">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span>

- [<span data-ttu-id="dd33f-330">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="dd33f-330">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="dd33f-331">查看 SharePoint Online、OneDrive 和 Microsoft 团队中检测到的恶意文件</span><span class="sxs-lookup"><span data-stu-id="dd33f-331">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="dd33f-332">获取有关威胁资源管理器中的视图的概述 (和实时检测) </span><span class="sxs-lookup"><span data-stu-id="dd33f-332">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="dd33f-333">Microsoft 威胁防护中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="dd33f-333">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="dd33f-334">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="dd33f-334">Required licenses and permissions</span></span>

<span data-ttu-id="dd33f-335">您必须具有 [Office 365 ATP](office-365-atp.md) 才能获取资源管理器或实时检测。</span><span class="sxs-lookup"><span data-stu-id="dd33f-335">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>

- <span data-ttu-id="dd33f-336">资源管理器包含在 Office 365 ATP 计划2中。</span><span class="sxs-lookup"><span data-stu-id="dd33f-336">Explorer is included in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="dd33f-337">实时检测报告包含在 Office 365 ATP 计划1中。</span><span class="sxs-lookup"><span data-stu-id="dd33f-337">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>
- <span data-ttu-id="dd33f-338">计划为应受 Office 365 ATP 保护的所有用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="dd33f-338">Plan to assign licenses for all users who should be protected by Office 365 ATP.</span></span> <span data-ttu-id="dd33f-339"> (资源管理器或实时检测显示许可用户的检测数据。 ) </span><span class="sxs-lookup"><span data-stu-id="dd33f-339">(Explorer or real-time detections shows detection data for licensed users.)</span></span>

<span data-ttu-id="dd33f-340">若要查看和使用资源管理器或实时检测，您必须具有适当的权限，例如，授予安全管理员或安全阅读者的权限。</span><span class="sxs-lookup"><span data-stu-id="dd33f-340">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="dd33f-341">对于安全 &amp; 合规中心，您必须具有以下分配的角色之一：</span><span class="sxs-lookup"><span data-stu-id="dd33f-341">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="dd33f-342">组织管理</span><span class="sxs-lookup"><span data-stu-id="dd33f-342">Organization Management</span></span>
  - <span data-ttu-id="dd33f-343">安全管理员 (可以在 Azure Active Directory 管理中心 (中分配此项 [https://aad.portal.azure.com](https://aad.portal.azure.com)) # A3</span><span class="sxs-lookup"><span data-stu-id="dd33f-343">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="dd33f-344">安全读取者</span><span class="sxs-lookup"><span data-stu-id="dd33f-344">Security Reader</span></span>

- <span data-ttu-id="dd33f-345">对于 Exchange Online，必须在 Exchange 管理中心 () 或 PowerShell cmdlet 中分配以下角色之一 [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) (请参阅 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) ：</span><span class="sxs-lookup"><span data-stu-id="dd33f-345">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="dd33f-346">组织管理</span><span class="sxs-lookup"><span data-stu-id="dd33f-346">Organization Management</span></span>
  - <span data-ttu-id="dd33f-347">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="dd33f-347">View-only Organization Management</span></span>
  - <span data-ttu-id="dd33f-348">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="dd33f-348">View-Only Recipients role</span></span>
  - <span data-ttu-id="dd33f-349">合规性管理</span><span class="sxs-lookup"><span data-stu-id="dd33f-349">Compliance Management</span></span>

<span data-ttu-id="dd33f-350">若要了解有关角色和权限的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="dd33f-350">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="dd33f-351">安全 &amp; 合规性中心中的权限</span><span class="sxs-lookup"><span data-stu-id="dd33f-351">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="dd33f-352">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="dd33f-352">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="dd33f-353">威胁资源管理器和实时检测的区别</span><span class="sxs-lookup"><span data-stu-id="dd33f-353">Some differences between Threat Explorer and real-time detections</span></span>

- <span data-ttu-id="dd33f-354">Office 365 ATP 计划1中提供了 **实时检测** 报告，而 **威胁浏览器** 在 office 365 atp 计划2中可用。</span><span class="sxs-lookup"><span data-stu-id="dd33f-354">The **real-time detections** report is available in Office 365 ATP Plan 1, whereas **Threat Explorer** is available in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="dd33f-355">**实时检测**报告允许你实时查看检测。</span><span class="sxs-lookup"><span data-stu-id="dd33f-355">The **real-time detections** report allows you to view detections in real-time.</span></span> <span data-ttu-id="dd33f-356">**威胁资源管理器** 也会执行此功能，但也允许您查看给定攻击的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="dd33f-356">**Threat Explorer** does this as well, but also allows you to view additional details for a given attack.</span></span>
- <span data-ttu-id="dd33f-357">" **所有电子邮件** " 视图在 **威胁资源管理器** 中可用 (并且不在 **实时检测** 报告) 中。</span><span class="sxs-lookup"><span data-stu-id="dd33f-357">An **All email** view is available in **Threat Explorer** (and is not in the **real-time detections** report).</span></span>
- <span data-ttu-id="dd33f-358">**威胁资源管理器**中包含更多筛选功能和可用操作。</span><span class="sxs-lookup"><span data-stu-id="dd33f-358">More filtering capabilities and available actions are included in **Threat Explorer**.</span></span>

<span data-ttu-id="dd33f-359">有关更多详细信息，请参阅 [Office 365 ATP 服务说明：功能在高级威胁防护中的功能可用性 (ATP) 计划](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="dd33f-359">For more details, see [Office 365 ATP Service Description: Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
