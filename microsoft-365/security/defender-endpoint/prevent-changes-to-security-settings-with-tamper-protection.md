---
title: 使用篡改保护保护安全设置
ms.reviewer: shwjha, hayhov
manager: dansimp
description: 使用防篡改保护防止恶意应用更改重要安全设置。
keywords: 恶意软件， defender， 防病毒， 防篡改保护
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 05/17/2021
ms.openlocfilehash: f6217cccf79b951c3103e1024ac74669d68645cd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925931"
---
# <a name="protect-security-settings-with-tamper-protection"></a><span data-ttu-id="881d2-104">使用篡改保护保护安全设置</span><span class="sxs-lookup"><span data-stu-id="881d2-104">Protect security settings with tamper protection</span></span>

<span data-ttu-id="881d2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="881d2-105">**Applies to:**</span></span>

- [<span data-ttu-id="881d2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="881d2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="881d2-107">防篡改保护适用于运行以下版本之一的设备Windows：</span><span class="sxs-lookup"><span data-stu-id="881d2-107">Tamper protection is available for devices that are running one of the following versions of Windows:</span></span>

- <span data-ttu-id="881d2-108">Windows 10</span><span class="sxs-lookup"><span data-stu-id="881d2-108">Windows 10</span></span>
- <span data-ttu-id="881d2-109">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="881d2-109">Windows Server 2019</span></span>
- <span data-ttu-id="881d2-110">Windows服务器版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="881d2-110">Windows Server, version 1803 or later</span></span>
- <span data-ttu-id="881d2-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="881d2-111">Windows Server 2016</span></span>

## <a name="overview"></a><span data-ttu-id="881d2-112">概述</span><span class="sxs-lookup"><span data-stu-id="881d2-112">Overview</span></span>

<span data-ttu-id="881d2-113">在某些类型的网络攻击期间，不良参与者会尝试在你的计算机上禁用安全功能，如防病毒保护。</span><span class="sxs-lookup"><span data-stu-id="881d2-113">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="881d2-114">不良操作者希望禁用安全功能，以便更轻松地访问数据、安装恶意软件，或者以其他方式利用你的数据、标识和设备。</span><span class="sxs-lookup"><span data-stu-id="881d2-114">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span> <span data-ttu-id="881d2-115">防篡改保护有助于防止这些类型的事件发生。</span><span class="sxs-lookup"><span data-stu-id="881d2-115">Tamper protection helps prevent these kinds of things from occurring.</span></span>

<span data-ttu-id="881d2-116">借助防篡改保护，恶意应用可防止其采取如下操作：</span><span class="sxs-lookup"><span data-stu-id="881d2-116">With tamper protection, malicious apps are prevented from taking actions such as:</span></span>

- <span data-ttu-id="881d2-117">禁用病毒和威胁防护</span><span class="sxs-lookup"><span data-stu-id="881d2-117">Disabling virus and threat protection</span></span>
- <span data-ttu-id="881d2-118">禁用实时保护</span><span class="sxs-lookup"><span data-stu-id="881d2-118">Disabling real-time protection</span></span>
- <span data-ttu-id="881d2-119">关闭行为监视</span><span class="sxs-lookup"><span data-stu-id="881d2-119">Turning off behavior monitoring</span></span>
- <span data-ttu-id="881d2-120">禁用防病毒 (如 IOfficeAntivirus (IOAV) ) </span><span class="sxs-lookup"><span data-stu-id="881d2-120">Disabling antivirus (such as IOfficeAntivirus (IOAV))</span></span>
- <span data-ttu-id="881d2-121">禁用云保护</span><span class="sxs-lookup"><span data-stu-id="881d2-121">Disabling cloud-delivered protection</span></span>
- <span data-ttu-id="881d2-122">删除安全智能更新</span><span class="sxs-lookup"><span data-stu-id="881d2-122">Removing security intelligence updates</span></span>

### <a name="how-it-works"></a><span data-ttu-id="881d2-123">运作方式</span><span class="sxs-lookup"><span data-stu-id="881d2-123">How it works</span></span>

<span data-ttu-id="881d2-124">防篡改保护实质上Microsoft Defender 防病毒锁定和阻止通过应用和方法更改安全设置，例如：</span><span class="sxs-lookup"><span data-stu-id="881d2-124">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods such as:</span></span>

- <span data-ttu-id="881d2-125">在注册表编辑器中配置Windows设备</span><span class="sxs-lookup"><span data-stu-id="881d2-125">Configuring settings in Registry Editor on your Windows device</span></span>
- <span data-ttu-id="881d2-126">通过 PowerShell cmdlet 更改设置</span><span class="sxs-lookup"><span data-stu-id="881d2-126">Changing settings through PowerShell cmdlets</span></span>
- <span data-ttu-id="881d2-127">通过组策略编辑或删除安全设置</span><span class="sxs-lookup"><span data-stu-id="881d2-127">Editing or removing security settings through group policies</span></span>

<span data-ttu-id="881d2-128">篡改保护不会阻止您查看安全设置。</span><span class="sxs-lookup"><span data-stu-id="881d2-128">Tamper protection doesn't prevent you from viewing your security settings.</span></span> <span data-ttu-id="881d2-129">而且，防篡改保护不会影响第三方防病毒应用向 Windows 安全中心 注册。</span><span class="sxs-lookup"><span data-stu-id="881d2-129">And, tamper protection doesn't affect how third-party antivirus apps register with the Windows Security app.</span></span> <span data-ttu-id="881d2-130">如果您的组织正在使用 Windows 10 企业版 E5，则单个用户不能更改篡改保护设置;在这种情况下，防篡改保护由安全团队进行管理。</span><span class="sxs-lookup"><span data-stu-id="881d2-130">If your organization is using Windows 10 Enterprise E5, individual users can't change the tamper protection setting; in those cases, tamper protection is managed by your security team.</span></span>

### <a name="what-do-you-want-to-do"></a><span data-ttu-id="881d2-131">要执行什么操作？</span><span class="sxs-lookup"><span data-stu-id="881d2-131">What do you want to do?</span></span>

| <span data-ttu-id="881d2-132">要执行此任务...</span><span class="sxs-lookup"><span data-stu-id="881d2-132">To perform this task...</span></span> | <span data-ttu-id="881d2-133">请参阅本部分...</span><span class="sxs-lookup"><span data-stu-id="881d2-133">See this section...</span></span> |
|:---|:---|
| <span data-ttu-id="881d2-134">管理租户中的篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-134">Manage tamper protection across your tenant</span></span> <p><span data-ttu-id="881d2-135">使用Microsoft Defender 安全中心打开或关闭防篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-135">Use the Microsoft Defender Security Center to turn tamper protection on or off</span></span> | [<span data-ttu-id="881d2-136">使用管理程序管理组织的防篡改Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="881d2-136">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| <span data-ttu-id="881d2-137">在组织中微调防篡改保护设置</span><span class="sxs-lookup"><span data-stu-id="881d2-137">Fine-tune tamper protection settings in your organization</span></span> <p><span data-ttu-id="881d2-138">使用 Intune (Microsoft Endpoint Manager) 打开或关闭防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="881d2-138">Use Intune (Microsoft Endpoint Manager) to turn tamper protection on or off.</span></span> <span data-ttu-id="881d2-139">您可以使用此方法为部分或所有用户配置篡改保护。</span><span class="sxs-lookup"><span data-stu-id="881d2-139">You can configure tamper protection for some or all users with this method.</span></span> | [<span data-ttu-id="881d2-140">使用 Intune 管理组织的篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-140">Manage tamper protection for your organization using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune) |
| <span data-ttu-id="881d2-141">使用 Configuration Manager (组织) 或关闭防篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-141">Turn tamper protection on (or off) for your organization with Configuration Manager</span></span> | [<span data-ttu-id="881d2-142">使用 Configuration Manager 版本 2006 的租户附加管理组织的防篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-142">Manage tamper protection for your organization using tenant attach with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| <span data-ttu-id="881d2-143">打开或关闭 (设备) 防篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-143">Turn tamper protection on (or off) for an individual device</span></span> | [<span data-ttu-id="881d2-144">在单个设备上管理篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-144">Manage tamper protection on an individual device</span></span>](#manage-tamper-protection-on-an-individual-device) |
| <span data-ttu-id="881d2-145">查看有关设备上篡改尝试的详细信息</span><span class="sxs-lookup"><span data-stu-id="881d2-145">View details about tampering attempts on devices</span></span> | [<span data-ttu-id="881d2-146">查看有关篡改尝试的信息</span><span class="sxs-lookup"><span data-stu-id="881d2-146">View information about tampering attempts</span></span>](#view-information-about-tampering-attempts) |
| <span data-ttu-id="881d2-147">查看安全建议</span><span class="sxs-lookup"><span data-stu-id="881d2-147">Review your security recommendations</span></span> | [<span data-ttu-id="881d2-148">查看安全建议</span><span class="sxs-lookup"><span data-stu-id="881d2-148">Review security recommendations</span></span>](#review-your-security-recommendations) |
| <span data-ttu-id="881d2-149">查看常见问题解答和常见问题 (列表) </span><span class="sxs-lookup"><span data-stu-id="881d2-149">Review the list of frequently asked questions (FAQs)</span></span> | [<span data-ttu-id="881d2-150">浏览常见问题解答</span><span class="sxs-lookup"><span data-stu-id="881d2-150">Browse the FAQs</span></span>](#view-information-about-tampering-attempts) |

<span data-ttu-id="881d2-151">根据用于启用防篡改保护的方法或管理工具，MAPS 和云提供的 (可能) 。</span><span class="sxs-lookup"><span data-stu-id="881d2-151">Depending on the method or management tool you use to enable Tamper protection, there might be a dependency on MAPS (cloud-delivered protection).</span></span> 

<span data-ttu-id="881d2-152">下表提供了有关方法、工具和依赖项的详细信息。</span><span class="sxs-lookup"><span data-stu-id="881d2-152">The following table provides details on the methods, tools, and dependencies.</span></span>

| <span data-ttu-id="881d2-153">如何启用防篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-153">How Tamper protection is enabled</span></span>  | <span data-ttu-id="881d2-154">对 MAPS 的依赖 (云提供的保护) </span><span class="sxs-lookup"><span data-stu-id="881d2-154">Dependency on MAPS (cloud-delivered protection)</span></span>    |
|:----|:----|
| <span data-ttu-id="881d2-155">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="881d2-155">Microsoft Intune</span></span>  | <span data-ttu-id="881d2-156">否</span><span class="sxs-lookup"><span data-stu-id="881d2-156">No</span></span> |
| <span data-ttu-id="881d2-157">Microsoft Endpoint Configuration Manager + 租户附加</span><span class="sxs-lookup"><span data-stu-id="881d2-157">Microsoft Endpoint Configuration Manager + Tenant Attach</span></span>  |     <span data-ttu-id="881d2-158">否</span><span class="sxs-lookup"><span data-stu-id="881d2-158">No</span></span>  |
| <span data-ttu-id="881d2-159">[https://securitycenter.microsoft.com](https://securitycenter.microsoft.com)Microsoft Defender 安全中心 () </span><span class="sxs-lookup"><span data-stu-id="881d2-159">Microsoft Defender Security Center ([https://securitycenter.microsoft.com](https://securitycenter.microsoft.com))</span></span>    |     <span data-ttu-id="881d2-160">是</span><span class="sxs-lookup"><span data-stu-id="881d2-160">Yes</span></span> |
| <span data-ttu-id="881d2-161">Microsoft 365安全中心 [https://security.microsoft.com](https://security.microsoft.com) () </span><span class="sxs-lookup"><span data-stu-id="881d2-161">Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com))</span></span>  |     <span data-ttu-id="881d2-162">是</span><span class="sxs-lookup"><span data-stu-id="881d2-162">Yes</span></span>  |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a><span data-ttu-id="881d2-163">使用管理程序管理组织的防篡改Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="881d2-163">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>

<span data-ttu-id="881d2-164">可以使用 Microsoft Defender 安全中心 () 为租户打开或 [https://securitycenter.windows.com](https://securitycenter.windows.com) 关闭防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="881d2-164">Tamper protection can be turned on or off for your tenant using the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span> <span data-ttu-id="881d2-165">以下是需要记住的几点：</span><span class="sxs-lookup"><span data-stu-id="881d2-165">Here are a few points to keep in mind:</span></span>

- <span data-ttu-id="881d2-166">目前，新部署中用于管理Microsoft Defender 安全中心保护的选项默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="881d2-166">Currently, the option to manage tamper protection in the Microsoft Defender Security Center is on by default for new deployments.</span></span> <span data-ttu-id="881d2-167">对于现有部署，可选择性地使用防篡改保护，并计划在近期选择默认方法。</span><span class="sxs-lookup"><span data-stu-id="881d2-167">For existing deployments, tamper protection is available on an opt-in basis, with plans to make opting in the default method in the near future.</span></span> <span data-ttu-id="881d2-168"> (要选择加入，请选择"Microsoft Defender 安全中心"设置"  >  **高级** 功能  >  **篡改** 保护") </span><span class="sxs-lookup"><span data-stu-id="881d2-168">(To opt in, in the Microsoft Defender Security Center, choose **Settings** > **Advanced features** > **Tamper protection**.)</span></span> 

- <span data-ttu-id="881d2-169">当你使用 Microsoft Defender 安全中心管理篡改保护时，你不需要使用 Intune 或租户附加方法。</span><span class="sxs-lookup"><span data-stu-id="881d2-169">When you use the Microsoft Defender Security Center to manage tamper protection, you do not have to use Intune or the tenant attach method.</span></span>

- <span data-ttu-id="881d2-170">在 Microsoft Defender 安全中心 中管理防篡改保护时，该设置将应用于租户范围，从而影响运行 Windows 10、Windows Server 2016 或 Windows Server 2019 的所有设备。</span><span class="sxs-lookup"><span data-stu-id="881d2-170">When you manage tamper protection in the Microsoft Defender Security Center, the setting is applied tenant wide, affecting all of your devices that are running Windows 10, Windows Server 2016, or Windows Server 2019.</span></span> <span data-ttu-id="881d2-171">若要微调防篡改 (例如在某些设备上对防篡改保护，但其他设备) ，请使用[Intune](#manage-tamper-protection-for-your-organization-using-intune)或具有租户附加的[Configuration Manager。](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)</span><span class="sxs-lookup"><span data-stu-id="881d2-171">To fine-tune tamper protection (such as having tamper protection on for some devices but off for others), use either [Intune](#manage-tamper-protection-for-your-organization-using-intune) or [Configuration Manager with tenant attach](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).</span></span>

- <span data-ttu-id="881d2-172">如果你有混合环境，则 Intune 中配置的防篡改保护设置优先于在 Microsoft Defender 安全中心 中配置的设置。</span><span class="sxs-lookup"><span data-stu-id="881d2-172">If you have a hybrid environment, tamper protection settings configured in Intune take precedence over settings configured in the Microsoft Defender Security Center.</span></span> 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a><span data-ttu-id="881d2-173">管理设备中的防篡改Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="881d2-173">Requirements for managing tamper protection in the Microsoft Defender Security Center</span></span>

- <span data-ttu-id="881d2-174">您必须具有适当的 [权限](/microsoft-365/security/defender-endpoint/assign-portal-access)，例如全局管理员、安全管理员或安全操作。</span><span class="sxs-lookup"><span data-stu-id="881d2-174">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="881d2-175">你的Windows设备必须运行以下版本之一Windows：</span><span class="sxs-lookup"><span data-stu-id="881d2-175">Your Windows devices must be running one of the following versions of Windows:</span></span>
   - <span data-ttu-id="881d2-176">Windows 10</span><span class="sxs-lookup"><span data-stu-id="881d2-176">Windows 10</span></span>
   - [<span data-ttu-id="881d2-177">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="881d2-177">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
   - <span data-ttu-id="881d2-178">Windows服务器版本[1803](/windows/release-health/status-windows-10-1803)或更高版本</span><span class="sxs-lookup"><span data-stu-id="881d2-178">Windows Server, version [1803](/windows/release-health/status-windows-10-1803) or later</span></span>
   - [<span data-ttu-id="881d2-179">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="881d2-179">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016)
   - <span data-ttu-id="881d2-180">有关版本详细信息，请参阅Windows 10[发布信息](/windows/release-health/release-information)。</span><span class="sxs-lookup"><span data-stu-id="881d2-180">For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).</span></span>

- <span data-ttu-id="881d2-181">你的设备必须[载入到适用于终结点的 Microsoft Defender。](/microsoft-365/security/defender-endpoint/onboarding)</span><span class="sxs-lookup"><span data-stu-id="881d2-181">Your devices must be [onboarded to Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/onboarding).</span></span>

- <span data-ttu-id="881d2-182">你的设备必须使用反恶意软件平台版本 4.18.2010.7 (或) 及 (或) 以上的反恶意软件引擎版本 1.1.17600.5。</span><span class="sxs-lookup"><span data-stu-id="881d2-182">Your devices must be using anti-malware platform version 4.18.2010.7 (or above) and anti-malware engine version 1.1.17600.5 (or above).</span></span> <span data-ttu-id="881d2-183"> ([管理Microsoft Defender 防病毒更新和应用](manage-updates-baselines-microsoft-defender-antivirus.md)比较基准 .) </span><span class="sxs-lookup"><span data-stu-id="881d2-183">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

- <span data-ttu-id="881d2-184">[云提供的保护](enable-cloud-protection-microsoft-defender-antivirus.md) 必须打开。</span><span class="sxs-lookup"><span data-stu-id="881d2-184">[Cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be turned on.</span></span>

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a><span data-ttu-id="881d2-185">打开或关闭 (中的) 篡改Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="881d2-185">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> 

![打开防篡改保护Microsoft Defender 安全中心](images/mde-turn-tamperprotect-on.png)

1. <span data-ttu-id="881d2-187">转到 [https://securitycenter.windows.com](https://securitycenter.windows.com) "Microsoft Defender 安全中心 () 并登录。</span><span class="sxs-lookup"><span data-stu-id="881d2-187">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="881d2-188">选择 **"设置"。**</span><span class="sxs-lookup"><span data-stu-id="881d2-188">Choose **Settings**.</span></span>

3. <span data-ttu-id="881d2-189">转到"**常规**  >  **高级功能"，** 然后打开防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="881d2-189">Go to **General** > **Advanced features**, and then turn tamper protection on.</span></span>

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a><span data-ttu-id="881d2-190">使用 Intune 管理组织的篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-190">Manage tamper protection for your organization using Intune</span></span>

<span data-ttu-id="881d2-191">如果你是组织安全团队的一员，并且订阅包含[Intune，](/intune/fundamentals/what-is-intune)可以在 (上或) 上为组织在 Microsoft Endpoint Manager 管理中心中 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 。</span><span class="sxs-lookup"><span data-stu-id="881d2-191">If you are part of your organization's security team, and your subscription includes [Intune](/intune/fundamentals/what-is-intune), you can turn tamper protection on (or off) for your organization in the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)).</span></span> <span data-ttu-id="881d2-192">当你想要微调防篡改保护设置时，请使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="881d2-192">Use Intune when you want to fine-tune tamper protection settings.</span></span> <span data-ttu-id="881d2-193">例如，如果你希望在某些设备上（而不是所有设备）启用篡改保护，请使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="881d2-193">For example, if you want to enable tamper protection on some devices, but not all, use Intune.</span></span>

### <a name="requirements-for-managing-tamper-protection-in-intune"></a><span data-ttu-id="881d2-194">在 Intune 中管理防篡改保护的要求</span><span class="sxs-lookup"><span data-stu-id="881d2-194">Requirements for managing tamper protection in Intune</span></span>

- <span data-ttu-id="881d2-195">您必须具有适当的 [权限](/microsoft-365/security/defender-endpoint/assign-portal-access)，例如全局管理员、安全管理员或安全操作。</span><span class="sxs-lookup"><span data-stu-id="881d2-195">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="881d2-196">你的组织使用 [Intune 管理设备](/intune/fundamentals/what-is-device-management)。</span><span class="sxs-lookup"><span data-stu-id="881d2-196">Your organization uses [Intune to manage devices](/intune/fundamentals/what-is-device-management).</span></span> <span data-ttu-id="881d2-197"> ([Intune 许可证](/intune/fundamentals/licenses)是必需的;Intune 包含在 Microsoft 365 E5.) </span><span class="sxs-lookup"><span data-stu-id="881d2-197">([Intune licenses](/intune/fundamentals/licenses) are required; Intune is included in Microsoft 365 E5.)</span></span>

- <span data-ttu-id="881d2-198">你的Windows设备必须运行Windows 10 OS [1709、1803、1809](/windows/release-health/status-windows-10-1803)或更高版本。 [](/windows/release-health/status-windows-10-1709) [](/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="881d2-198">Your Windows devices must be running Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) or later.</span></span> <span data-ttu-id="881d2-199"> (有关版本详细信息，请参阅 Windows 10 [release information](/windows/release-health/release-information).) </span><span class="sxs-lookup"><span data-stu-id="881d2-199">(For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).)</span></span>

- <span data-ttu-id="881d2-200">必须使用安全Windows更新到版本 1.287.60.0 或 (或) 。 [](https://www.microsoft.com/wdsi/definitions)</span><span class="sxs-lookup"><span data-stu-id="881d2-200">You must be using Windows security with [security intelligence](https://www.microsoft.com/wdsi/definitions) updated to version 1.287.60.0 (or above).</span></span>

- <span data-ttu-id="881d2-201">你的设备必须使用反恶意软件平台版本 4.18.1906.3 (或) 及) 或以上的反恶意软件引擎版本 1.1.15500.X (。</span><span class="sxs-lookup"><span data-stu-id="881d2-201">Your devices must be using anti-malware platform version 4.18.1906.3 (or above) and anti-malware engine version 1.1.15500.X (or above).</span></span> <span data-ttu-id="881d2-202"> ([管理Microsoft Defender 防病毒更新和应用](manage-updates-baselines-microsoft-defender-antivirus.md)比较基准 .) </span><span class="sxs-lookup"><span data-stu-id="881d2-202">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

### <a name="turn-tamper-protection-on-or-off-in-intune"></a><span data-ttu-id="881d2-203">在 Intune 中打开 (或) 篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-203">Turn tamper protection on (or off) in Intune</span></span>

![使用 Intune 打开防篡改保护](images/turnontamperprotect-MEM.png)

1. <span data-ttu-id="881d2-205">转到管理[Microsoft Endpoint Manager](https://endpoint.microsoft.com)中心，然后使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="881d2-205">Go to the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="881d2-206">选择 **"设备**  >  **配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="881d2-206">Select **Devices** > **Configuration Profiles**.</span></span>

3. <span data-ttu-id="881d2-207">创建包含以下设置的配置文件：</span><span class="sxs-lookup"><span data-stu-id="881d2-207">Create a profile that includes the following settings:</span></span>
    - <span data-ttu-id="881d2-208">**平台：Windows 10及更高版本**</span><span class="sxs-lookup"><span data-stu-id="881d2-208">**Platform: Windows 10 and later**</span></span>
    - <span data-ttu-id="881d2-209">**配置文件类型：终结点保护**</span><span class="sxs-lookup"><span data-stu-id="881d2-209">**Profile type: Endpoint protection**</span></span>
    - <span data-ttu-id="881d2-210">**类别：Microsoft Defender 安全中心**</span><span class="sxs-lookup"><span data-stu-id="881d2-210">**Category: Microsoft Defender Security Center**</span></span>
    - <span data-ttu-id="881d2-211">**防篡改保护：已启用**</span><span class="sxs-lookup"><span data-stu-id="881d2-211">**Tamper Protection: Enabled**</span></span>

4. <span data-ttu-id="881d2-212">将配置文件分配给一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="881d2-212">Assign the profile to one or more groups.</span></span>

### <a name="are-you-using-windows-os-1709-1803-or-1809"></a><span data-ttu-id="881d2-213">是否使用 Windows OS 1709、1803 或 1809？</span><span class="sxs-lookup"><span data-stu-id="881d2-213">Are you using Windows OS 1709, 1803, or 1809?</span></span>

<span data-ttu-id="881d2-214">如果你使用的是 Windows 10 OS [1709、1803](/windows/release-health/status-windows-10-1709)或[1809，](/windows/release-health/status-windows-10-1809-and-windows-server-2019)你将看不到 Windows 安全中心保护。 [](/windows/release-health/status-windows-10-1803)</span><span class="sxs-lookup"><span data-stu-id="881d2-214">If you are using Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), or [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), you won't see **Tamper Protection** in the Windows Security app.</span></span> <span data-ttu-id="881d2-215">相反，您可以使用 PowerShell 确定是否已启用防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="881d2-215">Instead, you can use PowerShell to determine whether tamper protection is enabled.</span></span>

#### <a name="use-powershell-to-determine-whether-tamper-protection-is-turned-on"></a><span data-ttu-id="881d2-216">使用 PowerShell 确定是否启用防篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-216">Use PowerShell to determine whether tamper protection is turned on</span></span>

1. <span data-ttu-id="881d2-217">打开Windows PowerShell应用。</span><span class="sxs-lookup"><span data-stu-id="881d2-217">Open the Windows PowerShell app.</span></span>

2. <span data-ttu-id="881d2-218">使用 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="881d2-218">Use the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet.</span></span>

3. <span data-ttu-id="881d2-219">在结果列表中，查找 `IsTamperProtected` 。</span><span class="sxs-lookup"><span data-stu-id="881d2-219">In the list of results, look for `IsTamperProtected`.</span></span> <span data-ttu-id="881d2-220"> (值为 *true* 表示已启用防篡改) </span><span class="sxs-lookup"><span data-stu-id="881d2-220">(A value of *true* means tamper protection is enabled.)</span></span>

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a><span data-ttu-id="881d2-221">使用 Configuration Manager 版本 2006 管理组织的篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-221">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>

<span data-ttu-id="881d2-222">如果你使用的是 Configuration [Manager 版本 2006，](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)可以使用称为租户附加 的方法管理 Windows 10、Windows Server 2016 和 Windows Server 2019 上的防篡改 *保护设置*。</span><span class="sxs-lookup"><span data-stu-id="881d2-222">If you're using [version 2006 of Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006), you can manage tamper protection settings on Windows 10, Windows Server 2016, and Windows Server 2019 by using a method called *tenant attach*.</span></span> <span data-ttu-id="881d2-223">租户附加使你能够将仅本地 Configuration Manager 设备同步到 Microsoft Endpoint Manager 管理中心，然后将终结点安全配置策略&设备。</span><span class="sxs-lookup"><span data-stu-id="881d2-223">Tenant attach enables you to sync your on-premises-only Configuration Manager devices into the Microsoft Endpoint Manager admin center, and then deliver endpoint security configuration policies to on-premises collections & devices.</span></span>

:::image type="content" source="images/win-security- exp-policy-endpt-security.png" alt-text="Windows 安全中心体验Endpoint Manager":::

> [!NOTE]
> <span data-ttu-id="881d2-225">该过程可用于将篡改保护扩展到运行 Windows 10 server 2019 Windows设备。</span><span class="sxs-lookup"><span data-stu-id="881d2-225">The procedure can be used to extend tamper protection to devices running Windows 10 and Windows Server 2019.</span></span> <span data-ttu-id="881d2-226">请务必查看此过程中提到的资源的先决条件和其他信息。</span><span class="sxs-lookup"><span data-stu-id="881d2-226">Make sure to review the prerequisites and other information in the resources mentioned in this procedure.</span></span>

1. <span data-ttu-id="881d2-227">设置租户附加。</span><span class="sxs-lookup"><span data-stu-id="881d2-227">Set up tenant attach.</span></span> <span data-ttu-id="881d2-228">若要了解更多信息，请参阅Microsoft Endpoint Manager[附加：设备同步和设备操作](/mem/configmgr/tenant-attach/device-sync-actions)。</span><span class="sxs-lookup"><span data-stu-id="881d2-228">To learn more, see [Microsoft Endpoint Manager tenant attach: Device sync and device actions](/mem/configmgr/tenant-attach/device-sync-actions).</span></span>

2. <span data-ttu-id="881d2-229">In the [Microsoft Endpoint Manager admin center，](https://go.microsoft.com/fwlink/?linkid=2109431)go to **Endpoint security**  >  **Antivirus**， and then choose **+ Create Policy**.</span><span class="sxs-lookup"><span data-stu-id="881d2-229">In the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Endpoint security** > **Antivirus**, and then choose **+ Create Policy**.</span></span><br/> 
   - <span data-ttu-id="881d2-230">在"**平台"** 列表中，选择"Windows 10 **Windows Server (ConfigMgr) "。**</span><span class="sxs-lookup"><span data-stu-id="881d2-230">In the **Platform** list, select **Windows 10 and Windows Server (ConfigMgr)**.</span></span>  
   - <span data-ttu-id="881d2-231">在"**配置文件"** 列表中 **，Windows 安全中心预览 (体验) 。**</span><span class="sxs-lookup"><span data-stu-id="881d2-231">In the **Profile** list, select **Windows Security experience (preview)**.</span></span> <br/>

3. <span data-ttu-id="881d2-232">将策略部署到设备集合。</span><span class="sxs-lookup"><span data-stu-id="881d2-232">Deploy the policy to your device collection.</span></span>

### <a name="need-help-with-this-method"></a><span data-ttu-id="881d2-233">需要有关此方法的帮助？</span><span class="sxs-lookup"><span data-stu-id="881d2-233">Need help with this method?</span></span> 

<span data-ttu-id="881d2-234">参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="881d2-234">See the following resources:</span></span>

- [<span data-ttu-id="881d2-235">设置中Windows 安全中心体验配置文件Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="881d2-235">Settings for the Windows Security experience profile in Microsoft Intune</span></span>](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [<span data-ttu-id="881d2-236">Tech Community博客：宣布对 Configuration Manager 租户附加客户端进行篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-236">Tech Community Blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a><span data-ttu-id="881d2-237">在单个设备上管理篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-237">Manage tamper protection on an individual device</span></span>

> [!NOTE]
> <span data-ttu-id="881d2-238">篡改保护会阻止尝试Microsoft Defender 防病毒注册表修改设置。</span><span class="sxs-lookup"><span data-stu-id="881d2-238">Tamper protection blocks attempts to modify Microsoft Defender Antivirus settings through the registry.</span></span>
>
> <span data-ttu-id="881d2-239">若要帮助确保防篡改不会干扰修改这些设置的第三方安全产品或企业安装脚本，请转到 **Windows 安全中心，** 将安全智能更新到版本 1.287.60.0 或更高版本。 </span><span class="sxs-lookup"><span data-stu-id="881d2-239">To help ensure that tamper protection doesn’t interfere with third-party security products or enterprise installation scripts that modify these settings, go to **Windows Security** and update **Security intelligence** to version 1.287.60.0 or later.</span></span> <span data-ttu-id="881d2-240"> (安全 [智能更新](https://www.microsoft.com/wdsi/definitions).) </span><span class="sxs-lookup"><span data-stu-id="881d2-240">(See [Security intelligence updates](https://www.microsoft.com/wdsi/definitions).)</span></span>
>
> <span data-ttu-id="881d2-241">进行此更新后，防篡改保护将继续保护注册表设置，并且日志会尝试修改它们而不会返回错误。</span><span class="sxs-lookup"><span data-stu-id="881d2-241">Once you’ve made this update, tamper protection continues to protect your registry settings, and logs attempts to modify them without returning errors.</span></span>

<span data-ttu-id="881d2-242">如果你是家庭用户，或者不受安全团队管理的设置的干扰，可以使用 Windows 安全中心 应用管理篡改保护。</span><span class="sxs-lookup"><span data-stu-id="881d2-242">If you are a home user, or you are not subject to settings managed by a security team, you can use the Windows Security app to manage tamper protection.</span></span> <span data-ttu-id="881d2-243">必须在设备上具有相应的管理员权限才能更改安全设置，例如防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="881d2-243">You must have appropriate admin permissions on your device to do change security settings, such as tamper protection.</span></span>

<span data-ttu-id="881d2-244">下面是在应用应用中Windows 安全中心内容：</span><span class="sxs-lookup"><span data-stu-id="881d2-244">Here's what you see in the Windows Security app:</span></span>

![防篡改保护在Windows 10 家庭版](images/tamperprotectionturnedon.png)

1. <span data-ttu-id="881d2-246">选择 **"开始**"，然后开始键入 *"安全"。*</span><span class="sxs-lookup"><span data-stu-id="881d2-246">Select **Start**, and start typing *Security*.</span></span> <span data-ttu-id="881d2-247">在搜索结果中，选择 **"Windows 安全中心"。**</span><span class="sxs-lookup"><span data-stu-id="881d2-247">In the search results, select **Windows Security**.</span></span>

2. <span data-ttu-id="881d2-248">选择 **病毒&威胁防护**  >  **病毒&威胁防护设置。**</span><span class="sxs-lookup"><span data-stu-id="881d2-248">Select **Virus & threat protection** > **Virus & threat protection settings**.</span></span>

3. <span data-ttu-id="881d2-249">将 **"防篡改保护\*\*\*\*"设置为"开**"或"**关"。**</span><span class="sxs-lookup"><span data-stu-id="881d2-249">Set **Tamper Protection** to **On** or **Off**.</span></span>

## <a name="view-information-about-tampering-attempts"></a><span data-ttu-id="881d2-250">查看有关篡改尝试的信息</span><span class="sxs-lookup"><span data-stu-id="881d2-250">View information about tampering attempts</span></span>

<span data-ttu-id="881d2-251">篡改尝试通常指示更大的网络攻击。</span><span class="sxs-lookup"><span data-stu-id="881d2-251">Tampering attempts typically indicate bigger cyberattacks.</span></span> <span data-ttu-id="881d2-252">不良参与者尝试更改安全设置，作为保留和保持未检测的一种方式。</span><span class="sxs-lookup"><span data-stu-id="881d2-252">Bad actors try to change security settings as a way to persist and stay undetected.</span></span> <span data-ttu-id="881d2-253">如果你是组织安全团队的成员，可以查看有关此类尝试的信息，然后采取适当的措施缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="881d2-253">If you're part of your organization's security team, you can view information about such attempts, and then take appropriate actions to mitigate threats.</span></span>

<span data-ttu-id="881d2-254">当检测到篡改尝试时，在系统[](/microsoft-365/security/defender-endpoint/portal-overview)Microsoft Defender 安全中心 () 。 [https://securitycenter.windows.com](https://securitycenter.windows.com)</span><span class="sxs-lookup"><span data-stu-id="881d2-254">When a tampering attempt is detected, an alert is raised in the [Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/portal-overview) ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

![Microsoft Defender 安全中心](images/tamperattemptalert.png)

<span data-ttu-id="881d2-256">使用 Microsoft Defender [](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) [for](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) Endpoint 中的终结点检测和响应以及高级搜寻功能，安全运营团队可以调查和处理此类尝试。</span><span class="sxs-lookup"><span data-stu-id="881d2-256">Using [endpoint detection and response](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) and [advanced hunting](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) capabilities in Microsoft Defender for Endpoint, your security operations team can investigate and address such attempts.</span></span>

## <a name="review-your-security-recommendations"></a><span data-ttu-id="881d2-257">查看安全建议</span><span class="sxs-lookup"><span data-stu-id="881d2-257">Review your security recommendations</span></span>

<span data-ttu-id="881d2-258">防篡改保护与 [威胁&漏洞管理功能](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) 集成在一起。</span><span class="sxs-lookup"><span data-stu-id="881d2-258">Tamper protection integrates with [Threat & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) capabilities.</span></span> <span data-ttu-id="881d2-259">[安全建议](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 包括确保打开防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="881d2-259">[Security recommendations](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) include making sure tamper protection is turned on.</span></span> <span data-ttu-id="881d2-260">例如，您可以搜索 *篡改*，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="881d2-260">For example, you can search on *tamper*, as shown in the following image:</span></span>

![篡改保护会导致安全建议](/images/securityrecs-tamperprotect.jpg)

<span data-ttu-id="881d2-262">在结果中，可以选择" **打开防** 篡改保护"了解更多信息并打开它。</span><span class="sxs-lookup"><span data-stu-id="881d2-262">In the results, you can select **Turn on Tamper Protection** to learn more and turn it on.</span></span>

![打开防篡改保护](images/tamperprotectsecurityrecos.png)

<span data-ttu-id="881d2-264">若要了解有关威胁和漏洞&，请参阅威胁&[漏洞管理Microsoft Defender 安全中心。](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="881d2-264">To learn more about Threat & Vulnerability Management, see [Threat & Vulnerability Management in Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="881d2-265">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="881d2-265">Frequently asked questions</span></span>

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a><span data-ttu-id="881d2-266">操作系统Windows篡改保护适用于哪些版本？</span><span class="sxs-lookup"><span data-stu-id="881d2-266">To which Windows OS versions is configuring tamper protection is applicable?</span></span>

<span data-ttu-id="881d2-267">Windows 10OS 1709、1803、1809 或更高版本以及[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)。 [](/windows/release-health/status-windows-10-1709) [](/windows/release-health/status-windows-10-1803) [](/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="881d2-267">Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), or later together with [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

<span data-ttu-id="881d2-268">如果使用的是具有租户附加的 Configuration Manager 版本 2006，则防篡改保护可以扩展到 Windows Server 2019。</span><span class="sxs-lookup"><span data-stu-id="881d2-268">If you are using Configuration Manager, version 2006, with tenant attach, tamper protection can be extended to Windows Server 2019.</span></span> <span data-ttu-id="881d2-269">请参阅 [租户附加：从 ](/mem/configmgr/tenant-attach/deploy-antivirus-policy)管理中心创建和部署终结点安全防病毒策略 (预览) 。</span><span class="sxs-lookup"><span data-stu-id="881d2-269">See [Tenant attach: Create and deploy endpoint security Antivirus policy from the admin center (preview)](/mem/configmgr/tenant-attach/deploy-antivirus-policy).</span></span>

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a><span data-ttu-id="881d2-270">篡改保护是否将影响第三方防病毒注册？</span><span class="sxs-lookup"><span data-stu-id="881d2-270">Will tamper protection have any impact on third-party antivirus registration?</span></span>

<span data-ttu-id="881d2-271">不正确。</span><span class="sxs-lookup"><span data-stu-id="881d2-271">No.</span></span> <span data-ttu-id="881d2-272">第三方防病毒产品将继续在应用程序Windows 安全中心注册。</span><span class="sxs-lookup"><span data-stu-id="881d2-272">Third-party antivirus offerings will continue to register with the Windows Security application.</span></span>

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a><span data-ttu-id="881d2-273">如果设备Microsoft Defender 防病毒处于活动状态，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="881d2-273">What happens if Microsoft Defender Antivirus is not active on a device?</span></span>

<span data-ttu-id="881d2-274">已载入 Microsoft Defender for Endpoint 的设备将Microsoft Defender 防病毒被动模式运行。</span><span class="sxs-lookup"><span data-stu-id="881d2-274">Devices that are onboarded to Microsoft Defender for Endpoint will have Microsoft Defender Antivirus running in passive mode.</span></span> <span data-ttu-id="881d2-275">防篡改保护将继续保护服务及其功能。</span><span class="sxs-lookup"><span data-stu-id="881d2-275">Tamper protection will continue to protect the service and its features.</span></span> 

### <a name="how-can-i-turn-tamper-protection-onoff"></a><span data-ttu-id="881d2-276">如何打开/关闭防篡改保护？</span><span class="sxs-lookup"><span data-stu-id="881d2-276">How can I turn tamper protection on/off?</span></span>

<span data-ttu-id="881d2-277">如果你是家庭用户，请参阅 [在单个设备上管理篡改保护](#manage-tamper-protection-on-an-individual-device)。</span><span class="sxs-lookup"><span data-stu-id="881d2-277">If you are a home user, see [Manage tamper protection on an individual device](#manage-tamper-protection-on-an-individual-device).</span></span>

<span data-ttu-id="881d2-278">如果你是使用 [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)的组织，你应该能够在 Intune 中管理篡改保护，类似于管理其他终结点保护功能的方式。</span><span class="sxs-lookup"><span data-stu-id="881d2-278">If you are an organization using [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint), you should be able to manage tamper protection in Intune similar to how you manage other endpoint protection features.</span></span> <span data-ttu-id="881d2-279">请参阅本文的以下部分：</span><span class="sxs-lookup"><span data-stu-id="881d2-279">See the following sections of this article:</span></span> 

- [<span data-ttu-id="881d2-280">使用 Intune 管理篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-280">Manage tamper protection using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune)
- [<span data-ttu-id="881d2-281">使用 Configuration Manager 版本 2006 管理篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-281">Manage tamper protection using Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="881d2-282">使用管理程序管理防Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="881d2-282">Manage tamper protection using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) 

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a><span data-ttu-id="881d2-283">在 Intune 中配置防篡改保护如何影响我Microsoft Defender 防病毒管理策略？</span><span class="sxs-lookup"><span data-stu-id="881d2-283">How does configuring tamper protection in Intune affect how I manage Microsoft Defender Antivirus through my group policy?</span></span>

<span data-ttu-id="881d2-284">常规组策略不适用于篡改保护，当防篡改保护打开时，Microsoft Defender 防病毒更改将被忽略。</span><span class="sxs-lookup"><span data-stu-id="881d2-284">Your regular group policy doesn’t apply to tamper protection, and changes to Microsoft Defender Antivirus settings are ignored when tamper protection is on.</span></span> 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a><span data-ttu-id="881d2-285">对于 Microsoft Defender for Endpoint，在 Intune 中是否仅针对整个组织配置防篡改保护？</span><span class="sxs-lookup"><span data-stu-id="881d2-285">For Microsoft Defender for Endpoint, is configuring tamper protection in Intune targeted to the entire organization only?</span></span>

<span data-ttu-id="881d2-286">在 Intune 或 Microsoft Endpoint Manager中配置防篡改保护可以面向整个组织以及特定设备和用户组。</span><span class="sxs-lookup"><span data-stu-id="881d2-286">Configuring tamper protection in Intune or Microsoft Endpoint Manager can be targeted to your entire organization and to specific devices and user groups.</span></span>

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="881d2-287">能否在 Microsoft Endpoint Configuration Manager 中配置防篡改保护？</span><span class="sxs-lookup"><span data-stu-id="881d2-287">Can I configure Tamper Protection in Microsoft Endpoint Configuration Manager?</span></span>

<span data-ttu-id="881d2-288">如果你使用的是租户附加，可以使用租户Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="881d2-288">If you are using tenant attach, you can use Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="881d2-289">参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="881d2-289">See the following resources:</span></span>
- [<span data-ttu-id="881d2-290">使用 Configuration Manager 版本 2006 管理组织的篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-290">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="881d2-291">Tech Community博客：宣布对 Configuration Manager 租户附加客户端进行篡改保护</span><span class="sxs-lookup"><span data-stu-id="881d2-291">Tech Community blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a><span data-ttu-id="881d2-292">我已注册Windows E3。</span><span class="sxs-lookup"><span data-stu-id="881d2-292">I have the Windows E3 enrollment.</span></span> <span data-ttu-id="881d2-293">能否在 Intune 中配置篡改保护？</span><span class="sxs-lookup"><span data-stu-id="881d2-293">Can I use configuring tamper protection in Intune?</span></span>

<span data-ttu-id="881d2-294">目前，在 Intune 中配置防篡改保护仅适用于拥有 [Microsoft Defender for Endpoint 的客户](/microsoft-365/security/defender-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="881d2-294">Currently, configuring tamper protection in Intune is only available for customers who have [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a><span data-ttu-id="881d2-295">如果在设备上启用了防篡改保护，如果我尝试更改 Intune、Microsoft Endpoint Configuration Manager 和 Windows Management Instrumentation 中的 Microsoft Defender，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="881d2-295">What happens if I try to change Microsoft Defender for Endpoint settings in Intune, Microsoft Endpoint Configuration Manager, and Windows Management Instrumentation when Tamper Protection is enabled on a device?</span></span>

<span data-ttu-id="881d2-296">你无法更改受篡改保护的功能;将忽略此类更改请求。</span><span class="sxs-lookup"><span data-stu-id="881d2-296">You won’t be able to change the features that are protected by tamper protection; such change requests are ignored.</span></span>

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a><span data-ttu-id="881d2-297">我是企业客户。</span><span class="sxs-lookup"><span data-stu-id="881d2-297">I’m an enterprise customer.</span></span> <span data-ttu-id="881d2-298">本地管理员能否更改其设备的篡改保护？</span><span class="sxs-lookup"><span data-stu-id="881d2-298">Can local admins change tamper protection on their devices?</span></span>

<span data-ttu-id="881d2-299">不正确。</span><span class="sxs-lookup"><span data-stu-id="881d2-299">No.</span></span> <span data-ttu-id="881d2-300">本地管理员无法更改或修改篡改保护设置。</span><span class="sxs-lookup"><span data-stu-id="881d2-300">Local admins cannot change or modify tamper protection settings.</span></span>

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a><span data-ttu-id="881d2-301">如果我的设备已载入 Microsoft Defender for Endpoint，然后进入板载状态，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="881d2-301">What happens if my device is onboarded with Microsoft Defender for Endpoint and then goes into an off-boarded state?</span></span>

<span data-ttu-id="881d2-302">如果设备从 Microsoft Defender for Endpoint 脱离，防篡改保护将打开，这是非托管设备的默认状态。</span><span class="sxs-lookup"><span data-stu-id="881d2-302">If a device is off-boarded from Microsoft Defender for Endpoint, tamper protection is turned on, which is the default state for unmanaged devices.</span></span> 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a><span data-ttu-id="881d2-303">是否将在更新过程中收到有关篡改保护状态更改的Microsoft Defender 安全中心？</span><span class="sxs-lookup"><span data-stu-id="881d2-303">Will there be an alert about tamper protection status changing in the Microsoft Defender Security Center?</span></span>

<span data-ttu-id="881d2-304">是。</span><span class="sxs-lookup"><span data-stu-id="881d2-304">Yes.</span></span> <span data-ttu-id="881d2-305">警报显示在警报 [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) **下**。</span><span class="sxs-lookup"><span data-stu-id="881d2-305">The alert is shown in [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) under **Alerts**.</span></span>

<span data-ttu-id="881d2-306">安全运营团队还可使用搜寻查询，如以下示例：</span><span class="sxs-lookup"><span data-stu-id="881d2-306">Your security operations team can also use hunting queries, such as the following example:</span></span>

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

<span data-ttu-id="881d2-307">[查看有关篡改尝试的信息](#view-information-about-tampering-attempts)。</span><span class="sxs-lookup"><span data-stu-id="881d2-307">[View information about tampering attempts](#view-information-about-tampering-attempts).</span></span>

## <a name="see-also"></a><span data-ttu-id="881d2-308">另请参阅</span><span class="sxs-lookup"><span data-stu-id="881d2-308">See also</span></span>

[<span data-ttu-id="881d2-309">使用Windows保护Endpoint Protection保护Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="881d2-309">Help secure Windows PCs with Endpoint Protection for Microsoft Intune</span></span>](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[<span data-ttu-id="881d2-310">获取适用于终结点的 Microsoft Defender 的概述</span><span class="sxs-lookup"><span data-stu-id="881d2-310">Get an overview of Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint)

[<span data-ttu-id="881d2-311">更好地结合：Microsoft Defender 防病毒软件和 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="881d2-311">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](why-use-microsoft-defender-antivirus.md)