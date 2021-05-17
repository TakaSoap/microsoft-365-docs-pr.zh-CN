---
title: Windows 安全更新见解
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941437"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="922a8-103">Windows 安全更新见解</span><span class="sxs-lookup"><span data-stu-id="922a8-103">Windows security update insights</span></span>
<span data-ttu-id="922a8-104">此视图概述了你的移动设备的安全更新Microsoft 托管桌面状态。</span><span class="sxs-lookup"><span data-stu-id="922a8-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="922a8-105">若要查看使用率数据，请选择"Windows<strong>安全更新"</strong>选项卡。</span><span class="sxs-lookup"><span data-stu-id="922a8-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows安全更新窗格：左侧列中设备状态和更新版本的条形图、在中央列中更新部署进度、按部署组更新活动设备的百分比，以及右列中达到 95% 部署目标所经过的天数。](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="922a8-107">设备状态</span><span class="sxs-lookup"><span data-stu-id="922a8-107">Device status</span></span>

<span data-ttu-id="922a8-108">若要通过 Windows 更新来更新设备，设备必须连接到 Internet，并且至少不要休眠六个小时，其中两小时必须持续。</span><span class="sxs-lookup"><span data-stu-id="922a8-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="922a8-109">尽管可能会更新不满足这些要求的设备，但满足这些要求的设备更新的可能性最大。</span><span class="sxs-lookup"><span data-stu-id="922a8-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="922a8-110">我们使用以下条款在更新Windows设备活动进行分类：</span><span class="sxs-lookup"><span data-stu-id="922a8-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="922a8-111"><strong>活动：</strong>满足最低活动条件的设备 (六小时，连续两) 更新版本，并且至少每五天使用 Microsoft Intune签入一次</span><span class="sxs-lookup"><span data-stu-id="922a8-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="922a8-112"><strong>已同步：</strong> 过去 28 天内使用 Intune 签入的设备</span><span class="sxs-lookup"><span data-stu-id="922a8-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="922a8-113"><strong>不同步：</strong>过去 28 天内未使用 Intune 签入的设备<i></i></span><span class="sxs-lookup"><span data-stu-id="922a8-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="922a8-114">更新版本状态</span><span class="sxs-lookup"><span data-stu-id="922a8-114">Update version status</span></span>

<span data-ttu-id="922a8-115">Microsoft 每月的第二个星期二发布安全更新。</span><span class="sxs-lookup"><span data-stu-id="922a8-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="922a8-116">每个版本都会添加已知安全漏洞的重要更新。</span><span class="sxs-lookup"><span data-stu-id="922a8-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="922a8-117">Microsoft 托管桌面确保其 95% 的托管设备每月更新最新的可用安全更新。</span><span class="sxs-lookup"><span data-stu-id="922a8-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="922a8-118">有时在其他时间发布安全更新，以紧急应对新威胁。</span><span class="sxs-lookup"><span data-stu-id="922a8-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="922a8-119">Microsoft 托管桌面部署这些更新的方式类似。</span><span class="sxs-lookup"><span data-stu-id="922a8-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="922a8-120">我们使用以下条款对安全更新版本的状态进行分类：</span><span class="sxs-lookup"><span data-stu-id="922a8-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="922a8-121"><strong>当前：</strong> 运行本月发布的更新的设备</span><span class="sxs-lookup"><span data-stu-id="922a8-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="922a8-122"><strong>上一个：</strong> 运行上个月发布的更新的设备</span><span class="sxs-lookup"><span data-stu-id="922a8-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="922a8-123"><strong>较旧：</strong> 运行上个月之前发布的任何安全更新的设备</span><span class="sxs-lookup"><span data-stu-id="922a8-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="922a8-124">你应该看到"较旧"类别中的<strong></strong>很少设备-一个较大或不断增加群体可能指示你应向用户报告一个Microsoft 托管桌面问题，以便我们可以进行调查。</span><span class="sxs-lookup"><span data-stu-id="922a8-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="922a8-125">部署进度</span><span class="sxs-lookup"><span data-stu-id="922a8-125">Deployment progress</span></span>

<span data-ttu-id="922a8-126">在每个安全更新发布周期开始时，Microsoft 托管桌面获取设备总体的快照，并设置其部署目标为该总体的 95%。</span><span class="sxs-lookup"><span data-stu-id="922a8-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="922a8-127">部署 <strong>进度</strong> 区域显示历史趋势，每日更新，跟踪更新部署在每个版本中达到此目标的进度。</span><span class="sxs-lookup"><span data-stu-id="922a8-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="922a8-128">此图只显示具有活动状态的设备。</span><span class="sxs-lookup"><span data-stu-id="922a8-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="922a8-129">可以使用右上角的下拉菜单查看上一次更新周期的数据。</span><span class="sxs-lookup"><span data-stu-id="922a8-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="922a8-130">在此菜单中选择的时间段适用于整个页面上的所有信息。</span><span class="sxs-lookup"><span data-stu-id="922a8-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="922a8-131">通过<strong>显示每个部署</strong>组更新安装的进度，"按部署组更新的活动设备"区域提供Microsoft 托管桌面视图。</span><span class="sxs-lookup"><span data-stu-id="922a8-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="922a8-132">" <strong>到达目标天数</strong> "区域显示使用当前安全更新更新总设备数的 95% 所用时间。</span><span class="sxs-lookup"><span data-stu-id="922a8-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="922a8-133">部署正在进行时，此区域会显示"仍在<strong></strong>更新"，直到达到所选更新的 95% 目标。</span><span class="sxs-lookup"><span data-stu-id="922a8-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="922a8-134">设备详细信息区域</span><span class="sxs-lookup"><span data-stu-id="922a8-134">Device details area</span></span>

<span data-ttu-id="922a8-135">仪表板底部是一个表格，其中显示设备的详细信息，包括设备[状态](#device-status)[和更新版本状态](#update-version-status)。</span><span class="sxs-lookup"><span data-stu-id="922a8-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="922a8-136">可以搜索此列表或按任何列出的值进行筛选。</span><span class="sxs-lookup"><span data-stu-id="922a8-136">You can search this list or filter it by any listed value.</span></span>


![设备详细信息表显示设备名称、分配的用户、设备状态、更新版本、操作系统版本以及设备上次同步日期的列。](../../media/security-update-insights-device-table-sterile.png)
