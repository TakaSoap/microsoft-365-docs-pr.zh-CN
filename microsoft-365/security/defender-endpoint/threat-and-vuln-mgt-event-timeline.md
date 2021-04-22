---
title: 威胁和漏洞管理中的事件时间线
description: 事件时间线是一个风险新闻源，可帮助你解释如何将风险引入组织，以及采取哪些缓解措施来降低风险。
keywords: 事件时间线， Microsoft Defender for Endpoint 事件时间线， Microsoft Defender for Endpoint tvm 事件时间线， 威胁和漏洞管理， Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 64362598ff4b0512eb110917071e6d32abb8ede9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933477"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a><span data-ttu-id="74297-104">事件时间线 - 威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="74297-104">Event timeline - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="74297-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="74297-105">**Applies to:**</span></span>
- [<span data-ttu-id="74297-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="74297-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="74297-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74297-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="74297-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="74297-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="74297-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="74297-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="74297-110">事件时间线是一个风险新闻源，可帮助您解释通过新漏洞或漏洞向组织引入风险的方式。</span><span class="sxs-lookup"><span data-stu-id="74297-110">Event timeline is a risk news feed that helps you interpret how risk is introduced into the organization through new vulnerabilities or exploits.</span></span> <span data-ttu-id="74297-111">您可以查看可能会影响组织风险的事件。</span><span class="sxs-lookup"><span data-stu-id="74297-111">You can view events that may impact your organization's risk.</span></span> <span data-ttu-id="74297-112">例如，你可以找到引入的新漏洞、被利用的漏洞、添加到攻击工具包的漏洞等。</span><span class="sxs-lookup"><span data-stu-id="74297-112">For example, you can find new vulnerabilities that were introduced, vulnerabilities that became exploitable, exploit that was added to an exploit kit, and more.</span></span>

<span data-ttu-id="74297-113">事件时间线还介绍你的 [曝光分数和](tvm-exposure-score.md) 适用于设备的 [Microsoft 安全](tvm-microsoft-secure-score-devices.md) 分数，以便你可以确定重大更改的原因。</span><span class="sxs-lookup"><span data-stu-id="74297-113">Event timeline also tells the story of your [exposure score](tvm-exposure-score.md) and [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) so you can determine the cause of large changes.</span></span> <span data-ttu-id="74297-114">事件可能会影响你的设备或你的设备分数。</span><span class="sxs-lookup"><span data-stu-id="74297-114">Events can impact your devices or your score for devices.</span></span> <span data-ttu-id="74297-115">通过根据优先安全建议解决需要修正的问题，减少 [曝光](tvm-security-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="74297-115">Reduce you exposure by addressing what needs to be remediated based on the prioritized [security recommendations](tvm-security-recommendation.md).</span></span>

>[!TIP]
><span data-ttu-id="74297-116">若要获取有关新漏洞事件的电子邮件，请参阅在 Microsoft [Defender for Endpoint](configure-vulnerability-email-notifications.md)中配置漏洞电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="74297-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-event-timeline-page"></a><span data-ttu-id="74297-117">导航到"事件时间线"页</span><span class="sxs-lookup"><span data-stu-id="74297-117">Navigate to the Event timeline page</span></span>

<span data-ttu-id="74297-118">威胁和漏洞管理仪表板中还有三 [个入口点](tvm-dashboard-insights.md)：</span><span class="sxs-lookup"><span data-stu-id="74297-118">There are also three entry points from the [threat and vulnerability management dashboard](tvm-dashboard-insights.md):</span></span>

- <span data-ttu-id="74297-119">**组织曝光分数卡**：将鼠标悬停在"时间曝光分数"图中的事件点上，然后选择"查看这一天的所有事件"。</span><span class="sxs-lookup"><span data-stu-id="74297-119">**Organization exposure score card**: Hover over the event dots in the "Exposure Score over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="74297-120">这些事件表示软件漏洞。</span><span class="sxs-lookup"><span data-stu-id="74297-120">The events represent software vulnerabilities.</span></span>
- <span data-ttu-id="74297-121">**Microsoft 设备安全分数**：将鼠标悬停在"设备一段时间的分数"图中的事件点上，然后选择"查看这一天的所有事件"。</span><span class="sxs-lookup"><span data-stu-id="74297-121">**Microsoft Secure Score for Devices**: Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="74297-122">这些事件表示新的配置评估。</span><span class="sxs-lookup"><span data-stu-id="74297-122">The events represent new configuration assessments.</span></span>
- <span data-ttu-id="74297-123">**Top events card**： Select "Show more" at the bottom of the top events table.</span><span class="sxs-lookup"><span data-stu-id="74297-123">**Top events card**: Select "Show more" at the bottom of the top events table.</span></span> <span data-ttu-id="74297-124">卡片显示最近 7 天内影响最大的三个事件。</span><span class="sxs-lookup"><span data-stu-id="74297-124">The card displays the three most impactful events in the last 7 days.</span></span> <span data-ttu-id="74297-125">如果事件影响大量设备，或者它是一个关键漏洞，则可包括有影响的事件。</span><span class="sxs-lookup"><span data-stu-id="74297-125">Impactful events can include if the event affects a large number of devices, or if it is a critical vulnerability.</span></span>

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a><span data-ttu-id="74297-126">设备曝光分数和 Microsoft 安全分数图</span><span class="sxs-lookup"><span data-stu-id="74297-126">Exposure score and Microsoft Secure Score for Devices graphs</span></span>

<span data-ttu-id="74297-127">在威胁和漏洞管理仪表板中，将鼠标悬停在曝光分数图上，查看当天影响设备的主要软件漏洞事件。</span><span class="sxs-lookup"><span data-stu-id="74297-127">In the threat and vulnerability management dashboard, hover over the Exposure score graph to view top software vulnerability events from that day that impacted your devices.</span></span> <span data-ttu-id="74297-128">将鼠标悬停在 Microsoft 设备安全分数图上可查看影响分数的新安全配置评估。</span><span class="sxs-lookup"><span data-stu-id="74297-128">Hover over the Microsoft Secure Score for Devices graph to view new security configuration assessments that affect your score.</span></span>

<span data-ttu-id="74297-129">如果没有影响你的设备或你的设备分数的事件，则不会显示任何事件。</span><span class="sxs-lookup"><span data-stu-id="74297-129">If there are no events that affect your devices or your score for devices, then none will be shown.</span></span>

<span data-ttu-id="74297-130">![曝光分数悬停 ](images/tvm-event-timeline-exposure-score350.png) 
 ![ Microsoft 设备安全分数悬停](images/tvm-event-timeline-device-hover360.png)</span><span class="sxs-lookup"><span data-stu-id="74297-130">![Exposure score hover](images/tvm-event-timeline-exposure-score350.png) 
![Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span></span>

### <a name="drill-down-to-events-from-that-day"></a><span data-ttu-id="74297-131">向下钻取到当天的事件</span><span class="sxs-lookup"><span data-stu-id="74297-131">Drill down to events from that day</span></span>

<span data-ttu-id="74297-132">选择 **"显示这一天的所有** 事件"将你访问具有该日期的自定义日期范围的"事件时间线"页。</span><span class="sxs-lookup"><span data-stu-id="74297-132">Selecting **Show all events from this day** takes you to the Event timeline page with a custom date range for that day.</span></span>

![事件时间线选择的自定义日期范围](images/tvm-event-timeline-drilldown.png)

<span data-ttu-id="74297-134">选择 **"自定义** 范围"将日期范围更改为其他自定义范围或预设的时区。</span><span class="sxs-lookup"><span data-stu-id="74297-134">Select **Custom range** to change the date range to another custom one, or a pre-set time range.</span></span>

![事件时间线日期范围选项](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a><span data-ttu-id="74297-136">事件时间线概述</span><span class="sxs-lookup"><span data-stu-id="74297-136">Event timeline overview</span></span>

<span data-ttu-id="74297-137">在"事件时间线"页上，可以查看与事件相关的全部必要信息。</span><span class="sxs-lookup"><span data-stu-id="74297-137">On the Event timeline page, you can view the all the necessary info related to an event.</span></span> 

<span data-ttu-id="74297-138">功能：</span><span class="sxs-lookup"><span data-stu-id="74297-138">Features:</span></span>

- <span data-ttu-id="74297-139">自定义列</span><span class="sxs-lookup"><span data-stu-id="74297-139">Customize columns</span></span>
- <span data-ttu-id="74297-140">按事件类型或受影响设备的百分比进行筛选</span><span class="sxs-lookup"><span data-stu-id="74297-140">Filter by event type or percent of impacted devices</span></span>
- <span data-ttu-id="74297-141">每页查看 30、50 或 100 个项目</span><span class="sxs-lookup"><span data-stu-id="74297-141">View 30, 50, or 100 items per page</span></span>

<span data-ttu-id="74297-142">页面顶部的两个大数字显示新漏洞和可利用漏洞的数量，而不是事件数。</span><span class="sxs-lookup"><span data-stu-id="74297-142">The two large numbers at the top of the page show the number of new vulnerabilities and exploitable vulnerabilities, not events.</span></span> <span data-ttu-id="74297-143">某些事件可能有多个漏洞，而某些漏洞可以有多个事件。</span><span class="sxs-lookup"><span data-stu-id="74297-143">Some events can have multiple vulnerabilities, and some vulnerabilities can have multiple events.</span></span>

![事件时间线页面](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a><span data-ttu-id="74297-145">列数</span><span class="sxs-lookup"><span data-stu-id="74297-145">Columns</span></span>

- <span data-ttu-id="74297-146">**日期**：月、日、年</span><span class="sxs-lookup"><span data-stu-id="74297-146">**Date**: month, day, year</span></span>
- <span data-ttu-id="74297-147">**事件**：影响的事件，包括组件、类型和受影响设备的数量</span><span class="sxs-lookup"><span data-stu-id="74297-147">**Event**: impactful event, including component, type, and number of impacted devices</span></span>
- <span data-ttu-id="74297-148">**相关组件**： 软件</span><span class="sxs-lookup"><span data-stu-id="74297-148">**Related component**: software</span></span>
- <span data-ttu-id="74297-149">**最初影响的设备**：最初发生此事件时受影响设备的数量和百分比。</span><span class="sxs-lookup"><span data-stu-id="74297-149">**Originally impacted devices**: the number, and percentage, of impacted devices when this event originally occurred.</span></span> <span data-ttu-id="74297-150">还可以按最初影响设备的百分比筛选出设备总数。</span><span class="sxs-lookup"><span data-stu-id="74297-150">You can also filter by the percent of originally impacted devices, out of your total number of devices.</span></span>
- <span data-ttu-id="74297-151">**当前影响的设备**：此事件当前影响的设备的当前数量和百分比。</span><span class="sxs-lookup"><span data-stu-id="74297-151">**Currently impacted devices**: the current number, and percentage, of devices that this event currently impacts.</span></span> <span data-ttu-id="74297-152">可以通过选择"自定义列 **"来查找此字段**。</span><span class="sxs-lookup"><span data-stu-id="74297-152">You can find this field by selecting **Customize columns**.</span></span>
- <span data-ttu-id="74297-153">**类型**：反映影响分数的时间戳事件。</span><span class="sxs-lookup"><span data-stu-id="74297-153">**Types**: reflect time-stamped events that impact the score.</span></span> <span data-ttu-id="74297-154">可以筛选它们。</span><span class="sxs-lookup"><span data-stu-id="74297-154">They can be filtered.</span></span>
    - <span data-ttu-id="74297-155">添加到攻击工具包的 Exploit</span><span class="sxs-lookup"><span data-stu-id="74297-155">Exploit added to an exploit kit</span></span>
    - <span data-ttu-id="74297-156">已验证攻击</span><span class="sxs-lookup"><span data-stu-id="74297-156">Exploit was verified</span></span>
    - <span data-ttu-id="74297-157">新的公共攻击</span><span class="sxs-lookup"><span data-stu-id="74297-157">New public exploit</span></span>
    - <span data-ttu-id="74297-158">新漏洞</span><span class="sxs-lookup"><span data-stu-id="74297-158">New vulnerability</span></span>
    - <span data-ttu-id="74297-159">新配置评估</span><span class="sxs-lookup"><span data-stu-id="74297-159">New configuration assessment</span></span>
- <span data-ttu-id="74297-160">**分数趋势**：曝光分数趋势</span><span class="sxs-lookup"><span data-stu-id="74297-160">**Score trend**: exposure score trend</span></span>

### <a name="icons"></a><span data-ttu-id="74297-161">图标</span><span class="sxs-lookup"><span data-stu-id="74297-161">Icons</span></span>

<span data-ttu-id="74297-162">事件旁边会显示以下图标：</span><span class="sxs-lookup"><span data-stu-id="74297-162">The following icons show up next to events:</span></span>

- ![Bug 图标](images/tvm-black-bug-icon.png) <span data-ttu-id="74297-164">新的公共攻击</span><span class="sxs-lookup"><span data-stu-id="74297-164">New public exploit</span></span>
- ![报告警告图标](images/report-warning-icon.png) <span data-ttu-id="74297-166">已发布新漏洞</span><span class="sxs-lookup"><span data-stu-id="74297-166">New vulnerability was published</span></span>
- ![攻击工具包](images/bug-lightning-icon2.png) <span data-ttu-id="74297-168">在攻击工具包中发现攻击</span><span class="sxs-lookup"><span data-stu-id="74297-168">Exploit found in exploit kit</span></span>
- ![带警告图标的 bug 图标](images/bug-caution-icon2.png) <span data-ttu-id="74297-170">已验证攻击</span><span class="sxs-lookup"><span data-stu-id="74297-170">Exploit verified</span></span>

### <a name="drill-down-to-a-specific-event"></a><span data-ttu-id="74297-171">向下钻取到特定事件</span><span class="sxs-lookup"><span data-stu-id="74297-171">Drill down to a specific event</span></span>

<span data-ttu-id="74297-172">选择事件后，将显示一个飞出列表，其中列出了影响设备的详细信息和当前 CVEs。</span><span class="sxs-lookup"><span data-stu-id="74297-172">Once you select an event, a flyout will appear with a list of the details and current CVEs that affect your devices.</span></span> <span data-ttu-id="74297-173">你可以显示更多 CVEs 或查看相关建议。</span><span class="sxs-lookup"><span data-stu-id="74297-173">You can show more CVEs or view the related recommendation.</span></span>

<span data-ttu-id="74297-174">"分数趋势"下方的箭头可帮助你确定此事件是可能会引发还是降低你的组织曝光分数。</span><span class="sxs-lookup"><span data-stu-id="74297-174">The arrow below "score trend" helps you determine whether this event potentially raised or lowered your organizational exposure score.</span></span> <span data-ttu-id="74297-175">曝光分数越高，设备更容易被利用。</span><span class="sxs-lookup"><span data-stu-id="74297-175">Higher exposure score means devices are more vulnerable to exploitation.</span></span>

![事件时间线飞出](images/tvm-event-timeline-flyout500.png)

<span data-ttu-id="74297-177">从中选择" **转到相关安全建议** "，查看解决安全建议页中的新软件 [漏洞的建议](tvm-security-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="74297-177">From there, select **Go to related security recommendation** view the recommendation that addresses the new software vulnerability in the [security recommendations page](tvm-security-recommendation.md).</span></span> <span data-ttu-id="74297-178">阅读安全建议中的说明和漏洞详细信息后，可以提交修正请求，并跟踪修正 [页面中的请求](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="74297-178">After reading the description and vulnerability details in the security recommendation, you can submit a remediation request, and track the request in the [remediation page](tvm-remediation.md).</span></span>  

## <a name="view-event-timelines-in-software-pages"></a><span data-ttu-id="74297-179">在软件页面中查看事件时间线</span><span class="sxs-lookup"><span data-stu-id="74297-179">View Event timelines in software pages</span></span>

<span data-ttu-id="74297-180">若要打开软件页面，请选择事件>在 ("相关组件"部分中选择超链接软件名称 (如 Visual Studio 2017) 。</span><span class="sxs-lookup"><span data-stu-id="74297-180">To open a software page, select an event > select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout.</span></span> [<span data-ttu-id="74297-181">详细了解软件页面</span><span class="sxs-lookup"><span data-stu-id="74297-181">Learn more about software pages</span></span>](tvm-software-inventory.md#software-pages)

<span data-ttu-id="74297-182">将显示一个完整的页面，其中包含特定软件的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="74297-182">A full page will appear with all the details of a specific software.</span></span> <span data-ttu-id="74297-183">将鼠标悬停在图形上以查看该特定软件的事件时间线。</span><span class="sxs-lookup"><span data-stu-id="74297-183">Mouse over the graph to see the timeline of events for that specific software.</span></span>

![具有事件时间线图的软件页面](images/tvm-event-timeline-software2.png)

<span data-ttu-id="74297-185">导航到事件时间线选项卡以查看与该软件相关的所有事件。</span><span class="sxs-lookup"><span data-stu-id="74297-185">Navigate to the event timeline tab to view all the events related to that software.</span></span> <span data-ttu-id="74297-186">还可以查看安全建议、发现的漏洞、已安装的设备以及版本分发。</span><span class="sxs-lookup"><span data-stu-id="74297-186">You can also see security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span>

![具有"事件时间线"选项卡的软件页面](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a><span data-ttu-id="74297-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="74297-188">Related topics</span></span>

- [<span data-ttu-id="74297-189">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="74297-189">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="74297-190">仪表板</span><span class="sxs-lookup"><span data-stu-id="74297-190">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="74297-191">风险评分</span><span class="sxs-lookup"><span data-stu-id="74297-191">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="74297-192">安全性建议</span><span class="sxs-lookup"><span data-stu-id="74297-192">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="74297-193">修正漏洞</span><span class="sxs-lookup"><span data-stu-id="74297-193">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="74297-194">软件库存</span><span class="sxs-lookup"><span data-stu-id="74297-194">Software inventory</span></span>](tvm-software-inventory.md)

