---
title: Microsoft 365网络评估
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365网络评估
ms.openlocfilehash: c09e34b1bc3a8bf0f82a4a1e3c72e67f320abd43
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470462"
---
# <a name="microsoft-365-network-assessment"></a><span data-ttu-id="b1fda-103">Microsoft 365网络评估</span><span class="sxs-lookup"><span data-stu-id="b1fda-103">Microsoft 365 network assessment</span></span>

<span data-ttu-id="b1fda-104">在Microsoft 365中心的网络连接中，网络评估将许多网络性能指标聚合到企业网络外围运行状况的快照中。</span><span class="sxs-lookup"><span data-stu-id="b1fda-104">In the Microsoft 365 Admin Center's network connectivity, **network assessments** distill an aggregate of many network performance metrics into a snapshot of your enterprise network perimeter health.</span></span> <span data-ttu-id="b1fda-105">网络评估会告知你客户负责的网络设计对用户体验Office 365的影响。</span><span class="sxs-lookup"><span data-stu-id="b1fda-105">A network assessment tells you how much the customer responsible network design is impacting Office 365 user experience.</span></span> <span data-ttu-id="b1fda-106">网络评估的范围既包括整个租户，也包括用户连接到租户的每个地理位置。</span><span class="sxs-lookup"><span data-stu-id="b1fda-106">Network assessments are scoped to both the entire tenant and to each geographic location from which users connect to your tenant.</span></span> <span data-ttu-id="b1fda-107">评估为Microsoft 365管理员提供了一种简单方法，以便立即了解企业的网络运行状况，并快速深入到任何全局办事处位置的详细报告。</span><span class="sxs-lookup"><span data-stu-id="b1fda-107">The assessments provide Microsoft 365 administrators with an easy way to instantly get a sense of the enterprise's network health and quickly drill down into a detailed report for any global office location.</span></span>

<span data-ttu-id="b1fda-108">网络评估点值从 0 到 100，是 TCP 延迟、下载速度和 UDP 连接质量指标的平均值。</span><span class="sxs-lookup"><span data-stu-id="b1fda-108">The network assessment points value is from 0 to 100 and is an average of TCP latency, download speed, and UDP connection quality metrics.</span></span> <span data-ttu-id="b1fda-109">这些指标每天编译一次。</span><span class="sxs-lookup"><span data-stu-id="b1fda-109">These metrics are compiled once a day.</span></span> <span data-ttu-id="b1fda-110">这些指标中不包括 Microsoft 拥有的网络的性能指标，以确保评估结果明确且特定于企业网络。</span><span class="sxs-lookup"><span data-stu-id="b1fda-110">Performance metrics for Microsoft-owned networks are excluded from these measurements to ensure that assessment results are unambiguous and specific to the corporate network.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1fda-111">![网络评估值](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)</span><span class="sxs-lookup"><span data-stu-id="b1fda-111">![Network assessment value](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)</span></span>

<span data-ttu-id="b1fda-112">非常低的网络评估值表明Microsoft 365客户端在连接到租户或维护快速响应用户体验时将遇到严重问题。</span><span class="sxs-lookup"><span data-stu-id="b1fda-112">A very low network assessment value suggests that Microsoft 365 clients will have significant problems connecting to the tenant or maintaining a responsive user experience.</span></span> <span data-ttu-id="b1fda-113">较高的值表示配置正确的网络，并且存在一些持续的性能问题。</span><span class="sxs-lookup"><span data-stu-id="b1fda-113">A high value indicates a properly configured network with few ongoing performance issues.</span></span> <span data-ttu-id="b1fda-114">值 80% 表示正常基线，超过该值时不应因网络性能而收到有关 Microsoft 365 连接或响应的常规用户投诉。</span><span class="sxs-lookup"><span data-stu-id="b1fda-114">A value of 80% represents a healthy baseline, above which you should not expect to receive regular user complaints about Microsoft 365 connectivity or responsiveness due to network performance.</span></span> <span data-ttu-id="b1fda-115">随着迭代网络连接改进，此值将随用户体验一起增加。</span><span class="sxs-lookup"><span data-stu-id="b1fda-115">As iterative network connectivity improvements are made, this value will increase along with user experience.</span></span>

| <span data-ttu-id="b1fda-116">网络评估</span><span class="sxs-lookup"><span data-stu-id="b1fda-116">Network assessment</span></span> | <span data-ttu-id="b1fda-117">预期的用户体验</span><span class="sxs-lookup"><span data-stu-id="b1fda-117">Expected user experience</span></span> |
| :----------------- | :----------------------- |
| <span data-ttu-id="b1fda-118">100</span><span class="sxs-lookup"><span data-stu-id="b1fda-118">100</span></span>                | <span data-ttu-id="b1fda-119">最好</span><span class="sxs-lookup"><span data-stu-id="b1fda-119">Best</span></span>                     |
| <span data-ttu-id="b1fda-120">80</span><span class="sxs-lookup"><span data-stu-id="b1fda-120">80</span></span>                 | <span data-ttu-id="b1fda-121">满足建议</span><span class="sxs-lookup"><span data-stu-id="b1fda-121">Meets recommendations</span></span>    |
| <span data-ttu-id="b1fda-122">60</span><span class="sxs-lookup"><span data-stu-id="b1fda-122">60</span></span>                 | <span data-ttu-id="b1fda-123">可以接受</span><span class="sxs-lookup"><span data-stu-id="b1fda-123">Acceptable</span></span>               |
| <span data-ttu-id="b1fda-124">40</span><span class="sxs-lookup"><span data-stu-id="b1fda-124">40</span></span>                 | <span data-ttu-id="b1fda-125">用户可能会遇到问题</span><span class="sxs-lookup"><span data-stu-id="b1fda-125">Users may experience issues</span></span> |
| <span data-ttu-id="b1fda-126">20</span><span class="sxs-lookup"><span data-stu-id="b1fda-126">20</span></span>                 | <span data-ttu-id="b1fda-127">用户可能抱怨</span><span class="sxs-lookup"><span data-stu-id="b1fda-127">Users may complain</span></span>       |
| <span data-ttu-id="b1fda-128">0</span><span class="sxs-lookup"><span data-stu-id="b1fda-128">0</span></span>                  | <span data-ttu-id="b1fda-129">网络问题是一个常见讨论主题</span><span class="sxs-lookup"><span data-stu-id="b1fda-129">Network problems a common topic of discussion</span></span> |

>[!IMPORTANT]
><span data-ttu-id="b1fda-130">Microsoft 365 管理中心中的网络见解、性能建议和评估目前处于预览状态，仅适用于已在功能预览计划中注册的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="b1fda-130">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="network-assessment-panel"></a><span data-ttu-id="b1fda-131">网络评估面板</span><span class="sxs-lookup"><span data-stu-id="b1fda-131">Network assessment panel</span></span>

<span data-ttu-id="b1fda-132">每个网络评估（无论范围是租户还是特定办公地点）都显示一个面板，其中详细介绍了评估。</span><span class="sxs-lookup"><span data-stu-id="b1fda-132">Each network assessment, whether scoped to the tenant or to a specific office location, shows a panel with details about the assessment.</span></span> <span data-ttu-id="b1fda-133">此面板显示评估的条形图，以百分比和总分表示每个组件工作负荷（包括仅收到测量数据的工作负荷）。</span><span class="sxs-lookup"><span data-stu-id="b1fda-133">This panel shows a bar chart of the assessment both as a percentage and as the total points for each component workload including only workloads where measurement data was received.</span></span> <span data-ttu-id="b1fda-134">对于办公室位置网络评估，我们还显示与报告与办公地点位于同一城市的数据的每五个Microsoft 365客户百分比的比较。</span><span class="sxs-lookup"><span data-stu-id="b1fda-134">For an office location network assessment, we also show a comparison to the percent of Microsoft 365 customers in each of five quintiles that reported data in the same city as your office location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1fda-135">![示例网络评估值](../media/m365-mac-perf/m365-mac-perf-overview-score.png)</span><span class="sxs-lookup"><span data-stu-id="b1fda-135">![Example network assessment value](../media/m365-mac-perf/m365-mac-perf-overview-score.png)</span></span>

<span data-ttu-id="b1fda-136">面板 **中的** 评估细分显示每个组件工作负荷的评估。</span><span class="sxs-lookup"><span data-stu-id="b1fda-136">The **Assessment breakdown** in the panel shows the assessment for each of the component workloads.</span></span>

<span data-ttu-id="b1fda-137">评估 **历史记录** 显示过去 30 天的评估和基准。</span><span class="sxs-lookup"><span data-stu-id="b1fda-137">The **Assessment history** shows the past 30 days of the assessment and the benchmark.</span></span> <span data-ttu-id="b1fda-138">您还可以使用"历史记录"选项卡报告任何办公地点的最多两年的指标历史记录。"历史记录"选项卡允许你选择要报告的属性。</span><span class="sxs-lookup"><span data-stu-id="b1fda-138">You can also report on the metrics history for any office location for up to two years using the history tab. The history tab allows you to select your attributes to report on.</span></span> <span data-ttu-id="b1fda-139">通过选择报告时间范围，可以突出显示网络更新项目的影响，并查看对网络评估的改进。</span><span class="sxs-lookup"><span data-stu-id="b1fda-139">By choosing a report time frame, you can highlight the impact of a network update project and see the improvement to your network assessment.</span></span>

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a><span data-ttu-id="b1fda-140">租户网络评估和办公地点网络评估</span><span class="sxs-lookup"><span data-stu-id="b1fda-140">Tenant network assessments and office location network assessments</span></span>

<span data-ttu-id="b1fda-141">网络评估衡量 Microsoft 网络办公地点的网络外围设计。</span><span class="sxs-lookup"><span data-stu-id="b1fda-141">A network assessment measures the design of the network perimeter of an office location to Microsoft's network.</span></span> <span data-ttu-id="b1fda-142">最好在每个办公室位置对网络外围进行改进。</span><span class="sxs-lookup"><span data-stu-id="b1fda-142">Improvements to the network perimeter are  best done at each office location.</span></span>

<span data-ttu-id="b1fda-143">我们在"网络性能概述"页上显示Microsoft 365租户的网络评估值。</span><span class="sxs-lookup"><span data-stu-id="b1fda-143">We show a network assessment value for the whole Microsoft 365 tenant on the network performance overview page.</span></span> <span data-ttu-id="b1fda-144">此值是所有办公地点的网络评估加权平均值。</span><span class="sxs-lookup"><span data-stu-id="b1fda-144">This value is a weighted average of the network assessments for all office locations.</span></span> <span data-ttu-id="b1fda-145">对于该位置的摘要页面上的每个检测到的办公地点，还有一个特定的网络评估值。</span><span class="sxs-lookup"><span data-stu-id="b1fda-145">There is also a specific network assessment value for each detected office location on that location's summary page.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="b1fda-146">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b1fda-146">Exchange Online</span></span>

<span data-ttu-id="b1fda-147">例如Exchange Online，将测量从客户端计算机到 Exchange服务前端的 TCP 延迟。</span><span class="sxs-lookup"><span data-stu-id="b1fda-147">For Exchange Online, the TCP latency from the client machine to the Exchange service front door is measured.</span></span> <span data-ttu-id="b1fda-148">网络通过客户 LAN 和 WAN 传输的距离会影响此延迟。</span><span class="sxs-lookup"><span data-stu-id="b1fda-148">This latency can be impacted by the distance the network travels over the customers LAN and WAN.</span></span> <span data-ttu-id="b1fda-149">它还受网络中介设备或服务的影响，从而延迟连接或导致重新发送数据包。</span><span class="sxs-lookup"><span data-stu-id="b1fda-149">It can also be impacted by network intermediary devices or services, which delay the connectivity or cause packets to be resent.</span></span> <span data-ttu-id="b1fda-150">它受最近的服务Exchange距离的影响。</span><span class="sxs-lookup"><span data-stu-id="b1fda-150">And it is impacted by how far away the nearest Exchange service front door is.</span></span> <span data-ttu-id="b1fda-151">中值 (前三天的所有度量值) 第 50 个百分点或 P50 度量值。</span><span class="sxs-lookup"><span data-stu-id="b1fda-151">The median (also known as the 50th percentile or P50 measure) is taken for all measurements over the previous three days.</span></span>

<span data-ttu-id="b1fda-152">评估Exchange Online下表进行。</span><span class="sxs-lookup"><span data-stu-id="b1fda-152">The Exchange Online assessment is made using the following table.</span></span> <span data-ttu-id="b1fda-153">阈值之间的任何 TCP 延迟数在带内以线性方式分配点。</span><span class="sxs-lookup"><span data-stu-id="b1fda-153">Any TCP latency number between the thresholds are assigned points linearly within the band.</span></span>

| <span data-ttu-id="b1fda-154">TCP 延迟</span><span class="sxs-lookup"><span data-stu-id="b1fda-154">TCP Latency</span></span>   | <span data-ttu-id="b1fda-155">Points</span><span class="sxs-lookup"><span data-stu-id="b1fda-155">Points</span></span> |
| :------------ | :----- |
| <span data-ttu-id="b1fda-156">10 毫秒或更少</span><span class="sxs-lookup"><span data-stu-id="b1fda-156">10 ms or less</span></span>  | <span data-ttu-id="b1fda-157">100</span><span class="sxs-lookup"><span data-stu-id="b1fda-157">100</span></span>    |
| <span data-ttu-id="b1fda-158">25 毫秒</span><span class="sxs-lookup"><span data-stu-id="b1fda-158">25 ms</span></span>          | <span data-ttu-id="b1fda-159">80</span><span class="sxs-lookup"><span data-stu-id="b1fda-159">80</span></span>     |
| <span data-ttu-id="b1fda-160">100 毫秒</span><span class="sxs-lookup"><span data-stu-id="b1fda-160">100 ms</span></span>         | <span data-ttu-id="b1fda-161">60</span><span class="sxs-lookup"><span data-stu-id="b1fda-161">60</span></span>     |
| <span data-ttu-id="b1fda-162">200 毫秒</span><span class="sxs-lookup"><span data-stu-id="b1fda-162">200 ms</span></span>         | <span data-ttu-id="b1fda-163">40</span><span class="sxs-lookup"><span data-stu-id="b1fda-163">40</span></span>     |
| <span data-ttu-id="b1fda-164">300 毫秒</span><span class="sxs-lookup"><span data-stu-id="b1fda-164">300 ms</span></span>         | <span data-ttu-id="b1fda-165">20</span><span class="sxs-lookup"><span data-stu-id="b1fda-165">20</span></span>     |
| <span data-ttu-id="b1fda-166">350 毫秒或更长</span><span class="sxs-lookup"><span data-stu-id="b1fda-166">350 ms or more</span></span> | <span data-ttu-id="b1fda-167">0</span><span class="sxs-lookup"><span data-stu-id="b1fda-167">0</span></span>      |

## <a name="sharepoint-online"></a><span data-ttu-id="b1fda-168">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b1fda-168">SharePoint Online</span></span>

<span data-ttu-id="b1fda-169">For SharePoint Online the download speed for a user to access a document from SharePoint or OneDrive is measured.</span><span class="sxs-lookup"><span data-stu-id="b1fda-169">For SharePoint Online the download speed available for a user to access a document from SharePoint or OneDrive is measured.</span></span> <span data-ttu-id="b1fda-170">这受客户端计算机和 Microsoft 网络之间的网络电路上可用带宽的影响。</span><span class="sxs-lookup"><span data-stu-id="b1fda-170">This can be impacted by the bandwidth available on network circuits between the client machine and Microsoft's network.</span></span> <span data-ttu-id="b1fda-171">它通常还受网络拥塞的影响，网络拥塞存在于复杂的网络设备中的瓶颈中，或者网络区域覆盖Wi-Fi不足。</span><span class="sxs-lookup"><span data-stu-id="b1fda-171">It is also often impacted by network congestion that exists in bottlenecks in complex network devices or in poor coverage Wi-Fi areas.</span></span> <span data-ttu-id="b1fda-172">下载速度以兆字节/秒为单位测量，大约为每秒兆位率的电路的十分之一。</span><span class="sxs-lookup"><span data-stu-id="b1fda-172">The download speed is measured in megabytes per second, which is approximately one tenth of a circuits rated megabits per second.</span></span> <span data-ttu-id="b1fda-173">每秒的 MbByte 单位非常有用，因为您可以直接查看在 1 秒钟内可以下载的大小文件。</span><span class="sxs-lookup"><span data-stu-id="b1fda-173">The MegaByte per second unit is helpful because you can directly see what size file can be downloaded in 1 second.</span></span> <span data-ttu-id="b1fda-174">前三天 (测量的第 25) P25 度量值。</span><span class="sxs-lookup"><span data-stu-id="b1fda-174">The 25th percentile (also known as the P25 measure) is taken for all measurements over the previous three days.</span></span> <span data-ttu-id="b1fda-175">此 25 个百分点值有助于降低随时间变化拥塞的影响。</span><span class="sxs-lookup"><span data-stu-id="b1fda-175">This 25th percentile helps reduce the impact of varying congestion over time.</span></span>

<span data-ttu-id="b1fda-176">联机SharePoint评估是使用下表进行。</span><span class="sxs-lookup"><span data-stu-id="b1fda-176">The SharePoint Online assessment is made using the following table.</span></span> <span data-ttu-id="b1fda-177">阈值之间的任何下载速度编号在带内以线性方式分配点。</span><span class="sxs-lookup"><span data-stu-id="b1fda-177">Any download speed number between the thresholds are assigned points linearly within the band.</span></span>

| <span data-ttu-id="b1fda-178">下载速度</span><span class="sxs-lookup"><span data-stu-id="b1fda-178">Download speed</span></span> | <span data-ttu-id="b1fda-179">Points</span><span class="sxs-lookup"><span data-stu-id="b1fda-179">Points</span></span> |
| :------------- | :----- |
| <span data-ttu-id="b1fda-180">20MBps 或更多</span><span class="sxs-lookup"><span data-stu-id="b1fda-180">20MBps or more</span></span> | <span data-ttu-id="b1fda-181">100</span><span class="sxs-lookup"><span data-stu-id="b1fda-181">100</span></span>    |
| <span data-ttu-id="b1fda-182">14MBps</span><span class="sxs-lookup"><span data-stu-id="b1fda-182">14MBps</span></span>         | <span data-ttu-id="b1fda-183">80</span><span class="sxs-lookup"><span data-stu-id="b1fda-183">80</span></span>     |
| <span data-ttu-id="b1fda-184">8MBps</span><span class="sxs-lookup"><span data-stu-id="b1fda-184">8MBps</span></span>          | <span data-ttu-id="b1fda-185">60</span><span class="sxs-lookup"><span data-stu-id="b1fda-185">60</span></span>     |
| <span data-ttu-id="b1fda-186">4MBps</span><span class="sxs-lookup"><span data-stu-id="b1fda-186">4MBps</span></span>          | <span data-ttu-id="b1fda-187">40</span><span class="sxs-lookup"><span data-stu-id="b1fda-187">40</span></span>     |
| <span data-ttu-id="b1fda-188">2MBps</span><span class="sxs-lookup"><span data-stu-id="b1fda-188">2MBps</span></span>          | <span data-ttu-id="b1fda-189">20</span><span class="sxs-lookup"><span data-stu-id="b1fda-189">20</span></span>     |
| <span data-ttu-id="b1fda-190">0MBps</span><span class="sxs-lookup"><span data-stu-id="b1fda-190">0MBps</span></span>          | <span data-ttu-id="b1fda-191">0</span><span class="sxs-lookup"><span data-stu-id="b1fda-191">0</span></span>      |

## <a name="microsoft-teams"></a><span data-ttu-id="b1fda-192">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1fda-192">Microsoft Teams</span></span>

<span data-ttu-id="b1fda-193">例如Microsoft Teams网络质量测量为 UDP 延迟、UDP 抖动和 UDP 数据包丢失。</span><span class="sxs-lookup"><span data-stu-id="b1fda-193">For Microsoft Teams the Network quality is measured as UDP latency, UDP jitter, and UDP packet loss.</span></span> <span data-ttu-id="b1fda-194">UDP 用于呼叫和会议音频和视频媒体连接，Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="b1fda-194">UDP is used for call and conferencing audio and video media connectivity for Microsoft Teams.</span></span> <span data-ttu-id="b1fda-195">除了网络 UDP 支持中的连接差异外，这受延迟和下载速度的相同因素影响，因为 UDP 单独配置为更常见的 TCP 协议。</span><span class="sxs-lookup"><span data-stu-id="b1fda-195">This can be impacted by the same factors as for latency and download speed in addition to connectivity gaps in a network's UDP support since UDP is configured separately to the more common TCP protocol.</span></span> <span data-ttu-id="b1fda-196">中值 (前三天的所有度量值) 第 50 个百分点或 P50 度量值。</span><span class="sxs-lookup"><span data-stu-id="b1fda-196">The median (also known as the 50th percentile or P50 measure) is taken for all measurements over the previous three days.</span></span> 

<span data-ttu-id="b1fda-197">我们计算这些 UDP 度量中从 1 到 5 的一个平均意见得分。</span><span class="sxs-lookup"><span data-stu-id="b1fda-197">We calculate a mean opinion score from these UDP measurements for a scale from one to five.</span></span> <span data-ttu-id="b1fda-198">然后，我们将该范围映射到 0-100 点范围，用于Microsoft Teams评估。</span><span class="sxs-lookup"><span data-stu-id="b1fda-198">Then we map that to the 0-100 points scale for the Microsoft Teams network assessment.</span></span>  <span data-ttu-id="b1fda-199">总体好于 87.5 点，整体坏值低于 50 点。</span><span class="sxs-lookup"><span data-stu-id="b1fda-199">Overall good is over 87.5 points and overall bad is below 50 points.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1fda-200">相关主题</span><span class="sxs-lookup"><span data-stu-id="b1fda-200">Related topics</span></span>

[<span data-ttu-id="b1fda-201">Microsoft 365 管理中心 (预览) </span><span class="sxs-lookup"><span data-stu-id="b1fda-201">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="b1fda-202">Microsoft 365预览版 (网络性能) </span><span class="sxs-lookup"><span data-stu-id="b1fda-202">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="b1fda-203">Microsoft 365预览版 (网络连接测试) </span><span class="sxs-lookup"><span data-stu-id="b1fda-203">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="b1fda-204">Microsoft 365网络连接位置服务 (预览) </span><span class="sxs-lookup"><span data-stu-id="b1fda-204">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
