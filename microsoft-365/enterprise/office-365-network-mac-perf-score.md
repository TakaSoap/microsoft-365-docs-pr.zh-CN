---
title: 'Microsoft 365 网络评估 (预览版) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: 'Microsoft 365 网络评估 (预览版) '
ms.openlocfilehash: 21fb9515ea1621225cffbe23fe87d0daeb5265de
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104542"
---
# <a name="microsoft-365-network-assessment-preview"></a><span data-ttu-id="5cff3-103">Microsoft 365 网络评估 (预览版) </span><span class="sxs-lookup"><span data-stu-id="5cff3-103">Microsoft 365 network assessment (preview)</span></span>

<span data-ttu-id="5cff3-104">在 Microsoft 365 管理中心的网络连接中， **网络评估** 将许多网络性能指标的聚合提取到企业网络外围运行状况的快照中，由 0-100 中的点值表示。</span><span class="sxs-lookup"><span data-stu-id="5cff3-104">In the Microsoft 365 Admin Center's network connectivity, **network assessments** distill an aggregate of many network performance metrics into a snapshot of your enterprise network perimeter health, represented by a points value from 0 - 100.</span></span> <span data-ttu-id="5cff3-105">网络评估告诉你客户负责网络设计对 Office 365 用户体验有多大影响。</span><span class="sxs-lookup"><span data-stu-id="5cff3-105">A network assessment tells you how much the customer responsible network design is impacting Office 365 user experience.</span></span> <span data-ttu-id="5cff3-106">网络评估的作用范围为整个租户和每个地理位置，用户将从该位置连接到你的租户，从而为 Microsoft 365 管理员提供一种简单的方法来即时了解企业网络运行状况的 gestalt，并快速深入到任何全球办公地点的详细报告。</span><span class="sxs-lookup"><span data-stu-id="5cff3-106">Network assessments are scoped to both the entire tenant and for each geographic location from which users connect to your tenant, providing Microsoft 365 administrators with an easy way to instantly grasp a gestalt of the enterprise's network health and quickly drill down into a detailed report for any global office location.</span></span>

<span data-ttu-id="5cff3-107">网络评估点值是一天编译的平均 TCP 延迟、下载速度和 UDP 连接质量指标。</span><span class="sxs-lookup"><span data-stu-id="5cff3-107">The network assessment points value is an average of TCP latency, download speed and UDP connection quality metrics compiled once a day.</span></span> <span data-ttu-id="5cff3-108">Microsoft 拥有的网络的性能指标将从这些度量中排除，以确保评估结果明确且特定于企业网络。</span><span class="sxs-lookup"><span data-stu-id="5cff3-108">Performance metrics for Microsoft-owned networks are excluded from these measurements to ensure that assessment results are unambiguous and specific to the corporate network.</span></span>

![网络评估价值](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

<span data-ttu-id="5cff3-110">非常低的网络评估价值表明 Microsoft 365 客户端将在连接到租户或维护响应前的用户体验时遇到严重问题，而较高的值表示配置正确的网络，且持续的性能问题很少。</span><span class="sxs-lookup"><span data-stu-id="5cff3-110">A very low network assessment value suggests that Microsoft 365 clients will have significant problems connecting to the tenant or maintaining a responsive user experience, while a high value indicates a properly configured network with few ongoing performance issues.</span></span> <span data-ttu-id="5cff3-111">80% 的值表示一个正常的基准，即您不应预期收到有关 Microsoft 365 连接或由于网络性能导致的响应的定期用户意见。</span><span class="sxs-lookup"><span data-stu-id="5cff3-111">A value of 80% represents a healthy baseline where you should not expect to receive regular user complaints about Microsoft 365 connectivity or responsiveness due to network performance.</span></span> <span data-ttu-id="5cff3-112">由于进行了重复的网络连接改进，因此此值将随用户体验的增加而增加。</span><span class="sxs-lookup"><span data-stu-id="5cff3-112">As iterative network connectivity improvements are made, this value will increase along with user experience.</span></span>

| <span data-ttu-id="5cff3-113">网络评估</span><span class="sxs-lookup"><span data-stu-id="5cff3-113">Network assessment</span></span> | <span data-ttu-id="5cff3-114">预期的用户体验</span><span class="sxs-lookup"><span data-stu-id="5cff3-114">Expected user experience</span></span> |
| :----------------- | :----------------------- |
| <span data-ttu-id="5cff3-115">100</span><span class="sxs-lookup"><span data-stu-id="5cff3-115">100</span></span>                | <span data-ttu-id="5cff3-116">最好</span><span class="sxs-lookup"><span data-stu-id="5cff3-116">Best</span></span>                     |
| <span data-ttu-id="5cff3-117">80</span><span class="sxs-lookup"><span data-stu-id="5cff3-117">80</span></span>                 | <span data-ttu-id="5cff3-118">满足建议</span><span class="sxs-lookup"><span data-stu-id="5cff3-118">Meets recommendations</span></span>    |
| <span data-ttu-id="5cff3-119">60</span><span class="sxs-lookup"><span data-stu-id="5cff3-119">60</span></span>                 | <span data-ttu-id="5cff3-120">可以接受</span><span class="sxs-lookup"><span data-stu-id="5cff3-120">Acceptable</span></span>               |
| <span data-ttu-id="5cff3-121">40</span><span class="sxs-lookup"><span data-stu-id="5cff3-121">40</span></span>                 | <span data-ttu-id="5cff3-122">用户可能会遇到问题</span><span class="sxs-lookup"><span data-stu-id="5cff3-122">Users may experience issues</span></span> |
| <span data-ttu-id="5cff3-123">20</span><span class="sxs-lookup"><span data-stu-id="5cff3-123">20</span></span>                 | <span data-ttu-id="5cff3-124">用户可能会抱怨</span><span class="sxs-lookup"><span data-stu-id="5cff3-124">Users may complain</span></span>       |
| <span data-ttu-id="5cff3-125">0</span><span class="sxs-lookup"><span data-stu-id="5cff3-125">0</span></span>                  | <span data-ttu-id="5cff3-126">网络问题讨论的常见主题</span><span class="sxs-lookup"><span data-stu-id="5cff3-126">Network problems a common topic of discussion</span></span> |

>[!IMPORTANT]
><span data-ttu-id="5cff3-127">网络洞察力、Microsoft 365 管理中心中的性能建议和评估当前处于预览状态，并且仅适用于已在功能预览计划中注册的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="5cff3-127">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="network-assessment-panel"></a><span data-ttu-id="5cff3-128">网络评估面板</span><span class="sxs-lookup"><span data-stu-id="5cff3-128">Network assessment panel</span></span>

<span data-ttu-id="5cff3-129">每个网络评估（无论是属于租户还是特定办公室位置）都将显示一个面板，其中包含有关评估的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5cff3-129">Each network assessment, whether scoped to the tenant or to a specific office location, shows a panel with details about the assessment.</span></span> <span data-ttu-id="5cff3-130">此面板显示评估的条形图，以百分比表示，并作为每个组件工作负荷的总积分，包括仅收到度量数据的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="5cff3-130">This panel shows a bar chart of the assessment both as a percentage and as the total points for each component workload including only workloads where measurement data was received.</span></span> <span data-ttu-id="5cff3-131">对于 "办公室位置网络评估"，我们还将显示与 quintiles 中的每五个中的 Microsoft 365 客户的百分比相比较，报告与您的办公室位置相同的城市内的数据。</span><span class="sxs-lookup"><span data-stu-id="5cff3-131">For an office location network assessment, we also show a comparison to the percent of Microsoft 365 customers in each of five quintiles that reported data in the same city as your office location.</span></span>

![示例网络评估值](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

<span data-ttu-id="5cff3-133">面板中的 **评估细目** 显示了每个组件工作负荷的评估。</span><span class="sxs-lookup"><span data-stu-id="5cff3-133">The **Assessment breakdown** in the panel shows the assessment for each of the component workloads.</span></span>

<span data-ttu-id="5cff3-134">**评估历史记录**显示了最近30天的评估和基准。</span><span class="sxs-lookup"><span data-stu-id="5cff3-134">The **Assessment history** shows the past 30 days of the assessment and the benchmark.</span></span> <span data-ttu-id="5cff3-135">您还可以使用 "历史记录" 选项卡报告最长为两年的任意办公地点的指标历史记录。通过 "历史记录" 选项卡，可以选择要报告的属性，并选择报告时间范围可以突出显示网络更新项目的影响，并查看对网络评估的改进。</span><span class="sxs-lookup"><span data-stu-id="5cff3-135">You can also report on the metrics history for any office location for up to two years using the history tab. The history tab allows you to select your attributes to report on and by choosing a report timeframe you can highlight the impact of a network update project and see the improvement to your network assessment.</span></span>

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a><span data-ttu-id="5cff3-136">租户网络评估和 office 位置网络评估</span><span class="sxs-lookup"><span data-stu-id="5cff3-136">Tenant network assessments and office location network assessments</span></span>

<span data-ttu-id="5cff3-137">网络评估可衡量办公室的网络外围位置到 Microsoft 网络的设计。</span><span class="sxs-lookup"><span data-stu-id="5cff3-137">A network assessment measures the design of the network perimeter of an office location to Microsoft's network.</span></span> <span data-ttu-id="5cff3-138">最好在每个办公室位置对网络周边进行改进。</span><span class="sxs-lookup"><span data-stu-id="5cff3-138">Improvements to the network perimeter is best done at each office location.</span></span>

<span data-ttu-id="5cff3-139">我们在网络性能概述页面上显示了整个 Microsoft 365 租户的网络评估值，这是所有办公地点的网络评估的加权平均值。</span><span class="sxs-lookup"><span data-stu-id="5cff3-139">We show a network assessment value for the whole Microsoft 365 tenant on the network performance overview page which is a weighted average of the network assessments for all office locations.</span></span> <span data-ttu-id="5cff3-140">在该位置的 "摘要" 页上，每个检测到的 office 位置也有一个特定的网络评估值。</span><span class="sxs-lookup"><span data-stu-id="5cff3-140">There is also a specific network assessment value for each detected office location on that location's summary page.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="5cff3-141">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5cff3-141">Exchange Online</span></span>

<span data-ttu-id="5cff3-142">对于 Exchange Online，测量来自客户端计算机到 Exchange 服务前向的 TCP 延迟。</span><span class="sxs-lookup"><span data-stu-id="5cff3-142">For Exchange Online the TCP latency from the client machine to the Exchange service front door is measured.</span></span> <span data-ttu-id="5cff3-143">这可能会受到网络通过客户 LAN 和 WAN 传输的距离的影响。</span><span class="sxs-lookup"><span data-stu-id="5cff3-143">This can be impacted by the distance the network travels over the customers LAN and WAN.</span></span> <span data-ttu-id="5cff3-144">它还可能受到网络中间设备或服务的影响，这些服务会延迟连接或导致发送数据包。</span><span class="sxs-lookup"><span data-stu-id="5cff3-144">It can also be impacted by network intermediary devices or services which delay the connectivity or cause packets to be resent.</span></span> <span data-ttu-id="5cff3-145">并受最近的 Exchange 服务前盖的距离的影响。</span><span class="sxs-lookup"><span data-stu-id="5cff3-145">And it is impacted by how far away the nearest Exchange service front door is.</span></span> <span data-ttu-id="5cff3-146">中间 (也称为第50个百分点值或 P50 度量值) 在前三天的所有度量值中采用。</span><span class="sxs-lookup"><span data-stu-id="5cff3-146">The median (also known as the 50th percentile or P50 measure) is taken for all measurements over the previous three days.</span></span>

<span data-ttu-id="5cff3-147">将使用下表进行 Exchange Online 评估。</span><span class="sxs-lookup"><span data-stu-id="5cff3-147">The Exchange Online assessment is made using the following table.</span></span> <span data-ttu-id="5cff3-148">阈值之间的任何 TCP 延迟数均以线性方式在频带内分配点。</span><span class="sxs-lookup"><span data-stu-id="5cff3-148">Any TCP latency number between the thresholds are assigned points linearly within the band.</span></span>

| <span data-ttu-id="5cff3-149">TCP 延迟</span><span class="sxs-lookup"><span data-stu-id="5cff3-149">TCP Latency</span></span>   | <span data-ttu-id="5cff3-150">Points</span><span class="sxs-lookup"><span data-stu-id="5cff3-150">Points</span></span> |
| :------------ | :----- |
| <span data-ttu-id="5cff3-151">10ms 或更低</span><span class="sxs-lookup"><span data-stu-id="5cff3-151">10ms or less</span></span>  | <span data-ttu-id="5cff3-152">100</span><span class="sxs-lookup"><span data-stu-id="5cff3-152">100</span></span>    |
| <span data-ttu-id="5cff3-153">25ms</span><span class="sxs-lookup"><span data-stu-id="5cff3-153">25ms</span></span>          | <span data-ttu-id="5cff3-154">80</span><span class="sxs-lookup"><span data-stu-id="5cff3-154">80</span></span>     |
| <span data-ttu-id="5cff3-155">100毫秒</span><span class="sxs-lookup"><span data-stu-id="5cff3-155">100ms</span></span>         | <span data-ttu-id="5cff3-156">60</span><span class="sxs-lookup"><span data-stu-id="5cff3-156">60</span></span>     |
| <span data-ttu-id="5cff3-157">200ms</span><span class="sxs-lookup"><span data-stu-id="5cff3-157">200ms</span></span>         | <span data-ttu-id="5cff3-158">40</span><span class="sxs-lookup"><span data-stu-id="5cff3-158">40</span></span>     |
| <span data-ttu-id="5cff3-159">300ms</span><span class="sxs-lookup"><span data-stu-id="5cff3-159">300ms</span></span>         | <span data-ttu-id="5cff3-160">20</span><span class="sxs-lookup"><span data-stu-id="5cff3-160">20</span></span>     |
| <span data-ttu-id="5cff3-161">350ms 或更多</span><span class="sxs-lookup"><span data-stu-id="5cff3-161">350ms or more</span></span> | <span data-ttu-id="5cff3-162">0</span><span class="sxs-lookup"><span data-stu-id="5cff3-162">0</span></span>      |

## <a name="sharepoint-online"></a><span data-ttu-id="5cff3-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5cff3-163">SharePoint Online</span></span>

<span data-ttu-id="5cff3-164">对于 SharePoint Online，可供用户从 SharePoint 或 OneDrive 访问文档的下载速度进行度量。</span><span class="sxs-lookup"><span data-stu-id="5cff3-164">For SharePoint Online the download speed available for a user to access a document from SharePoint or OneDrive is measured.</span></span> <span data-ttu-id="5cff3-165">这可能受客户端计算机和 Microsoft 网络之间网络线路上的可用带宽的影响。</span><span class="sxs-lookup"><span data-stu-id="5cff3-165">This can be impacted by the bandwidth available on network circuits between the client machine and Microsoft's network.</span></span> <span data-ttu-id="5cff3-166">通常，在复杂网络设备的瓶颈或较差的 Wlan 区域中存在的网络拥塞也会受到影响。</span><span class="sxs-lookup"><span data-stu-id="5cff3-166">It is also often impacted by network congestion that exists in bottlenecks in complex network devices or in poor coverage Wi-Fi areas.</span></span> <span data-ttu-id="5cff3-167">下载速度以每秒兆字节数度量，每秒大约为每秒额定的电路10秒。</span><span class="sxs-lookup"><span data-stu-id="5cff3-167">The download speed is measured in megabytes per second which is approximately one tenth of a circuits rated megabits per second.</span></span> <span data-ttu-id="5cff3-168">每秒的兆字节数很有用，因为您可以直接在1秒内看到可以下载的大小文件。</span><span class="sxs-lookup"><span data-stu-id="5cff3-168">The MegaByte per second unit is helpful because you can directly see what size file can be downloaded in 1 second.</span></span> <span data-ttu-id="5cff3-169">第25个百分点 (也称为 "P25" 度量值，) 在前三天的所有度量中采用。</span><span class="sxs-lookup"><span data-stu-id="5cff3-169">The 25th percentile (also known as the P25 measure) is taken for all measurements over the previous three days.</span></span> <span data-ttu-id="5cff3-170">第25个百分点值有助于降低随着时间的推移不同拥塞的影响。</span><span class="sxs-lookup"><span data-stu-id="5cff3-170">This 25th percentile helps reduce the impact of varying congestion over time.</span></span>

<span data-ttu-id="5cff3-171">使用下表进行 SharePoint Online 评估。</span><span class="sxs-lookup"><span data-stu-id="5cff3-171">The SharePoint Online assessment is made using the following table.</span></span> <span data-ttu-id="5cff3-172">阈值之间的任何下载速度编号都在频带中线性分配点。</span><span class="sxs-lookup"><span data-stu-id="5cff3-172">Any download speed number between the thresholds are assigned points linearly within the band.</span></span>

| <span data-ttu-id="5cff3-173">下载速度</span><span class="sxs-lookup"><span data-stu-id="5cff3-173">Download speed</span></span> | <span data-ttu-id="5cff3-174">Points</span><span class="sxs-lookup"><span data-stu-id="5cff3-174">Points</span></span> |
| :------------- | :----- |
| <span data-ttu-id="5cff3-175">20MBps 或更多</span><span class="sxs-lookup"><span data-stu-id="5cff3-175">20MBps or more</span></span> | <span data-ttu-id="5cff3-176">100</span><span class="sxs-lookup"><span data-stu-id="5cff3-176">100</span></span>    |
| <span data-ttu-id="5cff3-177">14MBps</span><span class="sxs-lookup"><span data-stu-id="5cff3-177">14MBps</span></span>         | <span data-ttu-id="5cff3-178">80</span><span class="sxs-lookup"><span data-stu-id="5cff3-178">80</span></span>     |
| <span data-ttu-id="5cff3-179">8MBps</span><span class="sxs-lookup"><span data-stu-id="5cff3-179">8MBps</span></span>          | <span data-ttu-id="5cff3-180">60</span><span class="sxs-lookup"><span data-stu-id="5cff3-180">60</span></span>     |
| <span data-ttu-id="5cff3-181">4MBps</span><span class="sxs-lookup"><span data-stu-id="5cff3-181">4MBps</span></span>          | <span data-ttu-id="5cff3-182">40</span><span class="sxs-lookup"><span data-stu-id="5cff3-182">40</span></span>     |
| <span data-ttu-id="5cff3-183">2MBps</span><span class="sxs-lookup"><span data-stu-id="5cff3-183">2MBps</span></span>          | <span data-ttu-id="5cff3-184">20</span><span class="sxs-lookup"><span data-stu-id="5cff3-184">20</span></span>     |
| <span data-ttu-id="5cff3-185">0MBps</span><span class="sxs-lookup"><span data-stu-id="5cff3-185">0MBps</span></span>          | <span data-ttu-id="5cff3-186">0</span><span class="sxs-lookup"><span data-stu-id="5cff3-186">0</span></span>      |

## <a name="microsoft-teams"></a><span data-ttu-id="5cff3-187">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5cff3-187">Microsoft Teams</span></span>

<span data-ttu-id="5cff3-188">对于 Microsoft 团队，网络质量是指 UDP 延迟、UDP 抖动和 UDP 数据包丢失。</span><span class="sxs-lookup"><span data-stu-id="5cff3-188">For Microsoft Teams the Network quality is measured as UDP latency, UDP jitter, and UDP packet loss.</span></span> <span data-ttu-id="5cff3-189">UDP 可用于 Microsoft 团队的呼叫和会议音频和视频媒体连接。</span><span class="sxs-lookup"><span data-stu-id="5cff3-189">UDP is used for call and conferencing audio and video media connectivity for Microsoft Teams.</span></span> <span data-ttu-id="5cff3-190">这可能受到与延迟和下载速度相同的因素的影响，除了网络的 UDP 支持中的连接间隙之外，因为 UDP 是分别配置为更常见的 TCP 协议。</span><span class="sxs-lookup"><span data-stu-id="5cff3-190">This can be impacted by the same factors as for latency and download speed in addition to connectivity gaps in a network's UDP support since UDP is configured separately to the more common TCP protocol.</span></span> <span data-ttu-id="5cff3-191">中间 (也称为第50个百分点值或 P50 度量值) 在前三天的所有度量值中采用。</span><span class="sxs-lookup"><span data-stu-id="5cff3-191">The median (also known as the 50th percentile or P50 measure) is taken for all measurements over the previous three days.</span></span> 

<span data-ttu-id="5cff3-192">我们根据从1到5的比例计算来自这些 UDP 度量值的平均意见得分。</span><span class="sxs-lookup"><span data-stu-id="5cff3-192">We calculate a mean opinion score from these UDP measurements for a scale from one to five.</span></span> <span data-ttu-id="5cff3-193">然后，我们将其映射到 Microsoft 团队网络评估的0-100 点刻度。</span><span class="sxs-lookup"><span data-stu-id="5cff3-193">Then we map that to the 0-100 points scale for the Microsoft Teams network assessment.</span></span>  <span data-ttu-id="5cff3-194">总体正常大于87.5 点，总体差低于50磅。</span><span class="sxs-lookup"><span data-stu-id="5cff3-194">Overall good is over 87.5 points and overall bad is below 50 points.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5cff3-195">相关主题</span><span class="sxs-lookup"><span data-stu-id="5cff3-195">Related topics</span></span>

[<span data-ttu-id="5cff3-196">Microsoft 365 管理中心中的网络连接 (预览版) </span><span class="sxs-lookup"><span data-stu-id="5cff3-196">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="5cff3-197">Microsoft 365 网络性能见解 (预览版) </span><span class="sxs-lookup"><span data-stu-id="5cff3-197">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="5cff3-198">M365 管理中心中的 Microsoft 365 连接测试 (preview) </span><span class="sxs-lookup"><span data-stu-id="5cff3-198">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="5cff3-199">Microsoft 365 网络连接位置服务 (预览) </span><span class="sxs-lookup"><span data-stu-id="5cff3-199">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)

[<span data-ttu-id="5cff3-200">Microsoft 365 网络连接测试工具 (预览) </span><span class="sxs-lookup"><span data-stu-id="5cff3-200">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
