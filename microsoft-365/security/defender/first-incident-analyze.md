---
title: 步骤 1. 会审和分析第一个事件
description: 如何对 Defender 中的第一个事件进行会审并开始Microsoft 365分析。
keywords: 事件， 警报， 调查， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8eb36ca630a9748de07c5cbe84f0e43ef23a47cf
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841074"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a><span data-ttu-id="468b9-105">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="468b9-105">Step 1.</span></span> <span data-ttu-id="468b9-106">会审和分析第一个事件</span><span class="sxs-lookup"><span data-stu-id="468b9-106">Triage and analyze your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="468b9-107">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="468b9-107">**Applies to:**</span></span>
- <span data-ttu-id="468b9-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="468b9-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="468b9-109">当您花时间根据组织标准建立、实施和维护安全措施时，您可以设置安全解决方案来帮助快速识别安全风险和威胁。</span><span class="sxs-lookup"><span data-stu-id="468b9-109">As you spend some time establishing, implementing, and maintaining security measures according to the organization’s standards, you can set up security solutions to help you quickly identify security risks and threats.</span></span> <span data-ttu-id="468b9-110">Microsoft 365Defender 允许你通过单窗格式体验检测、会审和调查事件，你可以找到及时做出决策时需要的信息。</span><span class="sxs-lookup"><span data-stu-id="468b9-110">Microsoft 365 Defender allows you to detect, triage, and investigate incidents through its single-pane-of-glass experience where you can find the information you need to make timely decisions.</span></span> 

<span data-ttu-id="468b9-111">检测到安全事件后，Microsoft 365 Defender 会提供详细信息，你需要对事件或事件进行会审，或将事件安排在其他人的优先级。</span><span class="sxs-lookup"><span data-stu-id="468b9-111">Once a security incident is detected, Microsoft 365 Defender presents details you will need to triage or prioritize an incident or incidents over others.</span></span> <span data-ttu-id="468b9-112">确定优先顺序后，分析员可以专注于调查分配给他们的情况。</span><span class="sxs-lookup"><span data-stu-id="468b9-112">After determining prioritization, analysts can then focus their energy on investigating cases assigned to them.</span></span>

## <a name="detection-by-microsoft-365-defender"></a><span data-ttu-id="468b9-113">通过 Defender Microsoft 365检测</span><span class="sxs-lookup"><span data-stu-id="468b9-113">Detection by Microsoft 365 Defender</span></span>

<span data-ttu-id="468b9-114">Microsoft 365Defender 接收来自多个 Microsoft 安全平台的警报和事件作为检测源，以创建恶意活动的整体图片和上下文。</span><span class="sxs-lookup"><span data-stu-id="468b9-114">Microsoft 365 Defender receives alerts and events from multiple Microsoft security platforms as detection sources to create a holistic picture and context of malicious activity.</span></span> <span data-ttu-id="468b9-115">这些是可能的检测源：</span><span class="sxs-lookup"><span data-stu-id="468b9-115">These are the possible detection sources:</span></span>

- <span data-ttu-id="468b9-116">[Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)是终结点检测和响应解决方案 (EDR) ，它使用 Microsoft Defender 防病毒以及使用 Microsoft 安全中心启用云的高级威胁Graph。</span><span class="sxs-lookup"><span data-stu-id="468b9-116">[Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md) is an endpoint detection and response solution (EDR) that uses Microsoft Defender antivirus as well as cloud-enabled advanced threat protection using Microsoft Security Graph.</span></span> <span data-ttu-id="468b9-117">Defender for Endpoint 是一个统一的平台，用于预防性保护、攻破后检测、自动调查和响应。</span><span class="sxs-lookup"><span data-stu-id="468b9-117">Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="468b9-118">它可保护终结点免受网络威胁的攻击，检测高级攻击和数据泄露，自动执行安全事件，并改进安全状况。</span><span class="sxs-lookup"><span data-stu-id="468b9-118">It protects endpoints from cyberthreats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span> 
- <span data-ttu-id="468b9-119">[Microsoft Defender for Identity](/defender-for-identity/what-is) 是一种基于云的安全解决方案，它使用本地 Active Directory 域服务 (AD DS) 信号识别、检测和调查针对你的组织的高级威胁、泄露的身份和恶意内部操作。</span><span class="sxs-lookup"><span data-stu-id="468b9-119">[Microsoft Defender for Identity](/defender-for-identity/what-is) is a cloud-based security solution that uses your on-premises Active Directory Domain Services (AD DS) signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> 
- <span data-ttu-id="468b9-120">[Microsoft Cloud App Security](/cloud-app-security/)充当网关人，在企业用户和用户使用的云资源之间实时代理访问，无论用户位于何处，无论他们使用何种设备。</span><span class="sxs-lookup"><span data-stu-id="468b9-120">[Microsoft Cloud App Security](/cloud-app-security/) acts as a gatekeeper to broker access in real time between your enterprise users and the cloud resources they use, wherever your users are located and regardless of the device they are using.</span></span> 
- <span data-ttu-id="468b9-121">[Microsoft Defender for Office 365](../office-365-security/overview.md)保护你的组织免受电子邮件、链接 (URL) 和协作工具中的恶意威胁。</span><span class="sxs-lookup"><span data-stu-id="468b9-121">[Microsoft Defender for Office 365](../office-365-security/overview.md) safeguards your organization against malicious threats in email messages, links (URLs), and collaboration tools.</span></span> 
- <span data-ttu-id="468b9-122">[Azure 安全](/azure/security-center/security-center-introduction) 中心是一个统一的基础结构安全管理系统，可增强数据中心的安全状态，并跨云和本地混合工作负载提供高级威胁防护。</span><span class="sxs-lookup"><span data-stu-id="468b9-122">[Azure Security Center](/azure/security-center/security-center-introduction) is a unified infrastructure security management system that strengthens the security posture of your data centers and provides advanced threat protection across your hybrid workloads in the cloud as well as on premises.</span></span> 

<span data-ttu-id="468b9-123">在 Microsoft 365 Defender[中，](incidents-overview.md)通过关联来自这些不同检测源的警报来标识事件。</span><span class="sxs-lookup"><span data-stu-id="468b9-123">In Microsoft 365 Defender, [incidents](incidents-overview.md) are identified by correlating alerts from these different detection sources.</span></span> <span data-ttu-id="468b9-124">你可以立即开始使用 defender 中的事件队列，而不是花费资源在一起或将多个警报区分到其各自事件中Microsoft 365队列。</span><span class="sxs-lookup"><span data-stu-id="468b9-124">Instead of spending resources stringing together or distinguishing multiple alerts into their respective incidents, you can start with the incident queue in Microsoft 365 Defender right away.</span></span> <span data-ttu-id="468b9-125">这使你可以有效地跨终结点、标识、电子邮件和应用程序对事件进行会审，并减少攻击造成的损失。</span><span class="sxs-lookup"><span data-stu-id="468b9-125">This allows you to triage incidents in an efficient manner across endpoints, identities, email, and applications, and reduce the damage from an attack.</span></span>

## <a name="triage-your-incidents"></a><span data-ttu-id="468b9-126">对事件进行会审</span><span class="sxs-lookup"><span data-stu-id="468b9-126">Triage your incidents</span></span>

<span data-ttu-id="468b9-127">使用组织Microsoft 365优先顺序对事件列表分类后，Defender 中的事件响应将启动。</span><span class="sxs-lookup"><span data-stu-id="468b9-127">Incident response in Microsoft 365 Defender starts once you triage the list of incidents using your organization’s recommended method of prioritization.</span></span> <span data-ttu-id="468b9-128">会审是指为事件分配重要性级别或紧急程度，然后确定调查事件的顺序。</span><span class="sxs-lookup"><span data-stu-id="468b9-128">To triage means to assign a level of importance or urgency to incidents, which then determines the order in which they will be investigated.</span></span> 

<span data-ttu-id="468b9-129">一个有用的示例指南，用于确定在 Microsoft 365 Defender 中应优先处理的事件，公式如下：严重性 *+ 影响 = 优先级*。</span><span class="sxs-lookup"><span data-stu-id="468b9-129">A useful sample guide for determining which incident to prioritize in Microsoft 365 Defender can be summarized by the formula: *Severity + Impact = Priority*.</span></span> 

- <span data-ttu-id="468b9-130">**严重性** 是由 defender 及其Microsoft 365安全组件指定的级别。</span><span class="sxs-lookup"><span data-stu-id="468b9-130">**Severity** is the level designated by Microsoft 365 Defender and its integrated security components.</span></span> 
- <span data-ttu-id="468b9-131">影响由组织确定，通常包括但不限于受影响的用户、设备、受影响服务的阈值 (或其组合) ，甚至警报类型。</span><span class="sxs-lookup"><span data-stu-id="468b9-131">**Impact** is determined by the organization and generally includes, but not limited to, a threshold number of impacted users, devices, services affected (or a combination thereof), and even alert type.</span></span> 

<span data-ttu-id="468b9-132">然后，分析员根据组织设置的 **优先级** 条件启动调查。</span><span class="sxs-lookup"><span data-stu-id="468b9-132">Analysts then initiate investigations based on the **Priority** criteria set by the organization.</span></span>

<span data-ttu-id="468b9-133">事件优先顺序可能因组织而异。</span><span class="sxs-lookup"><span data-stu-id="468b9-133">Incident prioritization might vary depending on the organization.</span></span> <span data-ttu-id="468b9-134">NIST 还建议考虑事件的功能和信息影响以及可恢复性。</span><span class="sxs-lookup"><span data-stu-id="468b9-134">NIST recommends also considering the functional and informational impact of the incident, and recoverability.</span></span>  

<span data-ttu-id="468b9-135">下面只是一种会审方法：</span><span class="sxs-lookup"><span data-stu-id="468b9-135">The following is just one approach to triage:</span></span> 

1. <span data-ttu-id="468b9-136">转到事件 [页面](incidents-overview.md) 以启动会审。</span><span class="sxs-lookup"><span data-stu-id="468b9-136">Go to the [incidents](incidents-overview.md) page to initiate triage.</span></span> <span data-ttu-id="468b9-137">你可以在此处查看影响组织的事件列表。</span><span class="sxs-lookup"><span data-stu-id="468b9-137">Here you can see a list of incidents affecting your organization.</span></span> <span data-ttu-id="468b9-138">默认情况下，它们从最近的事件到最早的事件进行排列。</span><span class="sxs-lookup"><span data-stu-id="468b9-138">By default, they are arranged from the most recent to the oldest incident.</span></span> <span data-ttu-id="468b9-139">在此处，您还可以查看每个事件的不同列，这些列显示其严重性、类别、活动警报数量以及影响的实体等等。</span><span class="sxs-lookup"><span data-stu-id="468b9-139">From here, you can also see different columns for each incident showing their severity, category, number of active alerts, and impacted entities, among others.</span></span> <span data-ttu-id="468b9-140">您可以通过选择列名称来自定义列集，并按这些列中的一些列对事件队列进行排序。</span><span class="sxs-lookup"><span data-stu-id="468b9-140">You can customize the set of columns and sort the incident queue by some these columns by selecting the column name.</span></span> <span data-ttu-id="468b9-141">您还可以根据需求筛选事件队列。</span><span class="sxs-lookup"><span data-stu-id="468b9-141">You can also filter the incident queue according to your needs.</span></span> <span data-ttu-id="468b9-142">有关可用筛选器的完整列表，请参阅确定 [事件的优先级](incident-queue.md#available-filters)。</span><span class="sxs-lookup"><span data-stu-id="468b9-142">For a full list of available filters, see [Prioritize incidents](incident-queue.md#available-filters).</span></span>
  
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="事件队列示例"::: 

    <span data-ttu-id="468b9-144">如何对此组事件执行会审的一个示例是确定影响更多用户和设备的事件的优先级。</span><span class="sxs-lookup"><span data-stu-id="468b9-144">One example of how you might perform triage for this set of incidents is to prioritize incidents that affected more users and devices.</span></span> <span data-ttu-id="468b9-145">本示例中，可能会设置事件 ID 6769 的优先级，因为它影响最多数量的实体：7 个设备、6 个用户和 2 个邮箱。</span><span class="sxs-lookup"><span data-stu-id="468b9-145">In this example, you might prioritize incident ID 6769 because it affected the largest number of entities: 7 devices, 6 users, and 2 mailboxes.</span></span> <span data-ttu-id="468b9-146">此外，事件似乎包含来自 Microsoft Defender for Identity 的警报，这些警报指示基于标识的警报和可能的凭据盗窃。</span><span class="sxs-lookup"><span data-stu-id="468b9-146">Furthermore, the incident appears to contain alerts from Microsoft Defender for Identity which indicate an identity-based alert and possible credential theft.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="影响很大事件的示例":::
 
2. <span data-ttu-id="468b9-148">选择事件名称旁边的圆圈查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="468b9-148">Select the circle next to the incident name to review the details.</span></span> <span data-ttu-id="468b9-149">侧窗格将显示在右侧，其中包含可进一步帮助你分类的其他信息。</span><span class="sxs-lookup"><span data-stu-id="468b9-149">A side pane will appear on the right side, which contains additional information that can assist your triage further.</span></span> 
 
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="事件侧窗格示例"::: 

   <span data-ttu-id="468b9-151">例如，通过查看攻击者基于事件类别使用的 [MITRE ATT&CK](https://attack.mitre.org/) 策略，你可能会确定此事件的优先级，因为攻击者使用了被盗的凭据、建立了命令和控制、执行了横向移动并窃取了一些数据。</span><span class="sxs-lookup"><span data-stu-id="468b9-151">For example, by looking at which [MITRE ATT&CK](https://attack.mitre.org/) tactics the attacker used based on the incident’s categories, you might prioritize this incident because the attacker used stolen credentials, established command and control, performed lateral movement, and exfiltrated some data.</span></span> <span data-ttu-id="468b9-152">这表明攻击者已深入网络，并且可能会窃取机密信息。</span><span class="sxs-lookup"><span data-stu-id="468b9-152">This suggests the attacker has already gone deep into the network and possibly stolen confidential information.</span></span>

   <span data-ttu-id="468b9-153">此外，如果你的组织已实施零信任框架，则你将凭据访问视为一种重要的安全冲突，值得优先处理。</span><span class="sxs-lookup"><span data-stu-id="468b9-153">Additionally, if your organization has implemented the Zero Trust framework, you would consider credential access as an important security violation worth prioritizing.</span></span>
 
   <span data-ttu-id="468b9-154">向下滚动侧窗格，你将看到特定受到影响的实体，如用户、设备和邮箱。</span><span class="sxs-lookup"><span data-stu-id="468b9-154">Scrolling down the side pane, you will see the specific impacted entities such as users, devices, and mailboxes.</span></span> <span data-ttu-id="468b9-155">你可以检查每台设备的曝光级别和受影响邮箱的所有者。</span><span class="sxs-lookup"><span data-stu-id="468b9-155">You can check the exposure level of each device and the owners of affected mailboxes.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="事件侧窗格详细信息的示例"::: 
 
3. <span data-ttu-id="468b9-157">在侧窗格的更下一步，你可以找到关联的警报。</span><span class="sxs-lookup"><span data-stu-id="468b9-157">Further down the side pane, you can find the associated alerts.</span></span> <span data-ttu-id="468b9-158">Microsoft 365Defender 已经对单个事件执行相关警报，从而节省你修正攻击所花的时间和资源。</span><span class="sxs-lookup"><span data-stu-id="468b9-158">Microsoft 365 Defender has already performed the correlation of said alerts into a single incident, saving you time and resources better spent remediating the attack.</span></span> <span data-ttu-id="468b9-159">警报是可疑的，因此可能是恶意系统事件，这些事件表示网络上存在攻击者。</span><span class="sxs-lookup"><span data-stu-id="468b9-159">Alerts are suspicious and therefore possibly malicious system events that suggest the presence of an attacker on a network.</span></span> 

   <span data-ttu-id="468b9-160">本示例中，87 个单独警报被确定为一个安全事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="468b9-160">In this example, 87 individual alerts were determined to be part of one security incident.</span></span> <span data-ttu-id="468b9-161">你可以查看所有警报，快速了解攻击的播放。</span><span class="sxs-lookup"><span data-stu-id="468b9-161">You can view all the alerts to get a quick view of how the attack played out.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="事件侧窗格中的警报示例"::: 
 
## <a name="analyze-your-first-incident"></a><span data-ttu-id="468b9-163">分析第一个事件</span><span class="sxs-lookup"><span data-stu-id="468b9-163">Analyze your first incident</span></span>

<span data-ttu-id="468b9-164">了解警报周围的上下文同样重要。</span><span class="sxs-lookup"><span data-stu-id="468b9-164">Understanding the context surrounding alerts is equally important.</span></span> <span data-ttu-id="468b9-165">通常，警报不是单个独立事件。</span><span class="sxs-lookup"><span data-stu-id="468b9-165">Often an alert is not a single independent event.</span></span> <span data-ttu-id="468b9-166">存在一系列可能未同时发生的进程、命令和操作。</span><span class="sxs-lookup"><span data-stu-id="468b9-166">There is a chain of processes created, commands, and actions that might not have occurred at the same time.</span></span> <span data-ttu-id="468b9-167">因此，分析员必须在设备时间线中查找可疑实体的第一个和最后一个活动，以了解警报的上下文。</span><span class="sxs-lookup"><span data-stu-id="468b9-167">Therefore, an analyst must look for the first and last activities of the suspicious entity in device timelines to understand the context of the alerts.</span></span>

<span data-ttu-id="468b9-168">使用 defender 读取和分析数据的方法有多种Microsoft 365，但分析员的最终目标是尽快响应事件。</span><span class="sxs-lookup"><span data-stu-id="468b9-168">There are multiple ways to read and analyze data using Microsoft 365 Defender but the end goal for analysts is to respond to incidents as quickly as possible.</span></span> <span data-ttu-id="468b9-169">尽管 Microsoft 365 Defender 可以通过行业领先的自动调查和响应功能大大减少修正 MTTR ([MTTR](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/)) 平均时间，但始终[](m365d-autoir.md)存在需要手动分析的情况。</span><span class="sxs-lookup"><span data-stu-id="468b9-169">While Microsoft 365 Defender can significantly reduce [Mean Time to Remediate (MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) through the industry-leading [automated investigation and response](m365d-autoir.md) feature, there are always cases that require manual analysis.</span></span> 

<span data-ttu-id="468b9-170">示例如下：</span><span class="sxs-lookup"><span data-stu-id="468b9-170">Here's an example:</span></span>

1. <span data-ttu-id="468b9-171">确定会审优先级后，分析员通过选择事件名称开始深入分析。</span><span class="sxs-lookup"><span data-stu-id="468b9-171">Once triage priority has been determined, an analyst begins an in-depth analysis by selecting the incident name.</span></span> <span data-ttu-id="468b9-172">此页面将显示"事件 **摘要** "，其中数据显示在选项卡中，以帮助进行分析。</span><span class="sxs-lookup"><span data-stu-id="468b9-172">This page brings up the **Incident Summary** where data is displayed in tabs to assist with the analysis.</span></span> <span data-ttu-id="468b9-173">在 **"警报"** 选项卡下，将显示警报类型。</span><span class="sxs-lookup"><span data-stu-id="468b9-173">Under the **Alerts** tab the type of alerts are displayed.</span></span> <span data-ttu-id="468b9-174">分析员可以单击每个警报，向下钻取到各自的检测源。</span><span class="sxs-lookup"><span data-stu-id="468b9-174">Analysts can click on each alert to drill down into the respective detection source.</span></span> 

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="事件&quot;摘要&quot;选项卡的示例"::: 
 
    <span data-ttu-id="468b9-176">有关每个检测源涵盖的域的快速指南，请查看本文的 [检测](#detection-by-microsoft-365-defender) 部分。</span><span class="sxs-lookup"><span data-stu-id="468b9-176">For a quick guide about which domain each detection source covers, review the [Detect](#detection-by-microsoft-365-defender) section of this article.</span></span>

2.  <span data-ttu-id="468b9-177">从 **警报选项卡** ，分析员可以透视到检测源，以执行更深入的调查和分析。</span><span class="sxs-lookup"><span data-stu-id="468b9-177">From the **Alerts** tab, an analyst can pivot to the detection source to conduct a more in-depth investigation and analysis.</span></span> <span data-ttu-id="468b9-178">例如，选择"恶意软件检测Microsoft Cloud App Security作为检测源，分析员将访问其相应的警报页面。</span><span class="sxs-lookup"><span data-stu-id="468b9-178">For example, selecting Malware Detection with Microsoft Cloud App Security as the detection source takes the analyst to its corresponding alert page.</span></span>
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="选择事件警报的示例"::: 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="页面中相应页面Microsoft Cloud App Security"::: 
  
3.  <span data-ttu-id="468b9-181">若要进一步调查我们的示例，请滚动到页面底部以查看受影响的 **用户**。</span><span class="sxs-lookup"><span data-stu-id="468b9-181">To investigate our example further, scrolling to the bottom of the page to view the **Users affected**.</span></span> <span data-ttu-id="468b9-182">To see the activity and context surrounding the malware detection， select Annette Hill's user page .</span><span class="sxs-lookup"><span data-stu-id="468b9-182">To see the activity and context surrounding the malware detection, select Annette Hill’s user page .</span></span> 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="用户页面示例":::
  
4.  <span data-ttu-id="468b9-184">在用户页面上，按时间顺序排列的事件列表，从 *TOR* 网络 IP 地址警报的有风险登录开始。</span><span class="sxs-lookup"><span data-stu-id="468b9-184">On the user page is a chronological list of events starting with a *Risky Sign-in from a TOR network IP Address* alert.</span></span> <span data-ttu-id="468b9-185">虽然活动的可疑程度取决于组织如何开展业务的性质，但在大多数情况下，使用 Onion 路由器 (TOR) （允许用户在企业环境中匿名浏览 Web 的网络）对于常规联机操作可能被视为不太可能和不必要的。</span><span class="sxs-lookup"><span data-stu-id="468b9-185">While the suspiciousness of an activity depends on the nature of how an organization conducts its business, in most cases the use of The Onion Router (TOR), a network that allows users to browse the web anonymously, in an enterprise environment might be considered highly unlikely and unnecessary for regular online operations.</span></span>
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="用户事件按时间顺序列表的示例":::
  
5.  <span data-ttu-id="468b9-187">可以选择每个警报以获取有关活动详细信息。</span><span class="sxs-lookup"><span data-stu-id="468b9-187">Each alert can be selected to obtain more information on the activity.</span></span> <span data-ttu-id="468b9-188">例如，从 **"Tor IP** 地址"警报中选择"活动"将引导你访问该警报自己的页面。</span><span class="sxs-lookup"><span data-stu-id="468b9-188">For example, selecting **Activity from a Tor IP Address** alert leads you to that alert’s own page.</span></span> <span data-ttu-id="468b9-189">Annette 是 Office 365 管理员，这意味着她具有提升的权限，并且源事件可能导致访问机密信息。</span><span class="sxs-lookup"><span data-stu-id="468b9-189">Annette is an Administrator of Office 365, which means she has elevated privileges and the source incident might have led to access to confidential information.</span></span> 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="适用于用户警报的详细信息Microsoft Cloud App Security"::: 
 
6.  <span data-ttu-id="468b9-191">通过选择其他警报，分析员可以全面了解攻击情况。</span><span class="sxs-lookup"><span data-stu-id="468b9-191">By selecting other alerts, an analyst can get a complete picture of the attack.</span></span>

## <a name="next-step"></a><span data-ttu-id="468b9-192">后续步骤</span><span class="sxs-lookup"><span data-stu-id="468b9-192">Next step</span></span>

<span data-ttu-id="468b9-193">[![步骤 2：了解如何修正事件](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)</span><span class="sxs-lookup"><span data-stu-id="468b9-193">[![Step 2: Learn how to remediate incidents](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)</span></span>

<span data-ttu-id="468b9-194">了解如何 [修正事件](first-incident-remediate.md)。</span><span class="sxs-lookup"><span data-stu-id="468b9-194">Learn how to [remediate incidents](first-incident-remediate.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="468b9-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="468b9-195">See also</span></span>

- [<span data-ttu-id="468b9-196">事件概述</span><span class="sxs-lookup"><span data-stu-id="468b9-196">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="468b9-197">调查事件</span><span class="sxs-lookup"><span data-stu-id="468b9-197">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="468b9-198">管理事件</span><span class="sxs-lookup"><span data-stu-id="468b9-198">Manage incidents</span></span>](manage-incidents.md)
