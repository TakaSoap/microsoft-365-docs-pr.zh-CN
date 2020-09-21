---
title: 'Microsoft 365 网络连接测试 (预览) '
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
description: 'Microsoft 365 网络连接测试 (预览) '
ms.openlocfilehash: 2197f3361efee51dfa2bd170b0c8d8e94709d3e8
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962392"
---
# <a name="microsoft-365-network-connectivity-test-preview"></a><span data-ttu-id="d877b-103">Microsoft 365 网络连接测试 (预览) </span><span class="sxs-lookup"><span data-stu-id="d877b-103">Microsoft 365 network connectivity test (preview)</span></span>

<span data-ttu-id="d877b-104">Microsoft 365 网络连接测试工具位于 <https://connectivity.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="d877b-104">The Microsoft 365 network connectivity test tool is located at <https://connectivity.office.com>.</span></span> <span data-ttu-id="d877b-105">它是一种辅助工具，适用于 Microsoft 365 管理中心中的 "网络评估" 和 "网络洞察力" 信息，在 **运行状况 |连接** 菜单。</span><span class="sxs-lookup"><span data-stu-id="d877b-105">It is an adjunct tool to the network assessment and network insights information available in the Microsoft 365 admin center under the **Health | Connectivity** menu.</span></span>

![连接测试工具](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
><span data-ttu-id="d877b-107">网络连接测试工具支持 WW 商业和德国的租户，但不支持 GCC 中、GCC 高级、DoD 或中国的租户。</span><span class="sxs-lookup"><span data-stu-id="d877b-107">The network connectivity test tool supports tenants in WW Commercial and Germany but not GCC Moderate, GCC High, DoD or China.</span></span>

<span data-ttu-id="d877b-108">Microsoft 365 管理中心中的网络见解基于每天进行聚合的 Microsoft 365 租户的定期产品度量。</span><span class="sxs-lookup"><span data-stu-id="d877b-108">The network insights in the Microsoft 365 Admin Center are based on regular in-product measurements for your Microsoft 365 tenant which are aggregated each day.</span></span> <span data-ttu-id="d877b-109">相比之下，Microsoft 365 网络连接测试中的网络洞察力在本地运行，一次在该工具中运行。</span><span class="sxs-lookup"><span data-stu-id="d877b-109">In comparison, the network insights from the Microsoft 365 network connectivity test are run locally and one time in the tool.</span></span> <span data-ttu-id="d877b-110">可以在产品中完成的测试是有限的，并且可以通过在用户的本地运行测试来收集更多数据，从而获得更深入的见解。</span><span class="sxs-lookup"><span data-stu-id="d877b-110">Testing that can be done in-product is limited and by running tests local to the user more data can be gathered resulting in deeper insights.</span></span> <span data-ttu-id="d877b-111">请考虑，Microsoft 365 管理中心中的网络见解将显示在特定办公地点使用 Microsoft 365 的网络问题。</span><span class="sxs-lookup"><span data-stu-id="d877b-111">Consider then that the network insights in the Microsoft 365 Admin Center will show that there is a networking problem for use of Microsoft 365 at a specific office location.</span></span> <span data-ttu-id="d877b-112">Microsoft 365 连接测试可帮助确定问题的根本原因，从而导致建议的网络性能改进操作。</span><span class="sxs-lookup"><span data-stu-id="d877b-112">The Microsoft 365 connectivity test can help to identify the root cause of that problem leading to a recommended network performance improvement action.</span></span>

<span data-ttu-id="d877b-113">我们建议将这些信息结合使用，以便在 Microsoft 365 管理中心中的每个办公室位置评估网络质量状态，并在部署基于 Microsoft 365 连接测试的测试之后找到更多的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d877b-113">We recommend that these be used together where networking quality status can be assessed for each office location in the Microsoft 365 Admin Center and more specifics can be found after deployment of testing based on the Microsoft 365 connectivity test.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d877b-114">网络洞察力、Microsoft 365 管理中心中的性能建议和评估当前处于预览状态，并且仅适用于已在功能预览计划中注册的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="d877b-114">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="the-advanced-tests-client-application"></a><span data-ttu-id="d877b-115">高级测试客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="d877b-115">The advanced tests client application</span></span>

<span data-ttu-id="d877b-116">Microsoft 365 网络连接测试分为两个部分; <https://connectivity.office.com> 运行高级网络连接测试的网站和可下载的 Windows 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="d877b-116">There are two parts to the Microsoft 365 network connectivity test; the web site <https://connectivity.office.com> and a downloadable Windows client application that runs advanced network connectivity tests.</span></span> <span data-ttu-id="d877b-117">大多数测试都需要运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="d877b-117">Most of the tests require the application to be run.</span></span> <span data-ttu-id="d877b-118">它将在运行时将结果重新填充到网页中。</span><span class="sxs-lookup"><span data-stu-id="d877b-118">It will populate results back into the web page as it runs.</span></span>

<span data-ttu-id="d877b-119">在 web 浏览器测试完成后，系统将提示您从网站下载高级客户端测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="d877b-119">You will be prompted to download the advanced client test application from the web site after the web browser tests have completed.</span></span> <span data-ttu-id="d877b-120">在出现提示时打开并运行该文件。</span><span class="sxs-lookup"><span data-stu-id="d877b-120">Open and run the file when prompted.</span></span>

![高级测试客户端应用程序](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

## <a name="sharing-your-test-report"></a><span data-ttu-id="d877b-122">共享测试报告</span><span class="sxs-lookup"><span data-stu-id="d877b-122">Sharing your test report</span></span>

<span data-ttu-id="d877b-123">测试报告需要登录 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="d877b-123">The test report requires sign-in to your Office 365 account.</span></span> <span data-ttu-id="d877b-124">您的管理员可以选择共享测试报告的方式。</span><span class="sxs-lookup"><span data-stu-id="d877b-124">Your administrator selects how you can share your test report.</span></span>

### <a name="sharing-your-report-with-your-administrator"></a><span data-ttu-id="d877b-125">与管理员共享你的报告</span><span class="sxs-lookup"><span data-stu-id="d877b-125">Sharing your report with your administrator</span></span>

<span data-ttu-id="d877b-126">登录时的所有测试报告都将与管理员共享。</span><span class="sxs-lookup"><span data-stu-id="d877b-126">All test reports while you are signed in are shared with your administrator.</span></span>

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a><span data-ttu-id="d877b-127">与你的 Microsoft 帐户团队、支持或其他人员共享</span><span class="sxs-lookup"><span data-stu-id="d877b-127">Sharing with your Microsoft account team, support or other personnel</span></span>

<span data-ttu-id="d877b-128">与 Microsoft 员工共享不含任何个人标识的测试报告。</span><span class="sxs-lookup"><span data-stu-id="d877b-128">Test reports excluding any personal identification are shared with Microsoft employees.</span></span> <span data-ttu-id="d877b-129">默认情况下启用此设置，您的管理员可以在 **运行状况 | 中禁用它。** Microsoft 365 管理中心中的 "网络连接" 页面。</span><span class="sxs-lookup"><span data-stu-id="d877b-129">This is enabled by default and can be disabled by your administrator in the **Health | Network Connectivity** page in the Microsoft 365 Admin Center.</span></span>

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a><span data-ttu-id="d877b-130">与登录到同一 Office 365 租户的其他用户共享</span><span class="sxs-lookup"><span data-stu-id="d877b-130">Sharing with other users who sign in to the same Office 365 tenant</span></span>

<span data-ttu-id="d877b-131">您可以选择要与之共享报告的用户，并且默认情况下会启用此功能。</span><span class="sxs-lookup"><span data-stu-id="d877b-131">You can choose users to share your report with and this is enabled by default.</span></span> <span data-ttu-id="d877b-132">管理员也可以禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="d877b-132">It can also be disabled by your administrator.</span></span>

![使用用户共享指向测试结果的链接](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a><span data-ttu-id="d877b-134">使用 ReportID 链接与任何人共享</span><span class="sxs-lookup"><span data-stu-id="d877b-134">Sharing with anyone using a ReportID link</span></span>

<span data-ttu-id="d877b-135">通过提供对 ReportID 链接的访问权限，您可以与任何人共享您的测试报告。</span><span class="sxs-lookup"><span data-stu-id="d877b-135">You can share your test report with anyone by providing access to a ReportID link.</span></span> <span data-ttu-id="d877b-136">这将生成一个 URL，可以将其发送给某人，以便他们能够在不登录的情况下引入测试报告。</span><span class="sxs-lookup"><span data-stu-id="d877b-136">This generates a URL that you can send to someone so that they can bring up the test report without signing in.</span></span> <span data-ttu-id="d877b-137">默认情况下，此设置处于禁用状态，必须由管理员启用。</span><span class="sxs-lookup"><span data-stu-id="d877b-137">This is disabled by default and must be enabled by your administrator.</span></span>

![共享指向测试结果的链接](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a><span data-ttu-id="d877b-139">网络连接测试结果</span><span class="sxs-lookup"><span data-stu-id="d877b-139">Network Connectivity Test Results</span></span>

<span data-ttu-id="d877b-140">结果将显示在 " **摘要** " 和 " **详细信息** " 选项卡中。</span><span class="sxs-lookup"><span data-stu-id="d877b-140">The results are shown in the **Summary** and **Details** tabs.</span></span> <span data-ttu-id="d877b-141">"摘要" 选项卡显示检测到的网络外围的地图以及网络评估与附近其他 Office 365 客户的比较。</span><span class="sxs-lookup"><span data-stu-id="d877b-141">The summary tab shows a map of the detected network perimeter and a comparison of the network assessment to other Office 365 customers nearby.</span></span> <span data-ttu-id="d877b-142">它还允许共享测试报告。</span><span class="sxs-lookup"><span data-stu-id="d877b-142">It also allows for sharing of the test report.</span></span> <span data-ttu-id="d877b-143">摘要结果视图的外观如下所示。</span><span class="sxs-lookup"><span data-stu-id="d877b-143">Here's what the summary results view looks like.</span></span>

![网络连接测试工具摘要结果](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

<span data-ttu-id="d877b-145">下面的示例展示了该工具显示的 "详细信息" 选项卡输出。</span><span class="sxs-lookup"><span data-stu-id="d877b-145">Here is an example of the details tab output that the tool shows.</span></span> <span data-ttu-id="d877b-146">在 "详细信息" 选项卡上，如果结果与阈值比较，则显示绿色圆圈复选标记。</span><span class="sxs-lookup"><span data-stu-id="d877b-146">On the details tab we show a green circle check mark if the result was compared favorably to a threshold.</span></span> <span data-ttu-id="d877b-147">如果结果超过了指示网络洞察力的阈值，我们将显示红色三角形感叹号。</span><span class="sxs-lookup"><span data-stu-id="d877b-147">We show a red triangle exclamation point if the result exceeded a threshold indicating a network insight.</span></span> <span data-ttu-id="d877b-148">以下各节介绍了每个详细信息选项卡结果行，并说明了用于网络洞察力的阈值。</span><span class="sxs-lookup"><span data-stu-id="d877b-148">The following sections describe each of the details tab results rows and explains the thresholds used for network insights.</span></span>

![网络连接测试工具示例测试结果](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a><span data-ttu-id="d877b-150">您的位置信息</span><span class="sxs-lookup"><span data-stu-id="d877b-150">Your location information</span></span>

<span data-ttu-id="d877b-151">此部分显示与您的位置相关的测试结果。</span><span class="sxs-lookup"><span data-stu-id="d877b-151">This section shows test results related to your location.</span></span>

#### <a name="your-location"></a><span data-ttu-id="d877b-152">您的位置</span><span class="sxs-lookup"><span data-stu-id="d877b-152">Your location</span></span>

<span data-ttu-id="d877b-153">用户在用户 web 浏览器中检测到用户位置，也可以在用户选项中键入该位置。</span><span class="sxs-lookup"><span data-stu-id="d877b-153">The user location is detected from the users web browser, or it can be typed in at the users choice.</span></span> <span data-ttu-id="d877b-154">它用于标识与企业网络周边的特定部分之间的网络距离。</span><span class="sxs-lookup"><span data-stu-id="d877b-154">It is used to identify network distances to specific parts of the enterprise network perimeter.</span></span> <span data-ttu-id="d877b-155">仅此位置检测中的市/县和到其他网络点的距离保存在报告中。</span><span class="sxs-lookup"><span data-stu-id="d877b-155">Only the city from this location detection and the distance to other network points are saved in the report.</span></span>

<span data-ttu-id="d877b-156">用户办公室位置显示在地图视图中。</span><span class="sxs-lookup"><span data-stu-id="d877b-156">The user office location is shown on the map view.</span></span>

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a><span data-ttu-id="d877b-157">网络传出位置 (网络连接到 ISP 的位置) </span><span class="sxs-lookup"><span data-stu-id="d877b-157">Network egress location (the location where your network connects to your ISP)</span></span>

<span data-ttu-id="d877b-158">我们在服务器端标识网络出口 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d877b-158">We identify the network egress IP address on the server side.</span></span> <span data-ttu-id="d877b-159">位置数据库用于查找网络出口的大概位置。</span><span class="sxs-lookup"><span data-stu-id="d877b-159">Location databases are used to look up the approximate location for the network egress.</span></span> <span data-ttu-id="d877b-160">这些数据库通常具有大约90% 的 IP 地址精度。</span><span class="sxs-lookup"><span data-stu-id="d877b-160">These databases typically have an accuracy of about 90% of IP addresses.</span></span> <span data-ttu-id="d877b-161">如果从网络传出 IP 地址查找的位置不准确，这将导致此测试产生错误结果。</span><span class="sxs-lookup"><span data-stu-id="d877b-161">If the location looked up from the network egress IP address is not accurate then this would lead to a false result from this test.</span></span> <span data-ttu-id="d877b-162">若要验证是否发生了特定 IP 地址的此错误，可以使用可公开访问的网络 IP 地址位置网站与实际位置进行比较。</span><span class="sxs-lookup"><span data-stu-id="d877b-162">To validate if this error is occurring for a specific IP address you can use publicly accessible network IP address location web sites to compare to your actual location.</span></span>

#### <a name="your-distance-from-the-network-egress-location"></a><span data-ttu-id="d877b-163">距网络传出位置的距离</span><span class="sxs-lookup"><span data-stu-id="d877b-163">Your distance from the network egress location</span></span>

<span data-ttu-id="d877b-164">我们确定从该位置到办公室位置之间的距离。</span><span class="sxs-lookup"><span data-stu-id="d877b-164">We determine the distance from that location to the office location.</span></span> <span data-ttu-id="d877b-165">如果距离大于 **500 英里** (800 公里，这会显示为网络洞察力) 因为这可能会导致超过25ms 的延迟，并且可能会影响用户体验。</span><span class="sxs-lookup"><span data-stu-id="d877b-165">This is shown as a network insight if the distance is greater than **500 miles** (800 kilometers) since that is likely to increase the TCP latency by more than 25ms and may affect user experience.</span></span>

<span data-ttu-id="d877b-166">网络出局位置显示在地图视图中，并连接到用户办公室位置，以指示企业 WAN 中的网络 backhaul。</span><span class="sxs-lookup"><span data-stu-id="d877b-166">The network egress location is shown on the map view and connected to the user office location indicating the network backhaul inside of the enterprise WAN.</span></span>

<span data-ttu-id="d877b-167">建议在 Microsoft 365 网络连接中，将本地和直接的网络出口从用户办公室位置实施到 Internet。</span><span class="sxs-lookup"><span data-stu-id="d877b-167">Implementing local and direct network egress from user office locations to the Internet is recommended for Microsoft 365 network connectivity.</span></span> <span data-ttu-id="d877b-168">对本地和直接出口的改进是解决此网络洞察力的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="d877b-168">Improvements to local and direct egress are the best way to address this network insight.</span></span>

#### <a name="proxy-server-information"></a><span data-ttu-id="d877b-169">代理服务器信息</span><span class="sxs-lookup"><span data-stu-id="d877b-169">Proxy server information</span></span>

<span data-ttu-id="d877b-170">我们) 在本地计算机上配置代理服务器 (s。</span><span class="sxs-lookup"><span data-stu-id="d877b-170">We identify proxy server(s) configured on the local machine.</span></span> <span data-ttu-id="d877b-171">我们确定是否在网络路径中配置了这些配置以优化类别 Microsoft 365 网络流量。</span><span class="sxs-lookup"><span data-stu-id="d877b-171">We identify if any of these are configured in the network path for optimize category Microsoft 365 network traffic.</span></span> <span data-ttu-id="d877b-172">我们确定从用户办公室位置到代理服务器的距离。</span><span class="sxs-lookup"><span data-stu-id="d877b-172">We identify the distance from the user office location to the proxy servers.</span></span> <span data-ttu-id="d877b-173">先通过 ICMP ping 测试距离，如果此操作失败，我们使用 TCP ping 进行测试，如果失败，则在 IP 地址位置数据库中查找代理服务器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d877b-173">The distance is tested first by ICMP ping and if that fails we test with TCP ping and finally if that fails we look up the proxy server IP Address in an IP Address location database.</span></span> <span data-ttu-id="d877b-174">如果代理服务器超过 **500 英里** (800 公里) 远离用户办公室位置，我们将显示网络洞察力。</span><span class="sxs-lookup"><span data-stu-id="d877b-174">We show a network insight if the proxy server is further than **500 miles** (800 kilometers) away from the user office location.</span></span>

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a><span data-ttu-id="d877b-175">用于连接到您的组织的虚拟专用网络 (VPN) </span><span class="sxs-lookup"><span data-stu-id="d877b-175">Virtual private network (VPN) you use to connect to your organization</span></span>

<span data-ttu-id="d877b-176">这将检测您是否正在使用 VPN 连接到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d877b-176">This detects if you are using a VPN to connect to Office 365.</span></span> <span data-ttu-id="d877b-177">如果你没有 VPN，或者你具有 Office 365 的推荐拆分隧道配置的 VPN，则将显示传递结果。</span><span class="sxs-lookup"><span data-stu-id="d877b-177">A passing result will show if you have no VPN, or if you have a VPN with recommended split tunnel configuration for Office 365.</span></span>

#### <a name="vpn-split-tunnel"></a><span data-ttu-id="d877b-178">VPN 拆分隧道</span><span class="sxs-lookup"><span data-stu-id="d877b-178">VPN Split Tunnel</span></span>

<span data-ttu-id="d877b-179">对 Exchange Online、SharePoint Online 和 Microsoft 团队的每个优化类别路由进行测试，以查看是否在 VPN 上 tunnelled。</span><span class="sxs-lookup"><span data-stu-id="d877b-179">Each optimize category route for Exchange Online, SharePoint Online, and Microsoft Teams is tested to see if it is tunnelled on the VPN or not.</span></span> <span data-ttu-id="d877b-180">拆分工作负载可以完全避免 VPN。</span><span class="sxs-lookup"><span data-stu-id="d877b-180">A split out workload avoids the VPN entirely.</span></span> <span data-ttu-id="d877b-181">Tunnelled 工作负荷是通过 VPN 发送的。</span><span class="sxs-lookup"><span data-stu-id="d877b-181">A tunnelled workload is all sent over the VPN.</span></span> <span data-ttu-id="d877b-182">一个选择性的 tunnelled 工作负荷具有通过 VPN 发送的某些路由，而某些路由已被剥离。如果所有工作负荷被拆分或选择性 tunnelled，则将显示传递结果。</span><span class="sxs-lookup"><span data-stu-id="d877b-182">A selective tunnelled workload has some routes sent over the VPN and some split out. A passing result will show if all workloads are split out or selective tunnelled.</span></span>

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a><span data-ttu-id="d877b-183">具有更佳性能的大都市区域内的客户</span><span class="sxs-lookup"><span data-stu-id="d877b-183">Customers in your metropolitan area with better performance</span></span>

<span data-ttu-id="d877b-184">与同一地铁区域中的其他 Microsoft 365 客户相比，Exchange Online 服务前向的用户办公室位置的网络 TCP 延迟。</span><span class="sxs-lookup"><span data-stu-id="d877b-184">The network TCP latency of the user office location to the Exchange Online service front door is compared to other Microsoft 365 customers in the same metro area.</span></span> <span data-ttu-id="d877b-185">如果在同一地铁区域中10% 或更多的客户具有更好的性能，则显示网络洞察力。</span><span class="sxs-lookup"><span data-stu-id="d877b-185">A network insight is shown if 10% or more of customers in the same metro area have better performance.</span></span> <span data-ttu-id="d877b-186">这意味着，在 Microsoft 365 用户界面中，用户将获得更好的性能。</span><span class="sxs-lookup"><span data-stu-id="d877b-186">This means their users will have better performance in the Microsoft 365 user interface.</span></span>

<span data-ttu-id="d877b-187">根据城市中的所有用户都可以访问相同的电信基础结构和与 Internet 电路和 Microsoft 网络的邻近性，生成网络洞察力。</span><span class="sxs-lookup"><span data-stu-id="d877b-187">This network insight is generated on the basis that all users in a city have access to the same telecommunications infrastructure and the same proximity to Internet circuits and Microsoft's network.</span></span>

#### <a name="time-to-make-a-dns-request-on-your-network"></a><span data-ttu-id="d877b-188">对网络发出 DNS 请求的时间</span><span class="sxs-lookup"><span data-stu-id="d877b-188">Time to make a DNS request on your network</span></span>

<span data-ttu-id="d877b-189">此示例显示在运行测试的客户端计算机上配置的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="d877b-189">This shows the DNS server configured on the client machine that ran the tests.</span></span> <span data-ttu-id="d877b-190">它可能是 DNS 递归解析器服务器，但这并不常见。</span><span class="sxs-lookup"><span data-stu-id="d877b-190">It might be a DNS Recursive Resolver server however this is uncommon.</span></span> <span data-ttu-id="d877b-191">它更可能是缓存 DNS 结果并将任何未缓存的 DNS 请求转发到另一个 DNS 服务器的 DNS 转发器服务器。</span><span class="sxs-lookup"><span data-stu-id="d877b-191">It is more likely to be a DNS forwarder server which caches DNS results and forwards any uncached DNS requests to another DNS server.</span></span>

<span data-ttu-id="d877b-192">提供此功能仅用于提供信息，并不会影响网络的洞察力。</span><span class="sxs-lookup"><span data-stu-id="d877b-192">This is provided for information only and does not contribute to any network insight.</span></span>

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a><span data-ttu-id="d877b-193">连接到 DNS 递归冲突解决程序的距离和/或时间</span><span class="sxs-lookup"><span data-stu-id="d877b-193">Your distance from and/or time to connect to a DNS recursive resolver</span></span>

<span data-ttu-id="d877b-194">通过发出特定的 DNS 请求，然后向 DNS 名称服务器提供来自收到相同请求的 IP 地址，可以标识使用中的 DNS 递归冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="d877b-194">The in-use DNS Recursive Resolver is identified by making a specific DNS request and then asking the DNS Name Server for the IP Address that it received the same request from.</span></span> <span data-ttu-id="d877b-195">此 IP 地址是 DNS 递归解析程序，将在 IP 地址位置数据库中查找以找到该位置。</span><span class="sxs-lookup"><span data-stu-id="d877b-195">This IP Address is the DNS Recursive Resolver and it will be looked up in IP Address location databases to find the location.</span></span> <span data-ttu-id="d877b-196">然后计算从用户办公室位置到 DNS 递归解析服务器位置之间的距离。</span><span class="sxs-lookup"><span data-stu-id="d877b-196">The distance from the user office location to the DNS Recursive Resolver server location is then calculated.</span></span> <span data-ttu-id="d877b-197">如果距离大于 **500 英里** (800 公里) ，这会显示为网络洞察力。</span><span class="sxs-lookup"><span data-stu-id="d877b-197">This is shown as a network insight if the distance is greater than **500 miles** (800 kilometers).</span></span>

<span data-ttu-id="d877b-198">从网络传出 IP 地址查找的位置可能不准确，这将导致此测试产生错误结果。</span><span class="sxs-lookup"><span data-stu-id="d877b-198">The location looked up from the network egress IP Address may not be accurate and this would lead to a false result from this test.</span></span> <span data-ttu-id="d877b-199">若要验证是否为特定 IP 地址出现此错误，可以使用可公开访问的网络 IP 地址位置网站。</span><span class="sxs-lookup"><span data-stu-id="d877b-199">To validate if this error is occurring for a specific IP Address you can use publicly accessible network IP Address location web sites.</span></span>

<span data-ttu-id="d877b-200">此网络洞察力尤其会影响 Exchange Online 服务前盖的选择。</span><span class="sxs-lookup"><span data-stu-id="d877b-200">This network insight will specifically impact the selection of the Exchange Online service front door.</span></span> <span data-ttu-id="d877b-201">若要解决此深入了解，本地和直接网络出口应为先决条件，然后 DNS 递归解析器应位于该网络出口附近。</span><span class="sxs-lookup"><span data-stu-id="d877b-201">To address this insight local and direct network egress should be a pre-requisite and then DNS Recursive Resolver should be located close to that network egress.</span></span>

### <a name="exchange-online"></a><span data-ttu-id="d877b-202">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d877b-202">Exchange Online</span></span>

<span data-ttu-id="d877b-203">此部分显示与 Exchange Online 相关的测试结果。</span><span class="sxs-lookup"><span data-stu-id="d877b-203">This section shows test results related to Exchange Online.</span></span>

#### <a name="exchange-service-front-door-location"></a><span data-ttu-id="d877b-204">Exchange 服务前盖位置</span><span class="sxs-lookup"><span data-stu-id="d877b-204">Exchange service front door location</span></span>

<span data-ttu-id="d877b-205">以 Outlook 执行此功能的相同方式标识使用中的 Exchange 服务前向门，并将网络 TCP 延迟从用户位置测量到它。</span><span class="sxs-lookup"><span data-stu-id="d877b-205">The in-use Exchange service front door is identified in the same way that Outlook does this and we measure the network TCP latency from the user location to it.</span></span> <span data-ttu-id="d877b-206">显示 TCP 延迟，并将正在使用的 Exchange 服务前向门与当前位置的最佳服务前盖列表进行比较。</span><span class="sxs-lookup"><span data-stu-id="d877b-206">The TCP latency is shown and the in-use Exchange service front door is compared to the list of best service front doors for the current location.</span></span> <span data-ttu-id="d877b-207">如果未使用最佳 Exchange 服务前向 (s) 中的一门，这将显示为网络洞察力。</span><span class="sxs-lookup"><span data-stu-id="d877b-207">This is shown as a network insight if one of the best Exchange service front door(s) is not in use.</span></span>

<span data-ttu-id="d877b-208">如果不使用最佳 Exchange 服务前向 (s) 可能是网络 backhaul 在公司网络出口之前导致的，我们建议本地和直接网络出口。</span><span class="sxs-lookup"><span data-stu-id="d877b-208">Not using one of the best Exchange service front door(s) could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="d877b-209">也可能是由于使用远程 DNS 递归冲突解决服务器而导致的，在这种情况下，我们建议您将 DNS 递归解析器服务器与网络出口对齐。</span><span class="sxs-lookup"><span data-stu-id="d877b-209">It could also be caused by use of a remote DNS recursive resolver server in which case we recommend aligning the DNS recursive resolver server with the network egress.</span></span>

<span data-ttu-id="d877b-210">我们计算了对 Exchange 服务前向门 (ms) 的 TCP 延迟的潜在改进。</span><span class="sxs-lookup"><span data-stu-id="d877b-210">We calculate a potential improvement in TCP latency (ms) to the Exchange service front door.</span></span> <span data-ttu-id="d877b-211">为此，请查看测试的用户办公室位置网络延迟，并将网络延迟从当前位置减去当前位置，再减去 closets Exchange service 的前向门。</span><span class="sxs-lookup"><span data-stu-id="d877b-211">This is done by looking at the tested user office location network latency and subtracting the network latency from the current location to the closets Exchange service front door.</span></span> <span data-ttu-id="d877b-212">不同之处表示潜在的改进机会。</span><span class="sxs-lookup"><span data-stu-id="d877b-212">The difference represents the potential opportunity for improvement.</span></span>

#### <a name="best-exchange-service-front-doors-for-your-location"></a><span data-ttu-id="d877b-213">适用于您的位置 (s) 的最佳 Exchange 服务前盖</span><span class="sxs-lookup"><span data-stu-id="d877b-213">Best Exchange service front door(s) for your location</span></span>

<span data-ttu-id="d877b-214">这将按城市列出你所在地区的最佳 Exchange 服务前盖位置。</span><span class="sxs-lookup"><span data-stu-id="d877b-214">This lists the best Exchange service front door locations by city for your location.</span></span>

#### <a name="service-front-door-recorded-in-the-client-dns"></a><span data-ttu-id="d877b-215">在客户端 DNS 中记录的服务前盖</span><span class="sxs-lookup"><span data-stu-id="d877b-215">Service front door recorded in the client DNS</span></span>

<span data-ttu-id="d877b-216">这将显示定向到的 Exchange 服务前端服务器的 DNS 名称和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d877b-216">This shows the DNS name and IP Address of the Exchange service front door server that you were directed to.</span></span> <span data-ttu-id="d877b-217">仅提供此信息，没有相关的网络洞察力。</span><span class="sxs-lookup"><span data-stu-id="d877b-217">It is provided for information only and there is no associated network insight.</span></span>

### <a name="sharepoint-online"></a><span data-ttu-id="d877b-218">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d877b-218">SharePoint Online</span></span>

<span data-ttu-id="d877b-219">此部分显示与 SharePoint Online 和 OneDrive 相关的测试结果。</span><span class="sxs-lookup"><span data-stu-id="d877b-219">This section shows test results related to SharePoint Online and OneDrive.</span></span>

#### <a name="the-service-front-door-location"></a><span data-ttu-id="d877b-220">服务前盖位置</span><span class="sxs-lookup"><span data-stu-id="d877b-220">The service front door location</span></span>

<span data-ttu-id="d877b-221">使用与 OneDrive 客户端相同的方式标识正在使用的 SharePoint 服务前向门，并将网络 TCP 延迟从用户办公室位置测量到它。</span><span class="sxs-lookup"><span data-stu-id="d877b-221">The in-use SharePoint service front door is identified in the same way that the OneDrive client does and we measure the network TCP latency from the user office location to it.</span></span>

#### <a name="download-speed"></a><span data-ttu-id="d877b-222">下载速度</span><span class="sxs-lookup"><span data-stu-id="d877b-222">Download speed</span></span>

<span data-ttu-id="d877b-223">我们通过 SharePoint 服务的前端衡量15Mb 文件的下载速度。</span><span class="sxs-lookup"><span data-stu-id="d877b-223">We measure the download speed for a 15Mb file from the SharePoint service front door.</span></span> <span data-ttu-id="d877b-224">结果以每秒 mb 为单位显示，以指示可以从 SharePoint 或 OneDrive 中 **一秒**下载的大小文件（以 mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="d877b-224">The result is shown in megabytes per second to indicate what size file in megabytes can be downloaded from SharePoint or OneDrive in **one second**.</span></span> <span data-ttu-id="d877b-225">该号码应类似于每秒最小电路带宽的十分之一。</span><span class="sxs-lookup"><span data-stu-id="d877b-225">The number should be similar to one tenth of the minimum circuit bandwidth in megabits per second.</span></span> <span data-ttu-id="d877b-226">例如，如果 internet 连接为100mbps，则可能需要每秒 10 mb (10MBps) 。</span><span class="sxs-lookup"><span data-stu-id="d877b-226">For example if you have a 100mbps internet connection, you may expect 10 megabytes per second (10MBps).</span></span>

#### <a name="buffer-bloat"></a><span data-ttu-id="d877b-227">缓冲区膨胀</span><span class="sxs-lookup"><span data-stu-id="d877b-227">Buffer bloat</span></span>

<span data-ttu-id="d877b-228">在15Mb 下载过程中，我们会将 TCP 延迟测量到 SharePoint 服务的前向门。</span><span class="sxs-lookup"><span data-stu-id="d877b-228">During the 15Mb download we measure the TCP latency to the SharePoint service front door.</span></span> <span data-ttu-id="d877b-229">这是负载下的延迟，并将与不在负载下时的延迟进行比较。</span><span class="sxs-lookup"><span data-stu-id="d877b-229">This is the latency under load and it is compared to the latency when not under load.</span></span> <span data-ttu-id="d877b-230">在负载不足时延迟的增加通常由 (或 bloated) 中加载的消费网络设备缓冲区所归属。</span><span class="sxs-lookup"><span data-stu-id="d877b-230">The increase in latency when under load is often attributable to consumer network device buffers being loaded (or bloated).</span></span> <span data-ttu-id="d877b-231">为1000或更多的膨胀显示网络洞察力。</span><span class="sxs-lookup"><span data-stu-id="d877b-231">A network insight is shown for any bloat of 1,000 or more.</span></span>

#### <a name="service-front-door-recorded-in-the-client-dns"></a><span data-ttu-id="d877b-232">在客户端 DNS 中记录的服务前盖</span><span class="sxs-lookup"><span data-stu-id="d877b-232">Service front door recorded in the client DNS</span></span>

<span data-ttu-id="d877b-233">此示例显示定向到的 SharePoint 服务前端服务器的 DNS 名称和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d877b-233">This shows the DNS name and IP Address of the SharePoint service front door server that you were directed to.</span></span> <span data-ttu-id="d877b-234">仅提供此信息，没有相关的网络洞察力。</span><span class="sxs-lookup"><span data-stu-id="d877b-234">It is provided for information only and there is no associated network insight.</span></span>

### <a name="microsoft-teams"></a><span data-ttu-id="d877b-235">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d877b-235">Microsoft Teams</span></span>

<span data-ttu-id="d877b-236">此部分显示与 Microsoft 团队相关的测试结果。</span><span class="sxs-lookup"><span data-stu-id="d877b-236">This section shows test results related to Microsoft Teams.</span></span>

#### <a name="media-connectivity-audio-video-and-application-sharing"></a><span data-ttu-id="d877b-237">媒体连接 (音频、视频和应用程序共享) </span><span class="sxs-lookup"><span data-stu-id="d877b-237">Media connectivity (audio, video, and application sharing)</span></span>

<span data-ttu-id="d877b-238">这将测试与 Microsoft 团队服务前盖的 UDP 连接。</span><span class="sxs-lookup"><span data-stu-id="d877b-238">This tests for UDP connectivity to the Microsoft Teams service front door.</span></span> <span data-ttu-id="d877b-239">如果阻止此操作，则 Microsoft 团队仍可能使用 TCP，但音频和视频将受到影响。</span><span class="sxs-lookup"><span data-stu-id="d877b-239">If this is blocked then Microsoft Teams may still work using TCP, but audio and video will be impaired.</span></span> <span data-ttu-id="d877b-240">阅读有关这些 UDP 网络度量的详细信息，这些度量也适用于 Microsoft 团队在 [Skype for Business Online 中的媒体质量和网络连接性能](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)</span><span class="sxs-lookup"><span data-stu-id="d877b-240">Read more about these UDP network measurements which also apply to Microsoft Teams at [Media Quality and Network Connectivity Performance in Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)</span></span>

#### <a name="packet-loss"></a><span data-ttu-id="d877b-241">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="d877b-241">Packet loss</span></span>

<span data-ttu-id="d877b-242">显示 UDP 数据包丢失量，以10秒测试音频呼叫从客户端到 Microsoft 团队服务前向门。</span><span class="sxs-lookup"><span data-stu-id="d877b-242">Shows the UDP packet loss measured in a 10 second test audio call from the client to the Microsoft Teams service front door.</span></span> <span data-ttu-id="d877b-243">对于 pass，这应低于 **1.00%** 。</span><span class="sxs-lookup"><span data-stu-id="d877b-243">This should be lower than **1.00%** for a pass.</span></span>

### <a name="latency"></a><span data-ttu-id="d877b-244">延迟</span><span class="sxs-lookup"><span data-stu-id="d877b-244">Latency</span></span>

<span data-ttu-id="d877b-245">显示度量的 UDP 延迟，该延迟应低于 **100 毫秒**。</span><span class="sxs-lookup"><span data-stu-id="d877b-245">Shows the measured UDP latency, which should be lower than **100ms**.</span></span>

#### <a name="jitter"></a><span data-ttu-id="d877b-246">抖动</span><span class="sxs-lookup"><span data-stu-id="d877b-246">Jitter</span></span>

<span data-ttu-id="d877b-247">显示测量的 UDP 抖动，它应低于 **30ms**。</span><span class="sxs-lookup"><span data-stu-id="d877b-247">Shows the measured UDP jitter, which should be lower than **30ms**.</span></span>

#### <a name="connectivity"></a><span data-ttu-id="d877b-248">连接</span><span class="sxs-lookup"><span data-stu-id="d877b-248">Connectivity</span></span>

<span data-ttu-id="d877b-249">我们测试从用户办公室位置到所有必需的 Microsoft 365 网络终结点的 HTTP 连接。</span><span class="sxs-lookup"><span data-stu-id="d877b-249">We test for HTTP connectivity from the user office location to all of the required Microsoft 365 network endpoints.</span></span> <span data-ttu-id="d877b-250">这些内容是在中发布的 [https://aka.ms/o365ip](https://aka.ms/o365ip) 。</span><span class="sxs-lookup"><span data-stu-id="d877b-250">These are published at [https://aka.ms/o365ip](https://aka.ms/o365ip).</span></span> <span data-ttu-id="d877b-251">对于任何不能连接到的必需网络终结点，都会显示网络洞察力。</span><span class="sxs-lookup"><span data-stu-id="d877b-251">A network insight is shown for any required network endpoints which cannot be connected to.</span></span>

<span data-ttu-id="d877b-252">连接 ay 由企业网络外围上的代理服务器、防火墙或其他网络安全设备阻止，或作为云代理使用。</span><span class="sxs-lookup"><span data-stu-id="d877b-252">Connectivity ay be blocked by a proxy server, a firewall, or another network security device on the enterprise network perimeter or in use as a cloud proxy.</span></span>

<span data-ttu-id="d877b-253">我们会在所需的每个 Microsoft 365 网络终结点（在上定义了）中测试 SSL 证书 [https://aka.ms/o365ip](https://aka.ms/o365ip) 。</span><span class="sxs-lookup"><span data-stu-id="d877b-253">We test the SSL certificate at each required Microsoft 365 network endpoint that is in the optimize or allow category as defined at [https://aka.ms/o365ip](https://aka.ms/o365ip).</span></span> <span data-ttu-id="d877b-254">如果有任何测试未找到 Microsoft SSL 证书，则已连接的加密网络必须已被中间网络设备截取。</span><span class="sxs-lookup"><span data-stu-id="d877b-254">If any tests do not find a Microsoft SSL certificate, then the encrypted network connected must have been intercepted by an intermediary network device.</span></span> <span data-ttu-id="d877b-255">网络洞察力显示在任何截获的加密网络终结点上。</span><span class="sxs-lookup"><span data-stu-id="d877b-255">A network insight is shown on any intercepted encrypted network endpoints.</span></span>

<span data-ttu-id="d877b-256">在找不到 Microsoft 提供的 SSL 证书的情况下，我们会显示该测试的 FQDN 以及正在使用的 SSL 证书所有者。</span><span class="sxs-lookup"><span data-stu-id="d877b-256">Where an SSL certificate is found that isn't provided by Microsoft, we show the FQDN for the test and the in-use SSL certificate owner.</span></span> <span data-ttu-id="d877b-257">此 SSL 证书所有者可能是代理服务器供应商，也可能是企业自签名证书。</span><span class="sxs-lookup"><span data-stu-id="d877b-257">This SSL certificate owner may be a proxy server vendor, or it may be an enterprise self-signed certificate.</span></span>

#### <a name="network-path"></a><span data-ttu-id="d877b-258">网络路径</span><span class="sxs-lookup"><span data-stu-id="d877b-258">Network path</span></span>

<span data-ttu-id="d877b-259">本节显示了 ICMP traceroute 对 Exchange Online 服务前向门、SharePoint Online service 前门和 Microsoft 团队服务前盖的结果。</span><span class="sxs-lookup"><span data-stu-id="d877b-259">This section shows the results of an ICMP traceroute to the Exchange Online service front door, the SharePoint Online service front door, and the Microsoft Teams service front door.</span></span> <span data-ttu-id="d877b-260">仅提供此信息，没有相关的网络洞察力。</span><span class="sxs-lookup"><span data-stu-id="d877b-260">It is provided for information only and there is no associated network insight.</span></span> <span data-ttu-id="d877b-261">提供了三个 traceroutes。</span><span class="sxs-lookup"><span data-stu-id="d877b-261">There are three traceroutes provided.</span></span> <span data-ttu-id="d877b-262">一个 traceroute 到 _outlook.office365.com_，一个 traceroute 到客户的 SharePoint 前端或 _microsoft.sharepoint.com_ ，如果未提供，则 traceroute 到 _world.tr.teams.microsoft.com_。</span><span class="sxs-lookup"><span data-stu-id="d877b-262">A traceroute to _outlook.office365.com_, a traceroute to the customers SharePoint front end or to _microsoft.sharepoint.com_ if one was not provided, and a traceroute to _world.tr.teams.microsoft.com_.</span></span>

## <a name="what-happens-at-each-test-step"></a><span data-ttu-id="d877b-263">每个测试步骤中会发生的情况</span><span class="sxs-lookup"><span data-stu-id="d877b-263">What happens at each test step</span></span>

### <a name="office-location-identification"></a><span data-ttu-id="d877b-264">办公室位置标识</span><span class="sxs-lookup"><span data-stu-id="d877b-264">Office location identification</span></span>

<span data-ttu-id="d877b-265">当您单击 "运行测试" 按钮时，将显示正在运行的测试页并标识办公室位置。</span><span class="sxs-lookup"><span data-stu-id="d877b-265">When you click the run test button we show the running test page and identify the office location.</span></span> <span data-ttu-id="d877b-266">您可以按城市、省市自治区和国家/地区键入，也可以在 web 浏览器中检测到该位置。</span><span class="sxs-lookup"><span data-stu-id="d877b-266">You can type in your location by city, state, and country or you can have it detected from the web browser.</span></span> <span data-ttu-id="d877b-267">如果检测到此情况，我们会从 web 浏览器请求纬度和经度，并在使用之前将精度限制为 300m 300m。</span><span class="sxs-lookup"><span data-stu-id="d877b-267">If you detect it then we request the latitude and longitude from the web browser and limit the accuracy to 300m by 300m before use.</span></span> <span data-ttu-id="d877b-268">我们这样做的原因是，与构建网络性能相比，不需要更准确地确定位置。</span><span class="sxs-lookup"><span data-stu-id="d877b-268">We do this because it is not necessary to identify the location more accurately than the building for network performance.</span></span> 

### <a name="javascript-tests"></a><span data-ttu-id="d877b-269">JavaScript 测试</span><span class="sxs-lookup"><span data-stu-id="d877b-269">JavaScript tests</span></span>

<span data-ttu-id="d877b-270">在 office 位置标识之后，我们会在 JavaScript 中运行 TCP 延迟测试，并向服务请求有关正在使用的 Office 365 服务前端服务器和建议的 Office 服务前端服务器的数据。</span><span class="sxs-lookup"><span data-stu-id="d877b-270">After office location identification we run a TCP latency test in JavaScript and we request data from the service about in-use and recommended Office 365 service front door servers.</span></span> <span data-ttu-id="d877b-271">完成这些操作后，我们会将其显示在地图上和 "详细信息" 选项卡中，在下一步之前可以查看它们。</span><span class="sxs-lookup"><span data-stu-id="d877b-271">When these are completed we show them on the map and in the details tab where they can be viewed prior to the next step.</span></span>

### <a name="download-the-advanced-tests-client-application"></a><span data-ttu-id="d877b-272">下载高级测试客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="d877b-272">Download the advanced tests client application</span></span>

<span data-ttu-id="d877b-273">接下来，我们将开始下载高级测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="d877b-273">Next we start the download of the advanced tests client application.</span></span> <span data-ttu-id="d877b-274">我们依赖用户来启动客户端应用程序，并且还必须安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d877b-274">We rely on the user to launch the client application and they must also have .NET Core installed.</span></span>

### <a name="start-the-advanced-tests-client-application"></a><span data-ttu-id="d877b-275">启动高级测试客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="d877b-275">Start the advanced tests client application</span></span>

<span data-ttu-id="d877b-276">在客户端应用程序启动后，网页将进行更新以显示此数据，并将开始将测试数据接收到网页。</span><span class="sxs-lookup"><span data-stu-id="d877b-276">Once the client application starts the web page will update to show this and test data will start to be received to the web page.</span></span> <span data-ttu-id="d877b-277">每次接收新数据时，它都会更新，您可以在数据到达时查看数据。</span><span class="sxs-lookup"><span data-stu-id="d877b-277">It updates each time new data is received and you can review the data as it arrives.</span></span>

### <a name="advanced-tests-completed-and-test-report-upload"></a><span data-ttu-id="d877b-278">高级测试已完成并测试报表上载</span><span class="sxs-lookup"><span data-stu-id="d877b-278">Advanced tests completed and test report upload</span></span>

<span data-ttu-id="d877b-279">完成测试后，网页和高级测试客户端将同时指明这一点，如果测试报告中的用户已登录，则会将其上载到客户租户。</span><span class="sxs-lookup"><span data-stu-id="d877b-279">Once the tests are completed the web page and the advanced tests client will both indicate this and if the user is signed in the test report will be uploaded to the customers tenant.</span></span>

## <a name="connectivity-reports"></a><span data-ttu-id="d877b-280">连接性报告</span><span class="sxs-lookup"><span data-stu-id="d877b-280">Connectivity reports</span></span>

<span data-ttu-id="d877b-281">登录后，您可以查看以前运行的报告。</span><span class="sxs-lookup"><span data-stu-id="d877b-281">When you are signed in you can review previous reports that you have run.</span></span> <span data-ttu-id="d877b-282">您也可以将其共享或从列表中删除。</span><span class="sxs-lookup"><span data-stu-id="d877b-282">You can also share them or delete them from the list.</span></span>

![报告](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a><span data-ttu-id="d877b-284">网络运行状况状态</span><span class="sxs-lookup"><span data-stu-id="d877b-284">Network health status</span></span>

<span data-ttu-id="d877b-285">这显示了 Microsoft 全球网络中可能影响 Microsoft 365 客户的任何重大运行状况问题。</span><span class="sxs-lookup"><span data-stu-id="d877b-285">This shows any significant health issues with Microsoft's global network which might impact Microsoft 365 customers.</span></span>

![网络运行状况状态](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a><span data-ttu-id="d877b-287">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="d877b-287">FAQ</span></span>

<span data-ttu-id="d877b-288">以下是一些常见问题的解答。</span><span class="sxs-lookup"><span data-stu-id="d877b-288">Here are answers to some of our frequently asked questions.</span></span>

### <a name="is-this-tool-released-and-supported-by-microsoft"></a><span data-ttu-id="d877b-289">此工具是否已发布并受 Microsoft 支持？</span><span class="sxs-lookup"><span data-stu-id="d877b-289">Is this tool released and supported by Microsoft?</span></span>

<span data-ttu-id="d877b-290">目前它是一个预览，我们计划定期提供更新，直到我们能够从 Microsoft 获得支持的常规可用性发布状态。</span><span class="sxs-lookup"><span data-stu-id="d877b-290">It is currently a preview and we plan to provide updates regularly until we reach general availability release status with support from Microsoft.</span></span> <span data-ttu-id="d877b-291">请提供反馈以帮助我们改进。</span><span class="sxs-lookup"><span data-stu-id="d877b-291">Please provide feedback to help us improve.</span></span> <span data-ttu-id="d877b-292">我们打算将更详细的 Office 365 网络加入指南作为此工具的一部分进行发布，此工具可通过其测试结果自定义为组织。</span><span class="sxs-lookup"><span data-stu-id="d877b-292">We are planning to publish a more detailed Office 365 Network Onboarding guide as part of this tool which is customized for the organization by its test results.</span></span>

### <a name="what-is-required-to-run-the-advanced-test-client"></a><span data-ttu-id="d877b-293">运行高级测试客户端需要什么？</span><span class="sxs-lookup"><span data-stu-id="d877b-293">What is required to run the advanced test client?</span></span>

<span data-ttu-id="d877b-294">高级测试客户端需要 .NET Core 3.1 桌面运行时。</span><span class="sxs-lookup"><span data-stu-id="d877b-294">The advanced test client requires .NET Core 3.1 Desktop Runtime.</span></span> <span data-ttu-id="d877b-295">如果在未安装的情况下运行高级测试客户端，则会转到 [.Net Core 3.1 installer 页面](https://dotnet.microsoft.com/download/dotnet-core/3.1)。</span><span class="sxs-lookup"><span data-stu-id="d877b-295">If you run the advanced test client without that installed you will be directed to [the .NET Core 3.1 installer page](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="d877b-296">请务必安装桌面运行时，而不是 SDK 或 ASP.NET Core Runtime 在页面上的位置。</span><span class="sxs-lookup"><span data-stu-id="d877b-296">Be sure to install the Desktop Runtime and not the SDK, or the ASP.NET Core Runtime which are higher up on the page.</span></span> <span data-ttu-id="d877b-297">计算机上的管理员权限是 reuqired，用于安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d877b-297">Administrator permissions on the machine is reuqired to install .NET Core.</span></span> 

### <a name="what-is-microsoft-365-service-front-door"></a><span data-ttu-id="d877b-298">什么是 Microsoft 365 服务的前门？</span><span class="sxs-lookup"><span data-stu-id="d877b-298">What is Microsoft 365 service front door?</span></span>

<span data-ttu-id="d877b-299">Microsoft 365 服务的前端是 Microsoft 全球网络的一个入口点，Office 客户端和服务终止其网络连接。</span><span class="sxs-lookup"><span data-stu-id="d877b-299">The Microsoft 365 service front door is an entry point on Microsoft's global network where Office clients and services terminate their network connection.</span></span> <span data-ttu-id="d877b-300">为实现到 Microsoft 365 的最佳网络连接，建议您的网络连接在城市或地铁的最近 Microsoft 365 前向外端终止。</span><span class="sxs-lookup"><span data-stu-id="d877b-300">For an optimal network connection to Microsoft 365, it is recommended that your network connection is terminated into the closest Microsoft 365 front door in your city or metro.</span></span>

<span data-ttu-id="d877b-301">注意： Microsoft 365 服务前向与 azure marketplace 提供的 **Azure 前门服务** 产品没有直接关系。</span><span class="sxs-lookup"><span data-stu-id="d877b-301">Note: Microsoft 365 service front door has no direct relationship to the **Azure Front Door Service** product available in the Azure marketplace.</span></span>

### <a name="what-is-the-best-microsoft-365-service-front-door"></a><span data-ttu-id="d877b-302">什么是最佳的 Microsoft 365 服务前盖？</span><span class="sxs-lookup"><span data-stu-id="d877b-302">What is the best Microsoft 365 service front door?</span></span>

<span data-ttu-id="d877b-303">最佳的 Microsoft 365 服务前盖 (以前称为最佳服务前盖) 是最接近您的网络出口（通常在您所在的城市或大都市区域中）的一门。</span><span class="sxs-lookup"><span data-stu-id="d877b-303">A best Microsoft 365 service front door (formerly known as an optimal service front door) is one that is closest to your network egress, generally in your city or metro area.</span></span> <span data-ttu-id="d877b-304">使用 Microsoft 365 网络性能工具来确定正在使用的 Microsoft 365 服务前盖的位置，以及最佳的服务前盖 (s) 。</span><span class="sxs-lookup"><span data-stu-id="d877b-304">Use the Microsoft 365 network performance tool to determine location of your in-use Microsoft 365 service front door and the best service front door(s).</span></span> <span data-ttu-id="d877b-305">如果该工具确定您的使用中的前门是最佳的，那么您应该会有连接到 Microsoft 全局网络的完美连接。</span><span class="sxs-lookup"><span data-stu-id="d877b-305">If the tool determines your in-use front door is one of the best ones, then you should expect great connectivity into Microsoft's global network.</span></span>

### <a name="what-is-an-internet-egress-location"></a><span data-ttu-id="d877b-306">Internet 出口的位置是什么？</span><span class="sxs-lookup"><span data-stu-id="d877b-306">What is an internet egress location?</span></span>

<span data-ttu-id="d877b-307">Internet 出局位置是网络流量退出企业网络并连接到 Internet 的位置。</span><span class="sxs-lookup"><span data-stu-id="d877b-307">The internet egress Location is the location where your network traffic exits your enterprise network and connects to the Internet.</span></span> <span data-ttu-id="d877b-308">这也标识为您的网络地址转换 (NAT) 设备的位置，通常与 Internet 服务提供商 (ISP) 进行连接的位置相同。</span><span class="sxs-lookup"><span data-stu-id="d877b-308">This is also identified as the location where you have a Network Address Translation (NAT) device and usually where you connect with an Internet Service Provider (ISP).</span></span> <span data-ttu-id="d877b-309">如果你发现您的位置和 internet 出局位置之间的距离很长，则这可能会发现重要的 WAN backhaul。</span><span class="sxs-lookup"><span data-stu-id="d877b-309">If you see a long distance between your location and your internet egress location, then this may identify a significant WAN backhaul.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d877b-310">相关主题</span><span class="sxs-lookup"><span data-stu-id="d877b-310">Related topics</span></span>

[<span data-ttu-id="d877b-311">Microsoft 365 管理中心中的网络性能建议 (preview) </span><span class="sxs-lookup"><span data-stu-id="d877b-311">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="d877b-312">Microsoft 365 网络性能见解 (预览版) </span><span class="sxs-lookup"><span data-stu-id="d877b-312">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="d877b-313">Microsoft 365 网络评估 (预览版) </span><span class="sxs-lookup"><span data-stu-id="d877b-313">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="d877b-314">Microsoft 365 网络连接位置服务 (预览) </span><span class="sxs-lookup"><span data-stu-id="d877b-314">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
