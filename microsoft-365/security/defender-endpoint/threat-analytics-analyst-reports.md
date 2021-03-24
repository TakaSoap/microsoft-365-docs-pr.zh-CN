---
title: 了解威胁分析中的分析员报告部分
ms.reviewer: ''
description: 了解每个威胁分析报告的分析师报告部分。 了解它如何提供有关威胁、缓解、检测、高级搜寻查询等的信息。
keywords: 分析员报告， 威胁分析， 检测， 高级搜寻查询， 缓解，
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 38d6d4f3ce1fd6a6ba51b2ac0802892c036f3e50
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056509"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a><span data-ttu-id="275bd-105">了解威胁分析中的分析员报告</span><span class="sxs-lookup"><span data-stu-id="275bd-105">Understand the analyst report in threat analytics</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="275bd-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="275bd-106">**Applies to:**</span></span>
- [<span data-ttu-id="275bd-107">Microsoft Defender 高级威胁防护 (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="275bd-107">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)
- [<span data-ttu-id="275bd-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="275bd-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="275bd-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="275bd-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="275bd-110">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="275bd-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="275bd-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="275bd-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="275bd-112">每个 [威胁分析报告都](threat-analytics.md) 包括动态部分和一个称为分析员报告的综合 _书面部分_。</span><span class="sxs-lookup"><span data-stu-id="275bd-112">Each [threat analytics report](threat-analytics.md) includes dynamic sections and a comprehensive written section called the _analyst report_.</span></span> <span data-ttu-id="275bd-113">若要访问此部分，请打开关于跟踪的威胁的报告，然后选择"分析 **员报告"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="275bd-113">To access this section, open the report about the tracked threat and select the **Analyst report** tab.</span></span>

![威胁分析报告的分析员报告部分的图像](images/ta-analyst-report-small.png)

<span data-ttu-id="275bd-115">_威胁分析报告的分析员报告部分_</span><span class="sxs-lookup"><span data-stu-id="275bd-115">_Analyst report section of a threat analytics report_</span></span>

## <a name="scan-the-analyst-report"></a><span data-ttu-id="275bd-116">扫描分析员报告</span><span class="sxs-lookup"><span data-stu-id="275bd-116">Scan the analyst report</span></span> 
<span data-ttu-id="275bd-117">分析员报告的每个部分旨在提供可操作的信息。</span><span class="sxs-lookup"><span data-stu-id="275bd-117">Each section of the analyst report is designed to provide actionable information.</span></span> <span data-ttu-id="275bd-118">尽管报告各不相同，但大多数报告包括下表中描述的部分。</span><span class="sxs-lookup"><span data-stu-id="275bd-118">While reports vary, most reports include the sections described in the following table.</span></span>

| <span data-ttu-id="275bd-119">"报告"部分</span><span class="sxs-lookup"><span data-stu-id="275bd-119">Report section</span></span> | <span data-ttu-id="275bd-120">说明</span><span class="sxs-lookup"><span data-stu-id="275bd-120">Description</span></span> |
|--|--|
| <span data-ttu-id="275bd-121">执行摘要</span><span class="sxs-lookup"><span data-stu-id="275bd-121">Executive summary</span></span> | <span data-ttu-id="275bd-122">威胁概述，包括首次看到威胁时、其动机、值得注意的事件、主要目标以及不同的工具和技术。</span><span class="sxs-lookup"><span data-stu-id="275bd-122">Overview of the threat, including when it was first seen, its motivations, notable events, major targets, and distinct tools and techniques.</span></span> <span data-ttu-id="275bd-123">可以使用此信息进一步评估如何在行业、地理位置和网络上下文中确定威胁的优先级。</span><span class="sxs-lookup"><span data-stu-id="275bd-123">You can use this information to further assess how to prioritize the threat in the context of your industry, geographic location, and network.</span></span> |
| <span data-ttu-id="275bd-124">分析</span><span class="sxs-lookup"><span data-stu-id="275bd-124">Analysis</span></span> | <span data-ttu-id="275bd-125">有关威胁的技术信息，包括攻击的详细信息以及攻击者如何利用新技术或攻击面</span><span class="sxs-lookup"><span data-stu-id="275bd-125">Technical information about the threats, including the details of an attack and how attackers might utilize a new technique or attack surface</span></span> | 
| <span data-ttu-id="275bd-126">MITRE ATT&观察到的 CK 技术</span><span class="sxs-lookup"><span data-stu-id="275bd-126">MITRE ATT&CK techniques observed</span></span> | <span data-ttu-id="275bd-127">观察技术如何映射到 [MITRE ATT&CK 攻击框架](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="275bd-127">How observed techniques map to the [MITRE ATT&CK attack framework](https://attack.mitre.org/)</span></span> | 
| [<span data-ttu-id="275bd-128">缓解</span><span class="sxs-lookup"><span data-stu-id="275bd-128">Mitigations</span></span>](#apply-additional-mitigations) | <span data-ttu-id="275bd-129">可以停止或帮助降低威胁影响的建议。</span><span class="sxs-lookup"><span data-stu-id="275bd-129">Recommendations that can stop or help reduce the impact of the threat.</span></span> <span data-ttu-id="275bd-130">本部分还包括作为威胁分析报告的一部分未动态跟踪的缓解。</span><span class="sxs-lookup"><span data-stu-id="275bd-130">This section also includes mitigations that aren't tracked dynamically as part of the threat analytics report.</span></span> |
| [<span data-ttu-id="275bd-131">检测详细信息</span><span class="sxs-lookup"><span data-stu-id="275bd-131">Detection details</span></span>](#understand-how-each-threat-can-be-detected) | <span data-ttu-id="275bd-132">Microsoft 安全解决方案提供的特定和通用检测，可显示与威胁关联的活动或组件。</span><span class="sxs-lookup"><span data-stu-id="275bd-132">Specific and generic detections provided by Microsoft security solutions that can surface activity or components associated with the threat.</span></span> | 
| [<span data-ttu-id="275bd-133">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="275bd-133">Advanced hunting</span></span>](#find-subtle-threat-artifacts-using-advanced-hunting) | <span data-ttu-id="275bd-134">[用于主动识别](advanced-hunting-overview.md) 可能的威胁活动的高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="275bd-134">[Advanced hunting queries](advanced-hunting-overview.md) for proactively identifying possible threat activity.</span></span> <span data-ttu-id="275bd-135">大多数查询都用于补充检测，尤其是用于找到无法动态评估为恶意的潜在恶意组件或行为。</span><span class="sxs-lookup"><span data-stu-id="275bd-135">Most queries are provided to supplement detections, especially for locating potentially malicious components or behaviors that couldn't be dynamically assessed to be malicious.</span></span> | 
| <span data-ttu-id="275bd-136">参考</span><span class="sxs-lookup"><span data-stu-id="275bd-136">References</span></span> | <span data-ttu-id="275bd-137">Microsoft 和分析师在报告创建期间引用的第三方出版物。</span><span class="sxs-lookup"><span data-stu-id="275bd-137">Microsoft and third-party publications referenced by analysts during the creation of the report.</span></span> <span data-ttu-id="275bd-138">威胁分析内容基于 Microsoft 研究人员验证的数据。</span><span class="sxs-lookup"><span data-stu-id="275bd-138">Threat analytics content is based on data validated by Microsoft researchers.</span></span> <span data-ttu-id="275bd-139">公开提供的、第三方源的信息会明确标识。</span><span class="sxs-lookup"><span data-stu-id="275bd-139">Information from publicly available, third-party sources are identified clearly as such.</span></span> | 
| <span data-ttu-id="275bd-140">更改日志</span><span class="sxs-lookup"><span data-stu-id="275bd-140">Change log</span></span> | <span data-ttu-id="275bd-141">报告的发布时间和对报告进行重大更改的时间。</span><span class="sxs-lookup"><span data-stu-id="275bd-141">The time the report was published and when significant changes were made to the report.</span></span> |

## <a name="apply-additional-mitigations"></a><span data-ttu-id="275bd-142">应用其他缓解</span><span class="sxs-lookup"><span data-stu-id="275bd-142">Apply additional mitigations</span></span>
<span data-ttu-id="275bd-143">威胁分析动态跟踪 [安全更新和安全配置的状态](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)。</span><span class="sxs-lookup"><span data-stu-id="275bd-143">Threat analytics dynamically tracks the [status of security updates and secure configurations](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices).</span></span> <span data-ttu-id="275bd-144">此信息在缓解选项卡中作为图表 **和表格** 提供。</span><span class="sxs-lookup"><span data-stu-id="275bd-144">This information is available as charts and tables in the **Mitigations** tab.</span></span>

<span data-ttu-id="275bd-145">除了这些跟踪的缓解之外，分析员报告还将讨论未 _动态_ 监视的缓解。</span><span class="sxs-lookup"><span data-stu-id="275bd-145">In addition to these tracked mitigations, the analyst report also discusses mitigations that are _not_ dynamically monitored.</span></span> <span data-ttu-id="275bd-146">下面是未动态跟踪的重要缓解的一些示例：</span><span class="sxs-lookup"><span data-stu-id="275bd-146">Here are some examples of important mitigations that are not dynamically tracked:</span></span>

- <span data-ttu-id="275bd-147">阻止带有 _.lnk_ 附件或其他可疑文件类型的电子邮件</span><span class="sxs-lookup"><span data-stu-id="275bd-147">Block emails with _.lnk_ attachments or other suspicious file types</span></span>
- <span data-ttu-id="275bd-148">随机化本地管理员密码</span><span class="sxs-lookup"><span data-stu-id="275bd-148">Randomize local administrator passwords</span></span>
- <span data-ttu-id="275bd-149">向最终用户就网络钓鱼电子邮件和其他威胁矢量进行培训</span><span class="sxs-lookup"><span data-stu-id="275bd-149">Educate end users about phishing email and other threat vectors</span></span>
- <span data-ttu-id="275bd-150">打开特定 [攻击面减少规则](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="275bd-150">Turn on specific [attack surface reduction rules](attack-surface-reduction.md)</span></span>

<span data-ttu-id="275bd-151">虽然可以使用"缓解" **选项卡评估** 针对威胁的安全状态，但这些建议可让你采取其他步骤改善安全状况。</span><span class="sxs-lookup"><span data-stu-id="275bd-151">While you can use the **Mitigations** tab to assess your security posture against a threat, these recommendations let you take additional steps towards improving your security posture.</span></span> <span data-ttu-id="275bd-152">仔细阅读分析员报告中的所有缓解指南，并尽可能应用它们。</span><span class="sxs-lookup"><span data-stu-id="275bd-152">Carefully read all the mitigation guidance in the analyst report and apply them whenever possible.</span></span>

## <a name="understand-how-each-threat-can-be-detected"></a><span data-ttu-id="275bd-153">了解如何检测每个威胁</span><span class="sxs-lookup"><span data-stu-id="275bd-153">Understand how each threat can be detected</span></span>
<span data-ttu-id="275bd-154">分析员报告还提供来自 Microsoft Defender for Endpoint 防病毒的检测以及终结点检测和响应 (EDR) 功能。</span><span class="sxs-lookup"><span data-stu-id="275bd-154">The analyst report also provides the detections from Microsoft Defender for Endpoint antivirus and _endpoint detection and response_ (EDR) capabilities.</span></span>

### <a name="antivirus-detections"></a><span data-ttu-id="275bd-155">防病毒检测</span><span class="sxs-lookup"><span data-stu-id="275bd-155">Antivirus detections</span></span>
<span data-ttu-id="275bd-156">这些检测在 Microsoft [Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 打开的设备上可用。</span><span class="sxs-lookup"><span data-stu-id="275bd-156">These detections are available on devices with [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) turned on.</span></span> <span data-ttu-id="275bd-157">当这些检测发生在已载入到 Microsoft Defender for Endpoint 的设备上时，它们还会触发警报，以点亮报告中的图表。</span><span class="sxs-lookup"><span data-stu-id="275bd-157">When these detections occur on devices that have been onboarded to Microsoft Defender for Endpoint, they also trigger alerts that light up the charts in the report.</span></span>

>[!NOTE]
><span data-ttu-id="275bd-158">除特定于跟踪的威胁的组件或行为外，分析员报告还列出了可标识各种威胁的通用检测。</span><span class="sxs-lookup"><span data-stu-id="275bd-158">The analyst report also lists **generic detections** that can identify a wide-range of threats, in addition to components or behaviors specific to the tracked threat.</span></span> <span data-ttu-id="275bd-159">这些常规检测不会在图表中反映出来。</span><span class="sxs-lookup"><span data-stu-id="275bd-159">These generic detections don't reflect in the charts.</span></span>

### <a name="endpoint-detection-and-response-edr-alerts"></a><span data-ttu-id="275bd-160">终结点检测和响应 (EDR) 警报</span><span class="sxs-lookup"><span data-stu-id="275bd-160">Endpoint detection and response (EDR) alerts</span></span>
<span data-ttu-id="275bd-161">对于载入到 Microsoft Defender [for Endpoint](onboard-configure.md)的设备，将引发 EDR 警报。</span><span class="sxs-lookup"><span data-stu-id="275bd-161">EDR alerts are raised for [devices onboarded to Microsoft Defender for Endpoint](onboard-configure.md).</span></span> <span data-ttu-id="275bd-162">这些警报通常依赖于 Microsoft Defender for Endpoint 传感器收集的安全信号和其他充当强大信号源的终结点功能（如防病毒、网络保护、防篡改保护）。</span><span class="sxs-lookup"><span data-stu-id="275bd-162">These alerts generally rely on security signals collected by the Microsoft Defender for Endpoint sensor and other endpoint capabilities—such as antivirus, network protection, tamper protection—that serve as powerful signal sources.</span></span>

<span data-ttu-id="275bd-163">与防病毒检测列表一样，一些 EDR 警报旨在一般标记可能未与跟踪威胁关联的可疑行为。</span><span class="sxs-lookup"><span data-stu-id="275bd-163">Like the list of antivirus detections, some EDR alerts are designed to generically flag suspicious behavior that might not be associated with the tracked threat.</span></span> <span data-ttu-id="275bd-164">在这种情况下，报告将清楚地将警报标识为"通用"，并且它并不影响报告中的任何图表。</span><span class="sxs-lookup"><span data-stu-id="275bd-164">In such cases, the report will clearly identify the alert as "generic" and that it doesn't influence any of the charts in the report.</span></span>

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a><span data-ttu-id="275bd-165">使用高级搜寻查找细微的威胁项目</span><span class="sxs-lookup"><span data-stu-id="275bd-165">Find subtle threat artifacts using advanced hunting</span></span>
<span data-ttu-id="275bd-166">虽然检测允许你自动识别和停止跟踪的威胁，但许多攻击活动留下需要额外检查的细微跟踪。</span><span class="sxs-lookup"><span data-stu-id="275bd-166">While detections allow you to identify and stop the tracked threat automatically, many attack activities leave subtle traces that require additional inspection.</span></span> <span data-ttu-id="275bd-167">某些攻击活动呈现的行为也是正常的，因此动态检测它们可能会导致操作干扰甚至误报。</span><span class="sxs-lookup"><span data-stu-id="275bd-167">Some attack activities exhibit behaviors that can also be normal, so detecting them dynamically can result in operational noise or even false positives.</span></span>

<span data-ttu-id="275bd-168">[高级搜寻](advanced-hunting-overview.md) 提供基于 Kusto 查询语言的查询接口，可简化威胁活动的细微指示器的定位。</span><span class="sxs-lookup"><span data-stu-id="275bd-168">[Advanced hunting](advanced-hunting-overview.md) provides a query interface based on Kusto Query Language that simplifies locating subtle indicators of threat activity.</span></span> <span data-ttu-id="275bd-169">它还允许你显示上下文信息并验证指示器是否已连接到威胁。</span><span class="sxs-lookup"><span data-stu-id="275bd-169">It also allows you to surface contextual information and verify whether indicators are connected to a threat.</span></span>

<span data-ttu-id="275bd-170">分析报告中的高级搜寻查询已经过 Microsoft 分析师审查，可随时在高级搜寻 [查询编辑器中运行](https://securitycenter.windows.com/advanced-hunting)。</span><span class="sxs-lookup"><span data-stu-id="275bd-170">Advanced hunting queries in the analyst reports have been vetted by Microsoft analysts and are ready for you to run in the [advanced hunting query editor](https://securitycenter.windows.com/advanced-hunting).</span></span> <span data-ttu-id="275bd-171">您还可以使用查询创建自定义 [检测规则，](custom-detection-rules.md) 以触发将来匹配项的警报。</span><span class="sxs-lookup"><span data-stu-id="275bd-171">You can also use the queries to create [custom detection rules](custom-detection-rules.md) that trigger alerts for future matches.</span></span>


## <a name="related-topics"></a><span data-ttu-id="275bd-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="275bd-172">Related topics</span></span>
- [<span data-ttu-id="275bd-173">威胁分析概述</span><span class="sxs-lookup"><span data-stu-id="275bd-173">Threat analytics overview</span></span>](threat-analytics.md)
- [<span data-ttu-id="275bd-174">使用高级搜寻主动查找威胁</span><span class="sxs-lookup"><span data-stu-id="275bd-174">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="275bd-175">自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="275bd-175">Custom detection rules</span></span>](custom-detection-rules.md)