---
title: 安全门户Microsoft 365配置文件
description: 查看组织中设备的风险和曝光级别。 分析过去和现在的威胁，使用最新更新保护设备。
keywords: 安全， 恶意软件， Microsoft 365， M365， Microsoft 365 Defender， 安全中心， Microsoft Defender for Endpoint， Microsoft Defender for Office 365， Microsoft Defender for Identity， 设备页面， 设备配置文件， 计算机页面， 计算机配置文件
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 8e2788fd9163a27b41bd3788facf5fc9623b0543
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935661"
---
# <a name="device-profile-page"></a><span data-ttu-id="a35af-105">设备配置文件页</span><span class="sxs-lookup"><span data-stu-id="a35af-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a35af-106">安全Microsoft 365门户提供了设备配置文件页面，以便你可以快速评估网络上设备的运行状况和状态。</span><span class="sxs-lookup"><span data-stu-id="a35af-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a35af-107">设备配置文件页面可能略有不同，具体取决于设备是注册 Microsoft Defender for Endpoint、Microsoft Defender for Identity 还是同时注册两者。</span><span class="sxs-lookup"><span data-stu-id="a35af-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="a35af-108">如果设备在 Microsoft Defender for Endpoint 中注册，则还可使用设备配置文件页执行一些常见的安全任务。</span><span class="sxs-lookup"><span data-stu-id="a35af-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="a35af-109">导航设备配置文件页</span><span class="sxs-lookup"><span data-stu-id="a35af-109">Navigating the device profile page</span></span>

<span data-ttu-id="a35af-110">配置文件页分为几个广泛的部分。</span><span class="sxs-lookup"><span data-stu-id="a35af-110">The profile page is broken up into several broad sections.</span></span>

![设备配置文件页面的图像， (1) 选项卡区域 (2) 边栏和 (3) 操作突出显示为红色](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="a35af-112">边栏 (1) 列出了有关设备的基本详细信息。</span><span class="sxs-lookup"><span data-stu-id="a35af-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="a35af-113">2 (2) 包含选项卡，你可以切换这些选项卡以查看有关设备的不同类型的信息。</span><span class="sxs-lookup"><span data-stu-id="a35af-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="a35af-114">如果设备在 Microsoft Defender for Endpoint 中注册，你还将看到第 3 步 (响应) 。</span><span class="sxs-lookup"><span data-stu-id="a35af-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="a35af-115">响应操作允许您执行与安全性相关的常见任务。</span><span class="sxs-lookup"><span data-stu-id="a35af-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="a35af-116">边栏</span><span class="sxs-lookup"><span data-stu-id="a35af-116">Sidebar</span></span>

<span data-ttu-id="a35af-117">设备配置文件页的主要内容区域旁边是边栏。</span><span class="sxs-lookup"><span data-stu-id="a35af-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![设备配置文件的边栏选项卡的图像](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="a35af-119">边栏列出了设备的全名和曝光级别。</span><span class="sxs-lookup"><span data-stu-id="a35af-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="a35af-120">它还在小子节中提供了一些可以打开或关闭的重要基本信息，例如：</span><span class="sxs-lookup"><span data-stu-id="a35af-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="a35af-121">**Tags** - 任何 Microsoft Defender for Endpoint、Microsoft Defender for Identity 或与设备关联的自定义标记。</span><span class="sxs-lookup"><span data-stu-id="a35af-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="a35af-122">Microsoft Defender for Identity 中的标记不可编辑。</span><span class="sxs-lookup"><span data-stu-id="a35af-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="a35af-123">**安全信息** - 打开事件和活动警报。</span><span class="sxs-lookup"><span data-stu-id="a35af-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="a35af-124">在适用于终结点的 Microsoft Defender 中注册的设备还将显示曝光级别和风险级别。</span><span class="sxs-lookup"><span data-stu-id="a35af-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="a35af-125">曝光级别与设备遵守安全建议的数量相关，而风险级别根据多种因素（包括活动警报的类型和严重性）进行计算。</span><span class="sxs-lookup"><span data-stu-id="a35af-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="a35af-126">**设备详细信息** - 域、操作系统、首次看到设备的时间戳、IP 地址、资源。</span><span class="sxs-lookup"><span data-stu-id="a35af-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="a35af-127">在 Microsoft Defender for Endpoint 中注册的设备还显示运行状况状态。</span><span class="sxs-lookup"><span data-stu-id="a35af-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="a35af-128">在 Microsoft Defender 中注册用于标识的设备将显示 SAM 名称和首次创建设备的时间戳。</span><span class="sxs-lookup"><span data-stu-id="a35af-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="a35af-129">**网络** 活动 - 第一次和最后一次在网络中看到设备的时间戳。</span><span class="sxs-lookup"><span data-stu-id="a35af-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="a35af-130">**目录数据** (在 Microsoft *Defender for Identity)* 注册的设备 - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) 标志 [、SNS](/windows/win32/ad/service-principal-names)和组成员身份。</span><span class="sxs-lookup"><span data-stu-id="a35af-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="a35af-131">响应操作</span><span class="sxs-lookup"><span data-stu-id="a35af-131">Response actions</span></span>

<span data-ttu-id="a35af-132">响应操作提供了一种快速防御和分析威胁的方法。</span><span class="sxs-lookup"><span data-stu-id="a35af-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![设备配置文件的操作栏的图像](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="a35af-134">[仅在设备](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) 在 Microsoft Defender for Endpoint 中注册时，响应操作才可用。</span><span class="sxs-lookup"><span data-stu-id="a35af-134">[Response actions](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="a35af-135">在 Microsoft Defender for Endpoint 中注册的设备可能会根据设备的操作系统和版本号显示不同数量的响应操作。</span><span class="sxs-lookup"><span data-stu-id="a35af-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="a35af-136">设备配置文件页上可用的操作包括：</span><span class="sxs-lookup"><span data-stu-id="a35af-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="a35af-137">**管理标记** - 更新已应用于此设备的自定义标记。</span><span class="sxs-lookup"><span data-stu-id="a35af-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="a35af-138">**隔离设备** - 将设备与组织的网络隔离，同时将其连接到 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="a35af-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a35af-139">你可以选择允许Outlook、Teams和Skype for Business隔离时运行，以用于通信目的。</span><span class="sxs-lookup"><span data-stu-id="a35af-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="a35af-140">**操作中心** - 查看已提交操作的状态。</span><span class="sxs-lookup"><span data-stu-id="a35af-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="a35af-141">仅在已选择其他操作时可用。</span><span class="sxs-lookup"><span data-stu-id="a35af-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="a35af-142">**限制应用执行** - 阻止未由 Microsoft 签名的应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="a35af-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="a35af-143">**运行防病毒扫描**- Windows Defender 防病毒定义并立即运行防病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="a35af-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="a35af-144">在快速扫描或完全扫描之间选择。</span><span class="sxs-lookup"><span data-stu-id="a35af-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="a35af-145">**收集调查包** - 收集有关设备的信息。</span><span class="sxs-lookup"><span data-stu-id="a35af-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="a35af-146">调查完成后，可以下载它。</span><span class="sxs-lookup"><span data-stu-id="a35af-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="a35af-147">**启动实时响应会话** - 在设备上加载远程 Shell 进行 [深入安全调查](/microsoft-365/security/defender-endpoint/live-response)。</span><span class="sxs-lookup"><span data-stu-id="a35af-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](/microsoft-365/security/defender-endpoint/live-response).</span></span>
* <span data-ttu-id="a35af-148">**启动自动调查** - [自动调查和修正威胁](../office-365-security/office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="a35af-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](../office-365-security/office-365-air.md).</span></span> <span data-ttu-id="a35af-149">尽管你可以手动触发自动调查以从此页运行，但某些警报策略[](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies)会自行触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="a35af-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="a35af-150">**操作中心** - 显示有关当前正在运行的任何响应操作的信息。</span><span class="sxs-lookup"><span data-stu-id="a35af-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="a35af-151">“选项卡”部分</span><span class="sxs-lookup"><span data-stu-id="a35af-151">Tabs section</span></span>

<span data-ttu-id="a35af-152">设备配置文件选项卡允许你切换有关设备的安全详细信息概述以及包含警报列表的表。</span><span class="sxs-lookup"><span data-stu-id="a35af-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="a35af-153">在 Microsoft Defender for Endpoint 中注册的设备还将显示选项卡，这些选项卡具有时间线、安全建议列表、软件清单、发现的漏洞列表和缺少的 (B) 。</span><span class="sxs-lookup"><span data-stu-id="a35af-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="a35af-154">"概述"选项卡</span><span class="sxs-lookup"><span data-stu-id="a35af-154">Overview tab</span></span>

<span data-ttu-id="a35af-155">默认选项卡是 **概述**。</span><span class="sxs-lookup"><span data-stu-id="a35af-155">The default tab is **Overview**.</span></span> <span data-ttu-id="a35af-156">它可快速查看有关设备最重要的安全事实。</span><span class="sxs-lookup"><span data-stu-id="a35af-156">It provides a quick look at the most important security fact about the device.</span></span>

![设备配置文件的"概述"选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="a35af-158">你可以在此处快速查看设备的活动警报以及任何当前登录的用户。</span><span class="sxs-lookup"><span data-stu-id="a35af-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="a35af-159">如果设备在适用于终结点的 Microsoft Defender 中注册，则还将看到设备的风险级别和安全评估的任何可用数据。</span><span class="sxs-lookup"><span data-stu-id="a35af-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="a35af-160">安全评估描述设备的曝光级别、提供安全建议，并列出受影响的软件和发现的漏洞。</span><span class="sxs-lookup"><span data-stu-id="a35af-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="a35af-161">警报选项卡</span><span class="sxs-lookup"><span data-stu-id="a35af-161">Alerts tab</span></span>

<span data-ttu-id="a35af-162">警报 **选项卡** 包含从 Microsoft Defender for Identity 和 Microsoft Defender for Endpoint 在设备上引发警报的列表。</span><span class="sxs-lookup"><span data-stu-id="a35af-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![设备配置文件的警报选项卡图像](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="a35af-164">您可以自定义显示的项目数，以及每个项目的显示列数。</span><span class="sxs-lookup"><span data-stu-id="a35af-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="a35af-165">默认行为是每页列出 30 个项目。</span><span class="sxs-lookup"><span data-stu-id="a35af-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="a35af-166">此选项卡中的列包含有关触发警报的威胁的严重性、状态、调查状态以及警报已分配给谁的信息。</span><span class="sxs-lookup"><span data-stu-id="a35af-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="a35af-167">受影响 *实体* 列是指当前 (其) 的设备实体，以及网络中受影响的任何其他设备。</span><span class="sxs-lookup"><span data-stu-id="a35af-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="a35af-168">从此列表选择一个项目将打开一个包含有关所选警报的详细信息的飞出列表。</span><span class="sxs-lookup"><span data-stu-id="a35af-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="a35af-169">此列表可以按严重性、状态或已为其分配警报的人进行筛选。</span><span class="sxs-lookup"><span data-stu-id="a35af-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="a35af-170">"日程表"选项卡</span><span class="sxs-lookup"><span data-stu-id="a35af-170">Timeline tab</span></span>

<span data-ttu-id="a35af-171">" **时间线** "选项卡包括设备上引发的所有事件的交互式按时间顺序排列的图表。</span><span class="sxs-lookup"><span data-stu-id="a35af-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="a35af-172">通过向左或向右移动图表的突出显示区域，可以查看不同时段内的事件。</span><span class="sxs-lookup"><span data-stu-id="a35af-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="a35af-173">您还可以从交互式图表和事件列表之间的下拉菜单中选择一个自定义日期范围。</span><span class="sxs-lookup"><span data-stu-id="a35af-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="a35af-174">图表下方是所选日期范围的事件列表。</span><span class="sxs-lookup"><span data-stu-id="a35af-174">Below the chart is a list of events for the selected range of dates.</span></span>

![设备配置文件的时间线选项卡图像](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="a35af-176">可以自定义显示的项目数和列表上的列数。</span><span class="sxs-lookup"><span data-stu-id="a35af-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="a35af-177">默认列列出事件时间、活动用户、操作类型、 (处理) 实体，以及事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="a35af-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="a35af-178">从此列表中选择一个项目将打开一个显示"事件实体"图的飞出图，其中显示事件所涉及的父进程和子进程。</span><span class="sxs-lookup"><span data-stu-id="a35af-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="a35af-179">该列表可以按特定类型的事件进行筛选;例如，注册表事件或 Smart Screen 事件。</span><span class="sxs-lookup"><span data-stu-id="a35af-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="a35af-180">该列表还可以导出到 CSV 文件进行下载。</span><span class="sxs-lookup"><span data-stu-id="a35af-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="a35af-181">虽然文件不受事件数限制，但可以选择导出的最大时间范围是七天。</span><span class="sxs-lookup"><span data-stu-id="a35af-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="a35af-182">"安全建议"选项卡</span><span class="sxs-lookup"><span data-stu-id="a35af-182">Security recommendations tab</span></span>

<span data-ttu-id="a35af-183">" **安全建议** "选项卡列出了可采取的保护设备的操作。</span><span class="sxs-lookup"><span data-stu-id="a35af-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="a35af-184">选择此列表上的项目将打开一个飞出区，你可以在此获取有关如何应用建议的说明。</span><span class="sxs-lookup"><span data-stu-id="a35af-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![设备配置文件的安全建议选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="a35af-186">与前面的选项卡一样，可以自定义每页显示的项目数以及哪些列可见。</span><span class="sxs-lookup"><span data-stu-id="a35af-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="a35af-187">默认视图包括详细说明解决的安全缺陷、关联威胁、受威胁影响的相关组件或软件等的列。</span><span class="sxs-lookup"><span data-stu-id="a35af-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="a35af-188">项目可以按建议的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="a35af-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="a35af-189">软件清单</span><span class="sxs-lookup"><span data-stu-id="a35af-189">Software inventory</span></span>

<span data-ttu-id="a35af-190">" **软件清单** "选项卡列出了设备上安装的软件。</span><span class="sxs-lookup"><span data-stu-id="a35af-190">The **Software inventory** tab lists software installed on the device.</span></span>

![设备配置文件的软件清单选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="a35af-192">默认视图显示软件供应商、已安装的版本号、已知软件漏洞的数量、威胁见解、产品代码和标签。</span><span class="sxs-lookup"><span data-stu-id="a35af-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="a35af-193">可以自定义显示的项目数和显示的列数。</span><span class="sxs-lookup"><span data-stu-id="a35af-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="a35af-194">从此列表中选择一个项目将打开一个包含有关所选软件的更多详细信息以及上次找到软件时的路径和时间戳的飞出图。</span><span class="sxs-lookup"><span data-stu-id="a35af-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="a35af-195">此列表可以按产品代码进行筛选。</span><span class="sxs-lookup"><span data-stu-id="a35af-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="a35af-196">"发现的漏洞"选项卡</span><span class="sxs-lookup"><span data-stu-id="a35af-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="a35af-197">" **发现的漏洞"** 选项卡列出了可能会影响设备 (C) 的常见漏洞和漏洞。</span><span class="sxs-lookup"><span data-stu-id="a35af-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![设备配置文件的已发现漏洞选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="a35af-199">默认视图列出了 CVE 的严重性、常见漏洞分数 (CVS) 、与 CVE 相关的软件、发布 CVE 的时间、上次更新 CVE 的时间，以及与 CVE 关联的威胁。</span><span class="sxs-lookup"><span data-stu-id="a35af-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="a35af-200">与前面的选项卡一样，可以自定义显示的项目数和可见的列。</span><span class="sxs-lookup"><span data-stu-id="a35af-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="a35af-201">从此列表选择一个项目将打开描述 CVE 的飞出区。</span><span class="sxs-lookup"><span data-stu-id="a35af-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="a35af-202">缺少 KB</span><span class="sxs-lookup"><span data-stu-id="a35af-202">Missing KBs</span></span>

<span data-ttu-id="a35af-203">缺少 **的 KB** 选项卡列出了尚未应用于设备的任何 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="a35af-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="a35af-204">相关"KBS"是 [描述](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) 这些更新的知识库文章;例如 [，KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)。</span><span class="sxs-lookup"><span data-stu-id="a35af-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![设备配置文件缺少 kbs 选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="a35af-206">默认视图列出了包含更新、操作系统版本、受影响的产品、解决的 CVEs、KB 编号和标记的公告。</span><span class="sxs-lookup"><span data-stu-id="a35af-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="a35af-207">可以自定义每页显示的项目数以及显示哪些列。</span><span class="sxs-lookup"><span data-stu-id="a35af-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="a35af-208">选择一个项目将打开链接到更新的飞出区。</span><span class="sxs-lookup"><span data-stu-id="a35af-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a35af-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="a35af-209">Related topics</span></span>

* [<span data-ttu-id="a35af-210">Microsoft 365Defender 概述</span><span class="sxs-lookup"><span data-stu-id="a35af-210">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
* [<span data-ttu-id="a35af-211">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a35af-211">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
* [<span data-ttu-id="a35af-212">使用实时响应调查设备上的实体</span><span class="sxs-lookup"><span data-stu-id="a35af-212">Investigate entities on devices, using live response</span></span>](../defender-endpoint/live-response.md)
* [<span data-ttu-id="a35af-213">自动调查和响应 (AIR) 中Office 365</span><span class="sxs-lookup"><span data-stu-id="a35af-213">Automated investigation and response (AIR) in Office 365</span></span>](../office-365-security/office-365-air.md)
