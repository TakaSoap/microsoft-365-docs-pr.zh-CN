---
title: 威胁和漏洞管理
description: 这一新功能使用基于游戏变化风险的方法来发现、确定终结点漏洞和错误配置并修复这些漏洞和错误配置。
keywords: 威胁&漏洞管理， 威胁和漏洞管理， MDATP TVM， MDATP-TVM， 漏洞管理， 漏洞评估， 威胁和漏洞扫描， 安全配置评估， microsoft defender atp， microsoft defender atp， 终结点漏洞， 下一代
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
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: 0c3c5ebbcd4483cae159fe9b46a6f4c376443be3
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499070"
---
# <a name="threat-and-vulnerability-management"></a><span data-ttu-id="5490e-104">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="5490e-104">Threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5490e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5490e-105">**Applies to:**</span></span>
- [<span data-ttu-id="5490e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5490e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5490e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5490e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="5490e-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="5490e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5490e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5490e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="5490e-110">有效识别、评估和修正终结点缺陷是运行正常安全计划并降低组织风险的关键。</span><span class="sxs-lookup"><span data-stu-id="5490e-110">Effectively identifying, assessing, and remediating endpoint weaknesses is pivotal in running a healthy security program and reducing organizational risk.</span></span> <span data-ttu-id="5490e-111">威胁和漏洞管理是减少组织风险，强化终结点表面区域和提高组织复原能力的基础结构。</span><span class="sxs-lookup"><span data-stu-id="5490e-111">Threat and vulnerability management serves as an infrastructure for reducing organizational exposure, hardening endpoint surface area, and increasing organizational resilience.</span></span>

<span data-ttu-id="5490e-112">使用传感器实时发现漏洞和错误配置，无需代理或定期扫描。</span><span class="sxs-lookup"><span data-stu-id="5490e-112">Discover vulnerabilities and misconfigurations in real time with sensors, and without the need of agents or periodic scans.</span></span> <span data-ttu-id="5490e-113">它根据威胁环境、您组织的检测、易受攻击的设备的敏感信息和业务上下文确定漏洞的优先级。</span><span class="sxs-lookup"><span data-stu-id="5490e-113">It prioritizes vulnerabilities based on the threat landscape, detections in your organization, sensitive information on vulnerable devices, and business context.</span></span>

<span data-ttu-id="5490e-114">观看此视频，快速概览威胁和漏洞管理。</span><span class="sxs-lookup"><span data-stu-id="5490e-114">Watch this video for a quick overview of threat and vulnerability management.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a><span data-ttu-id="5490e-115">桥接工作流差距</span><span class="sxs-lookup"><span data-stu-id="5490e-115">Bridging the workflow gaps</span></span>

<span data-ttu-id="5490e-116">威胁和漏洞管理内置、实时且由云支持。</span><span class="sxs-lookup"><span data-stu-id="5490e-116">Threat and vulnerability management is built in, real time, and cloud powered.</span></span> <span data-ttu-id="5490e-117">它与 Microsoft 终结点安全堆栈、Microsoft Intelligent Security Graph 和应用程序分析知识库完全集成。</span><span class="sxs-lookup"><span data-stu-id="5490e-117">It's fully integrated with Microsoft endpoint security stack, the Microsoft Intelligent Security Graph, and the application analytics knowledge base.</span></span>  

<span data-ttu-id="5490e-118">漏洞管理是行业首个在修正过程中弥补安全管理和 IT 管理差距的解决方案。</span><span class="sxs-lookup"><span data-stu-id="5490e-118">Vulnerability management is the first solution in the industry to bridge the gap between security administration and IT administration during remediation process.</span></span> <span data-ttu-id="5490e-119">与 Microsoft Intune 和 Microsoft Endpoint Configuration Manager 集成，创建安全任务或票证。</span><span class="sxs-lookup"><span data-stu-id="5490e-119">Create a security task or ticket by integrating with Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span>

### <a name="real-time-discovery"></a><span data-ttu-id="5490e-120">实时发现</span><span class="sxs-lookup"><span data-stu-id="5490e-120">Real-time discovery</span></span>

<span data-ttu-id="5490e-121">为了发现终结点漏洞和错误配置，威胁和漏洞管理使用相同的无代理内置 Defender for Endpoint 传感器，以减少繁琐的网络扫描和 IT 开销。</span><span class="sxs-lookup"><span data-stu-id="5490e-121">To discover endpoint vulnerabilities and misconfiguration, threat and vulnerability management uses the same agentless built-in Defender for Endpoint sensors to reduce cumbersome network scans and IT overhead.</span></span>

<span data-ttu-id="5490e-122">它还提供：</span><span class="sxs-lookup"><span data-stu-id="5490e-122">It also provides:</span></span>

- <span data-ttu-id="5490e-123">**实时设备清单** - 载入 Defender for Endpoint 的设备会自动将漏洞和安全配置数据报告并推送到仪表板。</span><span class="sxs-lookup"><span data-stu-id="5490e-123">**Real-time device inventory** - Devices onboarded to Defender for Endpoint automatically report and push vulnerability and security configuration data to the dashboard.</span></span>
- <span data-ttu-id="5490e-124">**了解软件和漏洞** - 组织软件清单的光学镜头，以及安装、卸载和修补程序等软件更改。</span><span class="sxs-lookup"><span data-stu-id="5490e-124">**Visibility into software and vulnerabilities** - Optics into the organization's software inventory, and software changes like installations, uninstalls, and patches.</span></span> <span data-ttu-id="5490e-125">新发现的漏洞通过针对第一方和第三方应用程序的可操作缓解建议进行报告。</span><span class="sxs-lookup"><span data-stu-id="5490e-125">Newly discovered vulnerabilities are reported with actionable mitigation recommendations for 1st and 3rd party applications.</span></span>
- <span data-ttu-id="5490e-126">**应用程序运行时上下文** - 有关应用程序使用模式的可见性，以更好地进行优先顺序和决策制定。</span><span class="sxs-lookup"><span data-stu-id="5490e-126">**Application runtime context** - Visibility on application usage patterns for better prioritization and decision-making.</span></span>
- <span data-ttu-id="5490e-127">**配置状态** - 了解组织安全配置或错误配置。</span><span class="sxs-lookup"><span data-stu-id="5490e-127">**Configuration posture** - Visibility into organizational security configuration or misconfigurations.</span></span> <span data-ttu-id="5490e-128">在仪表板中报告的问题以及可操作的安全建议。</span><span class="sxs-lookup"><span data-stu-id="5490e-128">Issues are reported in the dashboard with actionable security recommendations.</span></span>

### <a name="intelligence-driven-prioritization"></a><span data-ttu-id="5490e-129">智能驱动的优先顺序</span><span class="sxs-lookup"><span data-stu-id="5490e-129">Intelligence-driven prioritization</span></span>

<span data-ttu-id="5490e-130">威胁和漏洞管理可帮助客户确定优先级，并重点关注对组织构成最紧急且风险最高的漏洞。</span><span class="sxs-lookup"><span data-stu-id="5490e-130">Threat and vulnerability management helps customers prioritize and focus on the weaknesses that pose the most urgent and the highest risk to the organization.</span></span> <span data-ttu-id="5490e-131">它将安全建议与动态威胁和业务上下文融合在一起：</span><span class="sxs-lookup"><span data-stu-id="5490e-131">It fuses security recommendations with dynamic threat and business context:</span></span>

- <span data-ttu-id="5490e-132">**在通配符中公开新出现的攻击** - 动态对齐安全建议优先顺序。</span><span class="sxs-lookup"><span data-stu-id="5490e-132">**Exposing emerging attacks in the wild** - Dynamically aligns the prioritization of security recommendations.</span></span> <span data-ttu-id="5490e-133">威胁和漏洞管理重点关注当前在构成最高风险的新兴威胁中利用的漏洞。</span><span class="sxs-lookup"><span data-stu-id="5490e-133">Threat and vulnerability management focuses on vulnerabilities currently being exploited in the wild and emerging threats that pose the highest risk.</span></span>
- <span data-ttu-id="5490e-134">**精确定位活动漏洞** - 关联威胁和漏洞管理和 EDR 见解，以确定在组织内部的活动泄露中利用的漏洞的优先级。</span><span class="sxs-lookup"><span data-stu-id="5490e-134">**Pinpointing active breaches** - Correlates threat and vulnerability management and EDR insights to prioritize vulnerabilities being exploited in an active breach within the organization.</span></span>
- <span data-ttu-id="5490e-135">**保护高价值资产** - 使用业务关键应用程序、机密数据或高价值用户标识公开的设备。</span><span class="sxs-lookup"><span data-stu-id="5490e-135">**Protecting high-value assets** - Identify the exposed devices with business-critical applications, confidential data, or high-value users.</span></span>

### <a name="seamless-remediation"></a><span data-ttu-id="5490e-136">无缝修正</span><span class="sxs-lookup"><span data-stu-id="5490e-136">Seamless remediation</span></span>

<span data-ttu-id="5490e-137">威胁和漏洞管理允许安全管理员和 IT 管理员无缝协作以修正问题。</span><span class="sxs-lookup"><span data-stu-id="5490e-137">Threat and vulnerability management allows security administrators and IT administrators to collaborate seamlessly to remediate issues.</span></span>

- <span data-ttu-id="5490e-138">**发送给 IT 的修正请求** - 根据特定安全建议在 Microsoft Intune 中创建修正任务。</span><span class="sxs-lookup"><span data-stu-id="5490e-138">**Remediation requests sent to IT** - Create a remediation task in Microsoft Intune from a specific security recommendation.</span></span> <span data-ttu-id="5490e-139">我们计划将此功能扩展到其他 IT 安全管理平台。</span><span class="sxs-lookup"><span data-stu-id="5490e-139">We plan to expand this capability to other IT security management platforms.</span></span>
- <span data-ttu-id="5490e-140">**备用缓解** - 深入了解其他缓解，例如可降低与软件漏洞关联的风险的配置更改。</span><span class="sxs-lookup"><span data-stu-id="5490e-140">**Alternate mitigations** - Gain insights on additional mitigations, such as configuration changes that can reduce risk associated with software vulnerabilities.</span></span>
- <span data-ttu-id="5490e-141">**实时修正状态** - 实时监视整个组织中修正活动的状态和进度。</span><span class="sxs-lookup"><span data-stu-id="5490e-141">**Real-time remediation status** - Real-time monitoring of the status and progress of remediation activities across the organization.</span></span>

## <a name="threat-and-vulnerability-management-walk-through"></a><span data-ttu-id="5490e-142">威胁和漏洞管理演练</span><span class="sxs-lookup"><span data-stu-id="5490e-142">Threat and vulnerability management walk-through</span></span>

<span data-ttu-id="5490e-143">观看此视频，全面演练威胁和漏洞管理。</span><span class="sxs-lookup"><span data-stu-id="5490e-143">Watch this video for a comprehensive walk-through of threat and vulnerability management.</span></span>

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a><span data-ttu-id="5490e-144">导航窗格 </span><span class="sxs-lookup"><span data-stu-id="5490e-144">Navigation pane</span></span>

<span data-ttu-id="5490e-145">区域</span><span class="sxs-lookup"><span data-stu-id="5490e-145">Area</span></span> | <span data-ttu-id="5490e-146">说明</span><span class="sxs-lookup"><span data-stu-id="5490e-146">Description</span></span>
:---|:---
<span data-ttu-id="5490e-147">**仪表板**</span><span class="sxs-lookup"><span data-stu-id="5490e-147">**Dashboard**</span></span>   | <span data-ttu-id="5490e-148">获取组织曝光分数、适用于设备的 Microsoft 安全分数、设备曝光分布、顶级安全建议、最易受攻击的软件、顶级修正活动和最公开设备数据等高级视图。</span><span class="sxs-lookup"><span data-stu-id="5490e-148">Get a high-level view of the organization exposure score, Microsoft Secure Score for Devices, device exposure distribution, top security recommendations, top vulnerable software, top remediation activities, and top exposed device data.</span></span>
[<span data-ttu-id="5490e-149">**安全性建议**</span><span class="sxs-lookup"><span data-stu-id="5490e-149">**Security recommendations**</span></span>](tvm-security-recommendation.md) | <span data-ttu-id="5490e-150">请参阅安全建议和相关威胁信息列表。</span><span class="sxs-lookup"><span data-stu-id="5490e-150">See the list of security recommendations and related threat information.</span></span> <span data-ttu-id="5490e-151">当你从列表中选择一个项目时，将打开一个包含漏洞详细信息的飞出面板、一个打开软件页的链接以及修正和例外选项。</span><span class="sxs-lookup"><span data-stu-id="5490e-151">When you select an item from the list, a flyout panel opens with vulnerability details, a link to open the software page, and remediation and exception options.</span></span> <span data-ttu-id="5490e-152">如果你的设备通过 Azure Active Directory 加入，并且你已启用 Defender for Endpoint 中的 Intune 连接，则还可以在 Intune 中打开票证。</span><span class="sxs-lookup"><span data-stu-id="5490e-152">You can also open a ticket in Intune if your devices are joined through Azure Active Directory and you've enabled your Intune connections in Defender for Endpoint.</span></span>
[<span data-ttu-id="5490e-153">**修正**</span><span class="sxs-lookup"><span data-stu-id="5490e-153">**Remediation**</span></span>](tvm-remediation.md) | <span data-ttu-id="5490e-154">请参阅已创建的修正活动和建议例外。</span><span class="sxs-lookup"><span data-stu-id="5490e-154">See remediation activities you've created and recommendation exceptions.</span></span>
[<span data-ttu-id="5490e-155">**软件库存**</span><span class="sxs-lookup"><span data-stu-id="5490e-155">**Software inventory**</span></span>](tvm-software-inventory.md) | <span data-ttu-id="5490e-156">请参阅组织中易受攻击的软件列表，以及漏洞和威胁信息。</span><span class="sxs-lookup"><span data-stu-id="5490e-156">See the list of vulnerable software in your organization, along with weakness and threat information.</span></span>
[<span data-ttu-id="5490e-157">**漏洞**</span><span class="sxs-lookup"><span data-stu-id="5490e-157">**Weaknesses**</span></span>](tvm-weaknesses.md) | <span data-ttu-id="5490e-158">请参阅组织中 C CV 的常见 (曝光) 列表。</span><span class="sxs-lookup"><span data-stu-id="5490e-158">See the list of common vulnerabilities and exposures (CVEs) in your organization.</span></span>
[<span data-ttu-id="5490e-159">**活动日程表**</span><span class="sxs-lookup"><span data-stu-id="5490e-159">**Event timeline**</span></span>](threat-and-vuln-mgt-event-timeline.md) | <span data-ttu-id="5490e-160">查看可能会影响组织风险的事件。</span><span class="sxs-lookup"><span data-stu-id="5490e-160">View events that may impact your organization's risk.</span></span>

## <a name="apis"></a><span data-ttu-id="5490e-161">API</span><span class="sxs-lookup"><span data-stu-id="5490e-161">APIs</span></span>

<span data-ttu-id="5490e-162">运行与威胁和漏洞管理相关的 API 调用，以自动执行漏洞管理工作流。</span><span class="sxs-lookup"><span data-stu-id="5490e-162">Run threat and vulnerability management-related API calls to automate vulnerability management workflows.</span></span> <span data-ttu-id="5490e-163">从此 [Microsoft 技术社区博客文章了解更多信息](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)。</span><span class="sxs-lookup"><span data-stu-id="5490e-163">Learn more from this [Microsoft Tech Community blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615).</span></span>

<span data-ttu-id="5490e-164">请参阅以下相关 API 文章：</span><span class="sxs-lookup"><span data-stu-id="5490e-164">See the following articles for related APIs:</span></span>

- [<span data-ttu-id="5490e-165">支持的 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="5490e-165">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="5490e-166">计算机 API</span><span class="sxs-lookup"><span data-stu-id="5490e-166">Machine APIs</span></span>](machine.md)
- [<span data-ttu-id="5490e-167">建议 API</span><span class="sxs-lookup"><span data-stu-id="5490e-167">Recommendation APIs</span></span>](vulnerability.md)
- [<span data-ttu-id="5490e-168">分数 API</span><span class="sxs-lookup"><span data-stu-id="5490e-168">Score APIs</span></span>](score.md)
- [<span data-ttu-id="5490e-169">软件 API</span><span class="sxs-lookup"><span data-stu-id="5490e-169">Software APIs</span></span>](software.md)
- [<span data-ttu-id="5490e-170">漏洞 API</span><span class="sxs-lookup"><span data-stu-id="5490e-170">Vulnerability APIs</span></span>](vulnerability.md)
- [<span data-ttu-id="5490e-171">按计算机和软件列出漏洞</span><span class="sxs-lookup"><span data-stu-id="5490e-171">List vulnerabilities by machine and software</span></span>](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a><span data-ttu-id="5490e-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5490e-172">See also</span></span>

- [<span data-ttu-id="5490e-173">支持的操作系统和平台</span><span class="sxs-lookup"><span data-stu-id="5490e-173">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="5490e-174">威胁和漏洞管理仪表板</span><span class="sxs-lookup"><span data-stu-id="5490e-174">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="5490e-175">博客：Microsoft 的威胁&漏洞管理现在可帮助数以千计的客户实时发现、确定漏洞的优先级并修正漏洞</span><span class="sxs-lookup"><span data-stu-id="5490e-175">BLOG: Microsoft's Threat & Vulnerability Management now helps thousands of customers to discover, prioritize, and remediate vulnerabilities in real time</span></span>](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)
