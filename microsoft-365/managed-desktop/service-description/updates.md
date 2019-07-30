---
title: 如何在 Microsoft 托管桌面中处理更新
description: 将 Microsoft 托管桌面保持最新状态是速度和稳定性的平衡。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7709779c73293a4523bf3cc381d0b59f7fbca325
ms.sourcegitcommit: d137cb1bd67a79d8af84357dc156824830d35aa7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2019
ms.locfileid: "35924865"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="51539-104">如何在 Microsoft 托管桌面中处理更新</span><span class="sxs-lookup"><span data-stu-id="51539-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="51539-105">Microsoft 托管桌面将所有设备连接到基于云的新式基础结构。</span><span class="sxs-lookup"><span data-stu-id="51539-105">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure.</span></span> <span data-ttu-id="51539-106">保持 Windows、Office、驱动程序、固件和 Microsoft Store for Business 应用程序更新最新是速度和稳定性的平衡。</span><span class="sxs-lookup"><span data-stu-id="51539-106">Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business application updates up to date is a balance of speed and stability.</span></span> <span data-ttu-id="51539-107">部署组将用于确保以安全的方式推出 OS 和策略。</span><span class="sxs-lookup"><span data-stu-id="51539-107">Deployment groups will be used to ensure OS and policies are rolled out in a safe manner.</span></span> 

<span data-ttu-id="51539-108">由 Microsoft 发布的更新是累积的, 并被分类为质量或功能更新。</span><span class="sxs-lookup"><span data-stu-id="51539-108">Updates released by Microsoft are cumulative and are categorized as quality or feature updates.</span></span>
<span data-ttu-id="51539-109">有关详细信息, 请参阅[Windows update For Business: 更新类型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)。</span><span class="sxs-lookup"><span data-stu-id="51539-109">For more information, see [Windows Update for Business: Update types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types).</span></span> 

## <a name="update-groups"></a><span data-ttu-id="51539-110">更新组</span><span class="sxs-lookup"><span data-stu-id="51539-110">Update groups</span></span>

<span data-ttu-id="51539-111">Microsoft 托管桌面使用四个 Azure AD 组管理更新:</span><span class="sxs-lookup"><span data-stu-id="51539-111">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="51539-112">**测试**: 用于验证 Microsoft 托管桌面策略更改、OS 更新、功能更新和其他已推送到租户的更改。</span><span class="sxs-lookup"><span data-stu-id="51539-112">**Test**: Used to validate Microsoft Managed Desktop policy changes, OS updates, feature updates, and other changes pushed to the tenant.</span></span> <span data-ttu-id="51539-113">测试组中不应放置任何最终用户。</span><span class="sxs-lookup"><span data-stu-id="51539-113">There should not be any end users placed in the test group.</span></span> <span data-ttu-id="51539-114">测试组不受任何已建立的 Sla 和最终用户支持的支持。</span><span class="sxs-lookup"><span data-stu-id="51539-114">The test group is exempt from any established SLAs and end user support.</span></span> <span data-ttu-id="51539-115">此组可用于验证应用程序与新策略或操作系统更改的兼容性。</span><span class="sxs-lookup"><span data-stu-id="51539-115">This group is available for use to validate compatibility of applications with new Policy or OS Changes.</span></span>  
- <span data-ttu-id="51539-116">**First**: 包含早期的软件采用者和设备, 它们可能受预发布更新的制约。</span><span class="sxs-lookup"><span data-stu-id="51539-116">**First**: Contains early software adopters and devices that could be subject to pre-release updates.</span></span> <span data-ttu-id="51539-117">如果存在测试环中测试期间未涵盖的方案, 则此组中的设备可能会遇到中断。</span><span class="sxs-lookup"><span data-stu-id="51539-117">Devices in this group might experience outages if there are scenarios which were not covered during testing in the test ring.</span></span>
- <span data-ttu-id="51539-118">**Fast**: 按稳定性对速度进行优先级划分。</span><span class="sxs-lookup"><span data-stu-id="51539-118">**Fast**: Prioritizes speed over stability.</span></span> <span data-ttu-id="51539-119">用于在向广泛组提供质量问题之前检测质量问题。</span><span class="sxs-lookup"><span data-stu-id="51539-119">Useful for detecting quality issues before they are offered to the Broad group.</span></span> <span data-ttu-id="51539-120">此组可用作验证的下一层, 但通常比测试和第一组更稳定。</span><span class="sxs-lookup"><span data-stu-id="51539-120">This group serves as a next layer of validation but is generally more stable than the Test and First groups.</span></span> 
- <span data-ttu-id="51539-121">**广泛**: 最后一个组具有可用的功能和质量更新。</span><span class="sxs-lookup"><span data-stu-id="51539-121">**Broad**: Last group to have feature and quality updates available.</span></span> <span data-ttu-id="51539-122">此组包含租户中的大多数用户, 因此在部署过程中比速度更有利于稳定性。</span><span class="sxs-lookup"><span data-stu-id="51539-122">This group contains the majority of users in the tenant, and therefore favors stability over speed in deployment.</span></span> <span data-ttu-id="51539-123">应在此完成应用程序的测试, 因为环境最稳定。</span><span class="sxs-lookup"><span data-stu-id="51539-123">Testing of apps should be done here as the environment is most stable.</span></span> 

<span data-ttu-id="51539-124">有关这些部署组的详细信息角色和职责, 请参阅[Microsoft 托管桌面角色和职责](../intro/roles-and-responsibilities.md)</span><span class="sxs-lookup"><span data-stu-id="51539-124">For more information roles and responsibilities with these deployment groups, see [Microsoft Managed Desktop Roles and responsibilities](../intro/roles-and-responsibilities.md)</span></span>

<span data-ttu-id="51539-125">更新部署的工作原理:</span><span class="sxs-lookup"><span data-stu-id="51539-125">How update deployment works:</span></span>
- <span data-ttu-id="51539-126">Microsoft 托管桌面根据下面指定的计划, 部署新的功能或质量更新。</span><span class="sxs-lookup"><span data-stu-id="51539-126">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="51539-127">在部署过程中, Microsoft 托管的桌面监视器会针对故障或中断 (基于诊断数据信号和最终用户支持系统) 的迹象进行标记。</span><span class="sxs-lookup"><span data-stu-id="51539-127">During deployment, Microsoft Managed Desktop monitors for signs of failure or disruption (based on diagnostic data signals and end-user support system).</span></span> <span data-ttu-id="51539-128">如果检测到任何其他组, 则会立即暂停部署到当前和将来的所有组。</span><span class="sxs-lookup"><span data-stu-id="51539-128">If any are detected, then the deployment to all current and future groups is immediately paused.</span></span>
    - <span data-ttu-id="51539-129">示例: 如果在将质量更新部署到第一个组时发现了问题, 则在解决问题之前, 先将部署更新到第一个、快速和广泛的过程将会暂停。</span><span class="sxs-lookup"><span data-stu-id="51539-129">Example: if an issue is discovered while deploying a quality update to the First group, then update deployments to First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="51539-130">可以通过在 Microsoft 托管桌面 IT 管理门户中存档票证来报告兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="51539-130">Compatibility issues can be reported by filing a ticket in the Microsoft Managed Desktop IT Admin portal.</span></span>
- <span data-ttu-id="51539-131">功能和质量更新是独立暂停的。</span><span class="sxs-lookup"><span data-stu-id="51539-131">Feature and quality updates are paused independently.</span></span> <span data-ttu-id="51539-132">默认情况下, Pause 将对35天生效, 但可以根据问题是否修正来进行缩减或扩展。</span><span class="sxs-lookup"><span data-stu-id="51539-132">Pause is in effect for 35 days by default, but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="51539-133">一旦组未暂停, 部署将根据下面的计划恢复。</span><span class="sxs-lookup"><span data-stu-id="51539-133">Once the groups are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="51539-134">此部署过程适用于功能和质量更新, 尽管每个的时间线各不相同。</span><span class="sxs-lookup"><span data-stu-id="51539-134">This deployment process applies to both feature and quality updates, though the timeline varies for each.</span></span>

<table>
<tr><th colspan="5"><span data-ttu-id="51539-135">更新部署设置</span><span class="sxs-lookup"><span data-stu-id="51539-135">Update deployment settings</span></span></th></tr>
<tr><th><span data-ttu-id="51539-136">更新类型</span><span class="sxs-lookup"><span data-stu-id="51539-136">Update type</span></span></th><th><span data-ttu-id="51539-137">测试</span><span class="sxs-lookup"><span data-stu-id="51539-137">Test</span></span></th><th><span data-ttu-id="51539-138">First</span><span class="sxs-lookup"><span data-stu-id="51539-138">First</span></span></th><th><span data-ttu-id="51539-139">快速</span><span class="sxs-lookup"><span data-stu-id="51539-139">Fast</span></span></th><th><span data-ttu-id="51539-140">宽泛</span><span class="sxs-lookup"><span data-stu-id="51539-140">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="51539-141">操作系统的质量更新</span><span class="sxs-lookup"><span data-stu-id="51539-141">Quality updates for operating system</span></span></td><td><span data-ttu-id="51539-142">0天</span><span class="sxs-lookup"><span data-stu-id="51539-142">0 days</span></span></td><td><span data-ttu-id="51539-143">0天</span><span class="sxs-lookup"><span data-stu-id="51539-143">0 days</span></span></td><td><span data-ttu-id="51539-144">0天</span><span class="sxs-lookup"><span data-stu-id="51539-144">0 days</span></span></td><td><span data-ttu-id="51539-145">3 天</span><span class="sxs-lookup"><span data-stu-id="51539-145">3 days</span></span></td></tr>
<tr><td><span data-ttu-id="51539-146">操作系统的功能更新</span><span class="sxs-lookup"><span data-stu-id="51539-146">Feature updates for operating system</span></span></td><td><span data-ttu-id="51539-147">0天</span><span class="sxs-lookup"><span data-stu-id="51539-147">0 days</span></span></td><td><span data-ttu-id="51539-148">30 天</span><span class="sxs-lookup"><span data-stu-id="51539-148">30 days</span></span></td><td><span data-ttu-id="51539-149">60 天</span><span class="sxs-lookup"><span data-stu-id="51539-149">60 days</span></span></td><td><span data-ttu-id="51539-150">90 天</span><span class="sxs-lookup"><span data-stu-id="51539-150">90 days</span></span></td></tr>
<tr><td><span data-ttu-id="51539-151">驱动程序/固件</span><span class="sxs-lookup"><span data-stu-id="51539-151">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="51539-152">遵循质量更新计划</span><span class="sxs-lookup"><span data-stu-id="51539-152">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="51539-153">反病毒定义</span><span class="sxs-lookup"><span data-stu-id="51539-153">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="51539-154">更新每个扫描</span><span class="sxs-lookup"><span data-stu-id="51539-154">Updated with each scan</span></span></td></tr>
</table>

>[!NOTE]
><span data-ttu-id="51539-155">这些延期时段特意旨在确保所有用户的高安全性和性能标准。</span><span class="sxs-lookup"><span data-stu-id="51539-155">These deferral periods are intentionally designed to ensure high security and performance standards for all users.</span></span> <span data-ttu-id="51539-156">此外, 根据在所有 Microsoft 托管桌面设备上收集的数据以及更新的不同范围和影响, Microsoft 托管桌面保留了灵活性, 以便在 ad 上修改任意和所有部署组的上述延期时段的长度hoc。</span><span class="sxs-lookup"><span data-stu-id="51539-156">Furthermore, based on data gathered across all Microsoft Managed Desktop devices and the varying scope and impact of updates, Microsoft Managed Desktop reserves flexibility to modify the length of the above deferral periods for any and all deployment groups on an ad hoc basis.</span></span>
>
><span data-ttu-id="51539-157">Microsoft 托管桌面对每个 Windows 功能版本执行独立评估, 以评估其对托管租户的必要性和有用性。</span><span class="sxs-lookup"><span data-stu-id="51539-157">Microsoft Managed Desktop conducts an independent assessment of each Windows feature release to evaluate its necessity and usefulness to its managed tenants.</span></span> <span data-ttu-id="51539-158">因此, Microsoft 托管桌面可能会或可能不会部署所有 Windows 功能更新。</span><span class="sxs-lookup"><span data-stu-id="51539-158">Consequently, Microsoft Managed Desktop might or might not deploy all Windows feature updates.</span></span> 

## <a name="windows-insider-program"></a><span data-ttu-id="51539-159">Windows 预览体验计划</span><span class="sxs-lookup"><span data-stu-id="51539-159">Windows Insider Program</span></span>

<span data-ttu-id="51539-160">Microsoft 托管桌面不支持属于 Windows 预览体验计划的设备。</span><span class="sxs-lookup"><span data-stu-id="51539-160">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program.</span></span> <span data-ttu-id="51539-161">Windows 预览体验计划用于验证预发布的 Windows 软件, 适用于非关键设备。</span><span class="sxs-lookup"><span data-stu-id="51539-161">The Windows Insider program is used to validate pre-release Windows software and is intended for non-mission-critical devices.</span></span> <span data-ttu-id="51539-162">虽然这是一个重要的 Microsoft 计划, 但不适合在生产环境中进行广泛的部署。</span><span class="sxs-lookup"><span data-stu-id="51539-162">While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="51539-163">在 Windows 有问必答版本中找到的任何设备都可能放入测试组中, 并将从 Microsoft 托管桌面的更新服务级别协议 (Sla) 和最终用户支持中免除。</span><span class="sxs-lookup"><span data-stu-id="51539-163">Any devices found with Windows Insider builds might be put into the Test group and will be exempt from update service level agreements (SLAs) and end user support from Microsoft Managed Desktop.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="51539-164">带宽管理</span><span class="sxs-lookup"><span data-stu-id="51539-164">Bandwidth management</span></span>

<span data-ttu-id="51539-165">传递优化用于所有操作系统和驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="51539-165">Delivery optimization is used for all operating system and driver updates.</span></span> <span data-ttu-id="51539-166">通过从企业网络中的对等方处查找更新, 可最大限度地减少 Windows Update service 中的下载大小。</span><span class="sxs-lookup"><span data-stu-id="51539-166">It minimizes the download size from the Windows Update service by seeking updates from peers within the corporate network.</span></span>


