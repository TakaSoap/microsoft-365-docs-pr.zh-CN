---
title: 使用适用于终结点威胁分析的 Microsoft Defender 跟踪和响应新出现的威胁
ms.reviewer: ''
description: 了解新出现的威胁和攻击技术以及如何阻止它们。 评估其对组织的影响，并评估组织的恢复能力。
keywords: 威胁分析， 风险评估， 操作系统缓解， 微代码缓解， 缓解状态
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 63303f9eacd25a8de1c7154ac66c73578bfd495a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924451"
---
# <a name="track-and-respond-to-emerging-threats-through-threat-analytics"></a><span data-ttu-id="dd9b0-105">通过威胁分析跟踪和响应新出现的威胁</span><span class="sxs-lookup"><span data-stu-id="dd9b0-105">Track and respond to emerging threats through threat analytics</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dd9b0-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="dd9b0-106">**Applies to:**</span></span>
- [<span data-ttu-id="dd9b0-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dd9b0-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="dd9b0-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd9b0-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dd9b0-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="dd9b0-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dd9b0-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="dd9b0-111">随着更复杂的对手和新威胁的频繁和普遍出现，必须能够快速：</span><span class="sxs-lookup"><span data-stu-id="dd9b0-111">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="dd9b0-112">评估新威胁的影响</span><span class="sxs-lookup"><span data-stu-id="dd9b0-112">Assess the impact of new threats</span></span>
- <span data-ttu-id="dd9b0-113">查看抵御威胁或暴露给威胁的恢复能力</span><span class="sxs-lookup"><span data-stu-id="dd9b0-113">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="dd9b0-114">确定可以采取的停止或包含威胁的操作</span><span class="sxs-lookup"><span data-stu-id="dd9b0-114">Identify the actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="dd9b0-115">威胁分析是一组来自专业 Microsoft 安全研究人员的报告，涉及最相关的威胁，包括：</span><span class="sxs-lookup"><span data-stu-id="dd9b0-115">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats, including:</span></span>

- <span data-ttu-id="dd9b0-116">活动威胁参与者及其活动</span><span class="sxs-lookup"><span data-stu-id="dd9b0-116">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="dd9b0-117">热门和新的攻击技术</span><span class="sxs-lookup"><span data-stu-id="dd9b0-117">Popular and new attack techniques</span></span>
- <span data-ttu-id="dd9b0-118">关键漏洞</span><span class="sxs-lookup"><span data-stu-id="dd9b0-118">Critical vulnerabilities</span></span>
- <span data-ttu-id="dd9b0-119">常见的攻击面</span><span class="sxs-lookup"><span data-stu-id="dd9b0-119">Common attack surfaces</span></span>
- <span data-ttu-id="dd9b0-120">流行恶意软件</span><span class="sxs-lookup"><span data-stu-id="dd9b0-120">Prevalent malware</span></span>

<span data-ttu-id="dd9b0-121">每个报告都提供威胁的详细分析和有关如何防御该威胁的广泛指导。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-121">Each report provides a detailed analysis of a threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="dd9b0-122">它还包含来自你的网络的数据，指示威胁是否处于活动状态以及是否具有适用的保护。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-122">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

<span data-ttu-id="dd9b0-123">观看此简短视频，详细了解威胁分析如何有助于跟踪和阻止最新威胁。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-123">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="dd9b0-124">查看威胁分析仪表板</span><span class="sxs-lookup"><span data-stu-id="dd9b0-124">View the threat analytics dashboard</span></span>

<span data-ttu-id="dd9b0-125">威胁分析仪表板是获取与组织最相关的报告的主要起点。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-125">The threat analytics dashboard is a great jump off point for getting to the reports that are most relevant to your organization.</span></span> <span data-ttu-id="dd9b0-126">它总结了以下各节中的威胁：</span><span class="sxs-lookup"><span data-stu-id="dd9b0-126">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="dd9b0-127">**最新** 威胁 — 列出最新发布的威胁报告，以及具有活动警报和已解决警报的设备数量。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-127">**Latest threats**—lists the most recently published threat reports, along with the number of devices with active and resolved alerts.</span></span>
- <span data-ttu-id="dd9b0-128">**高影响** 威胁 — 列出对组织影响最大的威胁。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-128">**High-impact threats**—lists the threats that have had the highest impact to the organization.</span></span> <span data-ttu-id="dd9b0-129">本部分按具有活动警报的设备数量对威胁进行排名。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-129">This section ranks threats by the number of devices that have active alerts.</span></span>
- <span data-ttu-id="dd9b0-130">**威胁摘要** 通过显示具有活动警报和已解决警报的威胁数来显示跟踪的威胁的总体影响。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-130">**Threat summary**—shows the overall impact of tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="dd9b0-131">从仪表板中选择威胁以查看该威胁的报告。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-131">Select a threat from the dashboard to view the report for that threat.</span></span>

![威胁分析仪表板的图像](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="dd9b0-133">查看威胁分析报告</span><span class="sxs-lookup"><span data-stu-id="dd9b0-133">View a threat analytics report</span></span>

<span data-ttu-id="dd9b0-134">每个威胁分析报告提供三个部分的信息： **概述**、分析 **员报告** 和 **缓解**。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-134">Each threat analytics report provides information in three sections: **Overview**, **Analyst report**, and **Mitigations**.</span></span>

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="dd9b0-135">概述：快速了解威胁、评估其影响并审查防御</span><span class="sxs-lookup"><span data-stu-id="dd9b0-135">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="dd9b0-136">" **概述** "部分提供详细分析员报告的预览。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-136">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="dd9b0-137">它还提供了突出显示威胁对组织的影响以及通过错误配置和未修补的设备暴露的图表。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-137">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

<span data-ttu-id="dd9b0-138">![威胁分析报告概述部分的图像 ](images/ta-overview.png)
 </span><span class="sxs-lookup"><span data-stu-id="dd9b0-138">![Image of the overview section of a threat analytics report](images/ta-overview.png)
_Overview section of a threat analytics report_</span></span>

#### <a name="assess-the-impact-to-your-organization"></a><span data-ttu-id="dd9b0-139">评估对组织的影响</span><span class="sxs-lookup"><span data-stu-id="dd9b0-139">Assess the impact to your organization</span></span>
<span data-ttu-id="dd9b0-140">每个报告都包括旨在提供有关威胁的组织影响的图表：</span><span class="sxs-lookup"><span data-stu-id="dd9b0-140">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="dd9b0-141">**具有警报的设备**— 显示受威胁影响的当前不同设备的数量。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-141">**Devices with alerts**—shows the current number of distinct devices that have been impacted by the threat.</span></span> <span data-ttu-id="dd9b0-142">如果至少有一个警报与该威胁关联，则设备分类为"活动";如果与设备上的威胁关联的所有警报已解决，则将其分类为"已解决"。 </span><span class="sxs-lookup"><span data-stu-id="dd9b0-142">A device is categorized as **Active** if there is at least one alert associated with that threat and **Resolved** if *all* alerts associated with the threat on the device have been resolved.</span></span>
- <span data-ttu-id="dd9b0-143">**具有随着时间的警报的设备**- 显示随着时间的推移具有 **活动** 和已解决 **警报的不同** 设备的数量。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-143">**Devices with alerts over time**—shows the number of distinct devices with **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="dd9b0-144">已解决的警报数指示组织响应与威胁关联的警报的有多快。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-144">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="dd9b0-145">理想情况下，图表应显示几天内解决的警报。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-145">Ideally, the chart should be showing alerts resolved within a few days.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="dd9b0-146">查看安全恢复和状态</span><span class="sxs-lookup"><span data-stu-id="dd9b0-146">Review security resilience and posture</span></span>
<span data-ttu-id="dd9b0-147">每个报告都包括一些图表，这些图表概述了组织对给定威胁的复原能力：</span><span class="sxs-lookup"><span data-stu-id="dd9b0-147">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="dd9b0-148">**安全配置** 状态 — 显示已应用有助于缓解威胁的建议安全设置的设备数量。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-148">**Security configuration status**—shows the number of devices that have applied the recommended security settings that can help mitigate the threat.</span></span> <span data-ttu-id="dd9b0-149">如果设备已 **应用** 所有跟踪 _设置，则_ 被视为安全设备。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-149">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="dd9b0-150">**漏洞修补状态**— 显示已应用安全更新或修补程序以解决威胁所利用漏洞的设备数量。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-150">**Vulnerability patching status**—shows the number of devices that have applied security updates or patches that address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="dd9b0-151">分析员报告：从 Microsoft 安全研究人员获取专家见解</span><span class="sxs-lookup"><span data-stu-id="dd9b0-151">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="dd9b0-152">转到" **分析员报告** "部分，阅读详细的专家撰写。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-152">Go to the **Analyst report** section to read through the detailed expert write-up.</span></span> <span data-ttu-id="dd9b0-153">大多数报告都提供攻击链的详细说明，包括映射到 MITRE ATT&CK 框架的策略和技术、详细的建议列表和强大的 [威胁](advanced-hunting-overview.md) 搜寻指南。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-153">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="dd9b0-154">详细了解分析员报告</span><span class="sxs-lookup"><span data-stu-id="dd9b0-154">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="dd9b0-155">缓解：查看缓解列表和设备的状态</span><span class="sxs-lookup"><span data-stu-id="dd9b0-155">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="dd9b0-156">在 **"缓解"** 部分，查看特定可操作建议的列表，这些建议可帮助你提高组织应对威胁的复原能力。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-156">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="dd9b0-157">跟踪的缓解列表包括：</span><span class="sxs-lookup"><span data-stu-id="dd9b0-157">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="dd9b0-158">**安全更新**- 部署安全更新程序或漏洞修补程序</span><span class="sxs-lookup"><span data-stu-id="dd9b0-158">**Security updates**—deployment of security updates or patches for vulnerabilities</span></span>
- <span data-ttu-id="dd9b0-159">**Microsoft Defender 防病毒设置**</span><span class="sxs-lookup"><span data-stu-id="dd9b0-159">**Microsoft Defender Antivirus settings**</span></span>
  - <span data-ttu-id="dd9b0-160">安全智能版本</span><span class="sxs-lookup"><span data-stu-id="dd9b0-160">Security intelligence version</span></span>
  - <span data-ttu-id="dd9b0-161">云端保护</span><span class="sxs-lookup"><span data-stu-id="dd9b0-161">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="dd9b0-162">PUA 保护 (可能不需要) 应用程序</span><span class="sxs-lookup"><span data-stu-id="dd9b0-162">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="dd9b0-163">实时保护</span><span class="sxs-lookup"><span data-stu-id="dd9b0-163">Real-time protection</span></span>
 
<span data-ttu-id="dd9b0-164">本节中的缓解信息包含来自 危险和漏洞管理[](next-gen-threat-and-vuln-mgt.md)的数据，它还提供报告中各个链接的详细深化信息。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-164">Mitigation information in this section incorporates data from [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="dd9b0-165">![威胁分析报告缓解部分的威胁分析报告 ](images/ta-mitigations.png)
 _缓解部分的图像_</span><span class="sxs-lookup"><span data-stu-id="dd9b0-165">![Image of the mitigations section of a threat analytics report](images/ta-mitigations.png)
_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="dd9b0-166">其他报告详细信息和限制</span><span class="sxs-lookup"><span data-stu-id="dd9b0-166">Additional report details and limitations</span></span>
<span data-ttu-id="dd9b0-167">使用报告时，请牢记以下事项：</span><span class="sxs-lookup"><span data-stu-id="dd9b0-167">When using the reports, keep the following in mind:</span></span> 

- <span data-ttu-id="dd9b0-168">数据的范围基于基于角色的访问控制 (RBAC) 作用域。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-168">Data is scoped based on your role-based access control (RBAC) scope.</span></span> <span data-ttu-id="dd9b0-169">你将看到可以访问 的组中 [设备的状态](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-169">You will see the status of devices in [groups that you can access](machine-groups.md).</span></span>
- <span data-ttu-id="dd9b0-170">图表仅反映跟踪的缓解。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-170">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="dd9b0-171">查看报告概述，了解图表中未显示的其他缓解功能。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-171">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="dd9b0-172">缓解不保证完全恢复。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-172">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="dd9b0-173">提供的缓解反映了改进恢复能力所需的最佳可能操作。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-173">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="dd9b0-174">如果设备尚未将数据传输到服务，则被视为"不可用"。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-174">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="dd9b0-175">防病毒相关的统计信息基于Microsoft Defender 防病毒设置。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-175">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="dd9b0-176">具有第三方防病毒解决方案的设备可能显示为"公开"。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-176">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="dd9b0-177">相关主题</span><span class="sxs-lookup"><span data-stu-id="dd9b0-177">Related topics</span></span>
- [<span data-ttu-id="dd9b0-178">使用高级搜寻主动查找威胁</span><span class="sxs-lookup"><span data-stu-id="dd9b0-178">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="dd9b0-179">了解分析员报告部分</span><span class="sxs-lookup"><span data-stu-id="dd9b0-179">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="dd9b0-180">评估和解决安全漏洞和曝光</span><span class="sxs-lookup"><span data-stu-id="dd9b0-180">Assess and resolve security weaknesses and exposures</span></span>](next-gen-threat-and-vuln-mgt.md)
