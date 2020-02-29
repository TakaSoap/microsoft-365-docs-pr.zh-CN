---
title: Windows 安全更新见解
description: ''
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ef2d5c897709e7f7d2484d032b7471031be77d74
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341260"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="5d6b1-103">Windows 安全更新见解</span><span class="sxs-lookup"><span data-stu-id="5d6b1-103">Windows security update insights</span></span>
<span data-ttu-id="5d6b1-104">此视图概述了 Microsoft 托管桌面设备的安全更新状态。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="5d6b1-105">若要查看使用率数据，请选择 " <strong>Windows 安全更新</strong>" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows 安全更新窗格：设备状态的条形图和更新版本在左栏中，在一段时间内更新部署进度（中间列）和按部署组排列的活动设备百分比，以及达到95% 部署所需的天数右列中的目标。](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="5d6b1-107">设备状态</span><span class="sxs-lookup"><span data-stu-id="5d6b1-107">Device status</span></span>

<span data-ttu-id="5d6b1-108">对于要通过 Windows 更新进行更新的设备，必须将其连接到 Internet，且不能至少在6小时内休眠，其中两个必须是连续的。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="5d6b1-109">只要设备已连接且不处于休眠状态，就认为 "正在使用"。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-109">As long as a device is connected and not hibernating, it's considered to be "in use."</span></span> <span data-ttu-id="5d6b1-110">尽管可能会更新不符合这些要求的设备，但满足它们的设备的更新可能性最高。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-110">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="5d6b1-111">我们使用以下术语在 Windows Update 的上下文中对设备活动进行分类：</span><span class="sxs-lookup"><span data-stu-id="5d6b1-111">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="5d6b1-112"><strong>Active：</strong>满足最少使用条件（6小时、两个连续）的设备，适用于最新安全更新版本，并已在 Microsoft Intune 中至少每五天签入一次</span><span class="sxs-lookup"><span data-stu-id="5d6b1-112"><strong>Active:</strong> Devices that have met the minimum usage criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="5d6b1-113">已<strong>同步：</strong>在最近28天内使用 Intune 签入的设备</span><span class="sxs-lookup"><span data-stu-id="5d6b1-113"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="5d6b1-114">不<strong>同步：</strong>最近28天内<i>未</i>使用 Intune 签入的设备</span><span class="sxs-lookup"><span data-stu-id="5d6b1-114"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="5d6b1-115">更新版本状态</span><span class="sxs-lookup"><span data-stu-id="5d6b1-115">Update version status</span></span>

<span data-ttu-id="5d6b1-116">Microsoft 每月的第二个星期二发布安全更新。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-116">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="5d6b1-117">每个版本都添加了已知安全漏洞的重要更新。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-117">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="5d6b1-118">Microsoft 托管桌面可确保每月使用最新的可用安全更新更新95% 的托管设备。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-118">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="5d6b1-119">有时会在其他时间发布安全更新，以迫切解决新威胁。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-119">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="5d6b1-120">Microsoft 托管桌面以类似的方式部署这些更新。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-120">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="5d6b1-121">我们将安全更新版本的状态分类为以下术语：</span><span class="sxs-lookup"><span data-stu-id="5d6b1-121">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="5d6b1-122"><strong>Current：</strong>运行当前月发布的更新的设备</span><span class="sxs-lookup"><span data-stu-id="5d6b1-122"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="5d6b1-123"><strong>上一个：</strong>运行上个月发布的更新的设备</span><span class="sxs-lookup"><span data-stu-id="5d6b1-123"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="5d6b1-124"><strong>较旧：</strong>运行上个月之前发布的任何安全更新的设备</span><span class="sxs-lookup"><span data-stu-id="5d6b1-124"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="5d6b1-125">您应该会看到<strong>较旧</strong>类别中的几个设备-较大或增加的总体可能表示系统问题，您应报告给 Microsoft 托管桌面，以便我们可以进行调查。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-125">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="5d6b1-126">部署进度</span><span class="sxs-lookup"><span data-stu-id="5d6b1-126">Deployment progress</span></span>

<span data-ttu-id="5d6b1-127">在每个安全更新发布周期开始时，Microsoft 托管桌面将获取设备填充的快照，并将其部署目标设置为该总体的95%。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-127">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="5d6b1-128"><strong>部署进度</strong>区域显示一个历史趋势，每日更新一次，跟踪更新部署满足每个版本的此目标的程度。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-128">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="5d6b1-129">此图仅显示具有活动状态的设备。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-129">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="5d6b1-130">您可以使用右上角的下拉菜单查看以前的更新周期的此数据。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-130">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="5d6b1-131">您在此菜单中选择的时间段适用于整个页面上的所有信息。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-131">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="5d6b1-132">"<strong>按部署更新的活动设备" 组</strong>区域通过显示每个 Microsoft 托管桌面部署组的更新安装进度，提供了一个不同的视图。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-132">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="5d6b1-133"><strong>到达目标</strong>区域的天数显示要使用当前安全更新更新的设备总数的95% 所花的时间。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-133">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="5d6b1-134">在部署过程中，此区域显示<strong>更新</strong>，直到达到选定更新的95% 目标为止。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-134">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="5d6b1-135">设备详细信息区域</span><span class="sxs-lookup"><span data-stu-id="5d6b1-135">Device details area</span></span>

<span data-ttu-id="5d6b1-136">仪表板的底部是显示设备的详细信息的表格，其中包括[设备状态](#device-status)和[更新版本状态](#update-version-status)。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-136">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="5d6b1-137">您可以搜索此列表，也可以按任何列出的值对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="5d6b1-137">You can search this list or filter it by any listed value.</span></span>


![显示设备名称、分配的用户、设备状态、更新版本、操作系统版本以及设备上次同步日期的列的设备详细信息表。](../../media/security-update-insights-device-table-sterile.png)
