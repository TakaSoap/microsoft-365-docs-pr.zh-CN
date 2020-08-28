---
title: 如何在 Microsoft 托管桌面中处理更新
description: 将 Microsoft 托管桌面保持最新是速度和稳定性的平衡。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1349b58bdd6243b05323f14197e0ad92c1fc0d7b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289491"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="ffc95-104">如何在 Microsoft 托管桌面中处理更新</span><span class="sxs-lookup"><span data-stu-id="ffc95-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="ffc95-105">Microsoft 托管桌面将所有设备连接到基于云的新式基础结构。</span><span class="sxs-lookup"><span data-stu-id="ffc95-105">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure.</span></span> <span data-ttu-id="ffc95-106">将 Windows、Office、驱动程序、固件和 Microsoft Store for Business 应用程序保持为最新是速度和稳定性的平衡。</span><span class="sxs-lookup"><span data-stu-id="ffc95-106">Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business applications up to date is a balance of speed and stability.</span></span> <span data-ttu-id="ffc95-107">将使用部署组来确保操作系统更新和策略以安全的方式进行分发。</span><span class="sxs-lookup"><span data-stu-id="ffc95-107">Deployment groups will be used to ensure operating system updates and policies are rolled out in a safe manner.</span></span> <span data-ttu-id="ffc95-108">有关此操作的详细信息，请参阅视频 [Microsoft 托管桌面更改和发布过程](https://www.microsoft.com/videoplayer/embed/RE4mWqP)。</span><span class="sxs-lookup"><span data-stu-id="ffc95-108">For more about this, see the video [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).</span></span>

<span data-ttu-id="ffc95-109">由 Microsoft 发布的更新是累积的，并被分类为质量或功能更新。</span><span class="sxs-lookup"><span data-stu-id="ffc95-109">Updates released by Microsoft are cumulative and are categorized as quality or feature updates.</span></span>
<span data-ttu-id="ffc95-110">有关详细信息，请参阅 [Windows update For Business：更新类型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)。</span><span class="sxs-lookup"><span data-stu-id="ffc95-110">For more information, see [Windows Update for Business: Update types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types).</span></span> 

## <a name="update-groups"></a><span data-ttu-id="ffc95-111">更新组</span><span class="sxs-lookup"><span data-stu-id="ffc95-111">Update groups</span></span>

<span data-ttu-id="ffc95-112">Microsoft 托管桌面使用四个 Azure AD 组管理更新：</span><span class="sxs-lookup"><span data-stu-id="ffc95-112">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="ffc95-113">**测试**：用于验证 Microsoft 托管桌面策略更改、操作系统更新、功能更新以及推送到租户的其他更改。</span><span class="sxs-lookup"><span data-stu-id="ffc95-113">**Test**: Used to validate Microsoft Managed Desktop policy changes, operating system updates, feature updates, and other changes pushed to the tenant.</span></span> <span data-ttu-id="ffc95-114">不应在测试组中放置任何用户。</span><span class="sxs-lookup"><span data-stu-id="ffc95-114">There should not be any users placed in the test group.</span></span> <span data-ttu-id="ffc95-115">测试组不受任何已建立的服务级别协议和用户支持的免除。</span><span class="sxs-lookup"><span data-stu-id="ffc95-115">The test group is exempt from any established service level agreements and user support.</span></span> <span data-ttu-id="ffc95-116">此组可用于验证应用程序与新策略或操作系统更改的兼容性。</span><span class="sxs-lookup"><span data-stu-id="ffc95-116">This group is available for use to validate compatibility of applications with new policy or operating system changes.</span></span>  
- <span data-ttu-id="ffc95-117">**First**：包含早期的软件采用者和设备，它们可能受预发布更新的制约。</span><span class="sxs-lookup"><span data-stu-id="ffc95-117">**First**: Contains early software adopters and devices that could be subject to pre-release updates.</span></span> <span data-ttu-id="ffc95-118">如果存在测试环中测试期间未涵盖的方案，则此组中的设备可能会遇到中断。</span><span class="sxs-lookup"><span data-stu-id="ffc95-118">Devices in this group might experience outages if there are scenarios which were not covered during testing in the test ring.</span></span>
- <span data-ttu-id="ffc95-119">**Fast**：按稳定性对速度进行优先级划分。</span><span class="sxs-lookup"><span data-stu-id="ffc95-119">**Fast**: Prioritizes speed over stability.</span></span> <span data-ttu-id="ffc95-120">用于在向广泛组提供质量问题之前检测质量问题。</span><span class="sxs-lookup"><span data-stu-id="ffc95-120">Useful for detecting quality issues before they are offered to the Broad group.</span></span> <span data-ttu-id="ffc95-121">此组可用作验证的下一层，但通常比测试和第一组更稳定。</span><span class="sxs-lookup"><span data-stu-id="ffc95-121">This group serves as a next layer of validation but is generally more stable than the Test and First groups.</span></span> 
- <span data-ttu-id="ffc95-122">**广泛**：最后一个组具有可用的功能和质量更新。</span><span class="sxs-lookup"><span data-stu-id="ffc95-122">**Broad**: Last group to have feature and quality updates available.</span></span> <span data-ttu-id="ffc95-123">此组包含租户中的大多数用户，因此在部署过程中比速度更有利于稳定性。</span><span class="sxs-lookup"><span data-stu-id="ffc95-123">This group contains the majority of users in the tenant, and therefore favors stability over speed in deployment.</span></span> <span data-ttu-id="ffc95-124">应在此完成应用程序的测试，因为环境最稳定。</span><span class="sxs-lookup"><span data-stu-id="ffc95-124">Testing of apps should be done here as the environment is most stable.</span></span> 

> [!NOTE]
> <span data-ttu-id="ffc95-125">如果需要将用户移动到其他更新组，请提交支持请求。</span><span class="sxs-lookup"><span data-stu-id="ffc95-125">If you need to move a user to a different update group, submit a support request.</span></span> <span data-ttu-id="ffc95-126">有关提交支持请求的详细信息，请参阅 [支持 Microsoft 托管桌面](support.md) 。</span><span class="sxs-lookup"><span data-stu-id="ffc95-126">See [Support for Microsoft Managed Desktop](support.md) for more information on submitting support requests.</span></span> <span data-ttu-id="ffc95-127">如果您自己移动用户，移动将会恢复。</span><span class="sxs-lookup"><span data-stu-id="ffc95-127">If you move a user yourself, the move will be reverted.</span></span>

<span data-ttu-id="ffc95-128">有关这些部署组的详细信息角色和职责，请参阅 [Microsoft 托管桌面角色和职责](../intro/roles-and-responsibilities.md)</span><span class="sxs-lookup"><span data-stu-id="ffc95-128">For more information roles and responsibilities with these deployment groups, see [Microsoft Managed Desktop Roles and responsibilities](../intro/roles-and-responsibilities.md)</span></span>

<span data-ttu-id="ffc95-129">更新部署的工作原理：</span><span class="sxs-lookup"><span data-stu-id="ffc95-129">How update deployment works:</span></span>
- <span data-ttu-id="ffc95-130">Microsoft 托管桌面根据下面指定的计划，部署新的功能或质量更新。</span><span class="sxs-lookup"><span data-stu-id="ffc95-130">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="ffc95-131">在部署过程中，Microsoft 托管的桌面监视器根据诊断数据和用户支持系统) 的故障或中断 (的迹象。</span><span class="sxs-lookup"><span data-stu-id="ffc95-131">During deployment, Microsoft Managed Desktop monitors for signs of failure or disruption (based on diagnostic data and the user support system).</span></span> <span data-ttu-id="ffc95-132">如果检测到任何其他组，则会立即暂停部署到当前和将来的所有组。</span><span class="sxs-lookup"><span data-stu-id="ffc95-132">If any are detected, then the deployment to all current and future groups is immediately paused.</span></span>
    - <span data-ttu-id="ffc95-133">示例：如果在将质量更新部署到第一个组时发现了问题，则在解决问题之前，先将部署更新到第一个、快速和广泛的过程将会暂停。</span><span class="sxs-lookup"><span data-stu-id="ffc95-133">Example: if an issue is discovered while deploying a quality update to the First group, then update deployments to First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="ffc95-134">可以通过在 Microsoft 托管桌面管理门户中存档票证来报告兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="ffc95-134">Compatibility issues can be reported by filing a ticket in the Microsoft Managed Desktop Admin portal.</span></span>
- <span data-ttu-id="ffc95-135">功能和质量更新是独立暂停的。</span><span class="sxs-lookup"><span data-stu-id="ffc95-135">Feature and quality updates are paused independently.</span></span> <span data-ttu-id="ffc95-136">默认情况下，Pause 将对35天生效，但可以根据问题是否修正来进行缩减或扩展。</span><span class="sxs-lookup"><span data-stu-id="ffc95-136">Pause is in effect for 35 days by default, but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="ffc95-137">一旦组未暂停，部署将根据下面的计划恢复。</span><span class="sxs-lookup"><span data-stu-id="ffc95-137">Once the groups are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="ffc95-138">此部署过程适用于功能和质量更新，尽管每个的时间线各不相同。</span><span class="sxs-lookup"><span data-stu-id="ffc95-138">This deployment process applies to both feature and quality updates, though the timeline varies for each.</span></span>




<table>
<tr><th colspan="5"><span data-ttu-id="ffc95-139">更新部署设置</span><span class="sxs-lookup"><span data-stu-id="ffc95-139">Update deployment settings</span></span></th></tr>
<tr><th><span data-ttu-id="ffc95-140">更新类型</span><span class="sxs-lookup"><span data-stu-id="ffc95-140">Update type</span></span></th><th><span data-ttu-id="ffc95-141">测试</span><span class="sxs-lookup"><span data-stu-id="ffc95-141">Test</span></span></th><th><span data-ttu-id="ffc95-142">First</span><span class="sxs-lookup"><span data-stu-id="ffc95-142">First</span></span></th><th><span data-ttu-id="ffc95-143">快速</span><span class="sxs-lookup"><span data-stu-id="ffc95-143">Fast</span></span></th><th><span data-ttu-id="ffc95-144">宽泛</span><span class="sxs-lookup"><span data-stu-id="ffc95-144">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="ffc95-145">操作系统的质量更新</span><span class="sxs-lookup"><span data-stu-id="ffc95-145">Quality updates for operating system</span></span></td><td><span data-ttu-id="ffc95-146">0天</span><span class="sxs-lookup"><span data-stu-id="ffc95-146">0 days</span></span></td><td><span data-ttu-id="ffc95-147">0天</span><span class="sxs-lookup"><span data-stu-id="ffc95-147">0 days</span></span></td><td><span data-ttu-id="ffc95-148">0天</span><span class="sxs-lookup"><span data-stu-id="ffc95-148">0 days</span></span></td><td><span data-ttu-id="ffc95-149">3 天</span><span class="sxs-lookup"><span data-stu-id="ffc95-149">3 days</span></span></td></tr>
<tr><td><span data-ttu-id="ffc95-150">操作系统的功能更新</span><span class="sxs-lookup"><span data-stu-id="ffc95-150">Feature updates for operating system</span></span></td><td><span data-ttu-id="ffc95-151">0天</span><span class="sxs-lookup"><span data-stu-id="ffc95-151">0 days</span></span></td><td><span data-ttu-id="ffc95-152">30 天</span><span class="sxs-lookup"><span data-stu-id="ffc95-152">30 days</span></span></td><td><span data-ttu-id="ffc95-153">60 天</span><span class="sxs-lookup"><span data-stu-id="ffc95-153">60 days</span></span></td><td><span data-ttu-id="ffc95-154">90 天</span><span class="sxs-lookup"><span data-stu-id="ffc95-154">90 days</span></span></td></tr>
<tr><td><span data-ttu-id="ffc95-155">驱动程序/固件</span><span class="sxs-lookup"><span data-stu-id="ffc95-155">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="ffc95-156">遵循质量更新计划</span><span class="sxs-lookup"><span data-stu-id="ffc95-156">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="ffc95-157">反病毒定义</span><span class="sxs-lookup"><span data-stu-id="ffc95-157">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="ffc95-158">更新每个扫描</span><span class="sxs-lookup"><span data-stu-id="ffc95-158">Updated with each scan</span></span></td></tr>
<tr><td><span data-ttu-id="ffc95-159">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="ffc95-159">Microsoft 365 Apps for enterprise</span></span></td><td colspan="4"><span data-ttu-id="ffc95-160">遵循 Office 的当前频道</span><span class="sxs-lookup"><span data-stu-id="ffc95-160">Follows Office's Current Channel</span></span>
</table>

<span data-ttu-id="ffc95-161">有关适用于企业的 Microsoft 365 应用的当前频道的详细信息，请参阅 [microsoft 365 应用的更新通道概述](https://docs.microsoft.com/deployoffice/overview-update-channels)。</span><span class="sxs-lookup"><span data-stu-id="ffc95-161">For more information about Current Channel for Microsoft 365 Apps for enterprise, see [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span>

>[!NOTE]
><span data-ttu-id="ffc95-162">这些延期时段特意旨在确保所有用户的高安全性和性能标准。</span><span class="sxs-lookup"><span data-stu-id="ffc95-162">These deferral periods are intentionally designed to ensure high security and performance standards for all users.</span></span> <span data-ttu-id="ffc95-163">此外，根据在所有 Microsoft 托管桌面设备上收集的数据以及更新的不同范围和影响，Microsoft 托管桌面保留了灵活性，以针对任意和所有部署组（临时）修改上述延期时段的长度。</span><span class="sxs-lookup"><span data-stu-id="ffc95-163">Furthermore, based on data gathered across all Microsoft Managed Desktop devices and the varying scope and impact of updates, Microsoft Managed Desktop reserves flexibility to modify the length of the above deferral periods for any and all deployment groups on an ad hoc basis.</span></span>
>
><span data-ttu-id="ffc95-164">Microsoft 托管桌面对每个 Windows 功能版本执行独立评估，以评估其对托管租户的必要性和有用性。</span><span class="sxs-lookup"><span data-stu-id="ffc95-164">Microsoft Managed Desktop conducts an independent assessment of each Windows feature release to evaluate its necessity and usefulness to its managed tenants.</span></span> <span data-ttu-id="ffc95-165">因此，Microsoft 托管桌面可能会或可能不会部署所有 Windows 功能更新。</span><span class="sxs-lookup"><span data-stu-id="ffc95-165">Consequently, Microsoft Managed Desktop might or might not deploy all Windows feature updates.</span></span> 

## <a name="windows-insider-program"></a><span data-ttu-id="ffc95-166">Windows 预览体验计划</span><span class="sxs-lookup"><span data-stu-id="ffc95-166">Windows Insider Program</span></span>

<span data-ttu-id="ffc95-167">Microsoft 托管桌面不支持属于 Windows 预览体验计划的设备。</span><span class="sxs-lookup"><span data-stu-id="ffc95-167">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program.</span></span> <span data-ttu-id="ffc95-168">Windows 预览体验计划用于验证预发布的 Windows 软件，适用于非关键任务的设备。</span><span class="sxs-lookup"><span data-stu-id="ffc95-168">The Windows Insider program is used to validate pre-release Windows software and is intended for devices that aren't mission critical.</span></span> <span data-ttu-id="ffc95-169">虽然这是一个重要的 Microsoft 计划，但不适合在生产环境中进行广泛的部署。</span><span class="sxs-lookup"><span data-stu-id="ffc95-169">While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="ffc95-170">使用 Windows 有问必答版本找到的任何设备都可能会进入测试组，并将从 Microsoft 托管桌面的更新服务级别协议和用户支持中免除。</span><span class="sxs-lookup"><span data-stu-id="ffc95-170">Any devices found with Windows Insider builds might be put into the Test group and will be exempt from update service level agreements and user support from Microsoft Managed Desktop.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="ffc95-171">带宽管理</span><span class="sxs-lookup"><span data-stu-id="ffc95-171">Bandwidth management</span></span>

<span data-ttu-id="ffc95-172">我们将 [传递优化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) 用于所有操作系统和驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="ffc95-172">We use [Delivery Optimization](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) for all operating system and driver updates.</span></span> <span data-ttu-id="ffc95-173">这样可通过在企业网络中查找来自对等方的更新来最大限度地减少 Windows Update service 中的下载大小。</span><span class="sxs-lookup"><span data-stu-id="ffc95-173">This minimizes the download size from the Windows Update service by seeking updates from peers within the corporate network.</span></span>


