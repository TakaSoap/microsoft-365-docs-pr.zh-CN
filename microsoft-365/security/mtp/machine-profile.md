---
title: Microsoft 365 安全门户中的计算机配置文件
description: 查看组织中设备的风险和暴露级别。 分析过去和目前的威胁，并使用最新的更新保护计算机。
keywords: security、恶意软件、Microsoft 365、M365、Microsoft 威胁防护、MTP、security center、Microsoft Defender ATP、Office 365 ATP、Azure ATP、machine page、machine list、machine profile
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 7ab3f63008c65fca1a99128cc6f11f83bc86b2b4
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857551"
---
# <a name="machine-profile-page"></a><span data-ttu-id="13242-105">计算机配置文件页</span><span class="sxs-lookup"><span data-stu-id="13242-105">Machine profile page</span></span>

<span data-ttu-id="13242-106">Microsoft 365 安全门户为你提供了计算机配置文件页面，因此你可以评估网络上设备的运行状况和状态。</span><span class="sxs-lookup"><span data-stu-id="13242-106">The Microsoft 365 security portal provides you with Machine profile pages, so you can assess the health and status of devices on your network.</span></span> <span data-ttu-id="13242-107">每个计算机配置文件页包含有关设备的大量信息。</span><span class="sxs-lookup"><span data-stu-id="13242-107">Each Machine profile page contains a wealth of information about the device.</span></span>

<span data-ttu-id="13242-108">您可以查看有关其正在运行的软件、任何过去和呈现的安全事件或警报的详细信息，并查找相关软件修补程序的链接。</span><span class="sxs-lookup"><span data-stu-id="13242-108">You can review in-depth information about what software it is running, any past and present security events or alerts, and find links to relevant software patches.</span></span>

<span data-ttu-id="13242-109">您还可以使用计算机配置文件执行与安全相关的常见任务，并快速查看有关设备的基本详细信息。</span><span class="sxs-lookup"><span data-stu-id="13242-109">You can also use the Machine profile to perform common security-related tasks, and quickly review basic details about the device.</span></span>

## <a name="navigating-the-machine-profile-page"></a><span data-ttu-id="13242-110">导航计算机配置文件页</span><span class="sxs-lookup"><span data-stu-id="13242-110">Navigating the Machine profile page</span></span>

<span data-ttu-id="13242-111">可以通过直接选择 "计算机" 列表中的设备名称或通过在 "计算机列表" 浮出控件中选择 "**打开计算机" 页面**来访问计算机配置文件页。</span><span class="sxs-lookup"><span data-stu-id="13242-111">The Machine profile page can be accessed by directly selecting a device name on the Machines list or by choosing **Open Machine page** on the Machines list flyout.</span></span>

<span data-ttu-id="13242-112">打开页面后，您会发现它分为三个部分。</span><span class="sxs-lookup"><span data-stu-id="13242-112">Once you have the page open, you'll find that it is broken up into three sections.</span></span>

![带有（1）选项卡区域（2）侧栏和（3）操作以红色突出显示的计算机配置文件页的图像](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

<span data-ttu-id="13242-114">主内容区域（1）包含七个选项卡，可以通过切换这些选项卡来查看有关计算机的不同类型的信息。</span><span class="sxs-lookup"><span data-stu-id="13242-114">The main content area (1) contains seven tabs that you can toggle through to view different kinds of information about the machine.</span></span>

<span data-ttu-id="13242-115">边栏（2）列出有关计算机的基本详细信息。</span><span class="sxs-lookup"><span data-stu-id="13242-115">The sidebar (2) lists basic details about the machine.</span></span>

<span data-ttu-id="13242-116">在 "边栏" 和 "主内容" 部分前面的头（3）中还提供了响应操作。</span><span class="sxs-lookup"><span data-stu-id="13242-116">There are also response actions available in a header (3) before the sidebar and main content sections.</span></span> <span data-ttu-id="13242-117">您可以使用此标头中的操作执行常见的与安全相关的任务。</span><span class="sxs-lookup"><span data-stu-id="13242-117">You can use the actions in this header to perform common security-related tasks.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="13242-118">“选项卡”部分</span><span class="sxs-lookup"><span data-stu-id="13242-118">Tabs section</span></span>

<span data-ttu-id="13242-119">通过计算机配置文件选项卡，可以切换有关计算机的安全详细信息的概述、包含警报列表的表、时间线、安全建议列表、软件清单、发现的漏洞列表以及丢失Kb （安全更新）。</span><span class="sxs-lookup"><span data-stu-id="13242-119">The Machine profile tabs allow you to toggle through an overview of security details about the machine, and tables containing a list of alerts, a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="13242-120">概述选项卡</span><span class="sxs-lookup"><span data-stu-id="13242-120">Overview tab</span></span>

<span data-ttu-id="13242-121">默认选项卡为**概述**。</span><span class="sxs-lookup"><span data-stu-id="13242-121">The default tab is **Overview**.</span></span> <span data-ttu-id="13242-122">它提供了有关设备最重要的安全事实的快速讨论。</span><span class="sxs-lookup"><span data-stu-id="13242-122">It provides a quick look at the most important security fact about the device.</span></span>

![计算机配置文件的 "概述" 选项卡图像](../../media/mtp-machine-profile/overview.png)

<span data-ttu-id="13242-124">您可以在此处找到设备风险级别和活动警报的图表、任何当前登录的用户、最常使用的用户的简短列表以及详细说明设备的暴露程度、安全建议、受影响的软件和安全评估。发现的漏洞。</span><span class="sxs-lookup"><span data-stu-id="13242-124">Here, you can find a chart of the device's risk level and active alerts, any currently logged on users, a brief list of most and least frequent users, and security assessments that detail the device's exposure level, security recommendations, affected software, and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="13242-125">"通知" 选项卡</span><span class="sxs-lookup"><span data-stu-id="13242-125">Alerts tab</span></span>

<span data-ttu-id="13242-126">"**警报**" 选项卡包含已在设备上报告的警报的列表。</span><span class="sxs-lookup"><span data-stu-id="13242-126">The **Alerts** tab contains a list of alerts that have been reported on the device.</span></span>

![计算机配置文件的 "警报" 选项卡图像](../../media/mtp-machine-profile/alerts.png)

<span data-ttu-id="13242-128">您可以自定义所显示的项目数，以及为每个项目显示的列。</span><span class="sxs-lookup"><span data-stu-id="13242-128">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="13242-129">默认行为是为每个页面列出30个项目，并打开11列切换为显示。</span><span class="sxs-lookup"><span data-stu-id="13242-129">The default behavior is to list 30 items per page, and have 11 columns toggled on to display.</span></span>

<span data-ttu-id="13242-130">此选项卡中的列包含有关触发警报的威胁的严重性的信息，以及状态、调查状态以及是否已向其分配了警报的人。</span><span class="sxs-lookup"><span data-stu-id="13242-130">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who if anyone the alert has been assigned to.</span></span>

<span data-ttu-id="13242-131">*受影响的实体*列指的是当前正在查看其配置文件的计算机（实体），以及受影响的网络中的任何其他计算机。</span><span class="sxs-lookup"><span data-stu-id="13242-131">The *impacted entities* column refers to the machine (entity) whose profile you are currently viewing, plus any other machines in your network that are affected.</span></span>

<span data-ttu-id="13242-132">从该列表中选择一项将打开指向选定警报的链接。</span><span class="sxs-lookup"><span data-stu-id="13242-132">Selecting an item from this list will open a link to the selected alert.</span></span>

<span data-ttu-id="13242-133">可以按严重性、状态或受托人筛选此列表。</span><span class="sxs-lookup"><span data-stu-id="13242-133">This list can be filtered by severity, status, or assignee.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="13242-134">日程表选项卡</span><span class="sxs-lookup"><span data-stu-id="13242-134">Timeline tab</span></span>

<span data-ttu-id="13242-135">"**时间线**" 选项卡包含在设备上引发的事件的交互式、按时间排列的图表。</span><span class="sxs-lookup"><span data-stu-id="13242-135">The **Timeline** tab includes a interactive, chronological chart of events raised on the device.</span></span> <span data-ttu-id="13242-136">通过移动图表的突出显示区域，可以查看不同时间范围内的事件。</span><span class="sxs-lookup"><span data-stu-id="13242-136">By moving the highlighted area of the chart, you can view events over different ranges of time.</span></span> <span data-ttu-id="13242-137">您还可以键入日期的自定义范围。</span><span class="sxs-lookup"><span data-stu-id="13242-137">You can also type in a custom range of dates.</span></span>

<span data-ttu-id="13242-138">图表下面是选定日期范围内的事件的列表。</span><span class="sxs-lookup"><span data-stu-id="13242-138">Below the chart is a list of events for the selected range of dates.</span></span>

![计算机配置文件的 "日程表" 选项卡的图像](../../media/mtp-machine-profile/timeline.png)

<span data-ttu-id="13242-140">可以自定义显示的项目数和列表中的列。</span><span class="sxs-lookup"><span data-stu-id="13242-140">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="13242-141">默认列列出了事件时间、活动用户、操作类型、实体（进程）以及有关事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="13242-141">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="13242-142">从列表中选择一项将打开一个浮出控件，其中显示事件实体图，显示触发事件的父进程和子进程。</span><span class="sxs-lookup"><span data-stu-id="13242-142">Selecting an item from the list will open a flyout displaying an Event entities graph, showing the parent and child processes that triggered the event.</span></span>

<span data-ttu-id="13242-143">此列表可以按特定类型的事件进行筛选;例如，注册表事件或智能屏幕事件。</span><span class="sxs-lookup"><span data-stu-id="13242-143">This list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="13242-144">"安全性建议" 选项卡</span><span class="sxs-lookup"><span data-stu-id="13242-144">Security recommendations tab</span></span>

<span data-ttu-id="13242-145">"**安全建议**" 选项卡列出了可用于保护设备的操作。</span><span class="sxs-lookup"><span data-stu-id="13242-145">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="13242-146">选择此列表中的项将打开一个浮出控件，您可以在其中获取有关如何应用建议的说明。</span><span class="sxs-lookup"><span data-stu-id="13242-146">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![计算机配置文件的 "安全建议" 选项卡的图像](../../media/mtp-machine-profile/security-recs.png)

<span data-ttu-id="13242-148">与以前的选项卡一样，每页显示的项目数和可自定义的列数。</span><span class="sxs-lookup"><span data-stu-id="13242-148">As with the previous tabs, the number of items displayed per page and which columns are visible can be customized.</span></span>

<span data-ttu-id="13242-149">默认视图包含详细介绍了解决安全弱点的列、相关威胁、受威胁影响的相关组件或软件等。</span><span class="sxs-lookup"><span data-stu-id="13242-149">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="13242-150">可以按建议的状态筛选项目。</span><span class="sxs-lookup"><span data-stu-id="13242-150">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="13242-151">软件清单</span><span class="sxs-lookup"><span data-stu-id="13242-151">Software inventory</span></span>

<span data-ttu-id="13242-152">"**软件清单**" 选项卡列出了设备上安装的软件。</span><span class="sxs-lookup"><span data-stu-id="13242-152">The **Software inventory** tab lists software installed on the device.</span></span>

![计算机配置文件的 "软件清单" 选项卡的图像](../../media/mtp-machine-profile/software-inventory.png)

<span data-ttu-id="13242-154">默认视图显示软件供应商、已安装版本号、已知软件弱点数、威胁见解、产品代码和标记。</span><span class="sxs-lookup"><span data-stu-id="13242-154">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="13242-155">可以自定义所显示的项目数以及显示的列。</span><span class="sxs-lookup"><span data-stu-id="13242-155">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="13242-156">从该列表中选择一项将打开一个浮出控件，其中包含有关所选软件的更多详细信息，以及上次找到该软件时的路径和时间戳。</span><span class="sxs-lookup"><span data-stu-id="13242-156">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="13242-157">可以按产品代码筛选此列表。</span><span class="sxs-lookup"><span data-stu-id="13242-157">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="13242-158">发现的漏洞选项卡</span><span class="sxs-lookup"><span data-stu-id="13242-158">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="13242-159">"**发现的漏洞**" 选项卡列出了可能会影响设备的任何常见漏洞和漏洞（cve）。</span><span class="sxs-lookup"><span data-stu-id="13242-159">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![计算机配置文件的 "发现漏洞" 选项卡的图像](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

<span data-ttu-id="13242-161">默认视图列出了 CVE 的严重性、常见漏洞得分（CVS）、发布的 CVE 发布时间、CVE 的最后更新时间以及与 CVE 相关的威胁。</span><span class="sxs-lookup"><span data-stu-id="13242-161">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="13242-162">与前面的选项卡一样，可以自定义所显示的项目数和可见的列。</span><span class="sxs-lookup"><span data-stu-id="13242-162">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="13242-163">从该列表中选择一项将打开一个描述 CVE 的浮出控件。</span><span class="sxs-lookup"><span data-stu-id="13242-163">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="13242-164">缺少 Kb</span><span class="sxs-lookup"><span data-stu-id="13242-164">Missing KBs</span></span>

<span data-ttu-id="13242-165">"**缺少 kb** " 选项卡列出了所有尚未应用于计算机的 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="13242-165">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the machine.</span></span> <span data-ttu-id="13242-166">相关的 "Kb" 是介绍这些更新的[知识库文章](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query)。例如， [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)。</span><span class="sxs-lookup"><span data-stu-id="13242-166">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![缺少计算机配置文件的 kb 选项卡的图像](../../media/mtp-machine-profile/missing-kbs.PNG)

<span data-ttu-id="13242-168">默认视图列出包含更新、OS 版本、受影响的产品、Cve 地址、KB 编号和标记的公告。</span><span class="sxs-lookup"><span data-stu-id="13242-168">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="13242-169">每页显示的项目数和可自定义的列数。</span><span class="sxs-lookup"><span data-stu-id="13242-169">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="13242-170">选择某个项目将打开一个链接到更新的浮出控件。</span><span class="sxs-lookup"><span data-stu-id="13242-170">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="sidebar"></a><span data-ttu-id="13242-171">边栏</span><span class="sxs-lookup"><span data-stu-id="13242-171">Sidebar</span></span>

<span data-ttu-id="13242-172">在计算机配置文件页的主内容区域旁边是侧栏。</span><span class="sxs-lookup"><span data-stu-id="13242-172">Beside the main content area of the Machine profile page is the sidebar.</span></span>

![计算机配置文件的边栏选项卡的图像](../../media/mtp-machine-profile/sidebar.png)

<span data-ttu-id="13242-174">侧边栏提供了一些小子部分中的一些重要基本信息，这些信息可以切换为打开或关闭：</span><span class="sxs-lookup"><span data-stu-id="13242-174">The sidebar provides some important basic information in small subsections which can be toggled open or closed:</span></span>

* <span data-ttu-id="13242-175">**标记**-与设备关联的任何标记</span><span class="sxs-lookup"><span data-stu-id="13242-175">**Tags** - Any tags associated with the device</span></span>
* <span data-ttu-id="13242-176">**安全信息**-开放事件、活动警报、暴露程度和风险级别</span><span class="sxs-lookup"><span data-stu-id="13242-176">**Security info** - Open incidents, active alerts, exposure level and risk level</span></span>
* <span data-ttu-id="13242-177">**设备详细信息**-域、操作系统、资产组、运行状况状态、数据敏感度和 IP 地址</span><span class="sxs-lookup"><span data-stu-id="13242-177">**Device details** - Domain, OS, Asset group, health state, data sensitivity, and IP addresses</span></span>
* <span data-ttu-id="13242-178">**网络活动**-首次在网络上显示设备时的时间戳</span><span class="sxs-lookup"><span data-stu-id="13242-178">**Network activity** - Timestamps for the first time and last time the device was seen on the network</span></span>

<span data-ttu-id="13242-179">此部分还包括设备的名称和暴露程度，以及用于指示其当前在网络中是否处于活动状态的图标。</span><span class="sxs-lookup"><span data-stu-id="13242-179">This section also includes the name and exposure level of the device, and an icon to indicate if it is currently active on the network.</span></span>

## <a name="response-actions"></a><span data-ttu-id="13242-180">响应操作</span><span class="sxs-lookup"><span data-stu-id="13242-180">Response actions</span></span>

<span data-ttu-id="13242-181">响应操作提供了一种快速防御和分析威胁的方法。</span><span class="sxs-lookup"><span data-stu-id="13242-181">Response actions offer a quick way to defend against and analyze threats.</span></span>

![计算机配置文件的边栏选项卡的图像](../../media/mtp-machine-profile/actions.PNG)

<span data-ttu-id="13242-183">您可以在此处使用的响应操作包括：</span><span class="sxs-lookup"><span data-stu-id="13242-183">The response actions available to you here include:</span></span>

* <span data-ttu-id="13242-184">**管理标记**-更新已应用于此设备的自定义标记。</span><span class="sxs-lookup"><span data-stu-id="13242-184">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="13242-185">**隔离计算机**-将计算机与组织的网络隔离，同时保持它连接到 Microsoft Defender 高级威胁防护。</span><span class="sxs-lookup"><span data-stu-id="13242-185">**Isolate machine** - Isolates the machine from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="13242-186">你可以选择允许 Outlook、团队和 Skype for Business 在计算机被隔离的情况下运行，以便进行通信。</span><span class="sxs-lookup"><span data-stu-id="13242-186">You can choose to allow Outlook, Teams, and Skype for Business to run while the machine is isolated, for communication purposes.</span></span>
* <span data-ttu-id="13242-187">**限制应用程序执行**-阻止未由 Microsoft 签名的应用程序运行</span><span class="sxs-lookup"><span data-stu-id="13242-187">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running</span></span>
* <span data-ttu-id="13242-188">**运行防病毒扫描**-更新 Windows Defender 防病毒定义，并立即运行防病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="13242-188">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="13242-189">在快速扫描或完全扫描之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="13242-189">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="13242-190">收集有关计算机的**调查包**收集信息。</span><span class="sxs-lookup"><span data-stu-id="13242-190">**Collect investigation package** - Gathers information about the machine.</span></span> <span data-ttu-id="13242-191">调查完成后，你可以下载它。</span><span class="sxs-lookup"><span data-stu-id="13242-191">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="13242-192">**启动 Live Response session** -在计算机上加载远程命令行管理程序以进行[深入的安全调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)。</span><span class="sxs-lookup"><span data-stu-id="13242-192">**Initiate Live Response session** - Loads a remote shell on the machine for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="13242-193">**启动自动调查**-自动[调查和 remediates 威胁](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。</span><span class="sxs-lookup"><span data-stu-id="13242-193">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="13242-194">尽管您可以手动触发自动调查以从此页面运行，但[某些警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies)会触发自己的自动调查。</span><span class="sxs-lookup"><span data-stu-id="13242-194">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="13242-195">**操作中心**-查看已提交操作的状态。</span><span class="sxs-lookup"><span data-stu-id="13242-195">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="13242-196">仅在已选择另一操作时可用。</span><span class="sxs-lookup"><span data-stu-id="13242-196">Only available if another action has already been selected.</span></span>

## <a name="related-topics"></a><span data-ttu-id="13242-197">相关主题</span><span class="sxs-lookup"><span data-stu-id="13242-197">Related topics</span></span>

* [<span data-ttu-id="13242-198">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="13242-198">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="13242-199">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="13242-199">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="13242-200">使用实时响应调查计算机上的实体</span><span class="sxs-lookup"><span data-stu-id="13242-200">Investigate entities on machines using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="13242-201">Office 365 中的自动化调查和响应（空气）</span><span class="sxs-lookup"><span data-stu-id="13242-201">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
