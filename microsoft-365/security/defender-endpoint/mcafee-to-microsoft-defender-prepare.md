---
title: McAfee 到 Microsoft Defender for Endpoint - 准备
description: 这是第 1 阶段，准备，用于从 McAfee 迁移到 Microsoft Defender for Endpoint。
keywords: migration， Microsoft Defender for Endpoint， edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 171c9b4ff02e7f6ddb6918e430af772f44b1777a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538779"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a><span data-ttu-id="423d7-104">从 McAfee 迁移 - 第 1 阶段：准备迁移</span><span class="sxs-lookup"><span data-stu-id="423d7-104">Migrate from McAfee - Phase 1: Prepare for your migration</span></span>

<span data-ttu-id="423d7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="423d7-105">**Applies to:**</span></span>
- [<span data-ttu-id="423d7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="423d7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="423d7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="423d7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

|![阶段 1：准备](images/phase-diagrams/prepare.png)<br/><span data-ttu-id="423d7-109">阶段 1：准备</span><span class="sxs-lookup"><span data-stu-id="423d7-109">Phase 1: Prepare</span></span> |<span data-ttu-id="423d7-110">[![阶段 2：设置](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span><span class="sxs-lookup"><span data-stu-id="423d7-110">[![Phase 2: Set up](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span></span><br/>[<span data-ttu-id="423d7-111">阶段 2：设置</span><span class="sxs-lookup"><span data-stu-id="423d7-111">Phase 2: Set up</span></span>](mcafee-to-microsoft-defender-setup.md) |<span data-ttu-id="423d7-112">[![阶段 3：开始使用](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)</span><span class="sxs-lookup"><span data-stu-id="423d7-112">[![Phase 3: Onboard](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)</span></span><br/>[<span data-ttu-id="423d7-113">阶段 3：开始使用</span><span class="sxs-lookup"><span data-stu-id="423d7-113">Phase 3: Onboard</span></span>](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|<span data-ttu-id="423d7-114">*你在这里！*</span><span class="sxs-lookup"><span data-stu-id="423d7-114">*You are here!*</span></span>| | |


<span data-ttu-id="423d7-115">**欢迎使用从 McAfee Endpoint Security ([McAfee) 迁移到 Defender for Endpoint 的"准备"阶段](mcafee-to-microsoft-defender-migration.md#the-migration-process)**。</span><span class="sxs-lookup"><span data-stu-id="423d7-115">**Welcome to the Prepare phase of [migrating from McAfee Endpoint Security (McAfee) to Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)**.</span></span> 

<span data-ttu-id="423d7-116">此迁移阶段包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="423d7-116">This migration phase includes the following steps:</span></span>
1. [<span data-ttu-id="423d7-117">在组织设备上获取和部署更新</span><span class="sxs-lookup"><span data-stu-id="423d7-117">Get and deploy updates across your organization's devices</span></span>](#get-and-deploy-updates-across-your-organizations-devices)

2. <span data-ttu-id="423d7-118">[获取 Defender for Endpoint](#get-microsoft-defender-for-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="423d7-118">[Get Defender for Endpoint](#get-microsoft-defender-for-endpoint).</span></span>

3. <span data-ttu-id="423d7-119">[授予对 Microsoft Defender 安全中心 的访问权限](#grant-access-to-the-microsoft-defender-security-center)。</span><span class="sxs-lookup"><span data-stu-id="423d7-119">[Grant access to the Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).</span></span>

4. <span data-ttu-id="423d7-120">[配置设备代理和 Internet 连接设置](#configure-device-proxy-and-internet-connectivity-settings)。</span><span class="sxs-lookup"><span data-stu-id="423d7-120">[Configure device proxy and internet connectivity settings](#configure-device-proxy-and-internet-connectivity-settings).</span></span>

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a><span data-ttu-id="423d7-121">在组织设备上获取和部署更新</span><span class="sxs-lookup"><span data-stu-id="423d7-121">Get and deploy updates across your organization's devices</span></span>

<span data-ttu-id="423d7-122">最佳做法是使组织的设备和终结点保持最新。</span><span class="sxs-lookup"><span data-stu-id="423d7-122">As a best practice, keep your organization's devices and endpoints up to date.</span></span> <span data-ttu-id="423d7-123">请确保您的 McAfee Endpoint Security (McAfee) 解决方案是最新的，并且组织的操作系统和应用也具有最新的更新。</span><span class="sxs-lookup"><span data-stu-id="423d7-123">Make sure your McAfee Endpoint Security (McAfee) solution is up to date, and that the operating systems and apps your organization is also have the latest updates.</span></span> <span data-ttu-id="423d7-124">现在执行此操作有助于防止以后迁移到 Defender for Endpoint 时出现问题。</span><span class="sxs-lookup"><span data-stu-id="423d7-124">Doing this now can help prevent problems later as you migrate to Defender for Endpoint.</span></span>

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a><span data-ttu-id="423d7-125">确保 McAfee 解决方案是最新的</span><span class="sxs-lookup"><span data-stu-id="423d7-125">Make sure your McAfee solution is up to date</span></span>

<span data-ttu-id="423d7-126">使 McAfee 保持最新，并确保组织设备具有最新的安全更新。</span><span class="sxs-lookup"><span data-stu-id="423d7-126">Keep McAfee up to date, and make sure that your organization's devices have the latest security updates.</span></span> <span data-ttu-id="423d7-127">需要帮助?</span><span class="sxs-lookup"><span data-stu-id="423d7-127">Need help?</span></span> <span data-ttu-id="423d7-128">下面是一些 McAfee 资源：</span><span class="sxs-lookup"><span data-stu-id="423d7-128">Here are some McAfee resources:</span></span>

- [<span data-ttu-id="423d7-129">McAfee Enterprise产品文档：Endpoint Security 的工作原理</span><span class="sxs-lookup"><span data-stu-id="423d7-129">McAfee Enterprise Product Documentation: How Endpoint Security Works</span></span>](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [<span data-ttu-id="423d7-130">McAfee 知识库技术文章：Windows 安全中心中心间歇性地错误地报告终结点安全性在终结点安全中心Windows 10</span><span class="sxs-lookup"><span data-stu-id="423d7-130">McAfee Knowledge Center Technical Article: Windows Security Center intermittently incorrectly reports that Endpoint Security is disabled when running on Windows 10</span></span>](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [<span data-ttu-id="423d7-131">McAfee 知识库技术文章：Windows 安全中心中心报告终结点安全性在运行终结点安全性时处于禁用状态</span><span class="sxs-lookup"><span data-stu-id="423d7-131">McAfee Knowledge Center Technical Article: Windows Security Center reports Endpoint Security is disabled when Endpoint Security is running</span></span>](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- <span data-ttu-id="423d7-132">你的 McAfee 支持 ServicePortal [http://mysupport.mcafee.com](http://mysupport.mcafee.com) () </span><span class="sxs-lookup"><span data-stu-id="423d7-132">Your McAfee support ServicePortal ([http://mysupport.mcafee.com](http://mysupport.mcafee.com))</span></span>

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a><span data-ttu-id="423d7-133">确保组织的设备是最新的</span><span class="sxs-lookup"><span data-stu-id="423d7-133">Make sure your organization's devices are up to date</span></span>

<span data-ttu-id="423d7-134">需要更新组织设备的帮助？</span><span class="sxs-lookup"><span data-stu-id="423d7-134">Need help updating your organization's devices?</span></span> <span data-ttu-id="423d7-135">参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="423d7-135">See the following resources:</span></span>

|<span data-ttu-id="423d7-136">操作系统</span><span class="sxs-lookup"><span data-stu-id="423d7-136">OS</span></span> | <span data-ttu-id="423d7-137">Resource</span><span class="sxs-lookup"><span data-stu-id="423d7-137">Resource</span></span> |
|:--|:--|
|<span data-ttu-id="423d7-138">Windows</span><span class="sxs-lookup"><span data-stu-id="423d7-138">Windows</span></span> |[<span data-ttu-id="423d7-139">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="423d7-139">Microsoft Update</span></span>](https://www.update.microsoft.com) |
|<span data-ttu-id="423d7-140">macOS</span><span class="sxs-lookup"><span data-stu-id="423d7-140">macOS</span></span> | [<span data-ttu-id="423d7-141">如何在 Mac 上更新软件</span><span class="sxs-lookup"><span data-stu-id="423d7-141">How to update the software on your Mac</span></span>](https://support.apple.com/HT201541)|
|<span data-ttu-id="423d7-142">iOS</span><span class="sxs-lookup"><span data-stu-id="423d7-142">iOS</span></span> |[<span data-ttu-id="423d7-143">更新你的iPhone、iPad或 iPod 触摸</span><span class="sxs-lookup"><span data-stu-id="423d7-143">Update your iPhone, iPad, or iPod touch</span></span>](https://support.apple.com/HT204204)|
|<span data-ttu-id="423d7-144">Android</span><span class="sxs-lookup"><span data-stu-id="423d7-144">Android</span></span> |[<span data-ttu-id="423d7-145">检查& Android 版本</span><span class="sxs-lookup"><span data-stu-id="423d7-145">Check & update your Android version</span></span>](https://support.google.com/android/answer/7680439) |
|<span data-ttu-id="423d7-146">Linux</span><span class="sxs-lookup"><span data-stu-id="423d7-146">Linux</span></span> | [<span data-ttu-id="423d7-147">Linux 101：更新系统</span><span class="sxs-lookup"><span data-stu-id="423d7-147">Linux 101: Updating Your System</span></span>](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a><span data-ttu-id="423d7-148">获取 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="423d7-148">Get Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="423d7-149">现在，你已更新组织的设备，下一步是获取适用于终结点的 Defender、分配许可证并确保已预配服务。</span><span class="sxs-lookup"><span data-stu-id="423d7-149">Now that you've updated your organization's devices, the next step is to get Defender for Endpoint, assign licenses, and make sure the service is provisioned.</span></span>

1. <span data-ttu-id="423d7-150">立即购买或试用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="423d7-150">Buy or try Defender for Endpoint today.</span></span> <span data-ttu-id="423d7-151">[启动免费试用版或请求使用引号](https://aka.ms/mdatp)。</span><span class="sxs-lookup"><span data-stu-id="423d7-151">[Start a free trial or request a quote](https://aka.ms/mdatp).</span></span> 

2. <span data-ttu-id="423d7-152">验证许可证是否正确预配。</span><span class="sxs-lookup"><span data-stu-id="423d7-152">Verify that your licenses are properly provisioned.</span></span> <span data-ttu-id="423d7-153">[检查你的许可证状态](production-deployment.md#check-license-state)。</span><span class="sxs-lookup"><span data-stu-id="423d7-153">[Check your license state](production-deployment.md#check-license-state).</span></span>

3. <span data-ttu-id="423d7-154">作为全局管理员或安全管理员，设置适用于终结点的 Defender 的专用云实例。</span><span class="sxs-lookup"><span data-stu-id="423d7-154">As a global administrator or security administrator, set up your dedicated cloud instance of Defender for Endpoint.</span></span> <span data-ttu-id="423d7-155">请参阅 [Defender for Endpoint setup： Tenant configuration](production-deployment.md#tenant-configuration)。</span><span class="sxs-lookup"><span data-stu-id="423d7-155">See [Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).</span></span>

4. <span data-ttu-id="423d7-156">如果终结点 (，) 使用代理访问 Internet，请参阅 [Defender for Endpoint setup： Network configuration](production-deployment.md#network-configuration)。</span><span class="sxs-lookup"><span data-stu-id="423d7-156">If endpoints (such as devices) in your organization use a proxy to access the internet, see [Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration).</span></span>
 
<span data-ttu-id="423d7-157">此时，您已准备好向将使用安全管理策略的安全管理员和安全 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender 安全中心 () 。</span><span class="sxs-lookup"><span data-stu-id="423d7-157">At this point, you are ready to grant access to your security administrators and security operators who will use the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)).</span></span> 

> [!NOTE]
> <span data-ttu-id="423d7-158">该Microsoft Defender 安全中心有时称为 Defender for Endpoint 门户。</span><span class="sxs-lookup"><span data-stu-id="423d7-158">The Microsoft Defender Security Center is sometimes referred to as the Defender for Endpoint portal.</span></span> 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a><span data-ttu-id="423d7-159">向用户授予Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="423d7-159">Grant access to the Microsoft Defender Security Center</span></span>

<span data-ttu-id="423d7-160">此 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender 安全中心 () 访问和配置 Defender for Endpoint 的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="423d7-160">The Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) is where you access and configure features and capabilities of Defender for Endpoint.</span></span> <span data-ttu-id="423d7-161">若要了解更多信息，请参阅[Microsoft Defender 安全中心 概述](use.md)。</span><span class="sxs-lookup"><span data-stu-id="423d7-161">To learn more, see [Overview of the Microsoft Defender Security Center](use.md).</span></span>

<span data-ttu-id="423d7-162">可以使用 RBAC Microsoft Defender 安全中心基本权限或基于角色的访问控制来授予 (权限) 。</span><span class="sxs-lookup"><span data-stu-id="423d7-162">Permissions to the Microsoft Defender Security Center can be granted by using either basic permissions or role-based access control (RBAC).</span></span> <span data-ttu-id="423d7-163">我们建议使用 RBAC，以便可以更精细地控制权限。</span><span class="sxs-lookup"><span data-stu-id="423d7-163">We recommend using RBAC so that you have more granular control over permissions.</span></span>

1. <span data-ttu-id="423d7-164">为安全管理员和安全操作员规划角色和权限。</span><span class="sxs-lookup"><span data-stu-id="423d7-164">Plan the roles and permissions for your security administrators and security operators.</span></span> <span data-ttu-id="423d7-165">请参阅 [基于角色的访问控制](prepare-deployment.md#role-based-access-control)。</span><span class="sxs-lookup"><span data-stu-id="423d7-165">See [Role-based access control](prepare-deployment.md#role-based-access-control).</span></span>

2. <span data-ttu-id="423d7-166">设置和配置 RBAC。</span><span class="sxs-lookup"><span data-stu-id="423d7-166">Set up and configure RBAC.</span></span> <span data-ttu-id="423d7-167">我们建议使用[Intune](/mem/intune/fundamentals/what-is-intune)配置 RBAC，尤其是在组织结合使用 Windows 10、macOS、iOS 和 Android 设备时。</span><span class="sxs-lookup"><span data-stu-id="423d7-167">We recommend using [Intune](/mem/intune/fundamentals/what-is-intune) to configure RBAC, especially if your organization is using a combination of Windows 10, macOS, iOS, and Android devices.</span></span> <span data-ttu-id="423d7-168">请参阅[使用 Intune 设置 RBAC。](/mem/intune/fundamentals/role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="423d7-168">See [setting up RBAC using Intune](/mem/intune/fundamentals/role-based-access-control).</span></span>

    <span data-ttu-id="423d7-169">如果你的组织需要 Intune 外的其他方法，请选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="423d7-169">If your organization requires a method other than Intune, choose one of the following options:</span></span>

    - [<span data-ttu-id="423d7-170">配置管理器</span><span class="sxs-lookup"><span data-stu-id="423d7-170">Configuration Manager</span></span>](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [<span data-ttu-id="423d7-171">高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="423d7-171">Advanced Group Policy Management</span></span>](/microsoft-desktop-optimization-pack/agpm)

    - [<span data-ttu-id="423d7-172">Windows管理中心</span><span class="sxs-lookup"><span data-stu-id="423d7-172">Windows Admin Center</span></span>](/windows-server/manage/windows-admin-center/overview)

3. <span data-ttu-id="423d7-173">向用户授予Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="423d7-173">Grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="423d7-174"> (需要帮助？</span><span class="sxs-lookup"><span data-stu-id="423d7-174">(Need help?</span></span> <span data-ttu-id="423d7-175">请参阅 [使用 RBAC 管理门户](rbac.md)) 。</span><span class="sxs-lookup"><span data-stu-id="423d7-175">See [Manage portal access using RBAC](rbac.md)).</span></span>

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="423d7-176">配置设备代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="423d7-176">Configure device proxy and internet connectivity settings</span></span>

<span data-ttu-id="423d7-177">若要启用设备和 Defender for Endpoint 之间的通信，请配置代理和 Internet 设置。</span><span class="sxs-lookup"><span data-stu-id="423d7-177">To enable communication between your devices and Defender for Endpoint, configure proxy and internet settings.</span></span> <span data-ttu-id="423d7-178">下表包含指向可用于为各种操作系统和功能配置代理和 Internet 设置的资源的链接：</span><span class="sxs-lookup"><span data-stu-id="423d7-178">The following table includes links to resources you can use to configure your proxy and internet settings for various operating systems and capabilities:</span></span>

|<span data-ttu-id="423d7-179">功能</span><span class="sxs-lookup"><span data-stu-id="423d7-179">Capabilities</span></span>  | <span data-ttu-id="423d7-180">操作系统</span><span class="sxs-lookup"><span data-stu-id="423d7-180">Operating System</span></span> | <span data-ttu-id="423d7-181">资源</span><span class="sxs-lookup"><span data-stu-id="423d7-181">Resources</span></span> |
|--|--|--|
| <span data-ttu-id="423d7-182">[终结点检测和响应](overview-endpoint-detection-response.md) (EDR) </span><span class="sxs-lookup"><span data-stu-id="423d7-182">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR)</span></span> | [<span data-ttu-id="423d7-183">Windows 10</span><span class="sxs-lookup"><span data-stu-id="423d7-183">Windows 10</span></span>](/windows/release-health/release-information) <p> [<span data-ttu-id="423d7-184">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="423d7-184">Windows Server 2019</span></span>](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[<span data-ttu-id="423d7-185">Windows服务器 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="423d7-185">Windows Server 1803 or later</span></span>](/windows-server/get-started/whats-new-in-windows-server-1803)  | [<span data-ttu-id="423d7-186">配置计算机代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="423d7-186">Configure machine proxy and internet connectivity settings</span></span>](configure-proxy-internet.md) |
|<span data-ttu-id="423d7-187">EDR</span><span class="sxs-lookup"><span data-stu-id="423d7-187">EDR</span></span> | [<span data-ttu-id="423d7-188">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="423d7-188">Windows Server 2016</span></span>](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[<span data-ttu-id="423d7-189">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="423d7-189">Windows Server 2012 R2</span></span>](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[<span data-ttu-id="423d7-190">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="423d7-190">Windows Server 2008 R2 SP1</span></span>](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[<span data-ttu-id="423d7-191">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="423d7-191">Windows 8.1</span></span>](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[<span data-ttu-id="423d7-192">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="423d7-192">Windows 7 SP1</span></span>](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) | [<span data-ttu-id="423d7-193">配置代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="423d7-193">Configure proxy and internet connectivity settings</span></span>](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|<span data-ttu-id="423d7-194">EDR</span><span class="sxs-lookup"><span data-stu-id="423d7-194">EDR</span></span>  |<span data-ttu-id="423d7-195">macOS：</span><span class="sxs-lookup"><span data-stu-id="423d7-195">macOS:</span></span> <p><span data-ttu-id="423d7-196">11.3.1 (Big Sur) </span><span class="sxs-lookup"><span data-stu-id="423d7-196">11.3.1 (Big Sur)</span></span><p><span data-ttu-id="423d7-197">10.15 (加泰罗尼亚语) </span><span class="sxs-lookup"><span data-stu-id="423d7-197">10.15 (Catalina)</span></span><p><span data-ttu-id="423d7-198">10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="423d7-198">10.14 (Mojave)</span></span>  | [<span data-ttu-id="423d7-199">macOS 上的 Defender for Endpoint：网络连接</span><span class="sxs-lookup"><span data-stu-id="423d7-199">Defender for Endpoint on macOS: Network connections</span></span>](microsoft-defender-endpoint-mac.md#network-connections) |
|[<span data-ttu-id="423d7-200">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="423d7-200">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md) | [<span data-ttu-id="423d7-201">Windows 10</span><span class="sxs-lookup"><span data-stu-id="423d7-201">Windows 10</span></span>](/windows/release-health/release-information) <p> [<span data-ttu-id="423d7-202">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="423d7-202">Windows Server 2019</span></span>](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[<span data-ttu-id="423d7-203">Windows服务器 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="423d7-203">Windows Server 1803 or later</span></span>](/windows-server/get-started/whats-new-in-windows-server-1803) <p>[<span data-ttu-id="423d7-204">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="423d7-204">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016) |[<span data-ttu-id="423d7-205">配置和验证 Microsoft Defender 防病毒软件网络连接</span><span class="sxs-lookup"><span data-stu-id="423d7-205">Configure and validate Microsoft Defender Antivirus network connections</span></span>](configure-network-connections-microsoft-defender-antivirus.md) |
|<span data-ttu-id="423d7-206">防病毒</span><span class="sxs-lookup"><span data-stu-id="423d7-206">Antivirus</span></span> |<span data-ttu-id="423d7-207">macOS：</span><span class="sxs-lookup"><span data-stu-id="423d7-207">macOS:</span></span> <p><span data-ttu-id="423d7-208">11.3.1 (Big Sur) </span><span class="sxs-lookup"><span data-stu-id="423d7-208">11.3.1 (Big Sur)</span></span><p><span data-ttu-id="423d7-209">10.15 (加泰罗尼亚语) </span><span class="sxs-lookup"><span data-stu-id="423d7-209">10.15 (Catalina)</span></span><p><span data-ttu-id="423d7-210">10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="423d7-210">10.14 (Mojave)</span></span> |[<span data-ttu-id="423d7-211">macOS 上的 Defender for Endpoint：网络连接</span><span class="sxs-lookup"><span data-stu-id="423d7-211">Defender for Endpoint on macOS: Network connections</span></span>](microsoft-defender-endpoint-mac.md#network-connections) |
|<span data-ttu-id="423d7-212">防病毒</span><span class="sxs-lookup"><span data-stu-id="423d7-212">Antivirus</span></span> |<span data-ttu-id="423d7-213">Linux：</span><span class="sxs-lookup"><span data-stu-id="423d7-213">Linux:</span></span> <p><span data-ttu-id="423d7-214">RHEL 7.2+</span><span class="sxs-lookup"><span data-stu-id="423d7-214">RHEL 7.2+</span></span><p><span data-ttu-id="423d7-215">CentOS Linux 7.2+</span><span class="sxs-lookup"><span data-stu-id="423d7-215">CentOS Linux 7.2+</span></span><p><span data-ttu-id="423d7-216">Ubuntu 16 LTS 或更高版本 LTS</span><span class="sxs-lookup"><span data-stu-id="423d7-216">Ubuntu 16 LTS, or higher LTS</span></span><p><span data-ttu-id="423d7-217">SLES 12+</span><span class="sxs-lookup"><span data-stu-id="423d7-217">SLES 12+</span></span><p><span data-ttu-id="423d7-218">Debian 9+</span><span class="sxs-lookup"><span data-stu-id="423d7-218">Debian 9+</span></span><p><span data-ttu-id="423d7-219">Oracle Linux 7.2</span><span class="sxs-lookup"><span data-stu-id="423d7-219">Oracle Linux 7.2</span></span> |[<span data-ttu-id="423d7-220">Linux 上的 Defender for Endpoint：网络连接</span><span class="sxs-lookup"><span data-stu-id="423d7-220">Defender for Endpoint on Linux: Network connections</span></span>](microsoft-defender-endpoint-linux.md#network-connections) 

## <a name="next-step"></a><span data-ttu-id="423d7-221">后续步骤</span><span class="sxs-lookup"><span data-stu-id="423d7-221">Next step</span></span>

<span data-ttu-id="423d7-222">**恭喜！**</span><span class="sxs-lookup"><span data-stu-id="423d7-222">**Congratulations**!</span></span> <span data-ttu-id="423d7-223">你已完成从 McAfee 迁移到 Defender for Endpoint 的"准备["阶段](mcafee-to-microsoft-defender-migration.md#the-migration-process)！ </span><span class="sxs-lookup"><span data-stu-id="423d7-223">You have completed the **Prepare** phase of [migrating from McAfee to Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)!</span></span>

- <span data-ttu-id="423d7-224">[继续为终结点设置 Defender。](mcafee-to-microsoft-defender-setup.md)</span><span class="sxs-lookup"><span data-stu-id="423d7-224">[Proceed to set up Defender for Endpoint](mcafee-to-microsoft-defender-setup.md).</span></span>
