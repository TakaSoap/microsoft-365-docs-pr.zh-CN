---
title: Microsoft 托管桌面如何处理更新
description: 及时更新 Microsoft 托管桌面是速度和稳定性的平衡。
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 513e03b7d703e0a9f78281ddac764d8a29ed5c8f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865505"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="559a7-104">Microsoft 托管桌面如何处理更新</span><span class="sxs-lookup"><span data-stu-id="559a7-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="559a7-p101">Microsoft 托管桌面连接到基于云的现代基础结构的所有设备。确保业务应用程序更新的 Windows、 Office、 驱动程序、 固件和 Microsoft 存储最新是速度和稳定性的平衡。部署在拨打将用于确保 OS 和策略的推出以安全方式。</span><span class="sxs-lookup"><span data-stu-id="559a7-p101">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure. Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business application updates up to date is a balance of speed and stability. Deployment rings will be used to ensure OS and policies are rolled out in a safe manner.</span></span> 

## <a name="update-rings"></a><span data-ttu-id="559a7-108">更新响铃</span><span class="sxs-lookup"><span data-stu-id="559a7-108">Update rings</span></span>

<span data-ttu-id="559a7-109">Microsoft 托管桌面使用四个 Azure AD 组来管理更新：</span><span class="sxs-lookup"><span data-stu-id="559a7-109">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="559a7-110">测试： 测试拨打仅用于测试和验证的客户租户中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="559a7-110">Test: The test ring is only designed for test and validation of changes made in the customer tenant.</span></span>  
- <span data-ttu-id="559a7-111">第一个： 首先被用于与愿意早期安装软件和采用某些预发布更新的有限的技术知识用户早期测试振铃。</span><span class="sxs-lookup"><span data-stu-id="559a7-111">First: First is intended to be an early test ring with limited tech savvy users that are willing to install software early and be subject to some pre-release updates.</span></span>
- <span data-ttu-id="559a7-p102">快速： fast 环是我们期望用户一大组。 此拨打的目标是以保持设备更新和安全与软件传递快速速度。</span><span class="sxs-lookup"><span data-stu-id="559a7-p102">Fast: The fast ring is where we would expect a large set of users.  The goal for this ring is to keep devices updated and secure with a quick pace of software delivery.</span></span>  
- <span data-ttu-id="559a7-p103">广泛： 慢环是平衡保守滚超出质量和功能的更新。 高质量的更新仍传送较快的速度，但不是立即。</span><span class="sxs-lookup"><span data-stu-id="559a7-p103">Broad: The slow ring is a balanced conservative roll out of quality and feature updates.  Quality updates are still delivered at a fast pace, but not immediately.</span></span> 

<span data-ttu-id="559a7-116">拨打系统中的更新被分类为质量，或更新的功能：</span><span class="sxs-lookup"><span data-stu-id="559a7-116">The updates in the ring system are categorized as quality, or feature updates:</span></span>
- <span data-ttu-id="559a7-p104">高质量的更新包括安全，critical、 和驱动程序更新。 这些是通常每月更新。</span><span class="sxs-lookup"><span data-stu-id="559a7-p104">Quality updates include security, critical, and driver updates.  These are usually monthly updates.</span></span> 
- <span data-ttu-id="559a7-119">功能更新包含不仅安全和质量修订，但也显著功能新增功能和更改;每年分号发布它们。</span><span class="sxs-lookup"><span data-stu-id="559a7-119">Feature updates contain not only security and quality revisions, but also significant feature additions and changes; they are released semi-annually.</span></span> 

<span data-ttu-id="559a7-120">拨打升级的工作原理：</span><span class="sxs-lookup"><span data-stu-id="559a7-120">How ring promotion works:</span></span>
- <span data-ttu-id="559a7-121">Microsoft 托管桌面部署新的功能或质量更新，将根据下面指定的计划。</span><span class="sxs-lookup"><span data-stu-id="559a7-121">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="559a7-122">在部署期间，Microsoft 托管桌面监视的故障或其他中断 （通过遥测信号和我们最终用户支持系统）; 迹象如果检测到任何已立即暂停部署到所有当前和将来响铃。</span><span class="sxs-lookup"><span data-stu-id="559a7-122">During deployment, Microsoft Managed Desktop monitors for signs of failure or other disruption (via telemetry signals and our end-user support system); if any are detected, then the deployment to all current and future rings is immediately paused.</span></span>
    - <span data-ttu-id="559a7-123">示例： 如果质量的更新部署到首次响铃时发现问题时，然后首先，Fast 和广泛将所有暂停解决该问题之前。</span><span class="sxs-lookup"><span data-stu-id="559a7-123">Example: if an issue is discovered while deploying a quality update to the First ring, then First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="559a7-124">兼容性问题可能会报告归档 Microsoft 托管桌面 IT 管理门户中的票证。</span><span class="sxs-lookup"><span data-stu-id="559a7-124">Compatibility issues may be reported by filing a ticket in the Microsoft Managed Desktop IT Admin portal.</span></span>
- <span data-ttu-id="559a7-p105">功能和质量更新独立暂停。 暂停实际上是默认情况下 35 天，但可减少或扩展具体取决于是否修正问题。</span><span class="sxs-lookup"><span data-stu-id="559a7-p105">Feature and quality updates are paused independently.  Pause is in effect for 35 days by default but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="559a7-127">未暂停响铃后，部署恢复根据以下计划。</span><span class="sxs-lookup"><span data-stu-id="559a7-127">Once the rings are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="559a7-128">此升级过程适用于功能和质量更新，但日程表会有所不同，每个。</span><span class="sxs-lookup"><span data-stu-id="559a7-128">This promotion process applies to both feature and quality updates, though the timeline varies for each.</span></span>

<table>
<tr><th colspan="5"><span data-ttu-id="559a7-129">拨打和延迟设置</span><span class="sxs-lookup"><span data-stu-id="559a7-129">Rings and deferral settings</span></span></th></tr>
<tr><th><span data-ttu-id="559a7-130">更新类型</span><span class="sxs-lookup"><span data-stu-id="559a7-130">Update type</span></span></th><th><span data-ttu-id="559a7-131">测试拨打</span><span class="sxs-lookup"><span data-stu-id="559a7-131">Test ring</span></span></th><th><span data-ttu-id="559a7-132">第一个</span><span class="sxs-lookup"><span data-stu-id="559a7-132">First</span></span></th><th><span data-ttu-id="559a7-133">快速</span><span class="sxs-lookup"><span data-stu-id="559a7-133">Fast</span></span></th><th><span data-ttu-id="559a7-134">广泛</span><span class="sxs-lookup"><span data-stu-id="559a7-134">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="559a7-135">高质量的操作系统的更新</span><span class="sxs-lookup"><span data-stu-id="559a7-135">Quality updates for operating system</span></span></td><td><span data-ttu-id="559a7-136">0 天</span><span class="sxs-lookup"><span data-stu-id="559a7-136">0 days</span></span></td><td><span data-ttu-id="559a7-137">0 天</span><span class="sxs-lookup"><span data-stu-id="559a7-137">0 days</span></span></td><td><span data-ttu-id="559a7-138">1 天</span><span class="sxs-lookup"><span data-stu-id="559a7-138">1 day</span></span></td><td><span data-ttu-id="559a7-139">5 天</span><span class="sxs-lookup"><span data-stu-id="559a7-139">5 days</span></span></td></tr>
<tr><td><span data-ttu-id="559a7-140">操作系统的功能更新</span><span class="sxs-lookup"><span data-stu-id="559a7-140">Feature updates for operating system</span></span></td><td><span data-ttu-id="559a7-141">半年通道 （目标） + 0 天</span><span class="sxs-lookup"><span data-stu-id="559a7-141">Semi-annual channel (targeted) + 0 days</span></span></td><td><span data-ttu-id="559a7-142">半年通道 （目标） + 30 天</span><span class="sxs-lookup"><span data-stu-id="559a7-142">Semi-annual channel (targeted) + 30 days</span></span></td><td><span data-ttu-id="559a7-143">半年通道 （目标） + 60 天</span><span class="sxs-lookup"><span data-stu-id="559a7-143">Semi-annual channel (targeted) + 60 days</span></span></td><td><span data-ttu-id="559a7-144">半年通道 + 30 天</span><span class="sxs-lookup"><span data-stu-id="559a7-144">Semi-annual channel + 30 days</span></span></td></tr>
<tr><td><span data-ttu-id="559a7-145">驱动程序/固件</span><span class="sxs-lookup"><span data-stu-id="559a7-145">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="559a7-146">遵循高质量的更新的计划</span><span class="sxs-lookup"><span data-stu-id="559a7-146">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="559a7-147">防病毒定义</span><span class="sxs-lookup"><span data-stu-id="559a7-147">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="559a7-148">更新了每个扫描</span><span class="sxs-lookup"><span data-stu-id="559a7-148">Updated with each scan</span></span></td></tr>
<tr><td><span data-ttu-id="559a7-149">Office 支持加号单击可运行</span><span class="sxs-lookup"><span data-stu-id="559a7-149">Office Pro-Plus click to run</span></span></td><td colspan="4"><span data-ttu-id="559a7-150">与半年通道对齐</span><span class="sxs-lookup"><span data-stu-id="559a7-150">Aligned with semi-annual channel</span></span></td></tr>
</table>


## <a name="windows-insider-program"></a><span data-ttu-id="559a7-151">Windows 内幕计划</span><span class="sxs-lookup"><span data-stu-id="559a7-151">Windows Insider Program</span></span>

<span data-ttu-id="559a7-p106">Microsoft 托管桌面不支持 Windows 内幕计划的一部分的设备。此程序用于验证预发行 Windows 软件和适用于非任务关键设备。尽管这是一项重要 Microsoft 举措，它不是在生产环境中的广泛部署。</span><span class="sxs-lookup"><span data-stu-id="559a7-p106">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program. This program is used to validate pre-release Windows software and is intended for non-mission critical devices. While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="559a7-155">与 Windows 内幕生成找到任何设备将放入测试振铃，并不会包含更新 Sla。</span><span class="sxs-lookup"><span data-stu-id="559a7-155">Any devices found with Windows Insider builds will be put into the Test ring and not be included for update SLAs.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="559a7-156">带宽管理</span><span class="sxs-lookup"><span data-stu-id="559a7-156">Bandwidth management</span></span>

<span data-ttu-id="559a7-p107">传递优化用于所有操作的系统和驱动程序更新。它旨在从企业网络内部的对等方的更新，降至最低从 Windows 更新 (WU) 服务下载的大小。</span><span class="sxs-lookup"><span data-stu-id="559a7-p107">Delivery optimization is used for all operating system and driver updates. It minimizes the download size from the Windows Update (WU) service by seeking updates from peers within the corporate network.</span></span>


