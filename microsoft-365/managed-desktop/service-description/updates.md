---
title: 如何在 Microsoft 托管桌面中处理更新
description: 将 Microsoft 托管桌面保持最新状态是速度和稳定性的平衡。
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c2ab48c87f1239c21e6620ea00640bb3dabbdd45
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981633"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="e3af9-104">如何在 Microsoft 托管桌面中处理更新</span><span class="sxs-lookup"><span data-stu-id="e3af9-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="e3af9-105">Microsoft 托管桌面将所有设备连接到基于云的新式基础结构。</span><span class="sxs-lookup"><span data-stu-id="e3af9-105">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure.</span></span> <span data-ttu-id="e3af9-106">将 Windows、Office、驱动程序、固件和 Microsoft Store for Business 应用程序保持为最新是速度和稳定性的平衡。</span><span class="sxs-lookup"><span data-stu-id="e3af9-106">Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business applications up to date is a balance of speed and stability.</span></span> <span data-ttu-id="e3af9-107">将使用部署组来确保操作系统更新和策略以安全的方式进行分发。</span><span class="sxs-lookup"><span data-stu-id="e3af9-107">Deployment groups will be used to ensure operating system updates and policies are rolled out in a safe manner.</span></span> 

<span data-ttu-id="e3af9-108">由 Microsoft 发布的更新是累积的，并被分类为质量或功能更新。</span><span class="sxs-lookup"><span data-stu-id="e3af9-108">Updates released by Microsoft are cumulative and are categorized as quality or feature updates.</span></span>
<span data-ttu-id="e3af9-109">有关详细信息，请参阅[Windows update For Business：更新类型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)。</span><span class="sxs-lookup"><span data-stu-id="e3af9-109">For more information, see [Windows Update for Business: Update types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types).</span></span> 

## <a name="update-groups"></a><span data-ttu-id="e3af9-110">更新组</span><span class="sxs-lookup"><span data-stu-id="e3af9-110">Update groups</span></span>

<span data-ttu-id="e3af9-111">Microsoft 托管桌面使用四个 Azure AD 组管理更新：</span><span class="sxs-lookup"><span data-stu-id="e3af9-111">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="e3af9-112">**测试**：用于验证 Microsoft 托管桌面策略更改、操作系统更新、功能更新以及推送到租户的其他更改。</span><span class="sxs-lookup"><span data-stu-id="e3af9-112">**Test**: Used to validate Microsoft Managed Desktop policy changes, operating system updates, feature updates, and other changes pushed to the tenant.</span></span> <span data-ttu-id="e3af9-113">测试组中不应放置任何最终用户。</span><span class="sxs-lookup"><span data-stu-id="e3af9-113">There should not be any end users placed in the test group.</span></span> <span data-ttu-id="e3af9-114">测试组免除了任何已建立的服务级别协议和最终用户支持。</span><span class="sxs-lookup"><span data-stu-id="e3af9-114">The test group is exempt from any established service level agreements and end-user support.</span></span> <span data-ttu-id="e3af9-115">此组可用于验证应用程序与新策略或操作系统 hanges 的兼容性。</span><span class="sxs-lookup"><span data-stu-id="e3af9-115">This group is available for use to validate compatibility of applications with new policy or operating system hanges.</span></span>  
- <span data-ttu-id="e3af9-116">**First**：包含早期的软件采用者和设备，它们可能受预发布更新的制约。</span><span class="sxs-lookup"><span data-stu-id="e3af9-116">**First**: Contains early software adopters and devices that could be subject to pre-release updates.</span></span> <span data-ttu-id="e3af9-117">如果存在测试环中测试期间未涵盖的方案，则此组中的设备可能会遇到中断。</span><span class="sxs-lookup"><span data-stu-id="e3af9-117">Devices in this group might experience outages if there are scenarios which were not covered during testing in the test ring.</span></span>
- <span data-ttu-id="e3af9-118">**Fast**：按稳定性对速度进行优先级划分。</span><span class="sxs-lookup"><span data-stu-id="e3af9-118">**Fast**: Prioritizes speed over stability.</span></span> <span data-ttu-id="e3af9-119">用于在向广泛组提供质量问题之前检测质量问题。</span><span class="sxs-lookup"><span data-stu-id="e3af9-119">Useful for detecting quality issues before they are offered to the Broad group.</span></span> <span data-ttu-id="e3af9-120">此组可用作验证的下一层，但通常比测试和第一组更稳定。</span><span class="sxs-lookup"><span data-stu-id="e3af9-120">This group serves as a next layer of validation but is generally more stable than the Test and First groups.</span></span> 
- <span data-ttu-id="e3af9-121">**广泛**：最后一个组具有可用的功能和质量更新。</span><span class="sxs-lookup"><span data-stu-id="e3af9-121">**Broad**: Last group to have feature and quality updates available.</span></span> <span data-ttu-id="e3af9-122">此组包含租户中的大多数用户，因此在部署过程中比速度更有利于稳定性。</span><span class="sxs-lookup"><span data-stu-id="e3af9-122">This group contains the majority of users in the tenant, and therefore favors stability over speed in deployment.</span></span> <span data-ttu-id="e3af9-123">应在此完成应用程序的测试，因为环境最稳定。</span><span class="sxs-lookup"><span data-stu-id="e3af9-123">Testing of apps should be done here as the environment is most stable.</span></span> 

> [!NOTE]
> <span data-ttu-id="e3af9-124">如果需要将用户移动到其他更新组，请提交支持请求。</span><span class="sxs-lookup"><span data-stu-id="e3af9-124">If you need to move a user to a different update group, submit a support request.</span></span> <span data-ttu-id="e3af9-125">有关提交支持请求的详细信息，请参阅[支持 Microsoft 托管桌面](support.md)。</span><span class="sxs-lookup"><span data-stu-id="e3af9-125">See [Support for Microsoft Managed Desktop](support.md) for more information on submitting support requests.</span></span> <span data-ttu-id="e3af9-126">如果您自己移动用户，移动将会恢复。</span><span class="sxs-lookup"><span data-stu-id="e3af9-126">If you move a user yourself, the move will be reverted.</span></span>

<span data-ttu-id="e3af9-127">有关这些部署组的详细信息角色和职责，请参阅[Microsoft 托管桌面角色和职责](../intro/roles-and-responsibilities.md)</span><span class="sxs-lookup"><span data-stu-id="e3af9-127">For more information roles and responsibilities with these deployment groups, see [Microsoft Managed Desktop Roles and responsibilities](../intro/roles-and-responsibilities.md)</span></span>

<span data-ttu-id="e3af9-128">更新部署的工作原理：</span><span class="sxs-lookup"><span data-stu-id="e3af9-128">How update deployment works:</span></span>
- <span data-ttu-id="e3af9-129">Microsoft 托管桌面根据下面指定的计划，部署新的功能或质量更新。</span><span class="sxs-lookup"><span data-stu-id="e3af9-129">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="e3af9-130">在部署过程中，Microsoft 托管的桌面监视器会针对故障或中断（基于诊断数据和最终用户支持系统）的迹象进行标记。</span><span class="sxs-lookup"><span data-stu-id="e3af9-130">During deployment, Microsoft Managed Desktop monitors for signs of failure or disruption (based on diagnostic data and the end-user support system).</span></span> <span data-ttu-id="e3af9-131">如果检测到任何其他组，则会立即暂停部署到当前和将来的所有组。</span><span class="sxs-lookup"><span data-stu-id="e3af9-131">If any are detected, then the deployment to all current and future groups is immediately paused.</span></span>
    - <span data-ttu-id="e3af9-132">示例：如果在将质量更新部署到第一个组时发现了问题，则在解决问题之前，先将部署更新到第一个、快速和广泛的过程将会暂停。</span><span class="sxs-lookup"><span data-stu-id="e3af9-132">Example: if an issue is discovered while deploying a quality update to the First group, then update deployments to First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="e3af9-133">可以通过在 Microsoft 托管桌面管理门户中存档票证来报告兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="e3af9-133">Compatibility issues can be reported by filing a ticket in the Microsoft Managed Desktop Admin portal.</span></span>
- <span data-ttu-id="e3af9-134">功能和质量更新是独立暂停的。</span><span class="sxs-lookup"><span data-stu-id="e3af9-134">Feature and quality updates are paused independently.</span></span> <span data-ttu-id="e3af9-135">默认情况下，Pause 将对35天生效，但可以根据问题是否修正来进行缩减或扩展。</span><span class="sxs-lookup"><span data-stu-id="e3af9-135">Pause is in effect for 35 days by default, but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="e3af9-136">一旦组未暂停，部署将根据下面的计划恢复。</span><span class="sxs-lookup"><span data-stu-id="e3af9-136">Once the groups are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="e3af9-137">此部署过程适用于功能和质量更新，尽管每个的时间线各不相同。</span><span class="sxs-lookup"><span data-stu-id="e3af9-137">This deployment process applies to both feature and quality updates, though the timeline varies for each.</span></span>




<table>
<tr><th colspan="5"><span data-ttu-id="e3af9-138">更新部署设置</span><span class="sxs-lookup"><span data-stu-id="e3af9-138">Update deployment settings</span></span></th></tr>
<tr><th><span data-ttu-id="e3af9-139">更新类型</span><span class="sxs-lookup"><span data-stu-id="e3af9-139">Update type</span></span></th><th><span data-ttu-id="e3af9-140">测试</span><span class="sxs-lookup"><span data-stu-id="e3af9-140">Test</span></span></th><th><span data-ttu-id="e3af9-141">First</span><span class="sxs-lookup"><span data-stu-id="e3af9-141">First</span></span></th><th><span data-ttu-id="e3af9-142">快速</span><span class="sxs-lookup"><span data-stu-id="e3af9-142">Fast</span></span></th><th><span data-ttu-id="e3af9-143">宽泛</span><span class="sxs-lookup"><span data-stu-id="e3af9-143">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="e3af9-144">操作系统的质量更新</span><span class="sxs-lookup"><span data-stu-id="e3af9-144">Quality updates for operating system</span></span></td><td><span data-ttu-id="e3af9-145">0天</span><span class="sxs-lookup"><span data-stu-id="e3af9-145">0 days</span></span></td><td><span data-ttu-id="e3af9-146">0天</span><span class="sxs-lookup"><span data-stu-id="e3af9-146">0 days</span></span></td><td><span data-ttu-id="e3af9-147">0天</span><span class="sxs-lookup"><span data-stu-id="e3af9-147">0 days</span></span></td><td><span data-ttu-id="e3af9-148">3 天</span><span class="sxs-lookup"><span data-stu-id="e3af9-148">3 days</span></span></td></tr>
<tr><td><span data-ttu-id="e3af9-149">操作系统的功能更新</span><span class="sxs-lookup"><span data-stu-id="e3af9-149">Feature updates for operating system</span></span></td><td><span data-ttu-id="e3af9-150">0天</span><span class="sxs-lookup"><span data-stu-id="e3af9-150">0 days</span></span></td><td><span data-ttu-id="e3af9-151">30 天</span><span class="sxs-lookup"><span data-stu-id="e3af9-151">30 days</span></span></td><td><span data-ttu-id="e3af9-152">60 天</span><span class="sxs-lookup"><span data-stu-id="e3af9-152">60 days</span></span></td><td><span data-ttu-id="e3af9-153">90 天</span><span class="sxs-lookup"><span data-stu-id="e3af9-153">90 days</span></span></td></tr>
<tr><td><span data-ttu-id="e3af9-154">驱动程序/固件</span><span class="sxs-lookup"><span data-stu-id="e3af9-154">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="e3af9-155">遵循质量更新计划</span><span class="sxs-lookup"><span data-stu-id="e3af9-155">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="e3af9-156">反病毒定义</span><span class="sxs-lookup"><span data-stu-id="e3af9-156">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="e3af9-157">更新每个扫描</span><span class="sxs-lookup"><span data-stu-id="e3af9-157">Updated with each scan</span></span></td></tr>
<tr><td><span data-ttu-id="e3af9-158">Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="e3af9-158">Office 365 ProPlus</span></span></td><td colspan="4"><span data-ttu-id="e3af9-159">遵循 Office 的每月频道</span><span class="sxs-lookup"><span data-stu-id="e3af9-159">Follows Office's Monthly Channel</span></span>
</table>

<span data-ttu-id="e3af9-160">有关 Office 365 专业增强版的每月频道的详细信息，请参阅[office 365 专业增强版更新通道概述](https://docs.microsoft.com/deployoffice/overview-of-update-channels-for-office-365-proplus)。</span><span class="sxs-lookup"><span data-stu-id="e3af9-160">For more information about the Monthly Channel for Office 365 ProPlus, see [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-of-update-channels-for-office-365-proplus).</span></span>

>[!NOTE]
><span data-ttu-id="e3af9-161">这些延期时段特意旨在确保所有用户的高安全性和性能标准。</span><span class="sxs-lookup"><span data-stu-id="e3af9-161">These deferral periods are intentionally designed to ensure high security and performance standards for all users.</span></span> <span data-ttu-id="e3af9-162">此外，根据在所有 Microsoft 托管桌面设备上收集的数据以及更新的不同范围和影响，Microsoft 托管桌面保留了灵活性，以便在 ad 上修改任意和所有部署组的上述延期时段的长度hoc。</span><span class="sxs-lookup"><span data-stu-id="e3af9-162">Furthermore, based on data gathered across all Microsoft Managed Desktop devices and the varying scope and impact of updates, Microsoft Managed Desktop reserves flexibility to modify the length of the above deferral periods for any and all deployment groups on an ad hoc basis.</span></span>
>
><span data-ttu-id="e3af9-163">Microsoft 托管桌面对每个 Windows 功能版本执行独立评估，以评估其对托管租户的必要性和有用性。</span><span class="sxs-lookup"><span data-stu-id="e3af9-163">Microsoft Managed Desktop conducts an independent assessment of each Windows feature release to evaluate its necessity and usefulness to its managed tenants.</span></span> <span data-ttu-id="e3af9-164">因此，Microsoft 托管桌面可能会或可能不会部署所有 Windows 功能更新。</span><span class="sxs-lookup"><span data-stu-id="e3af9-164">Consequently, Microsoft Managed Desktop might or might not deploy all Windows feature updates.</span></span> 

## <a name="windows-insider-program"></a><span data-ttu-id="e3af9-165">Windows 预览体验计划</span><span class="sxs-lookup"><span data-stu-id="e3af9-165">Windows Insider Program</span></span>

<span data-ttu-id="e3af9-166">Microsoft 托管桌面不支持属于 Windows 预览体验计划的设备。</span><span class="sxs-lookup"><span data-stu-id="e3af9-166">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program.</span></span> <span data-ttu-id="e3af9-167">Windows 预览体验计划用于验证预发布的 Windows 软件，适用于非关键任务的设备。</span><span class="sxs-lookup"><span data-stu-id="e3af9-167">The Windows Insider program is used to validate pre-release Windows software and is intended for devices that aren't mission critical.</span></span> <span data-ttu-id="e3af9-168">虽然这是一个重要的 Microsoft 计划，但不适合在生产环境中进行广泛的部署。</span><span class="sxs-lookup"><span data-stu-id="e3af9-168">While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="e3af9-169">使用 Windows 有问必答版本找到的任何设备都可能会加入到测试组中，并将从 Microsoft 托管桌面的更新服务级别协议和最终用户支持中免除。</span><span class="sxs-lookup"><span data-stu-id="e3af9-169">Any devices found with Windows Insider builds might be put into the Test group and will be exempt from update service level agreements and end-user support from Microsoft Managed Desktop.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="e3af9-170">带宽管理</span><span class="sxs-lookup"><span data-stu-id="e3af9-170">Bandwidth management</span></span>

<span data-ttu-id="e3af9-171">我们将[传递优化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)用于所有操作系统和驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="e3af9-171">We use [Delivery Optimization](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) for all operating system and driver updates.</span></span> <span data-ttu-id="e3af9-172">这样可通过在企业网络中查找来自对等方的更新来最大限度地减少 Windows Update service 中的下载大小。</span><span class="sxs-lookup"><span data-stu-id="e3af9-172">This minimizes the download size from the Windows Update service by seeking updates from peers within the corporate network.</span></span>


