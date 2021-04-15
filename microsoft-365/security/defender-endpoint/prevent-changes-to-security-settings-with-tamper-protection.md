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
localization_priority: normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 84864965d7a18902a01307c1dcf373fa7c0534e8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765571"
---
# <a name="protect-security-settings-with-tamper-protection"></a><span data-ttu-id="d9b0e-104">使用篡改保护保护安全设置</span><span class="sxs-lookup"><span data-stu-id="d9b0e-104">Protect security settings with tamper protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d9b0e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-105">**Applies to:**</span></span>

- [<span data-ttu-id="d9b0e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9b0e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d9b0e-107">防篡改保护可用于运行以下 Windows 版本之一的设备：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-107">Tamper protection is available for devices that are running one of the following versions of Windows:</span></span>

- <span data-ttu-id="d9b0e-108">Windows 10</span><span class="sxs-lookup"><span data-stu-id="d9b0e-108">Windows 10</span></span>
- <span data-ttu-id="d9b0e-109">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="d9b0e-109">Windows Server 2019</span></span>
- <span data-ttu-id="d9b0e-110">Windows Server 版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d9b0e-110">Windows Server, version 1803 or later</span></span>
- <span data-ttu-id="d9b0e-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d9b0e-111">Windows Server 2016</span></span>

## <a name="overview"></a><span data-ttu-id="d9b0e-112">概述</span><span class="sxs-lookup"><span data-stu-id="d9b0e-112">Overview</span></span>

<span data-ttu-id="d9b0e-113">在某些类型的网络攻击期间，不良参与者会尝试在你的计算机上禁用安全功能，如防病毒保护。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-113">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="d9b0e-114">不良操作者希望禁用安全功能，以便更轻松地访问数据、安装恶意软件，或者以其他方式利用你的数据、标识和设备。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-114">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span> <span data-ttu-id="d9b0e-115">防篡改保护有助于防止这些类型的事件发生。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-115">Tamper protection helps prevent these kinds of things from occurring.</span></span>

<span data-ttu-id="d9b0e-116">借助防篡改保护，恶意应用可防止其采取如下操作：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-116">With tamper protection, malicious apps are prevented from taking actions such as:</span></span>

- <span data-ttu-id="d9b0e-117">禁用病毒和威胁防护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-117">Disabling virus and threat protection</span></span>
- <span data-ttu-id="d9b0e-118">禁用实时保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-118">Disabling real-time protection</span></span>
- <span data-ttu-id="d9b0e-119">关闭行为监视</span><span class="sxs-lookup"><span data-stu-id="d9b0e-119">Turning off behavior monitoring</span></span>
- <span data-ttu-id="d9b0e-120">禁用防病毒 (如 IOfficeAntivirus (IOAV) ) </span><span class="sxs-lookup"><span data-stu-id="d9b0e-120">Disabling antivirus (such as IOfficeAntivirus (IOAV))</span></span>
- <span data-ttu-id="d9b0e-121">禁用云保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-121">Disabling cloud-delivered protection</span></span>
- <span data-ttu-id="d9b0e-122">删除安全智能更新</span><span class="sxs-lookup"><span data-stu-id="d9b0e-122">Removing security intelligence updates</span></span>

### <a name="how-it-works"></a><span data-ttu-id="d9b0e-123">运作方式</span><span class="sxs-lookup"><span data-stu-id="d9b0e-123">How it works</span></span>

<span data-ttu-id="d9b0e-124">防篡改保护实质上会锁定 Microsoft Defender 防病毒，并阻止通过应用和方法更改安全设置，例如：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-124">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods such as:</span></span>

- <span data-ttu-id="d9b0e-125">在 Windows 设备的注册表编辑器中配置设置</span><span class="sxs-lookup"><span data-stu-id="d9b0e-125">Configuring settings in Registry Editor on your Windows device</span></span>
- <span data-ttu-id="d9b0e-126">通过 PowerShell cmdlet 更改设置</span><span class="sxs-lookup"><span data-stu-id="d9b0e-126">Changing settings through PowerShell cmdlets</span></span>
- <span data-ttu-id="d9b0e-127">通过组策略编辑或删除安全设置</span><span class="sxs-lookup"><span data-stu-id="d9b0e-127">Editing or removing security settings through group policies</span></span>

<span data-ttu-id="d9b0e-128">篡改保护不会阻止您查看安全设置。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-128">Tamper protection doesn't prevent you from viewing your security settings.</span></span> <span data-ttu-id="d9b0e-129">而且，防篡改保护不会影响第三方防病毒应用向 Windows 安全应用注册。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-129">And, tamper protection doesn't affect how third-party antivirus apps register with the Windows Security app.</span></span> <span data-ttu-id="d9b0e-130">如果你的组织使用的是 Windows 10 企业版 E5，则单个用户不能更改篡改保护设置;在这种情况下，防篡改保护由安全团队进行管理。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-130">If your organization is using Windows 10 Enterprise E5, individual users can't change the tamper protection setting; in those cases, tamper protection is managed by your security team.</span></span>

### <a name="what-do-you-want-to-do"></a><span data-ttu-id="d9b0e-131">要执行什么操作？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-131">What do you want to do?</span></span>

| <span data-ttu-id="d9b0e-132">要执行此任务...</span><span class="sxs-lookup"><span data-stu-id="d9b0e-132">To perform this task...</span></span> | <span data-ttu-id="d9b0e-133">请参阅本部分...</span><span class="sxs-lookup"><span data-stu-id="d9b0e-133">See this section...</span></span> |
|:---|:---|
| <span data-ttu-id="d9b0e-134">在 Microsoft Defender 安全 (打开) 或关闭防篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-134">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> <p><span data-ttu-id="d9b0e-135">管理租户中的篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-135">Manage tamper protection across your tenant</span></span> | [<span data-ttu-id="d9b0e-136">使用 Microsoft Defender 安全中心管理组织的篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-136">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| <span data-ttu-id="d9b0e-137">使用 Intune 为 (或) 或部分组织启用防篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-137">Turn tamper protection on (or off) for all or part of your organization using Intune</span></span> <p><span data-ttu-id="d9b0e-138">在组织中微调防篡改保护设置</span><span class="sxs-lookup"><span data-stu-id="d9b0e-138">Fine-tune tamper protection settings in your organization</span></span> | [<span data-ttu-id="d9b0e-139">使用 Intune 管理组织的篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-139">Manage tamper protection for your organization using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune) |
| <span data-ttu-id="d9b0e-140">使用 Configuration Manager (组织) 或关闭防篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-140">Turn tamper protection on (or off) for your organization with Configuration Manager</span></span> | [<span data-ttu-id="d9b0e-141">使用 Configuration Manager 版本 2006 的租户附加管理组织的防篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-141">Manage tamper protection for your organization using tenant attach with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| <span data-ttu-id="d9b0e-142">打开或关闭 (设备) 防篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-142">Turn tamper protection on (or off) for an individual device</span></span> | [<span data-ttu-id="d9b0e-143">在单个设备上管理篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-143">Manage tamper protection on an individual device</span></span>](#manage-tamper-protection-on-an-individual-device) |
| <span data-ttu-id="d9b0e-144">查看有关设备上篡改尝试的详细信息</span><span class="sxs-lookup"><span data-stu-id="d9b0e-144">View details about tampering attempts on devices</span></span> | [<span data-ttu-id="d9b0e-145">查看有关篡改尝试的信息</span><span class="sxs-lookup"><span data-stu-id="d9b0e-145">View information about tampering attempts</span></span>](#view-information-about-tampering-attempts) |
| <span data-ttu-id="d9b0e-146">查看安全建议</span><span class="sxs-lookup"><span data-stu-id="d9b0e-146">Review your security recommendations</span></span> | [<span data-ttu-id="d9b0e-147">查看安全建议</span><span class="sxs-lookup"><span data-stu-id="d9b0e-147">Review security recommendations</span></span>](#review-your-security-recommendations) |
| <span data-ttu-id="d9b0e-148">查看常见问题解答和常见问题 (列表) </span><span class="sxs-lookup"><span data-stu-id="d9b0e-148">Review the list of frequently asked questions (FAQs)</span></span> | [<span data-ttu-id="d9b0e-149">浏览常见问题解答</span><span class="sxs-lookup"><span data-stu-id="d9b0e-149">Browse the FAQs</span></span>](#view-information-about-tampering-attempts) |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a><span data-ttu-id="d9b0e-150">使用 Microsoft Defender 安全中心管理组织的篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-150">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>

<span data-ttu-id="d9b0e-151">可以使用 Microsoft Defender 安全中心或 () 为租户打开或 [https://securitycenter.windows.com](https://securitycenter.windows.com) 关闭防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-151">Tamper protection can be turned on or off for your tenant using the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span> <span data-ttu-id="d9b0e-152">以下是需要记住的几点：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-152">Here are a few points to keep in mind:</span></span>

- <span data-ttu-id="d9b0e-153">目前，对于新部署，Microsoft Defender 安全中心中管理防篡改保护的选项默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-153">Currently, the option to manage tamper protection in the Microsoft Defender Security Center is on by default for new deployments.</span></span> <span data-ttu-id="d9b0e-154">对于现有部署，防篡改保护在选择加入的基础上可用，并计划在近期内将这种方法设置为默认方法。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-154">For existing deployments, tamper protection is available on an opt-in basis, with plans to make this the default method in the near future.</span></span> <span data-ttu-id="d9b0e-155"> (选择加入，在 Microsoft Defender 安全中心中，选择"设置""高级功能  >    >  **篡改** 保护") </span><span class="sxs-lookup"><span data-stu-id="d9b0e-155">(To opt in, in the Microsoft Defender Security Center, choose **Settings** > **Advanced features** > **Tamper protection**.)</span></span> 

- <span data-ttu-id="d9b0e-156">使用 Microsoft Defender 安全中心管理防篡改保护时，不需要使用 Intune 或租户附加方法。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-156">When you use the Microsoft Defender Security Center to manage tamper protection, you do not have to use Intune or the tenant attach method.</span></span>

- <span data-ttu-id="d9b0e-157">在 Microsoft Defender 安全中心中管理防篡改保护时，该设置将应用于租户范围，从而影响运行 Windows 10、Windows Server 2016 或 Windows Server 2019 的所有设备。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-157">When you manage tamper protection in the Microsoft Defender Security Center, the setting is applied tenant wide, affecting all of your devices that are running Windows 10, Windows Server 2016, or Windows Server 2019.</span></span> <span data-ttu-id="d9b0e-158">若要微调防篡改 (例如在某些设备上对防篡改保护，但其他设备) ，请使用[Intune](#manage-tamper-protection-for-your-organization-using-intune)或具有租户附加的[Configuration Manager。](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)</span><span class="sxs-lookup"><span data-stu-id="d9b0e-158">To fine-tune tamper protection (such as having tamper protection on for some devices but off for others), use either [Intune](#manage-tamper-protection-for-your-organization-using-intune) or [Configuration Manager with tenant attach](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).</span></span>

- <span data-ttu-id="d9b0e-159">如果你有混合环境，则 Intune 中配置的防篡改保护设置优先于在 Microsoft Defender 安全中心配置的设置。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-159">If you have a hybrid environment, tamper protection settings configured in Intune take precedence over settings configured in the Microsoft Defender Security Center.</span></span> 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a><span data-ttu-id="d9b0e-160">在 Microsoft Defender 安全中心管理防篡改保护的要求</span><span class="sxs-lookup"><span data-stu-id="d9b0e-160">Requirements for managing tamper protection in the Microsoft Defender Security Center</span></span>

- <span data-ttu-id="d9b0e-161">您必须具有适当的 [权限](/microsoft-365/security/defender-endpoint/assign-portal-access)，例如全局管理员、安全管理员或安全操作。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-161">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="d9b0e-162">你的 Windows 设备必须运行以下 Windows 版本之一：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-162">Your Windows devices must be running one of the following versions of Windows:</span></span>
   - <span data-ttu-id="d9b0e-163">Windows 10</span><span class="sxs-lookup"><span data-stu-id="d9b0e-163">Windows 10</span></span>
   - [<span data-ttu-id="d9b0e-164">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="d9b0e-164">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
   - <span data-ttu-id="d9b0e-165">Windows Server 版本 [1803](/windows/release-health/status-windows-10-1803) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d9b0e-165">Windows Server, version [1803](/windows/release-health/status-windows-10-1803) or later</span></span>
   - [<span data-ttu-id="d9b0e-166">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d9b0e-166">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016)
   - <span data-ttu-id="d9b0e-167">有关版本详细信息，请参阅 Windows [10 版本信息](/windows/release-health/release-information)。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-167">For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).</span></span>

- <span data-ttu-id="d9b0e-168">你的设备必须[载入到适用于终结点的 Microsoft Defender。](/microsoft-365/security/defender-endpoint/onboarding)</span><span class="sxs-lookup"><span data-stu-id="d9b0e-168">Your devices must be [onboarded to Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/onboarding).</span></span>

- <span data-ttu-id="d9b0e-169">你的设备必须使用反恶意软件平台版本 4.18.2010.7 (或) 及 (或) 以上的反恶意软件引擎版本 1.1.17600.5。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-169">Your devices must be using anti-malware platform version 4.18.2010.7 (or above) and anti-malware engine version 1.1.17600.5 (or above).</span></span> <span data-ttu-id="d9b0e-170"> ([管理 Microsoft Defender 防病毒更新并应用](manage-updates-baselines-microsoft-defender-antivirus.md)基线 .) </span><span class="sxs-lookup"><span data-stu-id="d9b0e-170">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

- <span data-ttu-id="d9b0e-171">[云提供的保护](enable-cloud-protection-microsoft-defender-antivirus.md) 必须打开。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-171">[Cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be turned on.</span></span>

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a><span data-ttu-id="d9b0e-172">在 Microsoft Defender 安全 (打开) 或关闭防篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-172">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> 

![在 Microsoft Defender 安全中心中打开防篡改保护](images/mde-turn-tamperprotect-on.png)

1. <span data-ttu-id="d9b0e-174">转到 Microsoft Defender 安全中心 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-174">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="d9b0e-175">选择 **"设置"。**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-175">Choose **Settings**.</span></span>

3. <span data-ttu-id="d9b0e-176">转到"**常规**  >  **高级功能"，** 然后打开防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-176">Go to **General** > **Advanced features**, and then turn tamper protection on.</span></span>

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a><span data-ttu-id="d9b0e-177">使用 Intune 管理组织的篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-177">Manage tamper protection for your organization using Intune</span></span>

<span data-ttu-id="d9b0e-178">如果你是组织安全团队的一员，并且订阅包含 [Intune，](/intune/fundamentals/what-is-intune)可以在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com) 管理中心门户中为组织在 (或) 上打开防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-178">If you are part of your organization's security team, and your subscription includes [Intune](/intune/fundamentals/what-is-intune), you can turn tamper protection on (or off) for your organization in the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) portal.</span></span> <span data-ttu-id="d9b0e-179">当你想要微调防篡改保护设置时，请使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-179">Use Intune when you want to fine-tune tamper protection settings.</span></span> <span data-ttu-id="d9b0e-180">例如，如果你希望在某些设备上（而不是所有设备）启用篡改保护，请使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-180">For example, if you want to enable tamper protection on some devices, but not all, use Intune.</span></span>

### <a name="requirements-for-managing-tamper-protection-in-intune"></a><span data-ttu-id="d9b0e-181">在 Intune 中管理防篡改保护的要求</span><span class="sxs-lookup"><span data-stu-id="d9b0e-181">Requirements for managing tamper protection in Intune</span></span>

- <span data-ttu-id="d9b0e-182">您必须具有适当的 [权限](/microsoft-365/security/defender-endpoint/assign-portal-access)，例如全局管理员、安全管理员或安全操作。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-182">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="d9b0e-183">你的组织使用 [Intune 管理设备](/intune/fundamentals/what-is-device-management)。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-183">Your organization uses [Intune to manage devices](/intune/fundamentals/what-is-device-management).</span></span> <span data-ttu-id="d9b0e-184"> ([Intune 许可证](/intune/fundamentals/licenses) 是必需的;Intune 包含在 Microsoft 365 E5.) </span><span class="sxs-lookup"><span data-stu-id="d9b0e-184">([Intune licenses](/intune/fundamentals/licenses) are required; Intune is included in Microsoft 365 E5.)</span></span>

- <span data-ttu-id="d9b0e-185">你的 Windows 设备必须运行 Windows 10 OS 1709、1803、1809 或更高版本。 [](/windows/release-health/status-windows-10-1709) [](/windows/release-health/status-windows-10-1803) [](/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="d9b0e-185">Your Windows devices must be running Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) or later.</span></span> <span data-ttu-id="d9b0e-186"> (有关版本详细信息，请参阅 [Windows 10 版本信息](/windows/release-health/release-information).) </span><span class="sxs-lookup"><span data-stu-id="d9b0e-186">(For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).)</span></span>

- <span data-ttu-id="d9b0e-187">你必须将 Windows 安全与[](https://www.microsoft.com/wdsi/definitions)更新到版本 1.287.60.0 或 (或) 。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-187">You must be using Windows security with [security intelligence](https://www.microsoft.com/wdsi/definitions) updated to version 1.287.60.0 (or above).</span></span>

- <span data-ttu-id="d9b0e-188">你的设备必须使用反恶意软件平台版本 4.18.1906.3 (或) 及) 或以上的反恶意软件引擎版本 1.1.15500.X (。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-188">Your devices must be using anti-malware platform version 4.18.1906.3 (or above) and anti-malware engine version 1.1.15500.X (or above).</span></span> <span data-ttu-id="d9b0e-189"> ([管理 Microsoft Defender 防病毒更新并应用](manage-updates-baselines-microsoft-defender-antivirus.md)基线 .) </span><span class="sxs-lookup"><span data-stu-id="d9b0e-189">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

### <a name="turn-tamper-protection-on-or-off-in-intune"></a><span data-ttu-id="d9b0e-190">在 Intune 中打开 (或) 篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-190">Turn tamper protection on (or off) in Intune</span></span>

![使用 Intune 打开防篡改保护](images/turnontamperprotect-MEM.png)

1. <span data-ttu-id="d9b0e-192">转到 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com) ，然后使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-192">Go to the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="d9b0e-193">选择 **"设备**  >  **配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-193">Select **Devices** > **Configuration Profiles**.</span></span>

3. <span data-ttu-id="d9b0e-194">创建包含以下设置的配置文件：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-194">Create a profile that includes the following settings:</span></span>
    - <span data-ttu-id="d9b0e-195">**平台：Windows 10 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-195">**Platform: Windows 10 and later**</span></span>
    - <span data-ttu-id="d9b0e-196">**配置文件类型：终结点保护**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-196">**Profile type: Endpoint protection**</span></span>
    - <span data-ttu-id="d9b0e-197">**类别：Microsoft Defender 安全中心**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-197">**Category: Microsoft Defender Security Center**</span></span>
    - <span data-ttu-id="d9b0e-198">**防篡改保护：已启用**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-198">**Tamper Protection: Enabled**</span></span>

4. <span data-ttu-id="d9b0e-199">将配置文件分配给一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-199">Assign the profile to one or more groups.</span></span>

### <a name="are-you-using-windows-os-1709-1803-or-1809"></a><span data-ttu-id="d9b0e-200">是否使用 Windows OS 1709、1803 或 1809？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-200">Are you using Windows OS 1709, 1803, or 1809?</span></span>

<span data-ttu-id="d9b0e-201">如果你使用的是 Windows 10 OS [1709、1803](/windows/release-health/status-windows-10-1709)或 [1809，](/windows/release-health/status-windows-10-1809-and-windows-server-2019)你将看不到 Windows 安全应用中的 **防** 篡改保护。 [](/windows/release-health/status-windows-10-1803)</span><span class="sxs-lookup"><span data-stu-id="d9b0e-201">If you are using Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), or [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), you won't see **Tamper Protection** in the Windows Security app.</span></span> <span data-ttu-id="d9b0e-202">相反，您可以使用 PowerShell 确定是否已启用防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-202">Instead, you can use PowerShell to determine whether tamper protection is enabled.</span></span>

#### <a name="use-powershell-to-determine-whether-tamper-protection-is-turned-on"></a><span data-ttu-id="d9b0e-203">使用 PowerShell 确定是否启用防篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-203">Use PowerShell to determine whether tamper protection is turned on</span></span>

1. <span data-ttu-id="d9b0e-204">打开Windows PowerShell应用。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-204">Open the Windows PowerShell app.</span></span>

2. <span data-ttu-id="d9b0e-205">使用 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-205">Use the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet.</span></span>

3. <span data-ttu-id="d9b0e-206">在结果列表中，查找 `IsTamperProtected` 。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-206">In the list of results, look for `IsTamperProtected`.</span></span> <span data-ttu-id="d9b0e-207"> (值为 *true* 表示已启用防篡改) </span><span class="sxs-lookup"><span data-stu-id="d9b0e-207">(A value of *true* means tamper protection is enabled.)</span></span>

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a><span data-ttu-id="d9b0e-208">使用 Configuration Manager 版本 2006 管理组织的篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-208">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>

<span data-ttu-id="d9b0e-209">如果你使用的是 Configuration [Manager 版本 2006，](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)可以使用称为租户附加 的方法管理 Windows 10、Windows Server 2016 和 Windows Server 2019 上的防篡改 *保护设置*。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-209">If you're using [version 2006 of Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006), you can manage tamper protection settings on Windows 10, Windows Server 2016, and Windows Server 2019 by using a method called *tenant attach*.</span></span> <span data-ttu-id="d9b0e-210">租户附加使你能够将仅本地 Configuration Manager 设备同步到 Microsoft Endpoint Manager 管理中心，然后将终结点安全配置策略&设备。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-210">Tenant attach enables you to sync your on-premises-only Configuration Manager devices into the Microsoft Endpoint Manager admin center, and then deliver endpoint security configuration policies to on-premises collections & devices.</span></span>

![终结点管理器中的 Windows 安全体验](images/win-security- exp-policy-endpt-security.png)

> [!NOTE]
> <span data-ttu-id="d9b0e-212">该过程可用于将篡改保护扩展到运行 Windows 10 和 Windows Server 2019 的设备。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-212">The procedure can be used to extend tamper protection to devices running Windows 10 and Windows Server 2019.</span></span> <span data-ttu-id="d9b0e-213">请务必查看此过程中提到的资源的先决条件和其他信息。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-213">Make sure to review the prerequisites and other information in the resources mentioned in this procedure.</span></span>

1. <span data-ttu-id="d9b0e-214">设置租户附加。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-214">Set up tenant attach.</span></span> <span data-ttu-id="d9b0e-215">若要获取有关此内容的帮助，请参阅 [Microsoft Endpoint Manager 租户附加：设备同步和设备操作](/mem/configmgr/tenant-attach/device-sync-actions)。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-215">To get help with this, see [Microsoft Endpoint Manager tenant attach: Device sync and device actions](/mem/configmgr/tenant-attach/device-sync-actions).</span></span>

2. <span data-ttu-id="d9b0e-216">In the [Microsoft Endpoint Manager admin center，](https://go.microsoft.com/fwlink/?linkid=2109431)go to Endpoint **security**  >  **Antivirus**， and then choose **+ Create Policy**.</span><span class="sxs-lookup"><span data-stu-id="d9b0e-216">In the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Endpoint security** > **Antivirus**, and then choose **+ Create Policy**.</span></span><br/> 
   - <span data-ttu-id="d9b0e-217">在"**平台"** 列表中，选择 **"Windows 10"和"Windows Server (ConfigMgr) "。**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-217">In the **Platform** list, select **Windows 10 and Windows Server (ConfigMgr)**.</span></span>  
   - <span data-ttu-id="d9b0e-218">在配置文件 **列表中**，选择 **Windows 安全体验 (预览) 。**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-218">In the **Profile** list, select **Windows Security experience (preview)**.</span></span> <br/>

3. <span data-ttu-id="d9b0e-219">将策略部署到设备集合。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-219">Deploy the policy to your device collection.</span></span>

### <a name="need-help-with-this-method"></a><span data-ttu-id="d9b0e-220">需要有关此方法的帮助？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-220">Need help with this method?</span></span> 

<span data-ttu-id="d9b0e-221">参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-221">See the following resources:</span></span>

- [<span data-ttu-id="d9b0e-222">Microsoft Intune 中的 Windows 安全体验配置文件的设置</span><span class="sxs-lookup"><span data-stu-id="d9b0e-222">Settings for the Windows Security experience profile in Microsoft Intune</span></span>](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [<span data-ttu-id="d9b0e-223">技术社区博客：宣布对 Configuration Manager 租户附加客户端进行防篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-223">Tech Community Blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a><span data-ttu-id="d9b0e-224">在单个设备上管理篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-224">Manage tamper protection on an individual device</span></span>

> [!NOTE]
> <span data-ttu-id="d9b0e-225">篡改保护阻止通过注册表修改 Microsoft Defender 防病毒设置的尝试。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-225">Tamper protection blocks attempts to modify Microsoft Defender Antivirus settings through the registry.</span></span>
>
> <span data-ttu-id="d9b0e-226">若要帮助确保防篡改保护不会干扰修改这些设置的第三方安全产品或企业安装脚本，请转到 **Windows** 安全中心，将安全智能更新到版本 1.287.60.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-226">To help ensure that tamper protection doesn’t interfere with third-party security products or enterprise installation scripts that modify these settings, go to **Windows Security** and update **Security intelligence** to version 1.287.60.0 or later.</span></span> <span data-ttu-id="d9b0e-227"> (安全 [智能更新](https://www.microsoft.com/wdsi/definitions).) </span><span class="sxs-lookup"><span data-stu-id="d9b0e-227">(See [Security intelligence updates](https://www.microsoft.com/wdsi/definitions).)</span></span>
>
> <span data-ttu-id="d9b0e-228">进行此更新后，防篡改保护将继续保护注册表设置，并且日志会尝试修改它们而不会返回错误。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-228">Once you’ve made this update, tamper protection continues to protect your registry settings, and logs attempts to modify them without returning errors.</span></span>

<span data-ttu-id="d9b0e-229">如果你是家庭用户，或者不受安全团队管理的设置的干扰，可以使用 Windows 安全应用管理篡改保护。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-229">If you are a home user, or you are not subject to settings managed by a security team, you can use the Windows Security app to manage tamper protection.</span></span> <span data-ttu-id="d9b0e-230">必须在设备上具有相应的管理员权限才能更改安全设置，例如防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-230">You must have appropriate admin permissions on your device to do change security settings, such as tamper protection.</span></span>

<span data-ttu-id="d9b0e-231">以下是你在 Windows 安全应用中看到：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-231">Here's what you see in the Windows Security app:</span></span>

![Windows 10 家庭应用已打开防篡改保护](images/tamperprotectionturnedon.png)

1. <span data-ttu-id="d9b0e-233">选择 **"开始**"，然后开始键入 *"安全"。*</span><span class="sxs-lookup"><span data-stu-id="d9b0e-233">Select **Start**, and start typing *Security*.</span></span> <span data-ttu-id="d9b0e-234">在搜索结果中，选择 **"Windows 安全"。**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-234">In the search results, select **Windows Security**.</span></span>

2. <span data-ttu-id="d9b0e-235">选择 **病毒&威胁防护**  >  **病毒&威胁防护设置。**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-235">Select **Virus & threat protection** > **Virus & threat protection settings**.</span></span>

3. <span data-ttu-id="d9b0e-236">将 **"防篡改保护\*\*\*\*"设置为"开**"或"**关"。**</span><span class="sxs-lookup"><span data-stu-id="d9b0e-236">Set **Tamper Protection** to **On** or **Off**.</span></span>



## <a name="view-information-about-tampering-attempts"></a><span data-ttu-id="d9b0e-237">查看有关篡改尝试的信息</span><span class="sxs-lookup"><span data-stu-id="d9b0e-237">View information about tampering attempts</span></span>

<span data-ttu-id="d9b0e-238">篡改尝试通常指示更大的网络攻击。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-238">Tampering attempts typically indicate bigger cyberattacks.</span></span> <span data-ttu-id="d9b0e-239">不良参与者尝试更改安全设置，作为保留和保持未检测的一种方式。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-239">Bad actors try to change security settings as a way to persist and stay undetected.</span></span> <span data-ttu-id="d9b0e-240">如果你是组织安全团队的成员，可以查看有关此类尝试的信息，然后采取适当的措施缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-240">If you're part of your organization's security team, you can view information about such attempts, and then take appropriate actions to mitigate threats.</span></span>

<span data-ttu-id="d9b0e-241">当检测到篡改尝试时，Microsoft [Defender](/microsoft-365/security/defender-endpoint/portal-overview) 安全中心中将 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-241">When a tampering attempt is detected, an alert is raised in the [Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/portal-overview) ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

![Microsoft Defender 安全中心](images/tamperattemptalert.png)

<span data-ttu-id="d9b0e-243">使用 Microsoft Defender [](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) [for](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) Endpoint 中的终结点检测和响应以及高级搜寻功能，安全运营团队可以调查和处理此类尝试。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-243">Using [endpoint detection and response](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) and [advanced hunting](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) capabilities in Microsoft Defender for Endpoint, your security operations team can investigate and address such attempts.</span></span>

## <a name="review-your-security-recommendations"></a><span data-ttu-id="d9b0e-244">查看安全建议</span><span class="sxs-lookup"><span data-stu-id="d9b0e-244">Review your security recommendations</span></span>

<span data-ttu-id="d9b0e-245">防篡改保护与 [威胁&漏洞管理功能](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) 集成在一起。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-245">Tamper protection integrates with [Threat & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) capabilities.</span></span> <span data-ttu-id="d9b0e-246">[安全建议](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 包括确保打开防篡改保护。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-246">[Security recommendations](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) include making sure tamper protection is turned on.</span></span> <span data-ttu-id="d9b0e-247">例如，您可以搜索 *篡改*，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-247">For example, you can search on *tamper*, as shown in the following image:</span></span>

![篡改保护会导致安全建议](/images/securityrecs-tamperprotect.jpg)

<span data-ttu-id="d9b0e-249">在结果中，可以选择" **打开防** 篡改保护"了解更多信息并打开它。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-249">In the results, you can select **Turn on Tamper Protection** to learn more and turn it on.</span></span>

![打开防篡改保护](images/tamperprotectsecurityrecos.png)

<span data-ttu-id="d9b0e-251">若要了解有关威胁和漏洞&，请参阅 Microsoft Defender 安全& [中的威胁和漏洞管理](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-251">To learn more about Threat & Vulnerability Management, see [Threat & Vulnerability Management in Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d9b0e-252">常见问题</span><span class="sxs-lookup"><span data-stu-id="d9b0e-252">Frequently asked questions</span></span>

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a><span data-ttu-id="d9b0e-253">哪些 Windows 操作系统版本配置篡改保护适用？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-253">To which Windows OS versions is configuring tamper protection is applicable?</span></span>

<span data-ttu-id="d9b0e-254">Windows 10 OS 1709、1803、1809 或更高版本与[Microsoft Defender for Endpoint 一起](/microsoft-365/security/defender-endpoint)。 [](/windows/release-health/status-windows-10-1709) [](/windows/release-health/status-windows-10-1803) [](/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="d9b0e-254">Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), or later together with [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

<span data-ttu-id="d9b0e-255">如果你使用的是具有租户附加的 Configuration Manager 版本 2006，篡改保护可以扩展到 Windows Server 2019。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-255">If you are using Configuration Manager, version 2006, with tenant attach, tamper protection can be extended to Windows Server 2019.</span></span> <span data-ttu-id="d9b0e-256">请参阅 [租户附加：从 ](/mem/configmgr/tenant-attach/deploy-antivirus-policy)管理中心创建和部署终结点安全防病毒策略 (预览) 。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-256">See [Tenant attach: Create and deploy endpoint security Antivirus policy from the admin center (preview)](/mem/configmgr/tenant-attach/deploy-antivirus-policy).</span></span>

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a><span data-ttu-id="d9b0e-257">篡改保护是否将影响第三方防病毒注册？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-257">Will tamper protection have any impact on third-party antivirus registration?</span></span>

<span data-ttu-id="d9b0e-258">否。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-258">No.</span></span> <span data-ttu-id="d9b0e-259">第三方防病毒产品将继续向 Windows 安全应用程序注册。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-259">Third-party antivirus offerings will continue to register with the Windows Security application.</span></span>

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a><span data-ttu-id="d9b0e-260">如果 Microsoft Defender 防病毒在设备上未处于活动状态，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-260">What happens if Microsoft Defender Antivirus is not active on a device?</span></span>

<span data-ttu-id="d9b0e-261">载入 Microsoft Defender for Endpoint 的设备将在被动模式下运行 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-261">Devices that are onboarded to Microsoft Defender for Endpoint will have Microsoft Defender Antivirus running in passive mode.</span></span> <span data-ttu-id="d9b0e-262">防篡改保护将继续保护服务及其功能。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-262">Tamper protection will continue to protect the service and its features.</span></span> 

### <a name="how-can-i-turn-tamper-protection-onoff"></a><span data-ttu-id="d9b0e-263">如何打开/关闭防篡改保护？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-263">How can I turn tamper protection on/off?</span></span>

<span data-ttu-id="d9b0e-264">如果你是家庭用户，请参阅 [在单个设备上管理篡改保护](#manage-tamper-protection-on-an-individual-device)。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-264">If you are a home user, see [Manage tamper protection on an individual device](#manage-tamper-protection-on-an-individual-device).</span></span>

<span data-ttu-id="d9b0e-265">如果你是使用 [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)的组织，你应该能够在 Intune 中管理篡改保护，类似于管理其他终结点保护功能的方式。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-265">If you are an organization using [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint), you should be able to manage tamper protection in Intune similar to how you manage other endpoint protection features.</span></span> <span data-ttu-id="d9b0e-266">请参阅本文的以下部分：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-266">See the following sections of this article:</span></span> 

- [<span data-ttu-id="d9b0e-267">使用 Intune 管理篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-267">Manage tamper protection using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune)
- [<span data-ttu-id="d9b0e-268">使用 Configuration Manager 版本 2006 管理篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-268">Manage tamper protection using Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- <span data-ttu-id="d9b0e-269">[使用 Microsoft Defender 安全中心管理防篡改](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) (预览版) </span><span class="sxs-lookup"><span data-stu-id="d9b0e-269">[Manage tamper protection using the Microsoft Defender Security Center](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) (currently in preview)</span></span>

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a><span data-ttu-id="d9b0e-270">在 Intune 中配置防篡改保护如何影响我通过组策略管理 Microsoft Defender 防病毒？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-270">How does configuring tamper protection in Intune affect how I manage Microsoft Defender Antivirus through my group policy?</span></span>

<span data-ttu-id="d9b0e-271">常规组策略不适用于防篡改保护，当启用防篡改保护时，将忽略对 Microsoft Defender 防病毒设置所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-271">Your regular group policy doesn’t apply to tamper protection, and changes to Microsoft Defender Antivirus settings are ignored when tamper protection is on.</span></span> 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a><span data-ttu-id="d9b0e-272">对于 Microsoft Defender for Endpoint，在 Intune 中是否仅针对整个组织配置防篡改保护？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-272">For Microsoft Defender for Endpoint, is configuring tamper protection in Intune targeted to the entire organization only?</span></span>

<span data-ttu-id="d9b0e-273">在 Intune 或 Microsoft Endpoint Manager 中配置防篡改保护可以面向整个组织以及特定设备和用户组。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-273">Configuring tamper protection in Intune or Microsoft Endpoint Manager can be targeted to your entire organization and to specific devices and user groups.</span></span>

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="d9b0e-274">能否在 Microsoft Endpoint Configuration Manager 中配置防篡改保护？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-274">Can I configure Tamper Protection in Microsoft Endpoint Configuration Manager?</span></span>

<span data-ttu-id="d9b0e-275">如果你使用的是租户附加，可以使用 Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-275">If you are using tenant attach, you can use Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="d9b0e-276">参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-276">See the following resources:</span></span>
- [<span data-ttu-id="d9b0e-277">使用 Configuration Manager 版本 2006 管理组织的篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-277">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="d9b0e-278">技术社区博客：宣布对 Configuration Manager 租户附加客户端进行防篡改保护</span><span class="sxs-lookup"><span data-stu-id="d9b0e-278">Tech Community blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a><span data-ttu-id="d9b0e-279">我注册了 Windows E3。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-279">I have the Windows E3 enrollment.</span></span> <span data-ttu-id="d9b0e-280">能否在 Intune 中配置篡改保护？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-280">Can I use configuring tamper protection in Intune?</span></span>

<span data-ttu-id="d9b0e-281">目前，在 Intune 中配置防篡改保护仅适用于拥有 [Microsoft Defender for Endpoint 的客户](/microsoft-365/security/defender-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-281">Currently, configuring tamper protection in Intune is only available for customers who have [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a><span data-ttu-id="d9b0e-282">如果我尝试在 Intune、Microsoft Endpoint Configuration Manager 和 Windows Management Instrumentation 中更改适用于终结点设置的 Microsoft Defender，当设备上启用了防篡改保护时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-282">What happens if I try to change Microsoft Defender for Endpoint settings in Intune, Microsoft Endpoint Configuration Manager, and Windows Management Instrumentation when Tamper Protection is enabled on a device?</span></span>

<span data-ttu-id="d9b0e-283">你无法更改受篡改保护的功能;将忽略此类更改请求。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-283">You won’t be able to change the features that are protected by tamper protection; such change requests are ignored.</span></span>

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a><span data-ttu-id="d9b0e-284">我是企业客户。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-284">I’m an enterprise customer.</span></span> <span data-ttu-id="d9b0e-285">本地管理员能否更改其设备的篡改保护？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-285">Can local admins change tamper protection on their devices?</span></span>

<span data-ttu-id="d9b0e-286">否。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-286">No.</span></span> <span data-ttu-id="d9b0e-287">本地管理员无法更改或修改篡改保护设置。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-287">Local admins cannot change or modify tamper protection settings.</span></span>

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a><span data-ttu-id="d9b0e-288">如果我的设备已载入 Microsoft Defender for Endpoint，然后进入板载状态，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-288">What happens if my device is onboarded with Microsoft Defender for Endpoint and then goes into an off-boarded state?</span></span>

<span data-ttu-id="d9b0e-289">如果设备从 Microsoft Defender for Endpoint 脱离，防篡改保护将打开，这是非托管设备的默认状态。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-289">If a device is off-boarded from Microsoft Defender for Endpoint, tamper protection is turned on, which is the default state for unmanaged devices.</span></span> 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a><span data-ttu-id="d9b0e-290">是否将在 Microsoft Defender 安全中心中收到有关篡改保护状态更改的警报？</span><span class="sxs-lookup"><span data-stu-id="d9b0e-290">Will there be an alert about tamper protection status changing in the Microsoft Defender Security Center?</span></span>

<span data-ttu-id="d9b0e-291">是的。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-291">Yes.</span></span> <span data-ttu-id="d9b0e-292">警报显示在警报 [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) **下**。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-292">The alert is shown in [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) under **Alerts**.</span></span>

<span data-ttu-id="d9b0e-293">安全运营团队还可使用搜寻查询，如以下示例：</span><span class="sxs-lookup"><span data-stu-id="d9b0e-293">Your security operations team can also use hunting queries, such as the following example:</span></span>

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

<span data-ttu-id="d9b0e-294">[查看有关篡改尝试的信息](#view-information-about-tampering-attempts)。</span><span class="sxs-lookup"><span data-stu-id="d9b0e-294">[View information about tampering attempts](#view-information-about-tampering-attempts).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9b0e-295">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9b0e-295">See also</span></span>

[<span data-ttu-id="d9b0e-296">使用适用于 Microsoft Intune 的 Endpoint Protection 帮助保护 Windows 电脑</span><span class="sxs-lookup"><span data-stu-id="d9b0e-296">Help secure Windows PCs with Endpoint Protection for Microsoft Intune</span></span>](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[<span data-ttu-id="d9b0e-297">获取适用于终结点的 Microsoft Defender 的概述</span><span class="sxs-lookup"><span data-stu-id="d9b0e-297">Get an overview of Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint)

[<span data-ttu-id="d9b0e-298">更好地结合：Microsoft Defender 防病毒软件和 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9b0e-298">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](why-use-microsoft-defender-antivirus.md)