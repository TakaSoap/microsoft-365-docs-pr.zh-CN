---
title: 查看和组织 Microsoft Defender ATP 设备列表
description: 了解可从设备列表中使用的可用功能，例如排序、筛选和导出列表以增强调查。
keywords: 排序， 筛选， 导出， csv， 设备名称， 域， 上次看到时间， 内部 IP， 运行状况状态， 活动警报， 活动恶意软件检测， 威胁类别， 查看警报， 网络， 连接， 恶意软件， 类型， 密码窃取程序， 勒索软件， 攻击， 威胁， 常规恶意软件， 不需要的软件
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
ms.technology: mde
ms.openlocfilehash: 01ad9f92299cd9d1b4a723bdec54f86f32ca8274
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056529"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="c36bc-104">查看和组织适用于终结点设备的 Microsoft Defender 列表</span><span class="sxs-lookup"><span data-stu-id="c36bc-104">View and organize the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c36bc-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c36bc-105">**Applies to:**</span></span>
- [<span data-ttu-id="c36bc-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c36bc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="c36bc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c36bc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c36bc-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="c36bc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c36bc-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c36bc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


<span data-ttu-id="c36bc-110">**"设备"** 列表显示网络中生成警报的设备列表。</span><span class="sxs-lookup"><span data-stu-id="c36bc-110">The **Devices list** shows a list of the devices in your network where alerts were generated.</span></span> <span data-ttu-id="c36bc-111">默认情况下，队列显示最近 30 天内看到的设备。</span><span class="sxs-lookup"><span data-stu-id="c36bc-111">By default, the queue displays devices seen in the last 30 days.</span></span>  

<span data-ttu-id="c36bc-112">一目了然地，你将看到域、风险级别、操作系统平台和其他详细信息，以轻松识别风险最大的设备。</span><span class="sxs-lookup"><span data-stu-id="c36bc-112">At a glance you'll see information such as domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

<span data-ttu-id="c36bc-113">有几种选项可供选择以自定义设备列表视图。</span><span class="sxs-lookup"><span data-stu-id="c36bc-113">There are several options you can choose from to customize the devices list view.</span></span> <span data-ttu-id="c36bc-114">在顶部导航上，你可以：</span><span class="sxs-lookup"><span data-stu-id="c36bc-114">On the top navigation you can:</span></span>

- <span data-ttu-id="c36bc-115">添加或删除列</span><span class="sxs-lookup"><span data-stu-id="c36bc-115">Add or remove columns</span></span>
- <span data-ttu-id="c36bc-116">导出 CSV 格式的整个列表</span><span class="sxs-lookup"><span data-stu-id="c36bc-116">Export the entire list in CSV format</span></span>
- <span data-ttu-id="c36bc-117">选择要显示每页的项目数</span><span class="sxs-lookup"><span data-stu-id="c36bc-117">Select the number of items to show per page</span></span>
- <span data-ttu-id="c36bc-118">应用筛选器</span><span class="sxs-lookup"><span data-stu-id="c36bc-118">Apply filters</span></span>

<span data-ttu-id="c36bc-119">在载入过程中， **设备列表** 将随着设备开始报告传感器数据而逐渐填充。</span><span class="sxs-lookup"><span data-stu-id="c36bc-119">During the onboarding process, the **Devices list** is gradually populated with devices as they begin to report sensor data.</span></span> <span data-ttu-id="c36bc-120">使用此视图在已载入终结点联机时跟踪它们，或下载完整的终结点列表作为 CSV 文件进行脱机分析。</span><span class="sxs-lookup"><span data-stu-id="c36bc-120">Use this view to track your onboarded endpoints as they come online, or download the complete endpoint list as a CSV file for offline analysis.</span></span>

>[!NOTE]
> <span data-ttu-id="c36bc-121">如果导出设备列表，它将包含组织的每台设备。</span><span class="sxs-lookup"><span data-stu-id="c36bc-121">If you export the device list, it will contain every device in your organization.</span></span> <span data-ttu-id="c36bc-122">下载可能需要很长时间，具体取决于你的组织规模。</span><span class="sxs-lookup"><span data-stu-id="c36bc-122">It might take a significant amount of time to download, depending on how large your organization is.</span></span> <span data-ttu-id="c36bc-123">以 CSV 格式导出列表以未筛选的方式显示数据。</span><span class="sxs-lookup"><span data-stu-id="c36bc-123">Exporting the list in CSV format displays the data in an unfiltered manner.</span></span> <span data-ttu-id="c36bc-124">CSV 文件将包含组织的所有设备，而不考虑视图本身应用的任何筛选。</span><span class="sxs-lookup"><span data-stu-id="c36bc-124">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself.</span></span>

![包含设备列表的设备列表的图像](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a><span data-ttu-id="c36bc-126">排序和筛选设备列表</span><span class="sxs-lookup"><span data-stu-id="c36bc-126">Sort and filter the device list</span></span>

<span data-ttu-id="c36bc-127">可以应用以下筛选器来限制警报列表，并获取更集中的视图。</span><span class="sxs-lookup"><span data-stu-id="c36bc-127">You can apply the following filters to limit the list of alerts and get a more focused view.</span></span>

### <a name="risk-level"></a><span data-ttu-id="c36bc-128">风险级别</span><span class="sxs-lookup"><span data-stu-id="c36bc-128">Risk level</span></span>

<span data-ttu-id="c36bc-129">风险级别根据各种因素（包括设备上活动警报的类型和严重性）反映了设备的总体风险评估。</span><span class="sxs-lookup"><span data-stu-id="c36bc-129">The risk level reflects the overall risk assessment of the device based on a combination of factors, including the types and severity of active alerts on the device.</span></span> <span data-ttu-id="c36bc-130">解决活动警报、批准修正活动以及抑制后续警报会降低风险级别。</span><span class="sxs-lookup"><span data-stu-id="c36bc-130">Resolving active alerts, approving remediation activities, and suppressing subsequent alerts can lower the risk level.</span></span>

### <a name="exposure-level"></a><span data-ttu-id="c36bc-131">曝光级别</span><span class="sxs-lookup"><span data-stu-id="c36bc-131">Exposure level</span></span>

<span data-ttu-id="c36bc-132">曝光级别根据设备挂起的安全建议累积影响反映设备的当前曝光情况。</span><span class="sxs-lookup"><span data-stu-id="c36bc-132">The exposure level reflects the current exposure of the device based on the cumulative impact of its pending security recommendations.</span></span> <span data-ttu-id="c36bc-133">可能的级别为低、中和高。</span><span class="sxs-lookup"><span data-stu-id="c36bc-133">The possible levels are low, medium, and high.</span></span> <span data-ttu-id="c36bc-134">低曝光意味着你的设备不太容易被利用。</span><span class="sxs-lookup"><span data-stu-id="c36bc-134">Low exposure means your devices are less vulnerable from exploitation.</span></span>

<span data-ttu-id="c36bc-135">如果曝光级别显示"无可用数据"，可能有以下原因：</span><span class="sxs-lookup"><span data-stu-id="c36bc-135">If the exposure level says "No data available," there are a few reasons why this may be the case:</span></span>

- <span data-ttu-id="c36bc-136">设备停止报告超过 30 天 - 在这种情况下，它被视为非活动状态，并且未计算曝光</span><span class="sxs-lookup"><span data-stu-id="c36bc-136">Device stopped reporting for more than 30 days – in that case it is considered inactive, and the exposure isn't computed</span></span>
- <span data-ttu-id="c36bc-137">设备操作系统不受支持 - 请参阅 [Microsoft Defender for Endpoint 的最低要求](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="c36bc-137">Device OS not supported - see [minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)</span></span>
- <span data-ttu-id="c36bc-138">具有过时代理 (不太可能) </span><span class="sxs-lookup"><span data-stu-id="c36bc-138">Device with stale agent (very unlikely)</span></span>

### <a name="os-platform"></a><span data-ttu-id="c36bc-139">操作系统平台</span><span class="sxs-lookup"><span data-stu-id="c36bc-139">OS Platform</span></span>

<span data-ttu-id="c36bc-140">仅选择你有兴趣调查的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="c36bc-140">Select only the OS platforms you're interested in investigating.</span></span>

### <a name="health-state"></a><span data-ttu-id="c36bc-141">运行状况</span><span class="sxs-lookup"><span data-stu-id="c36bc-141">Health state</span></span>

<span data-ttu-id="c36bc-142">按以下设备运行状况状态进行筛选：</span><span class="sxs-lookup"><span data-stu-id="c36bc-142">Filter by the following device health states:</span></span>

- <span data-ttu-id="c36bc-143">**活动** – 主动向服务报告传感器数据的设备。</span><span class="sxs-lookup"><span data-stu-id="c36bc-143">**Active** – Devices that are actively reporting sensor data to the service.</span></span>
- <span data-ttu-id="c36bc-144">**非** 活动 – 已完全停止发送信号超过 7 天的设备。</span><span class="sxs-lookup"><span data-stu-id="c36bc-144">**Inactive** – Devices that have completely stopped sending signals for more than 7 days.</span></span>
- <span data-ttu-id="c36bc-145">**错误配置** – 与服务通信受损或无法发送传感器数据的设备。</span><span class="sxs-lookup"><span data-stu-id="c36bc-145">**Misconfigured** – Devices that have impaired communications with service or are unable to send sensor data.</span></span> <span data-ttu-id="c36bc-146">可以将错误配置的设备进一步分类为：</span><span class="sxs-lookup"><span data-stu-id="c36bc-146">Misconfigured devices can further be classified to:</span></span>
  - <span data-ttu-id="c36bc-147">无传感器数据</span><span class="sxs-lookup"><span data-stu-id="c36bc-147">No sensor data</span></span>
  - <span data-ttu-id="c36bc-148">通信受损</span><span class="sxs-lookup"><span data-stu-id="c36bc-148">Impaired communications</span></span>

  <span data-ttu-id="c36bc-149">若要详细了解如何解决错误配置设备上的问题，请参阅修复 [不正常的传感器](fix-unhealthy-sensors.md)。</span><span class="sxs-lookup"><span data-stu-id="c36bc-149">For more information on how to address issues on misconfigured devices see, [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span></span>

### <a name="antivirus-status"></a><span data-ttu-id="c36bc-150">防病毒状态</span><span class="sxs-lookup"><span data-stu-id="c36bc-150">Antivirus status</span></span>

<span data-ttu-id="c36bc-151">按防病毒状态筛选设备。</span><span class="sxs-lookup"><span data-stu-id="c36bc-151">Filter devices by antivirus status.</span></span> <span data-ttu-id="c36bc-152">仅适用于活动的 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="c36bc-152">Applies to active Windows 10 devices only.</span></span>

- <span data-ttu-id="c36bc-153">**已禁用** - &威胁防护已关闭。</span><span class="sxs-lookup"><span data-stu-id="c36bc-153">**Disabled** - Virus & threat protection is turned off.</span></span>
- <span data-ttu-id="c36bc-154">**不报告** - 病毒&威胁防护未报告。</span><span class="sxs-lookup"><span data-stu-id="c36bc-154">**Not reporting** - Virus & threat protection is not reporting.</span></span>
- <span data-ttu-id="c36bc-155">**未更新** - 病毒&威胁防护不是最新的。</span><span class="sxs-lookup"><span data-stu-id="c36bc-155">**Not updated** - Virus & threat protection is not up to date.</span></span>

<span data-ttu-id="c36bc-156">有关详细信息，请参阅查看威胁 [&漏洞管理仪表板](tvm-dashboard-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="c36bc-156">For more information, see [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span></span>

### <a name="threat-mitigation-status"></a><span data-ttu-id="c36bc-157">威胁缓解状态</span><span class="sxs-lookup"><span data-stu-id="c36bc-157">Threat mitigation status</span></span>

<span data-ttu-id="c36bc-158">若要查看受特定威胁影响的设备，请从下拉菜单中选择威胁，然后选择需要缓解的漏洞方面。</span><span class="sxs-lookup"><span data-stu-id="c36bc-158">To view devices that may be affected by a certain threat, select the threat from the dropdown menu, and then select what vulnerability aspect needs to be mitigated.</span></span>

<span data-ttu-id="c36bc-159">若要了解有关特定威胁的更多信息，请参阅 [威胁分析](threat-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="c36bc-159">To learn more about certain threats, see [Threat analytics](threat-analytics.md).</span></span> <span data-ttu-id="c36bc-160">有关缓解信息，请参阅[威胁&漏洞管理。](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="c36bc-160">For mitigation information, see [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span>

### <a name="windows-10-version"></a><span data-ttu-id="c36bc-161">Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="c36bc-161">Windows 10 version</span></span>

<span data-ttu-id="c36bc-162">仅选择你有兴趣调查的 Windows 10 版本。</span><span class="sxs-lookup"><span data-stu-id="c36bc-162">Select only the Windows 10 versions you're interested in investigating.</span></span>

### <a name="tags--groups"></a><span data-ttu-id="c36bc-163">标记&组</span><span class="sxs-lookup"><span data-stu-id="c36bc-163">Tags & Groups</span></span>

<span data-ttu-id="c36bc-164">根据已添加到个别设备的分组和标记筛选列表。</span><span class="sxs-lookup"><span data-stu-id="c36bc-164">Filter the list based on the grouping and tagging that you've added to individual devices.</span></span> <span data-ttu-id="c36bc-165">请参阅[创建和管理设备标记和](machine-tags.md)[创建和管理设备组](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="c36bc-165">See [Create and manage device tags](machine-tags.md) and [Create and manage device groups](machine-groups.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c36bc-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="c36bc-166">Related topics</span></span>

- [<span data-ttu-id="c36bc-167">调查 Microsoft Defender 终结点设备列表中的设备</span><span class="sxs-lookup"><span data-stu-id="c36bc-167">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
