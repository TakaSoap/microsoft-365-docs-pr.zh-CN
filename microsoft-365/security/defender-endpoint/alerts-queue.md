---
title: 查看和组织 Microsoft Defender 终结点警报队列
description: 了解 Microsoft Defender for Endpoint 警报队列如何工作，以及如何对警报列表进行排序和筛选。
keywords: 警报， 队列， 警报队列， 排序， 顺序， 筛选， 管理警报， 新， 正在进行， 已解决， 最新， 队列中的时间， 严重性， 时间段， Microsoft 威胁专家警报
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
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 48a3ff8dba5bccd62d7d43b295c136a814056a15
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934329"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a><span data-ttu-id="ba9ad-104">查看和组织 Microsoft Defender 终结点警报队列</span><span class="sxs-lookup"><span data-stu-id="ba9ad-104">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ba9ad-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ba9ad-105">**Applies to:**</span></span>
- [<span data-ttu-id="ba9ad-106">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ba9ad-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="ba9ad-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="ba9ad-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ba9ad-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-alertsq-abovefoldlink) 

<span data-ttu-id="ba9ad-109">**警报队列** 显示从网络中设备标记的警报列表。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-109">The **Alerts queue** shows a list of alerts that were flagged from devices in your network.</span></span> <span data-ttu-id="ba9ad-110">默认情况下，队列在分组视图中显示最近 30 天内看到的警报。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-110">By default, the queue displays alerts seen in the last 30 days in a grouped view.</span></span> <span data-ttu-id="ba9ad-111">最新警报在列表顶部显示，有助于你先查看最新警报。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-111">The most recent alerts are showed at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="ba9ad-112">通过自动调查和修正显著减少警报队列，使安全运营专家可以专注于更复杂的威胁和其他高价值计划。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-112">The alerts queue is significantly reduced with automated investigation and remediation, allowing security operations experts to focus on more sophisticated threats and other high value initiatives.</span></span> <span data-ttu-id="ba9ad-113">当警报包含用于自动调查的支持实体 (例如，文件) 支持的操作系统的设备中，可以启动自动调查和修正。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-113">When an alert contains a supported entity for automated investigation (for example, a file) in a device that has a supported operating system for it, an automated investigation and remediation can start.</span></span> <span data-ttu-id="ba9ad-114">有关自动调查详细信息，请参阅 [自动调查概述](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-114">For more information on automated investigations, see [Overview of Automated investigations](automated-investigations.md).</span></span>

<span data-ttu-id="ba9ad-115">有几种选项可供选择以自定义警报队列视图。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-115">There are several options you can choose from to customize the alerts queue view.</span></span> 

<span data-ttu-id="ba9ad-116">在顶部导航上，你可以：</span><span class="sxs-lookup"><span data-stu-id="ba9ad-116">On the top navigation you can:</span></span>

- <span data-ttu-id="ba9ad-117">选择分组视图或列表视图</span><span class="sxs-lookup"><span data-stu-id="ba9ad-117">Select grouped view or list view</span></span>
- <span data-ttu-id="ba9ad-118">自定义列以添加或删除列</span><span class="sxs-lookup"><span data-stu-id="ba9ad-118">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="ba9ad-119">选择要按页显示的项目</span><span class="sxs-lookup"><span data-stu-id="ba9ad-119">Select the items to show per page</span></span>
- <span data-ttu-id="ba9ad-120">在页面之间导航</span><span class="sxs-lookup"><span data-stu-id="ba9ad-120">Navigate between pages</span></span>
- <span data-ttu-id="ba9ad-121">应用筛选器</span><span class="sxs-lookup"><span data-stu-id="ba9ad-121">Apply filters</span></span>

![警报队列的图像](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a><span data-ttu-id="ba9ad-123">对警报队列进行排序、筛选和分组</span><span class="sxs-lookup"><span data-stu-id="ba9ad-123">Sort, filter, and group the alerts queue</span></span>

<span data-ttu-id="ba9ad-124">可以应用以下筛选器来限制警报列表，并更集中地查看警报。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-124">You can apply the following filters to limit the list of alerts and get a more focused view the alerts.</span></span>

### <a name="severity"></a><span data-ttu-id="ba9ad-125">Severity</span><span class="sxs-lookup"><span data-stu-id="ba9ad-125">Severity</span></span>

<span data-ttu-id="ba9ad-126">警报严重性</span><span class="sxs-lookup"><span data-stu-id="ba9ad-126">Alert severity</span></span> | <span data-ttu-id="ba9ad-127">说明</span><span class="sxs-lookup"><span data-stu-id="ba9ad-127">Description</span></span>
:---|:---
<span data-ttu-id="ba9ad-128">高</span><span class="sxs-lookup"><span data-stu-id="ba9ad-128">High</span></span> </br><span data-ttu-id="ba9ad-129"> (红色) </span><span class="sxs-lookup"><span data-stu-id="ba9ad-129">(Red)</span></span> | <span data-ttu-id="ba9ad-130">通常看到的与 APT 高级永久性威胁 (警报) 。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-130">Alerts commonly seen associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="ba9ad-131">这些警报表明存在高风险，因为它们可能会损坏设备的严重性。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-131">These alerts indicate a high risk because of  the severity of damage they can inflict on devices.</span></span> <span data-ttu-id="ba9ad-132">例如：凭据盗窃工具活动、未与任何组关联的勒索软件活动、篡改安全传感器或任何恶意活动，这些活动会指示人类对手。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-132">Some examples are: credential theft tools activities, ransomware activities not associated with any group, tampering with security sensors, or any malicious activities indicative of a human adversary.</span></span>
<span data-ttu-id="ba9ad-133">中</span><span class="sxs-lookup"><span data-stu-id="ba9ad-133">Medium</span></span> </br><span data-ttu-id="ba9ad-134"> (橙色) </span><span class="sxs-lookup"><span data-stu-id="ba9ad-134">(Orange)</span></span> | <span data-ttu-id="ba9ad-135">终结点检测和响应泄露后行为的警报，这些警报可能是 APT 高级永久性威胁 (的) 。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-135">Alerts from endpoint detection and response post-breach behaviors that might be a part of an advanced persistent threat (APT).</span></span> <span data-ttu-id="ba9ad-136">这包括观察到的攻击阶段的典型行为、异常注册表更改、执行可疑文件等。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-136">This includes observed behaviors typical of attack stages, anomalous registry change, execution of suspicious files, and so forth.</span></span> <span data-ttu-id="ba9ad-137">尽管其中一些可能是内部安全测试的一部分，但它需要进行调查，因为它也可能属于高级攻击。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-137">Although some might be part of internal security testing, it requires investigation as it might also be a part of an advanced attack.</span></span>
<span data-ttu-id="ba9ad-138">低</span><span class="sxs-lookup"><span data-stu-id="ba9ad-138">Low</span></span> </br><span data-ttu-id="ba9ad-139"> (黄色) </span><span class="sxs-lookup"><span data-stu-id="ba9ad-139">(Yellow)</span></span> | <span data-ttu-id="ba9ad-140">与流行恶意软件相关的威胁警报。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-140">Alerts on threats associated with prevalent malware.</span></span> <span data-ttu-id="ba9ad-141">例如，黑客工具、非恶意软件黑客工具（如运行探索命令、清除日志等）通常不会指示面向组织的高级威胁。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-141">For example, hack-tools, non-malware hack tools, such as running exploration commands, clearing logs, etc., that often do not indicate an advanced threat targeting the organization.</span></span> <span data-ttu-id="ba9ad-142">它还可能来自组织中用户隔离的安全工具测试。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-142">It could also come from an isolated security tool testing by a user in your organization.</span></span>
<span data-ttu-id="ba9ad-143">信息</span><span class="sxs-lookup"><span data-stu-id="ba9ad-143">Informational</span></span> </br><span data-ttu-id="ba9ad-144"> (灰色) </span><span class="sxs-lookup"><span data-stu-id="ba9ad-144">(Grey)</span></span> | <span data-ttu-id="ba9ad-145">可能被视为对网络有害的警报，但可以提升组织对潜在安全问题的安全意识。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-145">Alerts that might not be considered harmful to the network but can drive organizational security awareness on potential security issues.</span></span>

#### <a name="understanding-alert-severity"></a><span data-ttu-id="ba9ad-146">了解警报严重性</span><span class="sxs-lookup"><span data-stu-id="ba9ad-146">Understanding alert severity</span></span>

<span data-ttu-id="ba9ad-147">Microsoft Defender 防病毒 (Microsoft Defender AV) 和 Defender for Endpoint 警报严重性不同，因为它们表示不同的作用域。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-147">Microsoft Defender Antivirus (Microsoft Defender AV) and Defender for Endpoint alert severities are different because they represent different scopes.</span></span>

<span data-ttu-id="ba9ad-148">Microsoft Defender AV 威胁严重性表示检测到的威胁 (恶意软件) 的绝对严重性，如果受到感染，则根据单个设备的潜在风险进行分配。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-148">The Microsoft Defender AV threat severity represents the absolute severity of the detected threat (malware), and is assigned based on the potential risk to the individual device, if infected.</span></span>

<span data-ttu-id="ba9ad-149">Defender for Endpoint 警报严重性表示检测到的行为的严重性，即设备的实际风险，但更重要的是对组织带来潜在风险。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-149">The Defender for Endpoint alert severity represents the severity of the detected behavior, the actual risk to the device but more importantly the potential risk to the organization.</span></span>

<span data-ttu-id="ba9ad-150">例如：</span><span class="sxs-lookup"><span data-stu-id="ba9ad-150">So, for example:</span></span>

- <span data-ttu-id="ba9ad-151">有关 Microsoft Defender AV 检测到的、已完全阻止且未感染设备的威胁的 Defender for Endpoint 警报的严重性被归类为"信息"，因为没有实际损害。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-151">The severity of a Defender for Endpoint alert about a Microsoft Defender AV detected threat that was completely prevented and did not infect the device is categorized as "Informational" because there was no actual damage.</span></span>
- <span data-ttu-id="ba9ad-152">有关商业恶意软件的警报在执行时被检测到，但被 Microsoft Defender AV 阻止和修复，被分类为"低"，因为它可能给单个设备造成一些损坏，但不构成组织威胁。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-152">An alert about a commercial malware was detected while executing, but blocked and remediated by Microsoft Defender AV, is categorized as  "Low" because it may have caused some damage to the individual device but poses no organizational threat.</span></span>
- <span data-ttu-id="ba9ad-153">有关在执行时检测到的恶意软件的警报，不仅会对单个设备带来威胁，而且会对组织造成威胁，无论最终是否被阻止，其排名可能为"中"或"高"。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-153">An alert about malware detected while executing which can pose a threat not only to the individual device but to the organization, regardless if it was eventually blocked, may be ranked as "Medium" or "High".</span></span>
- <span data-ttu-id="ba9ad-154">根据相同的组织威胁注意事项，未阻止或修正的可疑行为警报将被排名为"低"、"中"或"高"。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-154">Suspicious behavioral alerts, which weren't blocked or remediated will be ranked "Low", "Medium" or "High" following the same organizational threat considerations.</span></span>

#### <a name="understanding-alert-categories"></a><span data-ttu-id="ba9ad-155">了解警报类别</span><span class="sxs-lookup"><span data-stu-id="ba9ad-155">Understanding alert categories</span></span>

<span data-ttu-id="ba9ad-156">我们重新定义了警报类别，以与 MITRE [](https://attack.mitre.org/tactics/enterprise/) ATT 和 CK 矩阵中的企业&[策略一致](https://attack.mitre.org/)。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-156">We've redefined the alert categories to align to the [enterprise attack tactics](https://attack.mitre.org/tactics/enterprise/) in the [MITRE ATT&CK matrix](https://attack.mitre.org/).</span></span> <span data-ttu-id="ba9ad-157">新类别名称适用于所有新警报。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-157">New category names apply to all new alerts.</span></span> <span data-ttu-id="ba9ad-158">现有警报将保留以前的类别名称。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-158">Existing alerts will keep the previous category names.</span></span>

<span data-ttu-id="ba9ad-159">下表列出了当前类别及其通常如何映射到以前的类别。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-159">The table below lists the current categories and how they generally map to previous categories.</span></span> 

| <span data-ttu-id="ba9ad-160">新类别</span><span class="sxs-lookup"><span data-stu-id="ba9ad-160">New   category</span></span>       | <span data-ttu-id="ba9ad-161">API 类别名称</span><span class="sxs-lookup"><span data-stu-id="ba9ad-161">API category name</span></span>   | <span data-ttu-id="ba9ad-162">检测到威胁活动或组件</span><span class="sxs-lookup"><span data-stu-id="ba9ad-162">Detected threat activity or   component</span></span>                                                                                                 |
|----------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ba9ad-163">集合</span><span class="sxs-lookup"><span data-stu-id="ba9ad-163">Collection</span></span>           | <span data-ttu-id="ba9ad-164">集合</span><span class="sxs-lookup"><span data-stu-id="ba9ad-164">Collection</span></span>          | <span data-ttu-id="ba9ad-165">定位和收集数据以用于筛选</span><span class="sxs-lookup"><span data-stu-id="ba9ad-165">Locating   and collecting data for exfiltration</span></span>                                                                                         |
| <span data-ttu-id="ba9ad-166">命令和控件</span><span class="sxs-lookup"><span data-stu-id="ba9ad-166">Command and control</span></span>  | <span data-ttu-id="ba9ad-167">CommandAndControl</span><span class="sxs-lookup"><span data-stu-id="ba9ad-167">CommandAndControl</span></span>   | <span data-ttu-id="ba9ad-168">连接到攻击者控制的网络基础结构以中继数据或接收命令</span><span class="sxs-lookup"><span data-stu-id="ba9ad-168">Connecting   to attacker-controlled network infrastructure to relay data or receive   commands</span></span>                                          |
| <span data-ttu-id="ba9ad-169">凭据访问</span><span class="sxs-lookup"><span data-stu-id="ba9ad-169">Credential access</span></span>    | <span data-ttu-id="ba9ad-170">CredentialAccess</span><span class="sxs-lookup"><span data-stu-id="ba9ad-170">CredentialAccess</span></span>    | <span data-ttu-id="ba9ad-171">获取有效凭据以扩展对网络中设备和其他资源的控制</span><span class="sxs-lookup"><span data-stu-id="ba9ad-171">Obtaining   valid credentials to extend control over devices and other resources in the   network</span></span>                                       |
| <span data-ttu-id="ba9ad-172">防御者</span><span class="sxs-lookup"><span data-stu-id="ba9ad-172">Defense evasion</span></span>      | <span data-ttu-id="ba9ad-173">DefenseEvasion</span><span class="sxs-lookup"><span data-stu-id="ba9ad-173">DefenseEvasion</span></span>      | <span data-ttu-id="ba9ad-174">例如，通过关闭安全应用、删除芯片和运行 rootkit 来避免安全控制</span><span class="sxs-lookup"><span data-stu-id="ba9ad-174">Avoiding security controls by, for example, turning off   security apps, deleting implants, and running rootkits</span></span>                        |
| <span data-ttu-id="ba9ad-175">Discovery</span><span class="sxs-lookup"><span data-stu-id="ba9ad-175">Discovery</span></span>            | <span data-ttu-id="ba9ad-176">Discovery</span><span class="sxs-lookup"><span data-stu-id="ba9ad-176">Discovery</span></span>           | <span data-ttu-id="ba9ad-177">收集有关重要设备和资源（如管理员计算机、域控制器和文件服务器）的信息</span><span class="sxs-lookup"><span data-stu-id="ba9ad-177">Gathering   information about important devices and resources, such as administrator   computers, domain controllers, and file servers</span></span>  |
| <span data-ttu-id="ba9ad-178">执行</span><span class="sxs-lookup"><span data-stu-id="ba9ad-178">Execution</span></span>            | <span data-ttu-id="ba9ad-179">执行</span><span class="sxs-lookup"><span data-stu-id="ba9ad-179">Execution</span></span>           | <span data-ttu-id="ba9ad-180">启动攻击者工具和恶意代码，包括 RAT 和后门</span><span class="sxs-lookup"><span data-stu-id="ba9ad-180">Launching   attacker tools and malicious code, including RATs and backdoors</span></span>                                                             |
| <span data-ttu-id="ba9ad-181">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="ba9ad-181">Exfiltration</span></span>         | <span data-ttu-id="ba9ad-182">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="ba9ad-182">Exfiltration</span></span>        | <span data-ttu-id="ba9ad-183">将数据从网络提取到外部攻击者控制的位置</span><span class="sxs-lookup"><span data-stu-id="ba9ad-183">Extracting   data from the network to an external, attacker-controlled location</span></span>                                                         |
| <span data-ttu-id="ba9ad-184">攻击</span><span class="sxs-lookup"><span data-stu-id="ba9ad-184">Exploit</span></span>              | <span data-ttu-id="ba9ad-185">攻击</span><span class="sxs-lookup"><span data-stu-id="ba9ad-185">Exploit</span></span>             | <span data-ttu-id="ba9ad-186">攻击代码和可能的利用活动</span><span class="sxs-lookup"><span data-stu-id="ba9ad-186">Exploit   code and possible exploitation activity</span></span>                                                                                       |
| <span data-ttu-id="ba9ad-187">初始访问</span><span class="sxs-lookup"><span data-stu-id="ba9ad-187">Initial access</span></span>       | <span data-ttu-id="ba9ad-188">InitialAccess</span><span class="sxs-lookup"><span data-stu-id="ba9ad-188">InitialAccess</span></span>       | <span data-ttu-id="ba9ad-189">获取目标网络的初始条目，通常涉及密码猜测、攻击或钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="ba9ad-189">Gaining   initial entry to the target network, usually involving password-guessing,   exploits, or phishing emails</span></span>                      |
| <span data-ttu-id="ba9ad-190">横向移动</span><span class="sxs-lookup"><span data-stu-id="ba9ad-190">Lateral movement</span></span>     | <span data-ttu-id="ba9ad-191">LateralMovement</span><span class="sxs-lookup"><span data-stu-id="ba9ad-191">LateralMovement</span></span>     | <span data-ttu-id="ba9ad-192">在目标网络中设备之间移动以到达关键资源或获取网络持久性</span><span class="sxs-lookup"><span data-stu-id="ba9ad-192">Moving   between devices in the target network to reach critical resources or gain   network persistence</span></span>                                |
| <span data-ttu-id="ba9ad-193">恶意软件</span><span class="sxs-lookup"><span data-stu-id="ba9ad-193">Malware</span></span>              | <span data-ttu-id="ba9ad-194">恶意软件</span><span class="sxs-lookup"><span data-stu-id="ba9ad-194">Malware</span></span>             | <span data-ttu-id="ba9ad-195">后门、特洛伊木马和其他类型的恶意代码</span><span class="sxs-lookup"><span data-stu-id="ba9ad-195">Backdoors,   trojans, and other types of malicious code</span></span>                                                                                 |
| <span data-ttu-id="ba9ad-196">持久性</span><span class="sxs-lookup"><span data-stu-id="ba9ad-196">Persistence</span></span>          | <span data-ttu-id="ba9ad-197">持久性</span><span class="sxs-lookup"><span data-stu-id="ba9ad-197">Persistence</span></span>         | <span data-ttu-id="ba9ad-198">创建自动启动扩展点 (ASP) 以保持活动状态并自系统重启后继续运行</span><span class="sxs-lookup"><span data-stu-id="ba9ad-198">Creating   autostart extensibility points (ASEPs) to remain active and survive system   restarts</span></span>                                        |
| <span data-ttu-id="ba9ad-199">特权提升</span><span class="sxs-lookup"><span data-stu-id="ba9ad-199">Privilege escalation</span></span> | <span data-ttu-id="ba9ad-200">PrivilegeEscalation</span><span class="sxs-lookup"><span data-stu-id="ba9ad-200">PrivilegeEscalation</span></span> | <span data-ttu-id="ba9ad-201">在特权进程或帐户上下文中运行代码，以获取更高权限级别的代码</span><span class="sxs-lookup"><span data-stu-id="ba9ad-201">Obtaining   higher permission levels for code by running it in the context of a   privileged process or account</span></span>                         |
| <span data-ttu-id="ba9ad-202">勒索软件</span><span class="sxs-lookup"><span data-stu-id="ba9ad-202">Ransomware</span></span>           | <span data-ttu-id="ba9ad-203">勒索软件</span><span class="sxs-lookup"><span data-stu-id="ba9ad-203">Ransomware</span></span>          | <span data-ttu-id="ba9ad-204">加密文件和扩展付款以还原访问权限的恶意软件</span><span class="sxs-lookup"><span data-stu-id="ba9ad-204">Malware   that encrypts files and extorts payment to restore access</span></span>                                                                     |
| <span data-ttu-id="ba9ad-205">可疑活动</span><span class="sxs-lookup"><span data-stu-id="ba9ad-205">Suspicious activity</span></span>  | <span data-ttu-id="ba9ad-206">SuspiciousActivity</span><span class="sxs-lookup"><span data-stu-id="ba9ad-206">SuspiciousActivity</span></span>  | <span data-ttu-id="ba9ad-207">可能是恶意软件活动或攻击一部分的非典型活动</span><span class="sxs-lookup"><span data-stu-id="ba9ad-207">Atypical   activity that could be malware activity or part of an attack</span></span>                                                                 |
| <span data-ttu-id="ba9ad-208">不需要的软件</span><span class="sxs-lookup"><span data-stu-id="ba9ad-208">Unwanted software</span></span>    | <span data-ttu-id="ba9ad-209">UnwantedSoftware</span><span class="sxs-lookup"><span data-stu-id="ba9ad-209">UnwantedSoftware</span></span>    | <span data-ttu-id="ba9ad-210">影响工作效率和用户体验的低信誉应用和应用;检测到 PUA 中可能不需要 (应用程序) </span><span class="sxs-lookup"><span data-stu-id="ba9ad-210">Low-reputation   apps and apps that impact productivity and the user experience; detected as   potentially unwanted applications (PUAs)</span></span> |

### <a name="status"></a><span data-ttu-id="ba9ad-211">状态</span><span class="sxs-lookup"><span data-stu-id="ba9ad-211">Status</span></span>

<span data-ttu-id="ba9ad-212">可以选择根据警报的状态限制警报列表。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-212">You can choose to limit the list of alerts based on their status.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="ba9ad-213">调查状态</span><span class="sxs-lookup"><span data-stu-id="ba9ad-213">Investigation state</span></span>

<span data-ttu-id="ba9ad-214">对应于自动调查状态。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-214">Corresponds to the automated investigation state.</span></span>

### <a name="category"></a><span data-ttu-id="ba9ad-215">类别</span><span class="sxs-lookup"><span data-stu-id="ba9ad-215">Category</span></span>

<span data-ttu-id="ba9ad-216">你可以选择筛选队列以显示特定类型的恶意活动。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-216">You can choose to filter the queue to display specific types of malicious activity.</span></span>

### <a name="assigned-to"></a><span data-ttu-id="ba9ad-217">分配到</span><span class="sxs-lookup"><span data-stu-id="ba9ad-217">Assigned to</span></span>

<span data-ttu-id="ba9ad-218">你可以选择显示分配给你的警报还是自动显示。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-218">You can choose between showing alerts that are assigned to you or automation.</span></span>

### <a name="detection-source"></a><span data-ttu-id="ba9ad-219">检测源</span><span class="sxs-lookup"><span data-stu-id="ba9ad-219">Detection source</span></span>

<span data-ttu-id="ba9ad-220">选择触发警报检测的源。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-220">Select the source that triggered the alert detection.</span></span> <span data-ttu-id="ba9ad-221">Microsoft 威胁专家预览参与者现在可以筛选和查看来自新威胁专家托管的搜寻服务的检测。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-221">Microsoft Threat Experts preview participants can now filter and see detections from the new threat experts-managed hunting service.</span></span>

>[!NOTE]
><span data-ttu-id="ba9ad-222">防病毒筛选器仅在设备将 Microsoft Defender 防病毒用作默认的反恶意软件实时保护产品时显示。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-222">The Antivirus filter will only appear if devices are using Microsoft Defender Antivirus as the default real-time protection antimalware product.</span></span>

| <span data-ttu-id="ba9ad-223">检测源</span><span class="sxs-lookup"><span data-stu-id="ba9ad-223">Detection source</span></span>                  | <span data-ttu-id="ba9ad-224">API 值</span><span class="sxs-lookup"><span data-stu-id="ba9ad-224">API value</span></span>                  |
|-----------------------------------|----------------------------|
| <span data-ttu-id="ba9ad-225">第三方传感器</span><span class="sxs-lookup"><span data-stu-id="ba9ad-225">3rd party sensors</span></span>                 | <span data-ttu-id="ba9ad-226">ThirdPartySensors</span><span class="sxs-lookup"><span data-stu-id="ba9ad-226">ThirdPartySensors</span></span>          |
| <span data-ttu-id="ba9ad-227">防病毒</span><span class="sxs-lookup"><span data-stu-id="ba9ad-227">Antivirus</span></span>                         | <span data-ttu-id="ba9ad-228">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="ba9ad-228">WindowsDefenderAv</span></span>          |
| <span data-ttu-id="ba9ad-229">自动调查</span><span class="sxs-lookup"><span data-stu-id="ba9ad-229">Automated investigation</span></span>           | <span data-ttu-id="ba9ad-230">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="ba9ad-230">AutomatedInvestigation</span></span>     |
| <span data-ttu-id="ba9ad-231">自定义检测</span><span class="sxs-lookup"><span data-stu-id="ba9ad-231">Custom detection</span></span>                  | <span data-ttu-id="ba9ad-232">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="ba9ad-232">CustomDetection</span></span>            |
| <span data-ttu-id="ba9ad-233">自定义 TI</span><span class="sxs-lookup"><span data-stu-id="ba9ad-233">Custom TI</span></span>                         | <span data-ttu-id="ba9ad-234">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="ba9ad-234">CustomerTI</span></span>                 |
| <span data-ttu-id="ba9ad-235">EDR</span><span class="sxs-lookup"><span data-stu-id="ba9ad-235">EDR</span></span>                               | <span data-ttu-id="ba9ad-236">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="ba9ad-236">WindowsDefenderAtp</span></span>         |
| <span data-ttu-id="ba9ad-237">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba9ad-237">Microsoft 365 Defender</span></span>            | <span data-ttu-id="ba9ad-238">MTP</span><span class="sxs-lookup"><span data-stu-id="ba9ad-238">MTP</span></span>                        |
| <span data-ttu-id="ba9ad-239">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ba9ad-239">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="ba9ad-240">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="ba9ad-240">OfficeATP</span></span>                  |
| <span data-ttu-id="ba9ad-241">Microsoft 威胁专家</span><span class="sxs-lookup"><span data-stu-id="ba9ad-241">Microsoft Threat Experts</span></span>          | <span data-ttu-id="ba9ad-242">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="ba9ad-242">ThreatExperts</span></span>              |
| <span data-ttu-id="ba9ad-243">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="ba9ad-243">SmartScreen</span></span>                       | <span data-ttu-id="ba9ad-244">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="ba9ad-244">WindowsDefenderSmartScreen</span></span> |

### <a name="os-platform"></a><span data-ttu-id="ba9ad-245">操作系统平台</span><span class="sxs-lookup"><span data-stu-id="ba9ad-245">OS platform</span></span>

<span data-ttu-id="ba9ad-246">通过选择你感兴趣的操作系统平台来限制警报队列视图。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-246">Limit the alerts queue view by selecting the OS platform that you're interested in investigating.</span></span>

### <a name="device-group"></a><span data-ttu-id="ba9ad-247">设备组</span><span class="sxs-lookup"><span data-stu-id="ba9ad-247">Device group</span></span>

<span data-ttu-id="ba9ad-248">如果你有对检查感兴趣的特定设备组，可以选择这些组来限制警报队列视图。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-248">If you have specific device groups that you're interested in checking, you can select the groups to limit the alerts queue view.</span></span> 

### <a name="associated-threat"></a><span data-ttu-id="ba9ad-249">关联威胁</span><span class="sxs-lookup"><span data-stu-id="ba9ad-249">Associated threat</span></span>

<span data-ttu-id="ba9ad-250">使用此筛选器专注于与高配置文件威胁相关的警报。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-250">Use this filter to focus on alerts that are related to high profile threats.</span></span> <span data-ttu-id="ba9ad-251">你可以查看威胁分析中的高配置文件威胁 [的完整列表](threat-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="ba9ad-251">You can see the full list of high-profile threats in [Threat analytics](threat-analytics.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ba9ad-252">相关主题</span><span class="sxs-lookup"><span data-stu-id="ba9ad-252">Related topics</span></span>

- [<span data-ttu-id="ba9ad-253">管理 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="ba9ad-253">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="ba9ad-254">调查 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="ba9ad-254">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="ba9ad-255">调查与 Microsoft Defender for Endpoint 警报关联的文件</span><span class="sxs-lookup"><span data-stu-id="ba9ad-255">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="ba9ad-256">调查 Microsoft Defender 终结点设备列表中的设备</span><span class="sxs-lookup"><span data-stu-id="ba9ad-256">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="ba9ad-257">调查与 Microsoft Defender for Endpoint 警报关联的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ba9ad-257">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="ba9ad-258">调查与 Microsoft Defender for Endpoint 警报关联的域</span><span class="sxs-lookup"><span data-stu-id="ba9ad-258">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="ba9ad-259">调查 Microsoft Defender for Endpoint 中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="ba9ad-259">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
