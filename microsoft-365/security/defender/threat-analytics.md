---
title: 使用威胁分析跟踪和响应新出现的威胁
ms.reviewer: ''
description: 了解新出现的威胁和攻击技术以及如何阻止它们。 评估其对组织的影响，并评估组织的恢复能力。
keywords: 威胁分析， 风险评估， Microsoft 365 Defender， M365D， 缓解状态， 安全配置， Microsoft Defender for Office 365， Microsoft Defender for Office 365 威胁分析， MDO 威胁分析， 集成 MDE 和 MDO 威胁分析数据， 威胁分析数据集成， 集成 Microsoft 365 Defender 威胁分析
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d07a7210b8426349f18a2305069c4ed0a08ce660
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096826"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="5bf21-105">使用威胁分析跟踪和响应新出现的威胁</span><span class="sxs-lookup"><span data-stu-id="5bf21-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5bf21-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5bf21-106">**Applies to:**</span></span>
- <span data-ttu-id="5bf21-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5bf21-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="5bf21-108">希望体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="5bf21-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="5bf21-109">你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="5bf21-109">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]


<span data-ttu-id="5bf21-110">威胁分析是我们来自专业 Microsoft 安全研究人员的产品内威胁情报解决方案，旨在帮助安全团队尽可能高效地应对新出现的威胁，包括：</span><span class="sxs-lookup"><span data-stu-id="5bf21-110">Threat analytics is our in-product threat intelligence solution from expert Microsoft security researchers, designed to assist security teams to be as efficient as possible while facing emerging threats, including:</span></span>

- <span data-ttu-id="5bf21-111">活动威胁参与者及其活动</span><span class="sxs-lookup"><span data-stu-id="5bf21-111">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="5bf21-112">热门和新的攻击技术</span><span class="sxs-lookup"><span data-stu-id="5bf21-112">Popular and new attack techniques</span></span>
- <span data-ttu-id="5bf21-113">关键漏洞</span><span class="sxs-lookup"><span data-stu-id="5bf21-113">Critical vulnerabilities</span></span>
- <span data-ttu-id="5bf21-114">常见的攻击面</span><span class="sxs-lookup"><span data-stu-id="5bf21-114">Common attack surfaces</span></span>
- <span data-ttu-id="5bf21-115">流行恶意软件</span><span class="sxs-lookup"><span data-stu-id="5bf21-115">Prevalent malware</span></span>

<span data-ttu-id="5bf21-116">观看此简短视频，详细了解威胁分析如何有助于跟踪和阻止最新威胁。</span><span class="sxs-lookup"><span data-stu-id="5bf21-116">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

<span data-ttu-id="5bf21-117">你可以从 Microsoft 365 安全门户导航栏的左上角访问威胁分析，也可以从显示组织中的主要威胁的专用仪表板卡访问威胁分析。了解活动或正在进行的市场活动，了解通过威胁分析可采取哪些措施，有助于让安全运营团队做出明智的决策。</span><span class="sxs-lookup"><span data-stu-id="5bf21-117">You can access threat analytics either from the upper left-hand side of Microsoft 365 security portal’s navigation bar, or from a dedicated dashboard card which shows the top threats in your org. Getting visibility on active or ongoing campaigns and knowing what to do through threat analytics can help equip your security operations team with informed decisions.</span></span> 

![威胁分析仪表板的图像](../../media/threat-analytics/ta_inlandingpage_mtp.png)

<span data-ttu-id="5bf21-119">_在何处访问威胁分析_</span><span class="sxs-lookup"><span data-stu-id="5bf21-119">_Where to access threat analytics_</span></span>

<span data-ttu-id="5bf21-120">随着更复杂的对手和新威胁的频繁和普遍出现，必须能够快速：</span><span class="sxs-lookup"><span data-stu-id="5bf21-120">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="5bf21-121">识别并应对新出现的威胁</span><span class="sxs-lookup"><span data-stu-id="5bf21-121">Identify and react to emerging threats</span></span> 
- <span data-ttu-id="5bf21-122">了解你当前是否受到攻击</span><span class="sxs-lookup"><span data-stu-id="5bf21-122">Learn if you are currently under attack</span></span>
- <span data-ttu-id="5bf21-123">评估威胁对资产的影响</span><span class="sxs-lookup"><span data-stu-id="5bf21-123">Assess the impact of the threat to your assets</span></span>
- <span data-ttu-id="5bf21-124">查看抵御威胁或暴露给威胁的恢复能力</span><span class="sxs-lookup"><span data-stu-id="5bf21-124">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="5bf21-125">确定可用于停止或包含威胁的缓解、恢复或防护操作</span><span class="sxs-lookup"><span data-stu-id="5bf21-125">Identify the mitigation, recovery, or prevention actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="5bf21-126">每个报告都提供跟踪威胁的分析，并提供有关如何防御该威胁的广泛指导。</span><span class="sxs-lookup"><span data-stu-id="5bf21-126">Each report provides an analysis of a tracked threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="5bf21-127">它还包含来自你的网络的数据，指示威胁是否处于活动状态以及是否具有适用的保护。</span><span class="sxs-lookup"><span data-stu-id="5bf21-127">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="5bf21-128">查看威胁分析仪表板</span><span class="sxs-lookup"><span data-stu-id="5bf21-128">View the threat analytics dashboard</span></span>

<span data-ttu-id="5bf21-129">威胁分析仪表板 (security.microsoft.com/threatanalytics3) 突出显示[](https://security.microsoft.com/threatanalytics3)与组织最相关的报告。</span><span class="sxs-lookup"><span data-stu-id="5bf21-129">The threat analytics dashboard ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) highlights the reports that are most relevant to your organization.</span></span> <span data-ttu-id="5bf21-130">它总结了以下各节中的威胁：</span><span class="sxs-lookup"><span data-stu-id="5bf21-130">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="5bf21-131">**最新威胁**— 列出最近发布或更新的威胁报告，以及活动警报和已解决警报的数量。</span><span class="sxs-lookup"><span data-stu-id="5bf21-131">**Latest threats**—lists the most recently published or updated threat reports, along with the number of active and resolved alerts.</span></span>
- <span data-ttu-id="5bf21-132">**高影响威胁**— 列出对组织影响最大的威胁。</span><span class="sxs-lookup"><span data-stu-id="5bf21-132">**High-impact threats**—lists the threats that have the highest impact to your organization.</span></span> <span data-ttu-id="5bf21-133">本节首先列出活动警报和已解决警报数最高的威胁。</span><span class="sxs-lookup"><span data-stu-id="5bf21-133">This section lists threats with the highest number of active and resolved alerts first.</span></span>
- <span data-ttu-id="5bf21-134">**威胁摘要**— 通过显示具有活动警报和已解决警报的威胁数，提供所有跟踪的威胁的总体影响。</span><span class="sxs-lookup"><span data-stu-id="5bf21-134">**Threat summary**—provides the overall impact of all tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="5bf21-135">从仪表板中选择威胁以查看该威胁的报告。</span><span class="sxs-lookup"><span data-stu-id="5bf21-135">Select a threat from the dashboard to view the report for that threat.</span></span>

![威胁分析仪表板的屏幕截图](../../media/threat-analytics/ta_dashboard_mtp.png)

<span data-ttu-id="5bf21-137">_威胁分析仪表板。还可以单击"搜索"图标，在与你要阅读的威胁分析报告相关的关键字中键。_</span><span class="sxs-lookup"><span data-stu-id="5bf21-137">_Threat analytics dashboard. You can also click the Search icon to key in a keyword related to the threat analytics report that you'd like to read._</span></span> 

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="5bf21-138">查看威胁分析报告</span><span class="sxs-lookup"><span data-stu-id="5bf21-138">View a threat analytics report</span></span>

<span data-ttu-id="5bf21-139">每个威胁分析报告分几节提供相关信息：</span><span class="sxs-lookup"><span data-stu-id="5bf21-139">Each threat analytics report provides information in several sections:</span></span> 

- [<span data-ttu-id="5bf21-140">**概述**</span><span class="sxs-lookup"><span data-stu-id="5bf21-140">**Overview**</span></span>](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses) 
- [<span data-ttu-id="5bf21-141">**分析员报告**</span><span class="sxs-lookup"><span data-stu-id="5bf21-141">**Analyst report**</span></span>](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [<span data-ttu-id="5bf21-142">**相关事件**</span><span class="sxs-lookup"><span data-stu-id="5bf21-142">**Related incidents**</span></span>](#related-incidents-view-and-manage-related-incidents)
- [<span data-ttu-id="5bf21-143">**影响的资产**</span><span class="sxs-lookup"><span data-stu-id="5bf21-143">**Impacted assets**</span></span>](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [<span data-ttu-id="5bf21-144">**阻止的电子邮件尝试**</span><span class="sxs-lookup"><span data-stu-id="5bf21-144">**Prevented email attempts**</span></span>](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [<span data-ttu-id="5bf21-145">**缓解**</span><span class="sxs-lookup"><span data-stu-id="5bf21-145">**Mitigations**</span></span>](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="5bf21-146">概述：快速了解威胁、评估其影响并审查防御</span><span class="sxs-lookup"><span data-stu-id="5bf21-146">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="5bf21-147">" **概述** "部分提供详细分析员报告的预览。</span><span class="sxs-lookup"><span data-stu-id="5bf21-147">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="5bf21-148">它还提供了突出显示威胁对组织的影响以及通过错误配置和未修补的设备暴露的图表。</span><span class="sxs-lookup"><span data-stu-id="5bf21-148">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

![威胁分析报告的概述部分的图像](../../media/threat-analytics/ta_overview_mtp.png)

<span data-ttu-id="5bf21-150">_威胁分析报告的概述部分_</span><span class="sxs-lookup"><span data-stu-id="5bf21-150">_Overview section of a threat analytics report_</span></span>

#### <a name="assess-impact-on-your-organization"></a><span data-ttu-id="5bf21-151">评估对组织的影响</span><span class="sxs-lookup"><span data-stu-id="5bf21-151">Assess impact on your organization</span></span>
<span data-ttu-id="5bf21-152">每个报告都包括旨在提供有关威胁的组织影响的图表：</span><span class="sxs-lookup"><span data-stu-id="5bf21-152">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="5bf21-153">**相关事件** 使用以下数据概述了跟踪的威胁对组织的影响：</span><span class="sxs-lookup"><span data-stu-id="5bf21-153">**Related incidents**—provides an overview of the impact of the tracked threat to your organization with the following data:</span></span>
  - <span data-ttu-id="5bf21-154">活动警报数及其关联的活动事件数</span><span class="sxs-lookup"><span data-stu-id="5bf21-154">Number of active alerts and the number of active incidents they are associated with</span></span>
  - <span data-ttu-id="5bf21-155">活动事件的严重性</span><span class="sxs-lookup"><span data-stu-id="5bf21-155">Severity of active incidents</span></span>
- <span data-ttu-id="5bf21-156">**一段时间的警报** 显示一段时间的相关 **活动\*\*\*\*警报和已** 解决警报数。</span><span class="sxs-lookup"><span data-stu-id="5bf21-156">**Alerts over time**—shows the number of related **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="5bf21-157">已解决的警报数指示组织响应与威胁关联的警报的有多快。</span><span class="sxs-lookup"><span data-stu-id="5bf21-157">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="5bf21-158">理想情况下，图表应显示几天内解决的警报。</span><span class="sxs-lookup"><span data-stu-id="5bf21-158">Ideally, the chart should be showing alerts resolved within a few days.</span></span>
- <span data-ttu-id="5bf21-159">**影响的资产**— 显示当前至少有一个活动警报 (跟踪威胁) 邮箱中不同设备和电子邮件帐户的数量。</span><span class="sxs-lookup"><span data-stu-id="5bf21-159">**Impacted assets**—shows the number of distinct devices and email accounts (mailboxes) that currently have at least one active alert associated with the tracked threat.</span></span> <span data-ttu-id="5bf21-160">对于收到威胁电子邮件的邮箱，将触发警报。</span><span class="sxs-lookup"><span data-stu-id="5bf21-160">Alerts are triggered for mailboxes that received threat emails.</span></span> <span data-ttu-id="5bf21-161">查看组织级别和用户级别的策略，查看导致发送威胁电子邮件的覆盖。</span><span class="sxs-lookup"><span data-stu-id="5bf21-161">Review both org- and user-level policies for overrides that cause the delivery of threat emails.</span></span>
- <span data-ttu-id="5bf21-162">**阻止的电子邮件尝试**— 显示过去七天内在传递前被阻止或传递到垃圾邮件文件夹的电子邮件数量。</span><span class="sxs-lookup"><span data-stu-id="5bf21-162">**Prevented email attempts**—shows the number of emails from the past seven days that were either blocked before delivery or delivered to the junk mail folder.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="5bf21-163">查看安全恢复和状态</span><span class="sxs-lookup"><span data-stu-id="5bf21-163">Review security resilience and posture</span></span>
<span data-ttu-id="5bf21-164">每个报告都包括一些图表，这些图表概述了组织对给定威胁的复原能力：</span><span class="sxs-lookup"><span data-stu-id="5bf21-164">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="5bf21-165">**安全配置** 状态 — 显示安全设置错误的设备数量。</span><span class="sxs-lookup"><span data-stu-id="5bf21-165">**Secure configuration status**—shows the number of devices with misconfigured security settings.</span></span> <span data-ttu-id="5bf21-166">应用建议的安全设置以帮助缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="5bf21-166">Apply the recommended security settings to help mitigate the threat.</span></span> <span data-ttu-id="5bf21-167">如果设备已 **应用** 所有跟踪 _设置，则_ 被视为安全设备。</span><span class="sxs-lookup"><span data-stu-id="5bf21-167">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="5bf21-168">**漏洞修补状态** 显示易受攻击的设备的数量。</span><span class="sxs-lookup"><span data-stu-id="5bf21-168">**Vulnerability patching status**—shows the number of vulnerable devices.</span></span> <span data-ttu-id="5bf21-169">应用安全更新或修补程序以解决威胁利用的漏洞。</span><span class="sxs-lookup"><span data-stu-id="5bf21-169">Apply security updates or patches to address vulnerabilities exploited by the threat.</span></span>

#### <a name="view-reports-per-threat-tags"></a><span data-ttu-id="5bf21-170">查看每个威胁标记的报告</span><span class="sxs-lookup"><span data-stu-id="5bf21-170">View reports per threat tags</span></span>
<span data-ttu-id="5bf21-171">你可以根据特定威胁标记或报告类型来筛选威胁报告列表 (相关) 报告。</span><span class="sxs-lookup"><span data-stu-id="5bf21-171">You can filter the threat report list and view the most relevant reports according to a specific threat tag (category) or a report type.</span></span> 
- <span data-ttu-id="5bf21-172">**威胁** 标记 — 帮助你根据特定威胁类别查看最相关的报告。</span><span class="sxs-lookup"><span data-stu-id="5bf21-172">**Threat tags**—assist you in viewing the most relevant reports according to a specific threat category.</span></span> <span data-ttu-id="5bf21-173">例如，所有与勒索软件相关的报告。</span><span class="sxs-lookup"><span data-stu-id="5bf21-173">For example, all reports related to ransomware.</span></span>
- <span data-ttu-id="5bf21-174">**报告** 类型 — 帮助您根据特定报告类型查看最相关的报告。</span><span class="sxs-lookup"><span data-stu-id="5bf21-174">**Report types**—assist you in viewing the most relevant reports according to a specific report type.</span></span> <span data-ttu-id="5bf21-175">例如，涵盖工具和技术的所有报告。</span><span class="sxs-lookup"><span data-stu-id="5bf21-175">For example, all reports that cover tools and techniques.</span></span> 
- <span data-ttu-id="5bf21-176">**筛选器**- 帮助你高效地查看威胁报告列表，并基于特定威胁标记或报告类型筛选视图。</span><span class="sxs-lookup"><span data-stu-id="5bf21-176">**Filters**—assist you in efficiently reviewing the threat report list and filtering the view based on a specific threat tag or report type.</span></span> <span data-ttu-id="5bf21-177">例如，查看与勒索软件类别相关的所有威胁报告或包含漏洞的威胁报告。</span><span class="sxs-lookup"><span data-stu-id="5bf21-177">For example, review all threat reports related to ransomware category, or threat reports that cover vulnerabilities.</span></span>

##### <a name="how-does-it-work"></a><span data-ttu-id="5bf21-178">它的工作原理</span><span class="sxs-lookup"><span data-stu-id="5bf21-178">How does it work?</span></span>
<span data-ttu-id="5bf21-179">Microsoft 威胁智能团队向每个威胁报告添加了威胁标记：</span><span class="sxs-lookup"><span data-stu-id="5bf21-179">The Microsoft Threat Intelligence team has added threat tags to each threat report:</span></span>
- <span data-ttu-id="5bf21-180">现在，有四个威胁标记可用：</span><span class="sxs-lookup"><span data-stu-id="5bf21-180">Four threat tags are now available:</span></span>
  - <span data-ttu-id="5bf21-181">勒索软件</span><span class="sxs-lookup"><span data-stu-id="5bf21-181">Ransomware</span></span>
  - <span data-ttu-id="5bf21-182">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="5bf21-182">Phishing</span></span>
  - <span data-ttu-id="5bf21-183">漏洞</span><span class="sxs-lookup"><span data-stu-id="5bf21-183">Vulnerability</span></span>
  - <span data-ttu-id="5bf21-184">活动组</span><span class="sxs-lookup"><span data-stu-id="5bf21-184">Activity group</span></span>
- <span data-ttu-id="5bf21-185">威胁标记在威胁分析页面顶部显示，每个标记下具有可用报告数量的计数器。</span><span class="sxs-lookup"><span data-stu-id="5bf21-185">Threat tags are presented at the top of the threat analytics page, with counters for the number of available reports under each tag.</span></span>
    <span data-ttu-id="5bf21-186">![威胁标记](../../media/threat-analytics/ta-threattags-mtp.png)</span><span class="sxs-lookup"><span data-stu-id="5bf21-186">![threat tags](../../media/threat-analytics/ta-threattags-mtp.png)</span></span>
- <span data-ttu-id="5bf21-187">该列表也可以按威胁标记排序：   ![ 列表](../../media/threat-analytics//ta-taglist-mtp.png)</span><span class="sxs-lookup"><span data-stu-id="5bf21-187">The list can also be sorted by threat tags:   ![lists](../../media/threat-analytics//ta-taglist-mtp.png)</span></span>
- <span data-ttu-id="5bf21-188">筛选器可用于每个威胁标记和报告类型：   ![ 筛选器](../../media/threat-analytics/ta-threattag-filters-mtp.png)</span><span class="sxs-lookup"><span data-stu-id="5bf21-188">Filters are available per threat tag and report type:   ![filters](../../media/threat-analytics/ta-threattag-filters-mtp.png)</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="5bf21-189">分析员报告：从 Microsoft 安全研究人员获取专家见解</span><span class="sxs-lookup"><span data-stu-id="5bf21-189">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="5bf21-190">在" **分析员报告** "部分，通读详细的专家撰写。</span><span class="sxs-lookup"><span data-stu-id="5bf21-190">In the **Analyst report** section, read through the detailed expert write-up.</span></span> <span data-ttu-id="5bf21-191">大多数报告都提供攻击链的详细说明，包括映射到 MITRE ATT&CK 框架的策略和技术、详细的建议列表和强大的 [威胁](advanced-hunting-overview.md) 搜寻指南。</span><span class="sxs-lookup"><span data-stu-id="5bf21-191">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="5bf21-192">详细了解分析员报告</span><span class="sxs-lookup"><span data-stu-id="5bf21-192">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a><span data-ttu-id="5bf21-193">相关事件：查看和管理相关事件</span><span class="sxs-lookup"><span data-stu-id="5bf21-193">Related incidents: View and manage related incidents</span></span>
<span data-ttu-id="5bf21-194">" **相关事件** "选项卡提供与跟踪威胁相关的所有事件的列表。</span><span class="sxs-lookup"><span data-stu-id="5bf21-194">The **Related incidents** tab provides the list of all incidents related to the tracked threat.</span></span> <span data-ttu-id="5bf21-195">你可以分配事件或管理链接到每个事件的警报。</span><span class="sxs-lookup"><span data-stu-id="5bf21-195">You can assign incidents or manage alerts linked to each incident.</span></span> 

![威胁分析报告的相关事件部分的图像](../../media/threat-analytics/ta_related_incidents_mtp.png)

<span data-ttu-id="5bf21-197">_威胁分析报告的相关事件部分_</span><span class="sxs-lookup"><span data-stu-id="5bf21-197">_Related incidents section of a threat analytics report_</span></span>

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a><span data-ttu-id="5bf21-198">影响的资产：获取受影响设备和邮箱的列表</span><span class="sxs-lookup"><span data-stu-id="5bf21-198">Impacted assets: Get list of impacted devices and mailboxes</span></span>
<span data-ttu-id="5bf21-199">如果资产受未解决活动警报的影响，则认为资产受到影响。</span><span class="sxs-lookup"><span data-stu-id="5bf21-199">An asset is considered impacted if it is affected by an active, unresolved alert.</span></span> <span data-ttu-id="5bf21-200">" **影响的资产"** 选项卡列出了以下类型的受影响资产：</span><span class="sxs-lookup"><span data-stu-id="5bf21-200">The **Impacted assets** tab lists the following types of impacted assets:</span></span>
- <span data-ttu-id="5bf21-201">**影响的设备**- 具有未解析的 Microsoft Defender for Endpoint 警报的终结点。</span><span class="sxs-lookup"><span data-stu-id="5bf21-201">**Impacted devices**—endpoints that have unresolved Microsoft Defender for Endpoint alerts.</span></span> <span data-ttu-id="5bf21-202">这些警报通常在看到已知威胁指示器和活动时触发。</span><span class="sxs-lookup"><span data-stu-id="5bf21-202">These alerts typically fire on sightings of known threat indicators and activities.</span></span>
- <span data-ttu-id="5bf21-203">**影响邮箱**— 已接收已触发 Microsoft Defender for Office 365警报的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5bf21-203">**Impacted mailboxes**—mailboxes that have received email messages that have triggered Microsoft Defender for Office 365 alerts.</span></span> <span data-ttu-id="5bf21-204">触发警报的多数消息通常会被阻止，但用户或组织级别的策略可以覆盖筛选器。</span><span class="sxs-lookup"><span data-stu-id="5bf21-204">While most messages that trigger alerts are typically blocked, user- or org-level policies can override filters.</span></span>

![威胁分析报告的影响资产部分的图像](../../media/threat-analytics/ta_impacted_assets_mtp.png)

<span data-ttu-id="5bf21-206">_威胁分析报告的"影响的资产"部分_</span><span class="sxs-lookup"><span data-stu-id="5bf21-206">_Impacted assets section of a threat analytics report_</span></span>

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a><span data-ttu-id="5bf21-207">阻止的电子邮件尝试：查看阻止或垃圾邮件威胁电子邮件</span><span class="sxs-lookup"><span data-stu-id="5bf21-207">Prevented email attempts: View blocked or junked threat emails</span></span>
<span data-ttu-id="5bf21-208">Microsoft Defender for Office 365通常阻止具有已知威胁指示器（包括恶意链接或附件）的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5bf21-208">Microsoft Defender for Office 365 typically blocks emails with known threat indicators, including malicious links or attachments.</span></span> <span data-ttu-id="5bf21-209">在某些情况下，检查可疑内容的主动筛选机制会改为将威胁电子邮件发送到垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="5bf21-209">In some cases, proactive filtering mechanisms that check for suspicious content will instead send threat emails to the junk mail folder.</span></span> <span data-ttu-id="5bf21-210">在任一情况下，威胁在设备上启动恶意软件代码的可能性都降低了。</span><span class="sxs-lookup"><span data-stu-id="5bf21-210">In either case, the chances of the threat launching malware code on the device is reduced.</span></span>

<span data-ttu-id="5bf21-211">"**阻止的电子邮件尝试**"选项卡列出了所有在传递前被阻止或由 Microsoft Defender 发送到垃圾邮件文件夹的电子邮件Office 365。</span><span class="sxs-lookup"><span data-stu-id="5bf21-211">The **Prevented email attempts** tab lists all the emails that have either been blocked before delivery or sent to the junk mail folder by Microsoft Defender for Office 365.</span></span> 

![威胁分析报告的阻止的电子邮件尝试部分的图像](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

<span data-ttu-id="5bf21-213">_威胁分析报告的"阻止的电子邮件尝试"部分_</span><span class="sxs-lookup"><span data-stu-id="5bf21-213">_Prevented email attempts section of a threat analytics report_</span></span>

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="5bf21-214">缓解：查看缓解列表和设备的状态</span><span class="sxs-lookup"><span data-stu-id="5bf21-214">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="5bf21-215">在 **"缓解"** 部分，查看特定可操作建议的列表，这些建议可帮助你提高组织应对威胁的复原能力。</span><span class="sxs-lookup"><span data-stu-id="5bf21-215">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="5bf21-216">跟踪的缓解列表包括：</span><span class="sxs-lookup"><span data-stu-id="5bf21-216">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="5bf21-217">**安全更新**- 部署在载入的设备上发现漏洞的受支持软件安全更新</span><span class="sxs-lookup"><span data-stu-id="5bf21-217">**Security updates**—deployment of supported software security updates for vulnerabilities found on onboarded devices</span></span>
- <span data-ttu-id="5bf21-218">**支持的安全配置**</span><span class="sxs-lookup"><span data-stu-id="5bf21-218">**Supported security configurations**</span></span>
  - <span data-ttu-id="5bf21-219">云端保护</span><span class="sxs-lookup"><span data-stu-id="5bf21-219">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="5bf21-220">PUA 保护 (可能不需要) 应用程序</span><span class="sxs-lookup"><span data-stu-id="5bf21-220">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="5bf21-221">实时保护</span><span class="sxs-lookup"><span data-stu-id="5bf21-221">Real-time protection</span></span>
 
<span data-ttu-id="5bf21-222">本节中的缓解信息包含来自 危险和漏洞管理[](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的数据，它还提供报告中各个链接的详细深化信息。</span><span class="sxs-lookup"><span data-stu-id="5bf21-222">Mitigation information in this section incorporates data from [threat and vulnerability management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="5bf21-223">![显示安全配置详细信息的威胁分析报告的缓解部分的图像 显示漏洞详细信息的威胁分析报告的缓解 ](../../media/threat-analytics/ta_mitigations_mtp.png)
 ![ 部分的图像](../../media/threat-analytics/ta_mitigations_mtp2.png)</span><span class="sxs-lookup"><span data-stu-id="5bf21-223">![Image of the mitigations section of a threat analytics report showing secure configuration details](../../media/threat-analytics/ta_mitigations_mtp.png)
![Image of the mitigations section of a threat analytics report showing vulnerability details](../../media/threat-analytics/ta_mitigations_mtp2.png)</span></span>

<span data-ttu-id="5bf21-224">_威胁分析报告的缓解部分_</span><span class="sxs-lookup"><span data-stu-id="5bf21-224">_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="5bf21-225">其他报告详细信息和限制</span><span class="sxs-lookup"><span data-stu-id="5bf21-225">Additional report details and limitations</span></span>
>[!NOTE]
><span data-ttu-id="5bf21-226">作为统一安全体验的一部分，威胁分析现在不仅适用于 Microsoft Defender for Endpoint，还适用于适用于 Office E5 许可证持有者的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="5bf21-226">As part of the unified security experience, threat analytics is now available not just for Microsoft Defender for Endpoint, but also for Microsoft Defender for Office E5 license holders.</span></span>
><span data-ttu-id="5bf21-227">如果你未使用 Microsoft 365 安全门户 (Microsoft 365 Defender) ，则还可以在 Microsoft Defender 安全中心 门户中查看报告详细信息 (，而无需 Microsoft Defender for Office data)  (Microsoft Defender for Endpoint) 。</span><span class="sxs-lookup"><span data-stu-id="5bf21-227">If you are not using the Microsoft 365 security portal (Microsoft 365 Defender), you can also see the report details (without the Microsoft Defender for Office data) in the Microsoft Defender Security Center portal (Microsoft Defender for Endpoint).</span></span> 

<span data-ttu-id="5bf21-228">若要访问威胁分析报告，你需要某些角色和权限。</span><span class="sxs-lookup"><span data-stu-id="5bf21-228">To access threat analytics report you need certain roles and permissions.</span></span> <span data-ttu-id="5bf21-229">有关详细信息[，请参阅基于角色的访问控制中的Microsoft 365 Defender](custom-roles.md)角色。</span><span class="sxs-lookup"><span data-stu-id="5bf21-229">See [Custom roles in role-based access control for Microsoft 365 Defender](custom-roles.md) for details.</span></span>
  - <span data-ttu-id="5bf21-230">若要查看警报、事件或受影响的资产数据，你需要拥有对 microsoft Defender for Office 或 Microsoft Defender for Endpoint 警报数据的权限，或同时拥有这两者的权限。</span><span class="sxs-lookup"><span data-stu-id="5bf21-230">To view alerts, incidents, or impacted assets data, you need to have permissions to Microsoft Defender for Office or Microsoft Defender for Endpoint alerts data, or both.</span></span>
  - <span data-ttu-id="5bf21-231">若要查看阻止的电子邮件尝试，你需要拥有 Microsoft Defender 的权限，才能Office数据。</span><span class="sxs-lookup"><span data-stu-id="5bf21-231">To view prevented email attempts, you need to have permissions to Microsoft Defender for Office hunting data.</span></span> 
  - <span data-ttu-id="5bf21-232">若要查看缓解，你需要拥有在 Microsoft Defender for Endpoint 危险和漏洞管理数据的权限。</span><span class="sxs-lookup"><span data-stu-id="5bf21-232">To view mitigations, you need to have permissions to threat and vulnerability management data in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="5bf21-233">查看威胁分析数据时，请记住以下因素：</span><span class="sxs-lookup"><span data-stu-id="5bf21-233">When looking at the threat analytics data, remember the following factors:</span></span>
- <span data-ttu-id="5bf21-234">图表仅反映跟踪的缓解。</span><span class="sxs-lookup"><span data-stu-id="5bf21-234">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="5bf21-235">查看报告概述，了解图表中未显示的其他缓解功能。</span><span class="sxs-lookup"><span data-stu-id="5bf21-235">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="5bf21-236">缓解不保证完全恢复。</span><span class="sxs-lookup"><span data-stu-id="5bf21-236">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="5bf21-237">提供的缓解反映了改进恢复能力所需的最佳可能操作。</span><span class="sxs-lookup"><span data-stu-id="5bf21-237">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="5bf21-238">如果设备尚未将数据传输到服务，则被视为"不可用"。</span><span class="sxs-lookup"><span data-stu-id="5bf21-238">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="5bf21-239">防病毒相关的统计信息基于Microsoft Defender 防病毒设置。</span><span class="sxs-lookup"><span data-stu-id="5bf21-239">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="5bf21-240">具有第三方防病毒解决方案的设备可能显示为"公开"。</span><span class="sxs-lookup"><span data-stu-id="5bf21-240">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="5bf21-241">相关主题</span><span class="sxs-lookup"><span data-stu-id="5bf21-241">Related topics</span></span>
- [<span data-ttu-id="5bf21-242">使用高级搜寻主动查找威胁</span><span class="sxs-lookup"><span data-stu-id="5bf21-242">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="5bf21-243">了解分析员报告部分</span><span class="sxs-lookup"><span data-stu-id="5bf21-243">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="5bf21-244">评估和解决安全漏洞和曝光</span><span class="sxs-lookup"><span data-stu-id="5bf21-244">Assess and resolve security weaknesses and exposures</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
