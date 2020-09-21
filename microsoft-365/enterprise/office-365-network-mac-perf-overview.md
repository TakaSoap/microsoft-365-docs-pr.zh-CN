---
title: 'Microsoft 365 管理中心中的网络连接 (预览版) '
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
description: 'Microsoft 365 管理中心中的网络连接概述 (预览) '
ms.openlocfilehash: 35ea28ec45a7e581901c0f4f22360a1dcd0def8b
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962283"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center-preview"></a><span data-ttu-id="b46db-103">Microsoft 365 管理中心中的网络连接 (预览版) </span><span class="sxs-lookup"><span data-stu-id="b46db-103">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>

<span data-ttu-id="b46db-104">Microsoft 365 管理中心现在包含从 Microsoft 365 租户收集的聚合网络连接指标，仅可供租户中的管理用户查看。</span><span class="sxs-lookup"><span data-stu-id="b46db-104">The Microsoft 365 Admin Center now includes aggregated network connectivity metrics collected from your Microsoft 365 tenant and available to view only by administrative users in your tenant.</span></span>

![网络连接测试工具](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

<span data-ttu-id="b46db-106">**网络评估** 和 **网络洞察力** 显示在 Microsoft 365 管理中心的 **运行状况 |连接**。</span><span class="sxs-lookup"><span data-stu-id="b46db-106">**Network assessments** and **network insights** are displayed in the Microsoft 365 Admin Center under **Health | Connectivity**.</span></span>

![网络性能页面](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

<span data-ttu-id="b46db-108">当您第一次导航到 "网络连接" 页面时，您将看到一个 "概述" 窗格，其中包含全局网络性能的地图、网络评估范围限定为整个租户以及当前问题的列表。</span><span class="sxs-lookup"><span data-stu-id="b46db-108">When you first navigate to the network connectivity page, you will see an overview pane containing a map of global network performance, a network assessment scoped to the entire tenant, and a list of current issues.</span></span> <span data-ttu-id="b46db-109">从概述中，您可以深入查看特定的网络性能指标和按位置的问题。</span><span class="sxs-lookup"><span data-stu-id="b46db-109">From the overview, you can drill down to view specific network performance metrics and issues by location.</span></span> <span data-ttu-id="b46db-110">有关详细信息，请参阅 [Microsoft 365 管理中心中的网络性能概述](#network-connectivity-overview-in-the-microsoft-365-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="b46db-110">For more information, see [Network performance overview in the Microsoft 365 Admin Center](#network-connectivity-overview-in-the-microsoft-365-admin-center).</span></span>

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a><span data-ttu-id="b46db-111">将显示网络连接评估的必备组件</span><span class="sxs-lookup"><span data-stu-id="b46db-111">Pre-requisites for network connectivity assessments to appear</span></span>

<span data-ttu-id="b46db-112">从你的办公室位置获取网络评估有三个选项：</span><span class="sxs-lookup"><span data-stu-id="b46db-112">There are three options for getting network assessments from your office locations:</span></span>

### <a name="1-enable-windows-location-services"></a><span data-ttu-id="b46db-113">1. 启用 Windows 定位服务</span><span class="sxs-lookup"><span data-stu-id="b46db-113">1. Enable Windows Location Services</span></span>

<span data-ttu-id="b46db-114">对于此选项，必须在每个支持必备组件的办公室位置至少有两台计算机运行。</span><span class="sxs-lookup"><span data-stu-id="b46db-114">For this option you must have at least two computers running at each office location that support the pre-requisites.</span></span> <span data-ttu-id="b46db-115">必须在每台计算机上安装 OneDrive for Windows 版本 **19.232** 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b46db-115">OneDrive for Windows version **19.232** or above must be installed on each computer.</span></span> <span data-ttu-id="b46db-116">有关 OneDrive 版本的详细信息，请参阅 [onedrive 发行说明](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0)。</span><span class="sxs-lookup"><span data-stu-id="b46db-116">For more information on OneDrive versions, see the [OneDrive release notes](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="b46db-117">在不久的将来，会计划在其他 Office 365 客户端应用程序中添加网络度量。</span><span class="sxs-lookup"><span data-stu-id="b46db-117">Network measurements are planned to be added in other Office 365 client applications in the near future.</span></span>

<span data-ttu-id="b46db-118">Windows 位置服务必须在计算机上同意。</span><span class="sxs-lookup"><span data-stu-id="b46db-118">Windows Location Service must be consented on the machines.</span></span> <span data-ttu-id="b46db-119">您可以通过运行 " **地图** " 应用并找到自己来对此进行测试。</span><span class="sxs-lookup"><span data-stu-id="b46db-119">You can test this by running the **Maps** app and locating yourself.</span></span> <span data-ttu-id="b46db-120">可以在具有设置的单台计算机上启用此功能 **|隐私 |** 必须启用设置 _允许应用访问你的位置_ 的位置。</span><span class="sxs-lookup"><span data-stu-id="b46db-120">It can be enabled on a single machine with **Settings | Privacy | Location** where the setting _Allow apps to access your location_ must be enabled.</span></span> <span data-ttu-id="b46db-121">可以将 Windows 位置服务同意部署到使用 MDM 或组策略的电脑中，设置 _LetAppsAccessLocation_。</span><span class="sxs-lookup"><span data-stu-id="b46db-121">Windows Location Services consent can be deployed to PCs using MDM or Group Policy with the setting _LetAppsAccessLocation_.</span></span>

<span data-ttu-id="b46db-122">您无需使用此方法在管理中心中添加位置，因为它们会在城市分辨率中自动标识。</span><span class="sxs-lookup"><span data-stu-id="b46db-122">You do not need to add locations in the Admin Center with this method as they are automatically identified at the city resolution.</span></span> <span data-ttu-id="b46db-123">您不能使用 Windows 定位服务在城市中显示多个办公室位置。</span><span class="sxs-lookup"><span data-stu-id="b46db-123">You cannot show multiple office locations within a city using Windows Location Services.</span></span>

<span data-ttu-id="b46db-124">计算机应具有 Wi-fi 网络，而不是以太网电缆。</span><span class="sxs-lookup"><span data-stu-id="b46db-124">The machines should have Wi-Fi networking rather than an ethernet cable.</span></span> <span data-ttu-id="b46db-125">具有以太网电缆的计算机没有准确的位置信息。</span><span class="sxs-lookup"><span data-stu-id="b46db-125">Machines with an ethernet cable do not have accurate location information.</span></span>

<span data-ttu-id="b46db-126">满足这些先决条件后，度量样本和办公室位置应会在24小时后开始显示。</span><span class="sxs-lookup"><span data-stu-id="b46db-126">Measurement samples and office locations should start to appear 24 hours after these pre-requisites have been met.</span></span>

### <a name="2-add-locations-and-provide-lan-subnet-information"></a><span data-ttu-id="b46db-127">2. 添加位置并提供 LAN 子网信息</span><span class="sxs-lookup"><span data-stu-id="b46db-127">2. Add locations and provide LAN subnet information</span></span>

<span data-ttu-id="b46db-128">对于此选项，Windows 定位服务和 Wi-fi 都不是必需的。</span><span class="sxs-lookup"><span data-stu-id="b46db-128">For this option neither Windows Location Services nor Wi-Fi are required.</span></span> <span data-ttu-id="b46db-129">您需要在每台计算机上安装了 OneDrive for Windows 版本20.161 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b46db-129">You need OneDrive for Windows version 20.161 or above installed on each computer at the location.</span></span>

<span data-ttu-id="b46db-130">此外，还需要在管理中心网络连接页面中添加位置，或从 CSV 文件中导入这些位置。</span><span class="sxs-lookup"><span data-stu-id="b46db-130">You also need to add locations in the Admin Center network connectivity page or to import those from a CSV file.</span></span> <span data-ttu-id="b46db-131">添加的位置必须包含 office LAN 子网信息。</span><span class="sxs-lookup"><span data-stu-id="b46db-131">The locations added must include your office LAN subnet information.</span></span>

<span data-ttu-id="b46db-132">由于要添加位置，因此可以在城市内定义多个办事处。</span><span class="sxs-lookup"><span data-stu-id="b46db-132">Because you are adding the locations, you can have multiple offices defined within a city.</span></span>

<span data-ttu-id="b46db-133">满足这些先决条件后，度量样本和办公室位置应会在24小时后开始显示。</span><span class="sxs-lookup"><span data-stu-id="b46db-133">Measurement samples and office locations should start to appear 24 hours after these pre-requisites have been met.</span></span>

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a><span data-ttu-id="b46db-134">3. 使用 Microsoft 365 网络连接测试工具手动收集测试报告</span><span class="sxs-lookup"><span data-stu-id="b46db-134">3. Manually gather test reports with the Microsoft 365 network connectivity test tool</span></span>

<span data-ttu-id="b46db-135">对于此选项，您需要在每个位置标识一个人。</span><span class="sxs-lookup"><span data-stu-id="b46db-135">For this option you need to identify a person at each location.</span></span> <span data-ttu-id="b46db-136">请他们在其上具有管理权限的 Windows 计算机上，浏览到 [Microsoft 365 网络连接测试](https://connectivity.office.com) 。</span><span class="sxs-lookup"><span data-stu-id="b46db-136">Ask them to browser to [Microsoft 365 network connectivity test](https://connectivity.office.com) on a Windows machine that they have administrative permissions on.</span></span> <span data-ttu-id="b46db-137">在网站上，他们需要在您想要查看结果的同一租户上登录到他们的 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="b46db-137">On the web site, they need to sign-in to their Office 365 account on the same tenant that you want to see the results.</span></span> <span data-ttu-id="b46db-138">然后单击 "运行测试"。</span><span class="sxs-lookup"><span data-stu-id="b46db-138">Then they click Run test.</span></span> <span data-ttu-id="b46db-139">在测试过程中有一个已下载的连接测试 EXE。</span><span class="sxs-lookup"><span data-stu-id="b46db-139">During the test there is a downloaded Connectivity test EXE.</span></span> <span data-ttu-id="b46db-140">他们还需要打开和执行。</span><span class="sxs-lookup"><span data-stu-id="b46db-140">They need to open and execute that also.</span></span> <span data-ttu-id="b46db-141">测试完成后，测试结果将上传到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="b46db-141">Once the tests are completed, the test result is uploaded to Microsoft.</span></span>

<span data-ttu-id="b46db-142">如果将测试报告添加到 LAN 子网信息中，则会将这些报告链接到该位置，否则这些报告将仅显示在城市位置。</span><span class="sxs-lookup"><span data-stu-id="b46db-142">Test reports are linked to a location if it was added with LAN subnet information, otherwise they are shown at the city location only.</span></span>

<span data-ttu-id="b46db-143">测试结果完成后，度量样本和办公室位置应会在2-3 分钟后开始。</span><span class="sxs-lookup"><span data-stu-id="b46db-143">Measurement samples and office locations should start to appear 2-3 minutes after a test result is completed.</span></span>

## <a name="how-do-i-use-this-information"></a><span data-ttu-id="b46db-144">如何使用此信息？</span><span class="sxs-lookup"><span data-stu-id="b46db-144">How do I use this information?</span></span>

<span data-ttu-id="b46db-145">**网络洞察力**、其相关的性能建议和网络评估旨在帮助为你的办公室位置设计网络外围。</span><span class="sxs-lookup"><span data-stu-id="b46db-145">**Network insights**, their related performance recommendations and network assessments are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="b46db-146">每个真知灼见都提供有关用户访问你的租户的每个地理位置的特定常见问题的性能特征的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b46db-146">Each insight provides details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span> <span data-ttu-id="b46db-147">每个网络洞察力的**性能建议**提供了您可以进行的特定网络体系结构设计更改，以改进与 Microsoft 365 网络连接相关的用户体验。</span><span class="sxs-lookup"><span data-stu-id="b46db-147">**Performance recommendations** for each network insight offer specific network architecture design changes you can make to improve user experience related to Microsoft 365 network connectivity.</span></span> <span data-ttu-id="b46db-148">网络评估显示网络连接对用户体验的影响，从而允许比较不同的用户位置网络连接。</span><span class="sxs-lookup"><span data-stu-id="b46db-148">The network assessment shows how network connectivity impacts user experience, allowing for comparison of different user location network connections.</span></span>

<span data-ttu-id="b46db-149">**网络评估** 将许多网络性能指标的聚合提取到企业网络运行状况的快照中，由 0-100 中的点值表示。</span><span class="sxs-lookup"><span data-stu-id="b46db-149">**Network assessments** distill an aggregate of many network performance metrics into a snapshot of your enterprise network health, represented by a points value from 0 - 100.</span></span> <span data-ttu-id="b46db-150">网络评估的作用范围为整个租户和每个地理位置，用户将从该位置连接到你的租户，从而为 Microsoft 365 管理员提供一种简单的方法来即时了解企业网络运行状况的 gestalt，并快速深入到任何全球办公地点的详细报告。</span><span class="sxs-lookup"><span data-stu-id="b46db-150">Network assessments are scoped to both the entire tenant and for each geographic location from which users connect to your tenant, providing Microsoft 365 administrators with an easy way to instantly grasp a gestalt of the enterprise's network health and quickly drill down into a detailed report for any global office location.</span></span>

<span data-ttu-id="b46db-151">具有多个办公室位置和非普通网络外围体系结构的复杂企业可以在初始加入 Microsoft 365 或解决使用情况增长发现的网络性能问题时从这些信息中受益。</span><span class="sxs-lookup"><span data-stu-id="b46db-151">Complex enterprises with multiple office locations and non-trivial network perimeter architectures can benefit from this information either during their initial onboarding to Microsoft 365 or to remediate network performance issues discovered with usage growth.</span></span> <span data-ttu-id="b46db-152">对于使用 Microsoft 365 的小型企业或已具有简单且直接的网络连接的企业，这通常是不必要的。</span><span class="sxs-lookup"><span data-stu-id="b46db-152">This is usually not necessary for small businesses using Microsoft 365, or any enterprises who already have simple and direct network connectivity.</span></span> <span data-ttu-id="b46db-153">具有500个以上的用户和多个办公地点的企业有望获益最多。</span><span class="sxs-lookup"><span data-stu-id="b46db-153">Enterprises with over 500 users and multiple office locations are expected to benefit the most.</span></span>

>[!IMPORTANT]
><span data-ttu-id="b46db-154">网络洞察力、Microsoft 365 管理中心中的性能建议和评估当前处于预览状态，并且仅适用于已在功能预览计划中注册的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="b46db-154">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="enterprise-network-connectivity-challenges"></a><span data-ttu-id="b46db-155">企业网络连接难题</span><span class="sxs-lookup"><span data-stu-id="b46db-155">Enterprise network connectivity challenges</span></span>

![客户网络到云](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

<span data-ttu-id="b46db-157">许多企业都具有网络外围配置，这些配置随着时间的推移而逐渐发展，主要旨在适应员工 Internet 网站访问，其中大多数网站都不是预先知道的，不受信任。</span><span class="sxs-lookup"><span data-stu-id="b46db-157">Many enterprises have network perimeter configurations which have grown over time and are primarily designed to accommodate employee Internet web site access where most web sites are not known in advance and are untrusted.</span></span> <span data-ttu-id="b46db-158">这些未知网站的受攻击和必要的重点是避免恶意软件和钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="b46db-158">The prevailing and necessary focus is avoiding malware and fishing attacks from these unknown web sites.</span></span> <span data-ttu-id="b46db-159">此网络配置策略虽然有助于安全目的，但会导致 Microsoft 365 用户性能和用户体验下降。</span><span class="sxs-lookup"><span data-stu-id="b46db-159">This network configuration strategy, while helpful for security purposes, can lead to degradation of Microsoft 365 user performance and user experience.</span></span>

## <a name="how-we-can-solve-these-challenges"></a><span data-ttu-id="b46db-160">我们可以如何解决这些难题</span><span class="sxs-lookup"><span data-stu-id="b46db-160">How we can solve these challenges</span></span>

<span data-ttu-id="b46db-161">企业可以通过遵循 [Office 365 连接原则](https://aka.ms/pnc) 和使用 Microsoft 365 管理中心网络连接功能来改进常规用户体验并保护其环境。</span><span class="sxs-lookup"><span data-stu-id="b46db-161">Enterprises can improve general user experience and secure their environment by following [Office 365 connectivity principles](https://aka.ms/pnc) and by using the Microsoft 365 Admin Center network connectivity feature.</span></span> <span data-ttu-id="b46db-162">在大多数情况下，遵循这些常规原则将对最终用户延迟、服务可靠性和 Microsoft 365 的总体性能产生重大影响。</span><span class="sxs-lookup"><span data-stu-id="b46db-162">In most cases, following these general principles will have a significant positive impact on end user latency, service reliability and overall performance of Microsoft 365.</span></span>

<span data-ttu-id="b46db-163">有时，microsoft 需要调查大型企业客户的 Microsoft 365 的网络性能问题，并且这些问题通常有与客户网络出口基础结构相关的根本原因。</span><span class="sxs-lookup"><span data-stu-id="b46db-163">Microsoft is sometimes asked to investigate network performance issues with Microsoft 365 for large enterprise customers, and these frequently have a root cause related to the customers network egress infrastructure.</span></span> <span data-ttu-id="b46db-164">当发现客户网络外围问题的常见根源时，我们会设法确定确定它的简单测试指标。</span><span class="sxs-lookup"><span data-stu-id="b46db-164">When a common root cause of a customer network perimeter issue is found we seek to identify simple test measurements that identifies it.</span></span> <span data-ttu-id="b46db-165">具有确定特定问题的度量阈值的测试非常有用，因为我们可以在任何位置测试相同的指标，告知是否存在此根本原因，并将其共享为与管理员的网络洞察力。</span><span class="sxs-lookup"><span data-stu-id="b46db-165">A test with a measurement threshold that identifies a specific problem is valuable because we can test the same measurement at any location, tell whether this root cause is present there and share it as a network insight with the administrator.</span></span>

<span data-ttu-id="b46db-166">一些网络见解只表示需要进一步调查的问题。</span><span class="sxs-lookup"><span data-stu-id="b46db-166">Some network insights will merely indicate a problem that needs further investigation.</span></span> <span data-ttu-id="b46db-167">一种网络洞察力，其中我们有足够的测试来显示解决根本原因的特定修正操作，作为 **建议的操作**列出。</span><span class="sxs-lookup"><span data-stu-id="b46db-167">A network insight where we have enough tests to show a specific remediation action to correct the root cause is listed as a **recommended action**.</span></span> <span data-ttu-id="b46db-168">这些建议基于实时指标，其中显示超出预先确定的阈值之外的值，比一般的最佳实践建议更有价值，因为它们是特定于您的环境的，并且会在进行建议的更改后显示实际的改进。</span><span class="sxs-lookup"><span data-stu-id="b46db-168">These recommendations, based on live metrics that reveal values that fall outside a predetermined threshold, are much more valuable than general best practice advice since they are specific to your environment and will show the actual improvement once the recommended changes have been made.</span></span>

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b46db-169">Microsoft 365 管理中心中的网络连接概述</span><span class="sxs-lookup"><span data-stu-id="b46db-169">Network connectivity overview in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="b46db-170">Microsoft 从多个 Office 桌面和 web 客户端中获得了支持 Microsoft 365 操作的现有网络度量。</span><span class="sxs-lookup"><span data-stu-id="b46db-170">Microsoft has existing network measurements from several Office desktop and web clients which support the operation of Microsoft 365.</span></span> <span data-ttu-id="b46db-171">这些度量现在用于提供网络体系结构设计见解和网络评估，这些数据显示在 Microsoft 365 管理中心的 " **网络连接** " 页面中。</span><span class="sxs-lookup"><span data-stu-id="b46db-171">These measurements are now being used to provide network architecture design insights and a network assessment which are shown in the **Network connectivity** page in the Microsoft 365 Admin Center.</span></span>

<span data-ttu-id="b46db-172">默认情况下，与网络度量相关联的近似位置信息标识客户端设备所在的城市。</span><span class="sxs-lookup"><span data-stu-id="b46db-172">By default, approximate location information associated with the network measurements identify the city where client devices are located.</span></span> <span data-ttu-id="b46db-173">每个位置的网络评估均以颜色显示，并且每个位置的用户相对数量由圆的大小表示。</span><span class="sxs-lookup"><span data-stu-id="b46db-173">The network assessment at each location is shown with color and the relative number of users at each location is represented by the size of the circle.</span></span>

![网络洞察力概述映射](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

<span data-ttu-id="b46db-175">概述页面还显示了客户的网络评估，作为所有办公地点的加权平均。</span><span class="sxs-lookup"><span data-stu-id="b46db-175">The overview page also shows the network assessment for the customer as a weighted average across all office locations.</span></span>

![网络评估](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

## <a name="specific-office-location-network-performance-summary-and-insights"></a><span data-ttu-id="b46db-177">特定的办公室位置网络性能摘要和见解</span><span class="sxs-lookup"><span data-stu-id="b46db-177">Specific office location network performance summary and insights</span></span>

<span data-ttu-id="b46db-178">选择 "办公室位置" 将打开一个特定位置的摘要页面，其中显示了已从该办公室位置测量指标中标识的网络出口的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b46db-178">Selecting an office location opens a location-specific summary page showing details of the network egress that has been identified from measurements for that office location.</span></span>

![按位置的网络洞察力详细信息](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

<span data-ttu-id="b46db-180">"Office 位置摘要" 页还会显示位置的网络评估、网络评估历史记录、此位置的评估与同一城市中的其他客户的比较，以及您可以采取以提高网络性能和可靠性的特定见解和建议的列表。</span><span class="sxs-lookup"><span data-stu-id="b46db-180">The office location summary page additionally shows the location's network assessment, network assessment history, a comparison of this location's assessment to other customers in the same city, and a list of specific insights and recommendations that you can undertake to improve network performance and reliability.</span></span> <span data-ttu-id="b46db-181">具有特定建议的位置也可能包括估计的潜在延迟改进。</span><span class="sxs-lookup"><span data-stu-id="b46db-181">Locations with specific recommendations may also include an estimated potential latency improvement.</span></span>

<span data-ttu-id="b46db-182">同一个城市中的客户之间的比较取决于所有客户都具有对网络服务提供商、电信基础结构和附近 Microsoft 网络状态点的同等访问权限的预期。</span><span class="sxs-lookup"><span data-stu-id="b46db-182">Comparisons between customers in the same city are based on the expectation that all customers have equal access to network service providers, telecommunications infrastructure, and nearby Microsoft network points of presence.</span></span>

![网络见解位置](../media/m365-mac-perf/m365-mac-perf-locations.png)

<span data-ttu-id="b46db-184">"Office 位置" 页上的 "详细信息" 选项卡显示了用于提供任何见解、建议和网络评估的具体测量结果。</span><span class="sxs-lookup"><span data-stu-id="b46db-184">The details tab on the office location page shows the specific measurement results that were used to come up with any insights, recommendations, and the network assessment.</span></span> <span data-ttu-id="b46db-185">提供此信息是为了让网络工程师能够验证其环境中的任何约束或细节方面的建议和因素。</span><span class="sxs-lookup"><span data-stu-id="b46db-185">This is provided so that network engineers can validate the recommendations and factor in any constraints or specifics in their environment.</span></span>

![位置特定的详细信息](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

## <a name="csv-import-for-lan-subnet-office-locations"></a><span data-ttu-id="b46db-187">LAN 子网办公地点的 CSV 导入</span><span class="sxs-lookup"><span data-stu-id="b46db-187">CSV Import for LAN subnet office locations</span></span>

<span data-ttu-id="b46db-188">对于 LAN 子网办公室标识，需要提前添加每个位置。</span><span class="sxs-lookup"><span data-stu-id="b46db-188">For LAN subnet office identification, you need to add each location in advance.</span></span> <span data-ttu-id="b46db-189">您可以从 CSV 文件中导入它们，而不是在 " **位置** " 选项卡中添加各个办公室位置。</span><span class="sxs-lookup"><span data-stu-id="b46db-189">Instead of adding individual office locations in the **Locations** tab you can import them from a CSV file.</span></span> <span data-ttu-id="b46db-190">你可以从存储它的其他位置（如呼叫质量仪表板或 Active Directory 站点和服务）获取此数据</span><span class="sxs-lookup"><span data-stu-id="b46db-190">You may be able to obtain this data from other places you have stored it such as the Call Quality Dashboard or Active Directory Sites and Services</span></span>

<span data-ttu-id="b46db-191">在 CSV 文件中，发现的城市位置标记为 " **城市**"，并且手动添加的 "office 位置" 标记为 " **位置**"。</span><span class="sxs-lookup"><span data-stu-id="b46db-191">In the CSV file a discovered city location is labeled **City**, and a manually added office location is labeled **Location**.</span></span>

1. <span data-ttu-id="b46db-192">在 " _Microsoft 365_ 的主要连接" 窗口中，单击 " **位置** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b46db-192">In the main _Connectivity to Microsoft 365_ window, click the **Locations** tab.</span></span>
1. <span data-ttu-id="b46db-193">单击 "位置" 列表正上方的 " **导入** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="b46db-193">Click the **Import** button just above the locations list.</span></span> <span data-ttu-id="b46db-194">将显示 " **导入 office 位置** " 浮出控件。</span><span class="sxs-lookup"><span data-stu-id="b46db-194">The **Import office locations** flyout will appear.</span></span>

   ![CSV 导入邮件](../media/m365-mac-perf/m365-mac-perf-import.png)

1. <span data-ttu-id="b46db-196">单击 " \*\*下载当前的 office 位置 ( .csv) \*\* 链接以将" 当前位置 "列表导出到 csv 文件，并将其保存到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="b46db-196">Click the **Download current office locations (.csv)** link to export the current locations list to a CSV file, and save it to your local hard disk.</span></span> <span data-ttu-id="b46db-197">这将为您提供一个格式正确的 CSV 以及您可以向其添加位置的列标题。</span><span class="sxs-lookup"><span data-stu-id="b46db-197">This will provide you with a correctly formatted CSV with column headings to which you can add locations.</span></span> <span data-ttu-id="b46db-198">您可以将现有导出的位置保留原样;当您导入更新的 CSV 时，将不会复制它们。</span><span class="sxs-lookup"><span data-stu-id="b46db-198">You can leave the existing exported locations as they are; they will not be duplicated when you import the updated CSV.</span></span> <span data-ttu-id="b46db-199">如果要更改现有位置的地址，则会在您导入 CSV 时对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="b46db-199">If you wish to change the address of an existing location, it will be updated when you import the CSV.</span></span> <span data-ttu-id="b46db-200">您无法更改发现的城市的地址。</span><span class="sxs-lookup"><span data-stu-id="b46db-200">You cannot change the address of a discovered city.</span></span>
1. <span data-ttu-id="b46db-201">打开 CSV 并添加您的位置，方法是在要添加的每个位置的新行上填写以下字段。</span><span class="sxs-lookup"><span data-stu-id="b46db-201">Open the CSV and add your locations by filling out the following fields on a new line for each location you want to add.</span></span> <span data-ttu-id="b46db-202">将所有其他字段保留为空;您在其他字段中输入的值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="b46db-202">Leave all other fields blank; values you enter in other fields will be ignored.</span></span>
   1. <span data-ttu-id="b46db-203">**Address** (必需的) ：办公室的物理地址</span><span class="sxs-lookup"><span data-stu-id="b46db-203">**Address** (required): The physical address of the office</span></span>
   1. <span data-ttu-id="b46db-204">**纬度** (可选) ：如果为空，则从 Bing 地图查找中填充</span><span class="sxs-lookup"><span data-stu-id="b46db-204">**Latitude** (optional): Populated from Bing maps lookup if blank</span></span>
   1. <span data-ttu-id="b46db-205">**经度** (可选) ：如果为空，则从 Bing 地图查找中填充</span><span class="sxs-lookup"><span data-stu-id="b46db-205">**Longitude** (optional): Populated from Bing maps lookup if blank</span></span>
   1. <span data-ttu-id="b46db-206">**出局 IP 地址范围 1-5** (可选) ：对于每个区域，输入电路名称，后跟一个以空格分隔的有效 IPv4 或 IPv6 CIDR 地址列表。</span><span class="sxs-lookup"><span data-stu-id="b46db-206">**Egress IP Address ranges 1-5** (optional): For each range, enter the circuit name followed by a space separated list of valid IPv4 or IPv6 CIDR addresses.</span></span> <span data-ttu-id="b46db-207">这些值用于区分使用相同 LAN 子网 IP 地址的多个办公室位置。</span><span class="sxs-lookup"><span data-stu-id="b46db-207">These values are used to differentiate multiple office locations where you use the same LAN subnet IP Addresses.</span></span>
   1. <span data-ttu-id="b46db-208">**LanIps** (必需的) ：列出在此办公室位置使用的 LAN 子网区域。</span><span class="sxs-lookup"><span data-stu-id="b46db-208">**LanIps** (required): List the LAN subnet ranges in use at this office location.</span></span>
1. <span data-ttu-id="b46db-209">添加办公室位置并保存文件后，单击 "**上载完成**时间" 字段旁边的 "**浏览**" 按钮，然后选择保存的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="b46db-209">When you have added your office locations and saved the file, click the **Browse** button next to the **Upload the completed** field and select the saved CSV file.</span></span>
1. <span data-ttu-id="b46db-210">将自动验证文件。</span><span class="sxs-lookup"><span data-stu-id="b46db-210">The file will be automatically validated.</span></span> <span data-ttu-id="b46db-211">如果存在验证错误，您将看到错误消息 _导入文件中存在一些错误。请查看错误，更正导入文件，然后重试。_</span><span class="sxs-lookup"><span data-stu-id="b46db-211">If there are validation errors, you will see the error message _There are some errors in the import file. Review the errors, correct the import file, and then try again._</span></span> <span data-ttu-id="b46db-212">有关特定字段验证错误的列表，请单击链接的 " **打开错误详细信息** "。</span><span class="sxs-lookup"><span data-stu-id="b46db-212">Click the link **Open error details** for a list of specific field validation errors.</span></span>

   ![CSV 导入错误消息](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. <span data-ttu-id="b46db-214">如果文件中没有任何错误，您将看到 _报告已准备好的消息。找到要添加的 x 位置和要更新的 x 位置。_</span><span class="sxs-lookup"><span data-stu-id="b46db-214">If there are no errors in the file, you will see the message _The report is ready. Found x locations to add and x locations to update._</span></span> <span data-ttu-id="b46db-215">单击 " **导入** " 按钮上传 CSV。</span><span class="sxs-lookup"><span data-stu-id="b46db-215">Click the **Import** button to upload the CSV.</span></span>

   ![CSV 导入就绪消息](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a><span data-ttu-id="b46db-217">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="b46db-217">FAQ</span></span>

### <a name="what-is-a-microsoft-365-service-front-door"></a><span data-ttu-id="b46db-218">什么是 Microsoft 365 服务的前盖？</span><span class="sxs-lookup"><span data-stu-id="b46db-218">What is a Microsoft 365 service front door?</span></span>

<span data-ttu-id="b46db-219">Microsoft 365 服务的前端是 Microsoft 全球网络的一个入口点，Office 客户端和服务终止其网络连接。</span><span class="sxs-lookup"><span data-stu-id="b46db-219">The Microsoft 365 service front door is an entry point on Microsoft's global network where Office clients and services terminate their network connection.</span></span> <span data-ttu-id="b46db-220">为实现到 Microsoft 365 的最佳网络连接，建议将您的网络连接终止为最近的 Microsoft 365 前盖。</span><span class="sxs-lookup"><span data-stu-id="b46db-220">For an optimal network connection to Microsoft 365, it is recommended that your network connection is terminated into the closest Microsoft 365 front door.</span></span>

>[!NOTE]
><span data-ttu-id="b46db-221">Microsoft 365 服务前向与 azure marketplace 提供的 Azure 前门服务产品没有直接关系。</span><span class="sxs-lookup"><span data-stu-id="b46db-221">Microsoft 365 service front door has no direct relationship to the Azure Front Door Service product available in the Azure marketplace.</span></span>

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a><span data-ttu-id="b46db-222">什么是最佳 Microsoft 365 服务前门？</span><span class="sxs-lookup"><span data-stu-id="b46db-222">What is an optimal Microsoft 365 service front door?</span></span>

<span data-ttu-id="b46db-223">最佳 Microsoft 365 服务前盖是最接近你的网络出口（通常在你所在的城市或大都市区域中）的一门。</span><span class="sxs-lookup"><span data-stu-id="b46db-223">An optimal Microsoft 365 service front door is one that is closest to your network egress, generally in your city or metro area.</span></span> <span data-ttu-id="b46db-224">使用 [microsoft 365 连接测试](office-365-network-mac-perf-onboarding-tool.md) 确定正在使用的 microsoft 365 服务前盖和最佳服务前盖的位置。</span><span class="sxs-lookup"><span data-stu-id="b46db-224">Use the [Microsoft 365 connectivity test](office-365-network-mac-perf-onboarding-tool.md) to determine location of your in-use Microsoft 365 service front door and optimal service front door.</span></span> <span data-ttu-id="b46db-225">如果该工具确定你的使用中的前向门是最佳的，则表示你正在以最佳方式连接到 Microsoft 的全球网络。</span><span class="sxs-lookup"><span data-stu-id="b46db-225">If the tool determines your in-use front door is optimal, then you are optimally connecting into Microsoft's global network.</span></span>

### <a name="what-is-an-internet-egress-location"></a><span data-ttu-id="b46db-226">Internet 出口的位置是什么？</span><span class="sxs-lookup"><span data-stu-id="b46db-226">What is an internet egress location?</span></span>

<span data-ttu-id="b46db-227">Internet 出局位置是网络流量退出企业网络并连接到 Internet 的位置。</span><span class="sxs-lookup"><span data-stu-id="b46db-227">The internet egress location is the location where your network traffic exits your enterprise network and connects to the Internet.</span></span> <span data-ttu-id="b46db-228">这也标识为您的网络地址转换 (NAT) 设备的位置，通常与 Internet 服务提供商 (ISP) 进行连接的位置相同。</span><span class="sxs-lookup"><span data-stu-id="b46db-228">This is also identified as the location where you have a Network Address Translation (NAT) device and usually where you connect with an Internet Service Provider (ISP).</span></span> <span data-ttu-id="b46db-229">如果你发现您的位置和 internet 出局位置之间的距离很长，则这可能表示有重要的 WAN backhaul。</span><span class="sxs-lookup"><span data-stu-id="b46db-229">If you see a long distance between your location and your internet egress location, then this may indicate a significant WAN backhaul.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b46db-230">相关主题</span><span class="sxs-lookup"><span data-stu-id="b46db-230">Related topics</span></span>

[<span data-ttu-id="b46db-231">Microsoft 365 网络见解 (预览) </span><span class="sxs-lookup"><span data-stu-id="b46db-231">Microsoft 365 network insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="b46db-232">Microsoft 365 网络评估 (预览版) </span><span class="sxs-lookup"><span data-stu-id="b46db-232">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="b46db-233">M365 管理中心中的 Microsoft 365 连接测试 (preview) </span><span class="sxs-lookup"><span data-stu-id="b46db-233">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="b46db-234">Microsoft 365 网络连接位置服务 (预览) </span><span class="sxs-lookup"><span data-stu-id="b46db-234">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)

[<span data-ttu-id="b46db-235">Microsoft 365 网络连接测试工具 (预览) </span><span class="sxs-lookup"><span data-stu-id="b46db-235">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
