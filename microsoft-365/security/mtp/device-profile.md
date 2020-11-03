---
title: Microsoft 365 安全门户中的设备配置文件
description: 查看组织中设备的风险和暴露级别。 分析过去和目前的威胁，并使用最新的更新保护设备。
keywords: security、malware、Microsoft 365、M365、Microsoft 威胁防护、MTP、security center、Microsoft Defender ATP、Office 365 ATP、Azure ATP、设备页面、设备配置文件、计算机页面、计算机配置文件
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
ms.openlocfilehash: 3840a6beae3b586fc90420f7813ff6e9d3cc6c60
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843848"
---
# <a name="device-profile-page"></a><span data-ttu-id="75139-105">设备配置文件页</span><span class="sxs-lookup"><span data-stu-id="75139-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="75139-106">Microsoft 365 安全门户为您提供了设备配置文件页，因此您可以快速评估网络上设备的运行状况和状态。</span><span class="sxs-lookup"><span data-stu-id="75139-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75139-107">设备配置文件页的外观可能略有不同，具体取决于设备是否已在 Microsoft Defender for Endpoint、Microsoft Defender Identity 或两者中注册。</span><span class="sxs-lookup"><span data-stu-id="75139-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="75139-108">如果设备已在 Microsoft Defender for Endpoint 中注册，则还可以使用设备配置文件页面执行一些常见的安全任务。</span><span class="sxs-lookup"><span data-stu-id="75139-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="75139-109">浏览设备配置文件页</span><span class="sxs-lookup"><span data-stu-id="75139-109">Navigating the device profile page</span></span>

<span data-ttu-id="75139-110">配置文件页面分为几个广义部分。</span><span class="sxs-lookup"><span data-stu-id="75139-110">The profile page is broken up into several broad sections.</span></span>

![ (1) 选项卡区域 (2) 边栏和 (3) 操作以红色突出显示的设备配置文件页的图像](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="75139-112">边栏 (1) 列出有关设备的基本详细信息。</span><span class="sxs-lookup"><span data-stu-id="75139-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="75139-113">主内容区域 (2) 包含选项卡，您可以切换这些选项卡以查看有关设备的不同类型的信息。</span><span class="sxs-lookup"><span data-stu-id="75139-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="75139-114">如果设备已在 Microsoft Defender for Endpoint 中注册，您还将看到 (3) 响应操作的列表。</span><span class="sxs-lookup"><span data-stu-id="75139-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="75139-115">响应操作允许您执行常见的与安全相关的任务。</span><span class="sxs-lookup"><span data-stu-id="75139-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="75139-116">边栏</span><span class="sxs-lookup"><span data-stu-id="75139-116">Sidebar</span></span>

<span data-ttu-id="75139-117">在设备配置文件页面的主要内容区域旁边是侧边栏。</span><span class="sxs-lookup"><span data-stu-id="75139-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![设备配置文件的边栏选项卡的图像](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="75139-119">侧栏列出设备的完整名称和曝光级别。</span><span class="sxs-lookup"><span data-stu-id="75139-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="75139-120">它还提供了一些小子部分中的一些重要基本信息，这些信息可以切换为打开或关闭，例如：</span><span class="sxs-lookup"><span data-stu-id="75139-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="75139-121">**标记** -任何 microsoft Defender for Endpoint、microsoft Defender for Identity 或与设备关联的自定义标记。</span><span class="sxs-lookup"><span data-stu-id="75139-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="75139-122">来自 Microsoft Defender for Identity 的标记是不可编辑的。</span><span class="sxs-lookup"><span data-stu-id="75139-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="75139-123">**安全信息** -打开事件和活动警报。</span><span class="sxs-lookup"><span data-stu-id="75139-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="75139-124">在 Microsoft Defender for Endpoint 中注册的设备也会显示暴露级别和风险级别。</span><span class="sxs-lookup"><span data-stu-id="75139-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="75139-125">暴露程度取决于设备符合安全建议的程度，而风险级别则根据许多因素计算，包括活动警报的类型和严重性。</span><span class="sxs-lookup"><span data-stu-id="75139-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="75139-126">**设备详细信息** -域、OS、设备首次看到时的时间戳、IP 地址、资源。</span><span class="sxs-lookup"><span data-stu-id="75139-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="75139-127">在 Microsoft Defender for Endpoint 中注册的设备也会显示运行状况状态。</span><span class="sxs-lookup"><span data-stu-id="75139-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="75139-128">在 Microsoft Defender for Identity 中注册的设备将显示 SAM 名称和在第一次创建设备时的时间戳。</span><span class="sxs-lookup"><span data-stu-id="75139-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="75139-129">**网络活动** -首次在网络上显示设备时的时间戳。</span><span class="sxs-lookup"><span data-stu-id="75139-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="75139-130">**目录数据** ( *仅适用于在 Microsoft Defender 中注册标识* ) 的设备- [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) 标志、 [spn](https://docs.microsoft.com/windows/win32/ad/service-principal-names)和组成员身份。</span><span class="sxs-lookup"><span data-stu-id="75139-130">**Directory data** ( *only for devices enrolled in Microsoft Defender for Identity* ) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="75139-131">响应操作</span><span class="sxs-lookup"><span data-stu-id="75139-131">Response actions</span></span>

<span data-ttu-id="75139-132">响应操作提供了一种快速防御和分析威胁的方法。</span><span class="sxs-lookup"><span data-stu-id="75139-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![设备配置文件的操作栏图像](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="75139-134">仅当设备已在 Microsoft Defender for Endpoint 中注册时，[响应操作](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)才可用。</span><span class="sxs-lookup"><span data-stu-id="75139-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="75139-135">在 Microsoft Defender for Endpoint 中注册的设备可能会根据设备的操作系统和版本号显示不同数量的响应操作。</span><span class="sxs-lookup"><span data-stu-id="75139-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="75139-136">在设备配置文件页上可用的操作包括：</span><span class="sxs-lookup"><span data-stu-id="75139-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="75139-137">**管理标记** -更新已应用于此设备的自定义标记。</span><span class="sxs-lookup"><span data-stu-id="75139-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="75139-138">**隔离设备** -将设备与组织的网络隔离，同时保持它连接到 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="75139-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="75139-139">你可以选择允许 Outlook、团队和 Skype for Business 在设备被隔离时运行，以便进行通信。</span><span class="sxs-lookup"><span data-stu-id="75139-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="75139-140">**操作中心** -查看已提交操作的状态。</span><span class="sxs-lookup"><span data-stu-id="75139-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="75139-141">仅在已选择另一操作时可用。</span><span class="sxs-lookup"><span data-stu-id="75139-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="75139-142">**限制应用程序执行** -阻止未由 Microsoft 签名的应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="75139-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="75139-143">**运行防病毒扫描** -更新 Windows Defender 防病毒定义，并立即运行防病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="75139-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="75139-144">在快速扫描或完全扫描之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="75139-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="75139-145">收集有关设备的 **调查包** 收集信息。</span><span class="sxs-lookup"><span data-stu-id="75139-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="75139-146">调查完成后，你可以下载它。</span><span class="sxs-lookup"><span data-stu-id="75139-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="75139-147">**启动 Live Response Session** -在设备上加载远程命令行管理程序以进行 [深入的安全调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)。</span><span class="sxs-lookup"><span data-stu-id="75139-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="75139-148">**启动自动调查** -自动 [调查和 remediates 威胁](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。</span><span class="sxs-lookup"><span data-stu-id="75139-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="75139-149">尽管您可以手动触发自动调查以从此页面运行，但 [某些警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) 会触发自己的自动调查。</span><span class="sxs-lookup"><span data-stu-id="75139-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="75139-150">**操作中心** -显示有关当前正在运行的所有响应操作的信息。</span><span class="sxs-lookup"><span data-stu-id="75139-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="75139-151">“选项卡”部分</span><span class="sxs-lookup"><span data-stu-id="75139-151">Tabs section</span></span>

<span data-ttu-id="75139-152">通过设备配置文件选项卡，可以切换有关设备的安全详细信息以及包含警报列表的表的概述。</span><span class="sxs-lookup"><span data-stu-id="75139-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="75139-153">在 Microsoft Defender for Endpoint 中注册的设备也将显示功能时间线的选项卡、安全建议列表、软件清单、发现漏洞的列表以及缺少的 Kb (安全更新) 。</span><span class="sxs-lookup"><span data-stu-id="75139-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="75139-154">概述选项卡</span><span class="sxs-lookup"><span data-stu-id="75139-154">Overview tab</span></span>

<span data-ttu-id="75139-155">默认选项卡为 **概述** 。</span><span class="sxs-lookup"><span data-stu-id="75139-155">The default tab is **Overview**.</span></span> <span data-ttu-id="75139-156">它提供了有关设备最重要的安全事实的快速讨论。</span><span class="sxs-lookup"><span data-stu-id="75139-156">It provides a quick look at the most important security fact about the device.</span></span>

![设备配置文件的 "概述" 选项卡图像](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="75139-158">你可以在此处快速查看设备的活动警报以及任何当前登录的用户。</span><span class="sxs-lookup"><span data-stu-id="75139-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="75139-159">如果设备已在 Microsoft Defender for Endpoint 中注册，你还将看到设备的风险级别和安全评估上的任何可用数据。</span><span class="sxs-lookup"><span data-stu-id="75139-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="75139-160">安全评估描述设备的暴露级别、提供安全建议，并列出受影响的软件和发现的漏洞。</span><span class="sxs-lookup"><span data-stu-id="75139-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="75139-161">"通知" 选项卡</span><span class="sxs-lookup"><span data-stu-id="75139-161">Alerts tab</span></span>

<span data-ttu-id="75139-162">" **警报** " 选项卡包含来自 Microsoft Defender for Identity 和 microsoft Defender for Endpoint 中已在设备上引发的警报的列表。</span><span class="sxs-lookup"><span data-stu-id="75139-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![设备配置文件的 "警报" 选项卡图像](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="75139-164">您可以自定义所显示的项目数，以及为每个项目显示的列。</span><span class="sxs-lookup"><span data-stu-id="75139-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="75139-165">默认行为是列出每个页面的三十个项目。</span><span class="sxs-lookup"><span data-stu-id="75139-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="75139-166">此选项卡中的列包含有关触发警报的威胁的严重性的信息，以及状态、调查状态和向其分配警报的发件者。</span><span class="sxs-lookup"><span data-stu-id="75139-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="75139-167">*受影响的实体* 列指的是当前正在查看其配置文件的设备 (实体) ，以及受影响的网络中的任何其他设备。</span><span class="sxs-lookup"><span data-stu-id="75139-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="75139-168">从该列表中选择一项将打开一个浮出控件，其中包含有关选定警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="75139-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="75139-169">可以按严重性、状态或向其分配警报的人筛选此列表。</span><span class="sxs-lookup"><span data-stu-id="75139-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="75139-170">日程表选项卡</span><span class="sxs-lookup"><span data-stu-id="75139-170">Timeline tab</span></span>

<span data-ttu-id="75139-171">" **时间线** " 选项卡包含设备上引发的所有事件的交互式、按时间排列的图表。</span><span class="sxs-lookup"><span data-stu-id="75139-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="75139-172">通过将图表的突出显示区域向左或向右移动，可以查看不同时间段的事件。</span><span class="sxs-lookup"><span data-stu-id="75139-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="75139-173">您还可以从 "交互式图表" 和 "事件" 列表之间的下拉菜单中选择一个自定义日期范围。</span><span class="sxs-lookup"><span data-stu-id="75139-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="75139-174">图表下面是选定日期范围内的事件的列表。</span><span class="sxs-lookup"><span data-stu-id="75139-174">Below the chart is a list of events for the selected range of dates.</span></span>

![设备配置文件的 "日程表" 选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="75139-176">可以自定义显示的项目数和列表中的列。</span><span class="sxs-lookup"><span data-stu-id="75139-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="75139-177">默认列列出事件时间、活动用户、操作类型、实体 (进程) 以及有关事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="75139-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="75139-178">从该列表中选择一项将打开一个浮出控件，其中显示事件实体图，显示事件中涉及的父进程和子进程。</span><span class="sxs-lookup"><span data-stu-id="75139-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="75139-179">该列表可以按特定类型的事件进行筛选;例如，注册表事件或智能屏幕事件。</span><span class="sxs-lookup"><span data-stu-id="75139-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="75139-180">此外，还可以将列表导出到 CSV 文件，以供下载。</span><span class="sxs-lookup"><span data-stu-id="75139-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="75139-181">尽管该文件不受事件数量的限制，但可以选择导出的最长时间范围是七天。</span><span class="sxs-lookup"><span data-stu-id="75139-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="75139-182">"安全性建议" 选项卡</span><span class="sxs-lookup"><span data-stu-id="75139-182">Security recommendations tab</span></span>

<span data-ttu-id="75139-183">" **安全建议** " 选项卡列出了可用于保护设备的操作。</span><span class="sxs-lookup"><span data-stu-id="75139-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="75139-184">选择此列表中的项将打开一个浮出控件，您可以在其中获取有关如何应用建议的说明。</span><span class="sxs-lookup"><span data-stu-id="75139-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![设备配置文件的 "安全建议" 选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="75139-186">与以前的选项卡一样，可以自定义每页显示的项数以及哪些列是可见的。</span><span class="sxs-lookup"><span data-stu-id="75139-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="75139-187">默认视图包含详细介绍了解决安全弱点的列、相关威胁、受威胁影响的相关组件或软件等。</span><span class="sxs-lookup"><span data-stu-id="75139-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="75139-188">可以按建议的状态筛选项目。</span><span class="sxs-lookup"><span data-stu-id="75139-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="75139-189">软件清单</span><span class="sxs-lookup"><span data-stu-id="75139-189">Software inventory</span></span>

<span data-ttu-id="75139-190">" **软件清单** " 选项卡列出了设备上安装的软件。</span><span class="sxs-lookup"><span data-stu-id="75139-190">The **Software inventory** tab lists software installed on the device.</span></span>

![设备配置文件的 "软件清单" 选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="75139-192">默认视图显示软件供应商、已安装版本号、已知软件弱点数、威胁见解、产品代码和标记。</span><span class="sxs-lookup"><span data-stu-id="75139-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="75139-193">可以自定义所显示的项目数以及显示的列。</span><span class="sxs-lookup"><span data-stu-id="75139-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="75139-194">从该列表中选择一项将打开一个浮出控件，其中包含有关所选软件的更多详细信息，以及上次找到该软件时的路径和时间戳。</span><span class="sxs-lookup"><span data-stu-id="75139-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="75139-195">可以按产品代码筛选此列表。</span><span class="sxs-lookup"><span data-stu-id="75139-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="75139-196">发现的漏洞选项卡</span><span class="sxs-lookup"><span data-stu-id="75139-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="75139-197">" **发现漏洞** " 选项卡列出了可能会影响设备的任何常见漏洞和漏洞 (cve) 。</span><span class="sxs-lookup"><span data-stu-id="75139-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![设备配置文件的 "发现漏洞" 选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="75139-199">默认视图列出了 CVE 的严重性、常见漏洞分数 (CVS) 、与 CVE 有关的软件、发布 CVE 时、何时最后更新 CVE 以及与 CVE 相关的威胁。</span><span class="sxs-lookup"><span data-stu-id="75139-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="75139-200">与前面的选项卡一样，可以自定义所显示的项目数和可见的列。</span><span class="sxs-lookup"><span data-stu-id="75139-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="75139-201">从该列表中选择一项将打开一个描述 CVE 的浮出控件。</span><span class="sxs-lookup"><span data-stu-id="75139-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="75139-202">缺少 Kb</span><span class="sxs-lookup"><span data-stu-id="75139-202">Missing KBs</span></span>

<span data-ttu-id="75139-203">" **缺少 kb** " 选项卡列出了所有尚未应用于设备的 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="75139-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="75139-204">相关的 "Kb" 是介绍这些更新的 [知识库文章](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) 。例如， [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)。</span><span class="sxs-lookup"><span data-stu-id="75139-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![设备配置文件缺少 kb 选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="75139-206">默认视图列出包含更新、OS 版本、受影响的产品、Cve 地址、KB 编号和标记的公告。</span><span class="sxs-lookup"><span data-stu-id="75139-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="75139-207">每页显示的项目数和可自定义的列数。</span><span class="sxs-lookup"><span data-stu-id="75139-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="75139-208">选择某个项目将打开一个链接到更新的浮出控件。</span><span class="sxs-lookup"><span data-stu-id="75139-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="75139-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="75139-209">Related topics</span></span>

* [<span data-ttu-id="75139-210">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="75139-210">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="75139-211">启用 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75139-211">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
* [<span data-ttu-id="75139-212">使用实时响应调查设备上的实体</span><span class="sxs-lookup"><span data-stu-id="75139-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="75139-213">Office 365 中的自动调查和响应 (空中) </span><span class="sxs-lookup"><span data-stu-id="75139-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
