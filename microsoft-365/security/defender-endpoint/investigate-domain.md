---
title: 调查 Microsoft Defender 终结点域
description: 使用调查选项查看设备和服务器是否一直与恶意域通信。
keywords: 调查域， 域， 恶意域， Microsoft Defender for Endpoint， 警报， URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7826229ba67384137c033745a5b85e557fc9c4a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933465"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="0a9a5-104">调查与 Microsoft Defender for Endpoint 警报关联的域</span><span class="sxs-lookup"><span data-stu-id="0a9a5-104">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0a9a5-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0a9a5-105">**Applies to:**</span></span>
- [<span data-ttu-id="0a9a5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0a9a5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0a9a5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a9a5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0a9a5-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="0a9a5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0a9a5-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

<span data-ttu-id="0a9a5-110">调查域以查看企业网络中设备和服务器是否一直与已知的恶意域通信。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-110">Investigate a domain to see if devices and servers in your enterprise network have been communicating with a known malicious domain.</span></span>

<span data-ttu-id="0a9a5-111">可以使用搜索功能或单击设备时间线中的域链接来调查 **域**。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-111">You can investigate a domain by using the search feature or by clicking on a domain link from the **Device timeline**.</span></span>

<span data-ttu-id="0a9a5-112">您可以在 URL 视图中查看以下部分的信息：</span><span class="sxs-lookup"><span data-stu-id="0a9a5-112">You can see information from the following sections in the URL view:</span></span>

- <span data-ttu-id="0a9a5-113">URL 详细信息、联系人、名称服务器</span><span class="sxs-lookup"><span data-stu-id="0a9a5-113">URL details, Contacts, Nameservers</span></span>
- <span data-ttu-id="0a9a5-114">与此 URL 相关的警报</span><span class="sxs-lookup"><span data-stu-id="0a9a5-114">Alerts related to this URL</span></span> 
- <span data-ttu-id="0a9a5-115">组织中 URL</span><span class="sxs-lookup"><span data-stu-id="0a9a5-115">URL in organization</span></span>
- <span data-ttu-id="0a9a5-116">最近观察到的具有 URL 的设备</span><span class="sxs-lookup"><span data-stu-id="0a9a5-116">Most recent observed devices with URL</span></span>

## <a name="url-worldwide"></a><span data-ttu-id="0a9a5-117">全球 URL</span><span class="sxs-lookup"><span data-stu-id="0a9a5-117">URL worldwide</span></span>

<span data-ttu-id="0a9a5-118">" **全球 URL"** 部分列出了 URL、指向 Whois 的更多详细信息的链接、相关打开事件的数量以及活动警报的数量。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-118">The **URL Worldwide** section lists the URL, a link to further details at Whois, the number of related open incidents, and the number of active alerts.</span></span>

## <a name="incident"></a><span data-ttu-id="0a9a5-119">事件</span><span class="sxs-lookup"><span data-stu-id="0a9a5-119">Incident</span></span>

<span data-ttu-id="0a9a5-120">事件 **卡片** 显示过去 180 天内所有事件活动警报的条形图。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-120">The **Incident** card displays a bar chart of all active alerts in incidents over the past 180 days.</span></span>

## <a name="prevalence"></a><span data-ttu-id="0a9a5-121">普遍程度</span><span class="sxs-lookup"><span data-stu-id="0a9a5-121">Prevalence</span></span>

<span data-ttu-id="0a9a5-122">**"普遍** 程度"卡片提供指定时段内组织中 URL 的普遍程度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-122">The **Prevalence** card provides details on the prevalence of the URL within the organization, over a specified period of time.</span></span>

<span data-ttu-id="0a9a5-123">尽管默认时间段是过去 30 天，但可以通过选择卡片右上角的向下箭头来自定义范围。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-123">Although the default time period is the past 30 days, you can customize the range by selecting the downward-pointing arrow in the corner of the card.</span></span> <span data-ttu-id="0a9a5-124">可用范围最短的是过去一天的普遍程度，最长范围是过去 6 个月。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-124">The shortest range available is for prevalence over the past day, while the longest range is over the past 6 months.</span></span>

## <a name="alerts"></a><span data-ttu-id="0a9a5-125">警报</span><span class="sxs-lookup"><span data-stu-id="0a9a5-125">Alerts</span></span>

<span data-ttu-id="0a9a5-126">" **警报** "选项卡提供与 URL 关联的警报列表。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-126">The **Alerts** tab provides a list of alerts that are associated with the URL.</span></span> <span data-ttu-id="0a9a5-127">此处显示的表是警报队列屏幕上显示的警报的筛选版本，只显示与域关联的警报、严重性、状态、关联事件、分类、调查状态等。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-127">The table shown here is a filtered version of the alerts visible on the Alert queue screen, showing only alerts associated with the domain, their severity, status, the associated incident, classification, investigation state, and more.</span></span>

<span data-ttu-id="0a9a5-128">通过从列标题上方的操作菜单中选择"自定义列"，可以调整"通知"选项卡以显示更多或更少的信息。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-128">The Alerts tab can be adjusted to show more or less information, by selecting **Customize columns** from the action menu above the column headers.</span></span> <span data-ttu-id="0a9a5-129">通过在同一菜单上选择每页的项目， **还可以调整显示** 的项目数。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-129">The number of items displayed can also be adjusted, by selecting **items per page** on the same menu.</span></span>

## <a name="observed-in-organization"></a><span data-ttu-id="0a9a5-130">在组织中观测到</span><span class="sxs-lookup"><span data-stu-id="0a9a5-130">Observed in organization</span></span>

<span data-ttu-id="0a9a5-131">" **在组织中观测** 到"选项卡提供有关在 URL 上观测到的事件和关联警报按时间顺序排列的视图。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-131">The **Observed in organization** tab provides a chronological view on the events and associated alerts that were observed on the URL.</span></span> <span data-ttu-id="0a9a5-132">此选项卡包括时间线和可自定义的表格，其中列出了事件详细信息，如时间、设备和所发生事件的简要说明。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-132">This tab includes a timeline and a customizable table listing event details, such as the time, device, and a brief description of what happened.</span></span> 

<span data-ttu-id="0a9a5-133">您可以通过在表格标题上方的文本字段中输入日期来查看不同时间段的事件。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-133">You can view events from different periods of time by entering the dates into the text fields above the table headers.</span></span> <span data-ttu-id="0a9a5-134">您还可以通过选择时间线的不同区域来自定义时间范围。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-134">You can also customize the time range by selecting different areas of the timeline.</span></span>

<span data-ttu-id="0a9a5-135">**调查域：**</span><span class="sxs-lookup"><span data-stu-id="0a9a5-135">**Investigate a domain:**</span></span>

1. <span data-ttu-id="0a9a5-136">从搜索栏 **下拉菜单中选择** **URL。**</span><span class="sxs-lookup"><span data-stu-id="0a9a5-136">Select **URL** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="0a9a5-137">在"搜索"字段中 **输入** URL。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-137">Enter the URL in the **Search** field.</span></span>
3. <span data-ttu-id="0a9a5-138">单击搜索图标或按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="0a9a5-138">Click the search icon   or press **Enter**.</span></span> <span data-ttu-id="0a9a5-139">将显示有关 URL 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-139">Details about the URL are displayed.</span></span> <span data-ttu-id="0a9a5-140">注意：将仅返回在来自组织中设备的通信中观察到的 URL 的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-140">Note: search results will only be returned for URLs observed in communications from devices in the organization.</span></span>
4. <span data-ttu-id="0a9a5-141">使用搜索筛选器定义搜索条件。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-141">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="0a9a5-142">您还可以使用时间线搜索框筛选组织中观测到与 URL 通信的所有设备的显示结果、与通信关联的文件和上次观测日期。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-142">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the URL, the file associated with the communication and the last date observed.</span></span>
5. <span data-ttu-id="0a9a5-143">单击任何设备名称将进入该设备的视图，你可以继续调查报告的警报、行为和事件。</span><span class="sxs-lookup"><span data-stu-id="0a9a5-143">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a9a5-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="0a9a5-144">Related topics</span></span>
- [<span data-ttu-id="0a9a5-145">查看和组织 Microsoft Defender 终结点警报队列</span><span class="sxs-lookup"><span data-stu-id="0a9a5-145">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="0a9a5-146">管理 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="0a9a5-146">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="0a9a5-147">调查 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="0a9a5-147">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="0a9a5-148">调查与 Microsoft Defender for Endpoint 警报关联的文件</span><span class="sxs-lookup"><span data-stu-id="0a9a5-148">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="0a9a5-149">调查 Microsoft Defender 终结点设备列表中的设备</span><span class="sxs-lookup"><span data-stu-id="0a9a5-149">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="0a9a5-150">调查与 Microsoft Defender for Endpoint 警报关联的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="0a9a5-150">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="0a9a5-151">调查 Microsoft Defender for Endpoint 中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="0a9a5-151">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
