---
title: 从 Symantec 到 Microsoft Defender for Endpoint - 第 1 阶段，正在准备
description: 这是从 Symantec 迁移到 Microsoft Defender for Endpoint 的第 1 阶段，即准备阶段。
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 7fe0eb8adc90c259d31f237082effc80c5e8622c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537975"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a><span data-ttu-id="7c02c-104">从 Symantec 迁移 - 阶段 1：准备迁移</span><span class="sxs-lookup"><span data-stu-id="7c02c-104">Migrate from Symantec - Phase 1: Prepare for your migration</span></span>

<span data-ttu-id="7c02c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7c02c-105">**Applies to:**</span></span>
- [<span data-ttu-id="7c02c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7c02c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7c02c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7c02c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

|![阶段 1：准备](images/phase-diagrams/prepare.png)<br/><span data-ttu-id="7c02c-109">阶段 1：准备</span><span class="sxs-lookup"><span data-stu-id="7c02c-109">Phase 1: Prepare</span></span> |<span data-ttu-id="7c02c-110">[![阶段 2：设置](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)</span><span class="sxs-lookup"><span data-stu-id="7c02c-110">[![Phase 2: Set up](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)</span></span><br/>[<span data-ttu-id="7c02c-111">阶段 2：设置</span><span class="sxs-lookup"><span data-stu-id="7c02c-111">Phase 2: Set up</span></span>](symantec-to-microsoft-defender-atp-setup.md) |<span data-ttu-id="7c02c-112">[![阶段 3：开始使用](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)</span><span class="sxs-lookup"><span data-stu-id="7c02c-112">[![Phase 3: Onboard](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)</span></span><br/>[<span data-ttu-id="7c02c-113">阶段 3：开始使用</span><span class="sxs-lookup"><span data-stu-id="7c02c-113">Phase 3: Onboard</span></span>](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|<span data-ttu-id="7c02c-114">*你在这里！*</span><span class="sxs-lookup"><span data-stu-id="7c02c-114">*You are here!*</span></span>| | |


<span data-ttu-id="7c02c-115">**欢迎使用从 [Symantec 迁移到 Defender for Endpoint 的"准备"阶段](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**。</span><span class="sxs-lookup"><span data-stu-id="7c02c-115">**Welcome to the Prepare phase of [migrating from Symantec to Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**.</span></span> 

<span data-ttu-id="7c02c-116">此迁移阶段包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7c02c-116">This migration phase includes the following steps:</span></span>

1. <span data-ttu-id="7c02c-117">[更新组织的设备](#update-your-organizations-devices)。</span><span class="sxs-lookup"><span data-stu-id="7c02c-117">[Update your organization's devices](#update-your-organizations-devices).</span></span>

2. <span data-ttu-id="7c02c-118">[获取 Microsoft Defender for Endpoint](#get-microsoft-defender-for-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="7c02c-118">[Get Microsoft Defender for Endpoint](#get-microsoft-defender-for-endpoint).</span></span>

3. <span data-ttu-id="7c02c-119">[授予对 Microsoft Defender 安全中心 的访问权限](#grant-access-to-the-microsoft-defender-security-center)。</span><span class="sxs-lookup"><span data-stu-id="7c02c-119">[Grant access to the Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).</span></span>

4. [<span data-ttu-id="7c02c-120">配置设备代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="7c02c-120">Configure device proxy and internet connectivity settings</span></span>](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="update-your-organizations-devices"></a><span data-ttu-id="7c02c-121">更新组织设备</span><span class="sxs-lookup"><span data-stu-id="7c02c-121">Update your organization's devices</span></span>

<span data-ttu-id="7c02c-122">最佳做法是使组织的设备和终结点保持最新。</span><span class="sxs-lookup"><span data-stu-id="7c02c-122">As a best practice, keep your organization's devices and endpoints up to date.</span></span> <span data-ttu-id="7c02c-123">请确保现有终结点保护和防病毒解决方案是最新的，并且组织的操作系统和应用也具有最新的更新。</span><span class="sxs-lookup"><span data-stu-id="7c02c-123">Make sure your existing endpoint protection and antivirus solution is up to date, and that the operating systems and apps your organization is also have the latest updates.</span></span> <span data-ttu-id="7c02c-124">现在执行此操作有助于防止以后迁移到 Defender for Endpoint 时出现问题。</span><span class="sxs-lookup"><span data-stu-id="7c02c-124">Doing this now can help prevent problems later as you migrate to Defender for Endpoint.</span></span>

### <a name="make-sure-symantec-is-up-to-date"></a><span data-ttu-id="7c02c-125">确保 Symantec 是最新的</span><span class="sxs-lookup"><span data-stu-id="7c02c-125">Make sure Symantec is up to date</span></span>

<span data-ttu-id="7c02c-126">使现有终结点保护解决方案保持最新，并确保组织设备具有最新的安全更新。</span><span class="sxs-lookup"><span data-stu-id="7c02c-126">Keep your existing endpoint protection solution up to date, and make sure that your organization's devices have the latest security updates.</span></span>

<span data-ttu-id="7c02c-127">需要帮助?</span><span class="sxs-lookup"><span data-stu-id="7c02c-127">Need help?</span></span> <span data-ttu-id="7c02c-128">请参阅 Broadcom 的文档[：Symantec Endpoint Protection安装和管理指南](https://techdocs.broadcom.com/us/en/symantec-security-software/endpoint-security-and-management/endpoint-protection/all.html)</span><span class="sxs-lookup"><span data-stu-id="7c02c-128">See Broadcom's documentation: [Symantec Endpoint Protection Installation and Administration Guide](https://techdocs.broadcom.com/us/en/symantec-security-software/endpoint-security-and-management/endpoint-protection/all.html)</span></span>

### <a name="make-sure-your-endpoints-are-up-to-date"></a><span data-ttu-id="7c02c-129">确保终结点是最新的</span><span class="sxs-lookup"><span data-stu-id="7c02c-129">Make sure your endpoints are up to date</span></span>

<span data-ttu-id="7c02c-130">需要更新组织设备的帮助？</span><span class="sxs-lookup"><span data-stu-id="7c02c-130">Need help updating your organization's devices?</span></span> <span data-ttu-id="7c02c-131">参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="7c02c-131">See the following resources:</span></span>


|<span data-ttu-id="7c02c-132">操作系统</span><span class="sxs-lookup"><span data-stu-id="7c02c-132">OS</span></span>  |<span data-ttu-id="7c02c-133">Resource</span><span class="sxs-lookup"><span data-stu-id="7c02c-133">Resource</span></span>  |
|---------|---------|
|<span data-ttu-id="7c02c-134">Windows</span><span class="sxs-lookup"><span data-stu-id="7c02c-134">Windows</span></span>     | [<span data-ttu-id="7c02c-135">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="7c02c-135">Microsoft Update</span></span>](https://www.update.microsoft.com/)        |
|<span data-ttu-id="7c02c-136">macOS</span><span class="sxs-lookup"><span data-stu-id="7c02c-136">macOS</span></span>     | [<span data-ttu-id="7c02c-137">如何在 Mac 上更新软件</span><span class="sxs-lookup"><span data-stu-id="7c02c-137">How to update the software on your Mac</span></span>](https://support.apple.com/HT201541)         |
|<span data-ttu-id="7c02c-138">iOS</span><span class="sxs-lookup"><span data-stu-id="7c02c-138">iOS</span></span>     | [<span data-ttu-id="7c02c-139">更新你的iPhone、iPad或 iPod 触摸</span><span class="sxs-lookup"><span data-stu-id="7c02c-139">Update your iPhone, iPad, or iPod touch</span></span>](https://support.apple.com/HT204204)         |
|<span data-ttu-id="7c02c-140">Android</span><span class="sxs-lookup"><span data-stu-id="7c02c-140">Android</span></span>     | [<span data-ttu-id="7c02c-141">检查& Android 版本</span><span class="sxs-lookup"><span data-stu-id="7c02c-141">Check & update your Android version</span></span>](https://support.google.com/android/answer/7680439)        |
|<span data-ttu-id="7c02c-142">Linux</span><span class="sxs-lookup"><span data-stu-id="7c02c-142">Linux</span></span>     | [<span data-ttu-id="7c02c-143">Linux 101：更新系统</span><span class="sxs-lookup"><span data-stu-id="7c02c-143">Linux 101: Updating Your System</span></span>](https://www.linux.com/training-tutorials/linux-101-updating-your-system)        |


## <a name="get-microsoft-defender-for-endpoint"></a><span data-ttu-id="7c02c-144">获取 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7c02c-144">Get Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="7c02c-145">现在，你已更新组织的设备，下一步是获取适用于终结点的 Defender、分配许可证并确保已预配服务。</span><span class="sxs-lookup"><span data-stu-id="7c02c-145">Now that you've updated your organization's devices, the next step is to get Defender for Endpoint, assign licenses, and make sure the service is provisioned.</span></span>

1. <span data-ttu-id="7c02c-146">立即购买或试用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="7c02c-146">Buy or try Defender for Endpoint today.</span></span> <span data-ttu-id="7c02c-147">[访问 Defender for Endpoint 以启动免费试用版或请求使用引号](https://aka.ms/mdatp)。</span><span class="sxs-lookup"><span data-stu-id="7c02c-147">[Visit Defender for Endpoint to start a free trial or request a quote](https://aka.ms/mdatp).</span></span> 

2. <span data-ttu-id="7c02c-148">验证许可证是否正确预配。</span><span class="sxs-lookup"><span data-stu-id="7c02c-148">Verify that your licenses are properly provisioned.</span></span> <span data-ttu-id="7c02c-149">[检查你的许可证状态](production-deployment.md#check-license-state)。</span><span class="sxs-lookup"><span data-stu-id="7c02c-149">[Check your license state](production-deployment.md#check-license-state).</span></span>

3. <span data-ttu-id="7c02c-150">作为全局管理员或安全管理员，设置适用于终结点的 Defender 的专用云实例。</span><span class="sxs-lookup"><span data-stu-id="7c02c-150">As a global administrator or security administrator, set up your dedicated cloud instance of Defender for Endpoint.</span></span> <span data-ttu-id="7c02c-151">请参阅 [Defender for Endpoint setup： Tenant configuration](production-deployment.md#tenant-configuration)。</span><span class="sxs-lookup"><span data-stu-id="7c02c-151">See [Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).</span></span>

4. <span data-ttu-id="7c02c-152">如果终结点 (，) 使用代理访问 Internet，请参阅 [Defender for Endpoint setup： Network configuration](production-deployment.md#network-configuration)。</span><span class="sxs-lookup"><span data-stu-id="7c02c-152">If endpoints (such as devices) in your organization use a proxy to access the internet, see [Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration).</span></span>
 
<span data-ttu-id="7c02c-153">此时，您已准备好向将使用安全管理策略的安全管理员和安全 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender 安全中心 () 。</span><span class="sxs-lookup"><span data-stu-id="7c02c-153">At this point, you are ready to grant access to your security administrators and security operators who will use the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)).</span></span> 

> [!NOTE]
> <span data-ttu-id="7c02c-154">该Microsoft Defender 安全中心有时称为 Defender for Endpoint 门户。</span><span class="sxs-lookup"><span data-stu-id="7c02c-154">The Microsoft Defender Security Center is sometimes referred to as the Defender for Endpoint portal.</span></span> 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a><span data-ttu-id="7c02c-155">向用户授予Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="7c02c-155">Grant access to the Microsoft Defender Security Center</span></span>

<span data-ttu-id="7c02c-156">此 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender 安全中心 () 访问和配置 Defender for Endpoint 的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="7c02c-156">The Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) is where you access and configure features and capabilities of Defender for Endpoint.</span></span> <span data-ttu-id="7c02c-157">若要了解更多信息，请参阅[Microsoft Defender 安全中心 概述](use.md)。</span><span class="sxs-lookup"><span data-stu-id="7c02c-157">To learn more, see [Overview of the Microsoft Defender Security Center](use.md).</span></span>

<span data-ttu-id="7c02c-158">可以使用 RBAC Microsoft Defender 安全中心基本权限或基于角色的访问控制来授予 (权限) 。</span><span class="sxs-lookup"><span data-stu-id="7c02c-158">Permissions to the Microsoft Defender Security Center can be granted by using either basic permissions or role-based access control (RBAC).</span></span> <span data-ttu-id="7c02c-159">我们建议使用 RBAC，以便可以更精细地控制权限。</span><span class="sxs-lookup"><span data-stu-id="7c02c-159">We recommend using RBAC so that you have more granular control over permissions.</span></span>

1. <span data-ttu-id="7c02c-160">为安全管理员和安全操作员规划角色和权限。</span><span class="sxs-lookup"><span data-stu-id="7c02c-160">Plan the roles and permissions for your security administrators and security operators.</span></span> <span data-ttu-id="7c02c-161">请参阅 [基于角色的访问控制](prepare-deployment.md#role-based-access-control)。</span><span class="sxs-lookup"><span data-stu-id="7c02c-161">See [Role-based access control](prepare-deployment.md#role-based-access-control).</span></span>

2. <span data-ttu-id="7c02c-162">设置和配置 RBAC。</span><span class="sxs-lookup"><span data-stu-id="7c02c-162">Set up and configure RBAC.</span></span> <span data-ttu-id="7c02c-163">我们建议使用[Intune](/mem/intune/fundamentals/what-is-intune)配置 RBAC，尤其是在组织结合使用 Windows 10、macOS、iOS 和 Android 设备时。</span><span class="sxs-lookup"><span data-stu-id="7c02c-163">We recommend using [Intune](/mem/intune/fundamentals/what-is-intune) to configure RBAC, especially if your organization is using a combination of Windows 10, macOS, iOS, and Android devices.</span></span> <span data-ttu-id="7c02c-164">请参阅[使用 Intune 设置 RBAC。](/mem/intune/fundamentals/role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="7c02c-164">See [setting up RBAC using Intune](/mem/intune/fundamentals/role-based-access-control).</span></span>

   <span data-ttu-id="7c02c-165">如果你的组织需要 Intune 外的其他方法，请选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="7c02c-165">If your organization requires a method other than Intune, choose one of the following options:</span></span>

    - [<span data-ttu-id="7c02c-166">配置管理器</span><span class="sxs-lookup"><span data-stu-id="7c02c-166">Configuration Manager</span></span>](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [<span data-ttu-id="7c02c-167">高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="7c02c-167">Advanced Group Policy Management</span></span>](/microsoft-desktop-optimization-pack/agpm)

    - [<span data-ttu-id="7c02c-168">Windows管理中心</span><span class="sxs-lookup"><span data-stu-id="7c02c-168">Windows Admin Center</span></span>](/windows-server/manage/windows-admin-center/overview)

3. <span data-ttu-id="7c02c-169">向用户授予Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="7c02c-169">Grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="7c02c-170"> (需要帮助？</span><span class="sxs-lookup"><span data-stu-id="7c02c-170">(Need help?</span></span> <span data-ttu-id="7c02c-171">请参阅 [使用 RBAC 管理门户](rbac.md)) 。</span><span class="sxs-lookup"><span data-stu-id="7c02c-171">See [Manage portal access using RBAC](rbac.md)).</span></span>

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="7c02c-172">配置设备代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="7c02c-172">Configure device proxy and internet connectivity settings</span></span>

<span data-ttu-id="7c02c-173">若要启用设备和 Defender for Endpoint 之间的通信，请配置代理和 Internet 设置。</span><span class="sxs-lookup"><span data-stu-id="7c02c-173">To enable communication between your devices and Defender for Endpoint, configure proxy and internet settings.</span></span> <span data-ttu-id="7c02c-174">下表包含指向可用于为各种操作系统和功能配置代理和 Internet 设置的资源的链接：</span><span class="sxs-lookup"><span data-stu-id="7c02c-174">The following table includes links to resources you can use to configure your proxy and internet settings for various operating systems and capabilities:</span></span>

|<span data-ttu-id="7c02c-175">功能</span><span class="sxs-lookup"><span data-stu-id="7c02c-175">Capabilities</span></span>  | <span data-ttu-id="7c02c-176">操作系统</span><span class="sxs-lookup"><span data-stu-id="7c02c-176">Operating System</span></span> | <span data-ttu-id="7c02c-177">资源</span><span class="sxs-lookup"><span data-stu-id="7c02c-177">Resources</span></span> |
|:----|:----|:---|
|<span data-ttu-id="7c02c-178">[终结点检测和响应](overview-endpoint-detection-response.md) (EDR) </span><span class="sxs-lookup"><span data-stu-id="7c02c-178">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR)</span></span> | [<span data-ttu-id="7c02c-179">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7c02c-179">Windows 10</span></span>](/windows/release-health/release-information/) <p> [<span data-ttu-id="7c02c-180">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="7c02c-180">Windows Server 2019</span></span>](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[<span data-ttu-id="7c02c-181">Windows服务器 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7c02c-181">Windows Server 1803 or later</span></span>](/windows-server/get-started/whats-new-in-windows-server-1803)  |[<span data-ttu-id="7c02c-182">配置计算机代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="7c02c-182">Configure machine proxy and internet connectivity settings</span></span>](configure-proxy-internet.md) |
|<span data-ttu-id="7c02c-183">EDR</span><span class="sxs-lookup"><span data-stu-id="7c02c-183">EDR</span></span> | [<span data-ttu-id="7c02c-184">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="7c02c-184">Windows Server 2016</span></span>](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[<span data-ttu-id="7c02c-185">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="7c02c-185">Windows Server 2012 R2</span></span>](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[<span data-ttu-id="7c02c-186">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="7c02c-186">Windows Server 2008 R2 SP1</span></span>](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[<span data-ttu-id="7c02c-187">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="7c02c-187">Windows 8.1</span></span>](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[<span data-ttu-id="7c02c-188">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="7c02c-188">Windows 7 SP1</span></span>](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[<span data-ttu-id="7c02c-189">配置代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="7c02c-189">Configure proxy and internet connectivity settings</span></span>](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|<span data-ttu-id="7c02c-190">EDR</span><span class="sxs-lookup"><span data-stu-id="7c02c-190">EDR</span></span>  |<span data-ttu-id="7c02c-191">macOS：</span><span class="sxs-lookup"><span data-stu-id="7c02c-191">macOS:</span></span> <p><span data-ttu-id="7c02c-192">11.3.1 (Big Sur) </span><span class="sxs-lookup"><span data-stu-id="7c02c-192">11.3.1 (Big Sur)</span></span><p><span data-ttu-id="7c02c-193">10.15 (加泰罗尼亚语) </span><span class="sxs-lookup"><span data-stu-id="7c02c-193">10.15 (Catalina)</span></span><p><span data-ttu-id="7c02c-194">10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="7c02c-194">10.14 (Mojave)</span></span> |[<span data-ttu-id="7c02c-195">macOS 上的 Defender for Endpoint：网络连接</span><span class="sxs-lookup"><span data-stu-id="7c02c-195">Defender for Endpoint on macOS: Network connections</span></span>](microsoft-defender-endpoint-mac.md#network-connections) |
|[<span data-ttu-id="7c02c-196">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="7c02c-196">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md) |[<span data-ttu-id="7c02c-197">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7c02c-197">Windows 10</span></span>](/windows/release-health/release-information/)<p>[<span data-ttu-id="7c02c-198">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="7c02c-198">Windows Server 2019</span></span>](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[<span data-ttu-id="7c02c-199">Windows服务器 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7c02c-199">Windows Server 1803 or later</span></span>](/windows-server/get-started/whats-new-in-windows-server-1803)<p>[<span data-ttu-id="7c02c-200">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="7c02c-200">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016) |[<span data-ttu-id="7c02c-201">配置和验证 Microsoft Defender 防病毒软件网络连接</span><span class="sxs-lookup"><span data-stu-id="7c02c-201">Configure and validate Microsoft Defender Antivirus network connections</span></span>](configure-network-connections-microsoft-defender-antivirus.md) |
|<span data-ttu-id="7c02c-202">防病毒</span><span class="sxs-lookup"><span data-stu-id="7c02c-202">Antivirus</span></span> |<span data-ttu-id="7c02c-203">macOS：</span><span class="sxs-lookup"><span data-stu-id="7c02c-203">macOS:</span></span> <p><span data-ttu-id="7c02c-204">11.3.1 (Big Sur) </span><span class="sxs-lookup"><span data-stu-id="7c02c-204">11.3.1 (Big Sur)</span></span><p><span data-ttu-id="7c02c-205">10.15 (加泰罗尼亚语) </span><span class="sxs-lookup"><span data-stu-id="7c02c-205">10.15 (Catalina)</span></span><p><span data-ttu-id="7c02c-206">10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="7c02c-206">10.14 (Mojave)</span></span>  |[<span data-ttu-id="7c02c-207">Mac 上的 Defender for Endpoint：网络连接</span><span class="sxs-lookup"><span data-stu-id="7c02c-207">Defender for Endpoint on Mac: Network connections</span></span>](microsoft-defender-endpoint-mac.md#network-connections) |
|<span data-ttu-id="7c02c-208">防病毒</span><span class="sxs-lookup"><span data-stu-id="7c02c-208">Antivirus</span></span> |<span data-ttu-id="7c02c-209">Linux：</span><span class="sxs-lookup"><span data-stu-id="7c02c-209">Linux:</span></span> <p><span data-ttu-id="7c02c-210">RHEL 7.2+</span><span class="sxs-lookup"><span data-stu-id="7c02c-210">RHEL 7.2+</span></span><p><span data-ttu-id="7c02c-211">CentOS Linux 7.2+</span><span class="sxs-lookup"><span data-stu-id="7c02c-211">CentOS Linux 7.2+</span></span><p><span data-ttu-id="7c02c-212">Ubuntu 16 LTS 或更高版本 LTS</span><span class="sxs-lookup"><span data-stu-id="7c02c-212">Ubuntu 16 LTS, or higher LTS</span></span><p><span data-ttu-id="7c02c-213">SLES 12+</span><span class="sxs-lookup"><span data-stu-id="7c02c-213">SLES 12+</span></span><p><span data-ttu-id="7c02c-214">Debian 9+</span><span class="sxs-lookup"><span data-stu-id="7c02c-214">Debian 9+</span></span><p><span data-ttu-id="7c02c-215">Oracle Linux 7.2</span><span class="sxs-lookup"><span data-stu-id="7c02c-215">Oracle Linux 7.2</span></span> |[<span data-ttu-id="7c02c-216">Linux 上的 Defender for Endpoint：网络连接</span><span class="sxs-lookup"><span data-stu-id="7c02c-216">Defender for Endpoint on Linux: Network connections</span></span>](microsoft-defender-endpoint-linux.md#network-connections)  |

## <a name="next-step"></a><span data-ttu-id="7c02c-217">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7c02c-217">Next step</span></span>

<span data-ttu-id="7c02c-218">**恭喜！**</span><span class="sxs-lookup"><span data-stu-id="7c02c-218">**Congratulations**!</span></span> <span data-ttu-id="7c02c-219">你已完成从[Symantec 迁移到 Defender for Endpoint 的"准备"阶段](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)！</span><span class="sxs-lookup"><span data-stu-id="7c02c-219">You have completed the **Prepare** phase of [migrating from Symantec to Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)!</span></span>
- <span data-ttu-id="7c02c-220">[继续为终结点设置 Defender。](symantec-to-microsoft-defender-atp-setup.md)</span><span class="sxs-lookup"><span data-stu-id="7c02c-220">[Proceed to set up Defender for Endpoint](symantec-to-microsoft-defender-atp-setup.md).</span></span>
