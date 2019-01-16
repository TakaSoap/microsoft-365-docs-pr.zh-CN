---
title: Microsoft 托管桌面如何处理更新
description: 及时更新 Microsoft 托管桌面是速度和稳定性的平衡。
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.openlocfilehash: bee6381b0f2b7b1e2d929329c3cf628ab7657678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865505"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="4030c-104">Microsoft 托管桌面如何处理更新</span><span class="sxs-lookup"><span data-stu-id="4030c-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="4030c-p101">Microsoft 托管桌面连接到基于云的现代基础结构的所有设备。确保业务应用程序更新的 Windows、 Office、 驱动程序、 固件和 Microsoft 存储最新是速度和稳定性的平衡。部署在拨打将用于确保 OS 和策略的推出以安全方式。</span><span class="sxs-lookup"><span data-stu-id="4030c-p101">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure. Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business application updates up to date is a balance of speed and stability. Deployment rings will be used to ensure OS and policies are rolled out in a safe manner.</span></span> 

## <a name="update-groups"></a><span data-ttu-id="4030c-108">更新组</span><span class="sxs-lookup"><span data-stu-id="4030c-108">Update groups</span></span>

<span data-ttu-id="4030c-109">Microsoft 托管桌面使用四个 Azure AD 组来管理更新：</span><span class="sxs-lookup"><span data-stu-id="4030c-109">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="4030c-p102">测试： 非生产设备用于验证跨租户的其余部分部署所做的更改之前的更改。在此拨打的设备超出记录的最终用户支持的范围。</span><span class="sxs-lookup"><span data-stu-id="4030c-p102">Test: Non-production devices intended to validate changes prior to deploying the changes across the rest of the tenant. Devices in this ring are out of scope for documented end user support.</span></span> 
- <span data-ttu-id="4030c-112">首先： 包含前期软件应用，并且设备可能受到预发布更新。</span><span class="sxs-lookup"><span data-stu-id="4030c-112">First: Contains early software adopters, and devices may be subject to pre-release updates.</span></span>
- <span data-ttu-id="4030c-p103">Fast： 优先稳定性速度。用于检测质量问题之前它们拨打给广泛的组。</span><span class="sxs-lookup"><span data-stu-id="4030c-p103">Fast: Prioritizes speed over stability. Useful for detecting quality issues before they are offered to the Broad group.</span></span> 
- <span data-ttu-id="4030c-p104">广泛： 最后一组具有可用的功能和质量更新。此组包含大多数租户中的用户，因此倾向稳定性于优先于部署中的速度。</span><span class="sxs-lookup"><span data-stu-id="4030c-p104">Broad: Last group to have feature and quality updates available. This group contains the majority of users in the tenant, and therefore favors stability over speed in deployment.</span></span>

<span data-ttu-id="4030c-p105">累积和可能归类为质量或功能更新 Microsoft 发布的更新。有关详细信息，请参阅[Windows Update： 常见问题](https://support.microsoft.com/help/12373/windows-update-faq)。</span><span class="sxs-lookup"><span data-stu-id="4030c-p105">Updates released by Microsoft are cumulative and may be categorized as quality or feature updates. For more information, see [Windows Update: FAQ](https://support.microsoft.com/help/12373/windows-update-faq).</span></span> 

<span data-ttu-id="4030c-119">如何更新部署的工作方式：</span><span class="sxs-lookup"><span data-stu-id="4030c-119">How update deployment works:</span></span>
- <span data-ttu-id="4030c-120">Microsoft 托管桌面部署新的功能或质量更新，将根据下面指定的计划。</span><span class="sxs-lookup"><span data-stu-id="4030c-120">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="4030c-p106">在部署期间，Microsoft 托管桌面监视故障或中断 （基于遥测信号和最终用户支持系统） 的迹象。如果检测到任何已立即暂停部署到当前和将来的所有组。</span><span class="sxs-lookup"><span data-stu-id="4030c-p106">During deployment, Microsoft Managed Desktop monitors for signs of failure or disruption (based on telemetry signals and end-user support system). If any are detected, then the deployment to all current and future groups is immediately paused.</span></span>
    - <span data-ttu-id="4030c-123">示例： 如果发现问题时质量的更新部署到的第一个组，然后更新到第一个、 Fast、 和广泛的部署将所有暂停解决该问题之前。</span><span class="sxs-lookup"><span data-stu-id="4030c-123">Example: if an issue is discovered while deploying a quality update to the First group, then update deployments to First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="4030c-124">兼容性问题可能会报告归档 Microsoft 托管桌面 IT 管理门户中的票证。</span><span class="sxs-lookup"><span data-stu-id="4030c-124">Compatibility issues may be reported by filing a ticket in the Microsoft Managed Desktop IT Admin portal.</span></span>
- <span data-ttu-id="4030c-p107">功能和质量更新独立暂停。暂停实际上是 35 天，默认情况下，但可减少或扩展具体取决于是否修正问题。</span><span class="sxs-lookup"><span data-stu-id="4030c-p107">Feature and quality updates are paused independently. Pause is in effect for 35 days by default, but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="4030c-127">未暂停组后，部署恢复根据以下计划。</span><span class="sxs-lookup"><span data-stu-id="4030c-127">Once the groups are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="4030c-128">此部署过程适用于功能和质量更新，但日程表会有所不同，每个。</span><span class="sxs-lookup"><span data-stu-id="4030c-128">This deployment process applies to both feature and quality updates, though the timeline varies for each.</span></span>

<table>
<tr><th colspan="5"><span data-ttu-id="4030c-129">更新部署设置</span><span class="sxs-lookup"><span data-stu-id="4030c-129">Update deployment settings</span></span></th></tr>
<tr><th><span data-ttu-id="4030c-130">更新类型</span><span class="sxs-lookup"><span data-stu-id="4030c-130">Update type</span></span></th><th><span data-ttu-id="4030c-131">测试</span><span class="sxs-lookup"><span data-stu-id="4030c-131">Test</span></span></th><th><span data-ttu-id="4030c-132">第一个</span><span class="sxs-lookup"><span data-stu-id="4030c-132">First</span></span></th><th><span data-ttu-id="4030c-133">快速</span><span class="sxs-lookup"><span data-stu-id="4030c-133">Fast</span></span></th><th><span data-ttu-id="4030c-134">广泛</span><span class="sxs-lookup"><span data-stu-id="4030c-134">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="4030c-135">高质量的操作系统的更新</span><span class="sxs-lookup"><span data-stu-id="4030c-135">Quality updates for operating system</span></span></td><td><span data-ttu-id="4030c-136">0 天</span><span class="sxs-lookup"><span data-stu-id="4030c-136">0 days</span></span></td><td><span data-ttu-id="4030c-137">0 天</span><span class="sxs-lookup"><span data-stu-id="4030c-137">0 days</span></span></td><td><span data-ttu-id="4030c-138">0 天</span><span class="sxs-lookup"><span data-stu-id="4030c-138">0 days</span></span></td><td><span data-ttu-id="4030c-139">3 天</span><span class="sxs-lookup"><span data-stu-id="4030c-139">3 days</span></span></td></tr>
<tr><td><span data-ttu-id="4030c-140">操作系统的功能更新</span><span class="sxs-lookup"><span data-stu-id="4030c-140">Feature updates for operating system</span></span></td><td><span data-ttu-id="4030c-141">0 天</span><span class="sxs-lookup"><span data-stu-id="4030c-141">0 days</span></span></td><td><span data-ttu-id="4030c-142">30 天</span><span class="sxs-lookup"><span data-stu-id="4030c-142">30 days</span></span></td><td><span data-ttu-id="4030c-143">60 天</span><span class="sxs-lookup"><span data-stu-id="4030c-143">60 days</span></span></td><td><span data-ttu-id="4030c-144">90 天</span><span class="sxs-lookup"><span data-stu-id="4030c-144">90 days</span></span></td></tr>
<tr><td><span data-ttu-id="4030c-145">驱动程序/固件</span><span class="sxs-lookup"><span data-stu-id="4030c-145">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="4030c-146">遵循高质量的更新的计划</span><span class="sxs-lookup"><span data-stu-id="4030c-146">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="4030c-147">防病毒定义</span><span class="sxs-lookup"><span data-stu-id="4030c-147">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="4030c-148">更新了每个扫描</span><span class="sxs-lookup"><span data-stu-id="4030c-148">Updated with each scan</span></span></td></tr>
</table>

<span data-ttu-id="4030c-p108">这些延期段有意旨在确保高安全性和性能标准的所有用户。Microsoft 托管桌面基于跨所有 Microsoft 托管桌面设备和不同的范围和更新的影响整个收集的数据，此外，保留灵活地修改 ad 上的所有部署组上述延期期的时长临时基础。</span><span class="sxs-lookup"><span data-stu-id="4030c-p108">These deferral periods are intentionally designed to ensure high security and performance standards for all users. Furthermore, based on data gathered across all Microsoft Managed Desktop devices and the varying scope and impact of updates, Microsoft Managed Desktop reserves flexibility to modify the length of the above deferral periods for any and all deployment groups on an ad hoc basis.</span></span>

## <a name="windows-insider-program"></a><span data-ttu-id="4030c-151">Windows 内幕计划</span><span class="sxs-lookup"><span data-stu-id="4030c-151">Windows Insider Program</span></span>

<span data-ttu-id="4030c-p109">Microsoft 托管桌面不支持 Windows 内幕计划的一部分的设备。Windows 内幕计划用于验证预发行 Windows 软件和适用于非任务关键设备。尽管这是一项重要 Microsoft 举措，它不是在生产环境中的广泛部署。</span><span class="sxs-lookup"><span data-stu-id="4030c-p109">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program. The Windows Insider program is used to validate pre-release Windows software and is intended for non-mission critical devices. While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="4030c-155">与 Windows 内幕生成找到任何设备将置于测试组，且不可包含更新服务级别协议 (Sla。</span><span class="sxs-lookup"><span data-stu-id="4030c-155">Any devices found with Windows Insider builds will be put into the Test group and not be included for update service level agreements (SLAs.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="4030c-156">带宽管理</span><span class="sxs-lookup"><span data-stu-id="4030c-156">Bandwidth management</span></span>

<span data-ttu-id="4030c-p110">传递优化用于所有操作的系统和驱动程序更新。它旨在从企业网络内部的对等方的更新，降至最低从 Windows 更新 (WU) 服务下载的大小。</span><span class="sxs-lookup"><span data-stu-id="4030c-p110">Delivery optimization is used for all operating system and driver updates. It minimizes the download size from the Windows Update (WU) service by seeking updates from peers within the corporate network.</span></span>


