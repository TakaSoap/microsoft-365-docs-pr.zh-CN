---
title: 阻止模式下的终结点检测和响应
description: 了解阻止模式下的终结点检测和响应
keywords: Microsoft Defender ATP，阻止模式下的 EDR，被动模式阻止
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 01/26/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 7bee6c99d2c1c5ad3cec8f2e317b729a0a4e1f8b
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379474"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a><span data-ttu-id="85ebe-104">在阻止模式下， (EDR) 终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="85ebe-104">Endpoint detection and response (EDR) in block mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="85ebe-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="85ebe-105">**Applies to:**</span></span>
- [<span data-ttu-id="85ebe-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="85ebe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="85ebe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85ebe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="85ebe-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="85ebe-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="85ebe-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="85ebe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a><span data-ttu-id="85ebe-110">什么是阻止模式下的 EDR？</span><span class="sxs-lookup"><span data-stu-id="85ebe-110">What is EDR in block mode?</span></span>

<span data-ttu-id="85ebe-111">[在阻止模式下](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) 终结点检测和响应功能可提供对恶意项目的保护，即使 Microsoft Defender 防病毒在被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="85ebe-111">[Endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="85ebe-112">打开后，阻止模式下的 EDR 将阻止在设备上检测到的恶意项目或行为。</span><span class="sxs-lookup"><span data-stu-id="85ebe-112">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="85ebe-113">阻止模式下的 EDR 在后台工作，可修正在泄露后检测到的恶意项目。</span><span class="sxs-lookup"><span data-stu-id="85ebe-113">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span> 

<span data-ttu-id="85ebe-114">阻止模式下的 EDR 也与威胁和漏洞& [集成](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)。</span><span class="sxs-lookup"><span data-stu-id="85ebe-114">EDR in block mode is also integrated with [threat & vulnerability management](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="85ebe-115">如果尚未启用 EDR，组织[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)的安全团队会获得一条安全建议，以在阻止模式下打开它。</span><span class="sxs-lookup"><span data-stu-id="85ebe-115">Your organization's security team will get a [security recommendation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) to turn EDR in block mode on if it isn't already enabled.</span></span> 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="建议在阻止模式下打开 EDR":::

> [!NOTE]
> <span data-ttu-id="85ebe-117">若要获取最佳保护，请确保为终结点基线 **[部署 Microsoft Defender。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**</span><span class="sxs-lookup"><span data-stu-id="85ebe-117">To get the best protection, make sure to **[deploy Microsoft Defender for Endpoint baselines](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**.</span></span>

## <a name="what-happens-when-something-is-detected"></a><span data-ttu-id="85ebe-118">检测到某些内容时会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="85ebe-118">What happens when something is detected?</span></span>

<span data-ttu-id="85ebe-119">当在阻止模式下打开 EDR 并检测到恶意项目时，适用于终结点的 Microsoft Defender 将阻止并修正这些项目。</span><span class="sxs-lookup"><span data-stu-id="85ebe-119">When EDR in block mode is turned on, and a malicious artifact is detected, Microsoft Defender for Endpoint blocks and remediates that artifact.</span></span> <span data-ttu-id="85ebe-120">你将在操作中心看到检测状态为"已阻止"或 **"** 已阻止"为已完成 [操作](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)。</span><span class="sxs-lookup"><span data-stu-id="85ebe-120">You'll see detection status as **Blocked** or **Prevented** as completed actions in the [Action center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center).</span></span>

<span data-ttu-id="85ebe-121">下图显示了在阻止模式下通过 EDR 检测并阻止的不需要软件的实例：</span><span class="sxs-lookup"><span data-stu-id="85ebe-121">The following image shows an instance of unwanted software that was detected and blocked through EDR in block mode:</span></span>

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="阻止模式下的 EDR 检测到某些内容":::


## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="85ebe-123">在阻止模式下启用 EDR</span><span class="sxs-lookup"><span data-stu-id="85ebe-123">Enable EDR in block mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85ebe-124">在阻止 [模式下打开](#requirements-for-edr-in-block-mode) EDR 之前，请确保满足要求。</span><span class="sxs-lookup"><span data-stu-id="85ebe-124">Make sure the [requirements](#requirements-for-edr-in-block-mode) are met before turning on EDR in block mode.</span></span>

1. <span data-ttu-id="85ebe-125">转到 Microsoft Defender 安全中心 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="85ebe-125">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span> 

2. <span data-ttu-id="85ebe-126">选择 **"设置**  >  **""高级功能"。**</span><span class="sxs-lookup"><span data-stu-id="85ebe-126">Choose **Settings** > **Advanced features**.</span></span>

3. <span data-ttu-id="85ebe-127">在阻止 **模式下打开 EDR。**</span><span class="sxs-lookup"><span data-stu-id="85ebe-127">Turn on **EDR in block mode**.</span></span>

> [!NOTE]
> <span data-ttu-id="85ebe-128">阻止模式下的 EDR 只能在 Microsoft Defender 安全中心中打开。</span><span class="sxs-lookup"><span data-stu-id="85ebe-128">EDR in block mode can be turned on only in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="85ebe-129">不能使用注册表项、Intune 或组策略在阻止模式下启用或禁用 EDR。</span><span class="sxs-lookup"><span data-stu-id="85ebe-129">You cannot use registry keys, Intune, or group policies to enable or disable EDR in block mode.</span></span>

## <a name="requirements-for-edr-in-block-mode"></a><span data-ttu-id="85ebe-130">阻止模式下的 EDR 要求</span><span class="sxs-lookup"><span data-stu-id="85ebe-130">Requirements for EDR in block mode</span></span>

|<span data-ttu-id="85ebe-131">要求</span><span class="sxs-lookup"><span data-stu-id="85ebe-131">Requirement</span></span>  |<span data-ttu-id="85ebe-132">详细信息</span><span class="sxs-lookup"><span data-stu-id="85ebe-132">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="85ebe-133">权限</span><span class="sxs-lookup"><span data-stu-id="85ebe-133">Permissions</span></span> |<span data-ttu-id="85ebe-134">在 Azure Active Directory 中分配的全局管理员或 [安全管理员角色](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="85ebe-134">Global Administrator or Security Administrator role assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span> <span data-ttu-id="85ebe-135">请参阅 [基本权限](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions)。</span><span class="sxs-lookup"><span data-stu-id="85ebe-135">See [Basic permissions](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions).</span></span> |
|<span data-ttu-id="85ebe-136">操作系统</span><span class="sxs-lookup"><span data-stu-id="85ebe-136">Operating system</span></span>     |<span data-ttu-id="85ebe-137">以下版本之一：</span><span class="sxs-lookup"><span data-stu-id="85ebe-137">One of the following versions:</span></span> <br/><span data-ttu-id="85ebe-138">- Windows 10 (所有版本) </span><span class="sxs-lookup"><span data-stu-id="85ebe-138">- Windows 10 (all releases)</span></span> <br/><span data-ttu-id="85ebe-139">- Windows Server 版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="85ebe-139">- Windows Server, version 1803 or newer</span></span> <br/><span data-ttu-id="85ebe-140">- Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="85ebe-140">- Windows Server 2019</span></span>         |
|<span data-ttu-id="85ebe-141">Windows E5 注册</span><span class="sxs-lookup"><span data-stu-id="85ebe-141">Windows E5 enrollment</span></span>     |<span data-ttu-id="85ebe-142">Windows E5 包含在以下订阅中：</span><span class="sxs-lookup"><span data-stu-id="85ebe-142">Windows E5 is included in the following subscriptions:</span></span> <br/><span data-ttu-id="85ebe-143">- Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="85ebe-143">- Microsoft 365 E5</span></span> <br/><span data-ttu-id="85ebe-144">- Microsoft 365 E3 以及 Identity &威胁防护产品</span><span class="sxs-lookup"><span data-stu-id="85ebe-144">- Microsoft 365 E3 together with the Identity & Threat Protection offering</span></span> <br/><br/><span data-ttu-id="85ebe-145">请参阅[每个](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components)[计划的组件和功能](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="85ebe-145">See [Components](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) and [features and capabilities for each plan](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>       |
|<span data-ttu-id="85ebe-146">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="85ebe-146">Microsoft Defender Antivirus</span></span>  |<span data-ttu-id="85ebe-147">必须在主动模式或被动模式下安装并运行 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="85ebe-147">Microsoft Defender Antivirus must be installed and running in either active mode or passive mode.</span></span> <span data-ttu-id="85ebe-148"> (可以将 Microsoft Defender 防病毒与非 Microsoft 防病毒解决方案一同使用。) 确认 Microsoft Defender 防病毒 [处于主动或被动模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="85ebe-148">(You can use Microsoft Defender Antivirus alongside a non-Microsoft antivirus solution.) [Confirm Microsoft Defender Antivirus is in active or passive mode](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).</span></span> |
|<span data-ttu-id="85ebe-149">云保护</span><span class="sxs-lookup"><span data-stu-id="85ebe-149">Cloud-delivered protection</span></span> |<span data-ttu-id="85ebe-150">确保配置了 Microsoft Defender 防病毒，以启用 [云保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="85ebe-150">Make sure Microsoft Defender Antivirus is configured such that [cloud-delivered protection is enabled](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus).</span></span> |
|<span data-ttu-id="85ebe-151">Microsoft Defender 防病毒反恶意软件客户端</span><span class="sxs-lookup"><span data-stu-id="85ebe-151">Microsoft Defender Antivirus antimalware client</span></span> |<span data-ttu-id="85ebe-152">确保你的客户端是最新的。</span><span class="sxs-lookup"><span data-stu-id="85ebe-152">Make sure your client is up to date.</span></span> <span data-ttu-id="85ebe-153">使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="85ebe-153">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="85ebe-154">在 **AMProductVersion** 行中，应该会看到 **4.18.2001.10** 或更上方。</span><span class="sxs-lookup"><span data-stu-id="85ebe-154">In the **AMProductVersion** line, you should see **4.18.2001.10** or above.</span></span> |
|<span data-ttu-id="85ebe-155">Microsoft Defender 防病毒引擎</span><span class="sxs-lookup"><span data-stu-id="85ebe-155">Microsoft Defender Antivirus engine</span></span> |<span data-ttu-id="85ebe-156">确保你的引擎是最新的。</span><span class="sxs-lookup"><span data-stu-id="85ebe-156">Make sure your engine is up to date.</span></span> <span data-ttu-id="85ebe-157">使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="85ebe-157">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="85ebe-158">在 **AMEngineVersion** 行中，应该会看到 **1.1.16700.2** 或更上方。</span><span class="sxs-lookup"><span data-stu-id="85ebe-158">In the **AMEngineVersion** line, you should see **1.1.16700.2** or above.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="85ebe-159">若要获取最佳保护值，请确保防病毒解决方案配置为接收定期更新和基本功能，并且已配置排除 [项](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="85ebe-159">To get the best protection value, make sure your antivirus solution is configured to receive regular updates and essential features, and that your [exclusions are configured](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="85ebe-160">阻止模式下的 EDR 遵守为 Microsoft Defender 防病毒定义的排除项。</span><span class="sxs-lookup"><span data-stu-id="85ebe-160">EDR in block mode respects exclusions that are defined for Microsoft Defender Antivirus.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="85ebe-161">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="85ebe-161">Frequently asked questions</span></span> 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a><span data-ttu-id="85ebe-162">我是否需要在阻止模式下打开 EDR，即使我在设备上运行 Microsoft Defender 防病毒？</span><span class="sxs-lookup"><span data-stu-id="85ebe-162">Do I need to turn EDR in block mode on even when I have Microsoft Defender Antivirus running on devices?</span></span>

<span data-ttu-id="85ebe-163">我们建议在阻止模式下保持 EDR 处于打开状态，无论 Microsoft Defender 防病毒是在被动模式下运行还是处于活动模式。</span><span class="sxs-lookup"><span data-stu-id="85ebe-163">We recommend keeping EDR in block mode on, whether Microsoft Defender Antivirus is running in passive mode or in active mode.</span></span> <span data-ttu-id="85ebe-164">块模式下的 EDR 通过 Microsoft Defender for Endpoint 提供另一层防御。</span><span class="sxs-lookup"><span data-stu-id="85ebe-164">EDR in block mode provides another layer of defense with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="85ebe-165">它允许 Defender for Endpoint 根据攻破后的行为 EDR 检测采取操作。</span><span class="sxs-lookup"><span data-stu-id="85ebe-165">It allows Defender for Endpoint to take actions based on post-breach behavioral EDR detections.</span></span> 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a><span data-ttu-id="85ebe-166">阻止模式下的 EDR 是否将影响用户的防病毒保护？</span><span class="sxs-lookup"><span data-stu-id="85ebe-166">Will EDR in block mode have any impact on a user's antivirus protection?</span></span> 

<span data-ttu-id="85ebe-167">阻止模式下的 EDR 不会影响在用户设备上运行的第三方防病毒保护。</span><span class="sxs-lookup"><span data-stu-id="85ebe-167">EDR in block mode does not affect third-party antivirus protection running on users' devices.</span></span> <span data-ttu-id="85ebe-168">如果主防病毒解决方案遗漏了某些内容，或者存在泄露后检测，则阻止模式下的 EDR 可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="85ebe-168">EDR in block mode works if the primary antivirus solution misses something, or if there is a post-breach detection.</span></span> <span data-ttu-id="85ebe-169">阻止模式下的 EDR 的工作方式与被动模式下 [的 Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)的工作方式类似，但它也会阻止和修正检测到的恶意项目或行为。</span><span class="sxs-lookup"><span data-stu-id="85ebe-169">EDR in block mode works just like [Microsoft Defender Antivirus in passive mode](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state), except it also blocks and remediates malicious artifacts or behaviors that are detected.</span></span> 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a><span data-ttu-id="85ebe-170">为什么需要使 Microsoft Defender 防病毒保持最新状态？</span><span class="sxs-lookup"><span data-stu-id="85ebe-170">Why do I need to keep Microsoft Defender Antivirus up to date?</span></span> 

<span data-ttu-id="85ebe-171">由于 Microsoft Defender 防病毒会检测并修正恶意项目，因此保持其最新状态非常重要。</span><span class="sxs-lookup"><span data-stu-id="85ebe-171">Because Microsoft Defender Antivirus detects and remediates malicious items, it's important to keep it up to date.</span></span> <span data-ttu-id="85ebe-172">为了在块模式中实现 EDR 有效，它使用最新的设备学习模型、行为检测和启发。</span><span class="sxs-lookup"><span data-stu-id="85ebe-172">For EDR in block mode to be effective, it uses the latest device learning models, behavioral detections, and heuristics.</span></span> <span data-ttu-id="85ebe-173">[Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection)功能堆栈以集成方式工作。</span><span class="sxs-lookup"><span data-stu-id="85ebe-173">The [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) stack of capabilities works in an integrated manner.</span></span> <span data-ttu-id="85ebe-174">若要获得最佳保护价值，应使 Microsoft Defender 防病毒保持最新。</span><span class="sxs-lookup"><span data-stu-id="85ebe-174">To get best protection value, you should keep Microsoft Defender Antivirus up to date.</span></span>  

### <a name="why-do-we-need-cloud-protection-on"></a><span data-ttu-id="85ebe-175">为什么需要云保护？</span><span class="sxs-lookup"><span data-stu-id="85ebe-175">Why do we need cloud protection on?</span></span> 

<span data-ttu-id="85ebe-176">需要云保护才能在设备上启用该功能。</span><span class="sxs-lookup"><span data-stu-id="85ebe-176">Cloud protection is needed to turn on the feature on the device.</span></span> <span data-ttu-id="85ebe-177">云保护 [允许 Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) 基于安全智能的广度和深度以及行为和设备学习模型提供最新且最丰富的保护。</span><span class="sxs-lookup"><span data-stu-id="85ebe-177">Cloud protection allows [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) to deliver the latest and greatest protection based on our breadth and depth of security intelligence, along with behavioral and device learning models.</span></span>

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="85ebe-178">如何将 Microsoft Defender 防病毒设置为被动模式？</span><span class="sxs-lookup"><span data-stu-id="85ebe-178">How do I set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="85ebe-179">请参阅 [启用 Microsoft Defender 防病毒并确认它处于被动模式](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="85ebe-179">See [Enable Microsoft Defender Antivirus and confirm it's in passive mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode).</span></span>

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a><span data-ttu-id="85ebe-180">如何确认 Microsoft Defender 防病毒处于主动或被动模式？</span><span class="sxs-lookup"><span data-stu-id="85ebe-180">How do I confirm Microsoft Defender Antivirus is in active or passive mode?</span></span>

<span data-ttu-id="85ebe-181">若要确认 Microsoft Defender 防病毒是在主动模式还是被动模式下运行，可以在运行 Windows 的设备上使用命令提示符或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="85ebe-181">To confirm whether Microsoft Defender Antivirus is running in active or passive mode, you can use Command Prompt or PowerShell on a device running Windows.</span></span>

#### <a name="use-powershell"></a><span data-ttu-id="85ebe-182">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="85ebe-182">Use PowerShell</span></span>

1. <span data-ttu-id="85ebe-183">选择"开始"菜单，开始键入 `PowerShell` ，然后Windows PowerShell结果中的"开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="85ebe-183">Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span>

2. <span data-ttu-id="85ebe-184">类型 `Get-MpComputerStatus`。</span><span class="sxs-lookup"><span data-stu-id="85ebe-184">Type `Get-MpComputerStatus`.</span></span>

3. <span data-ttu-id="85ebe-185">在结果列表中，在 **AMRunningMode** 行中查找下列值之一：</span><span class="sxs-lookup"><span data-stu-id="85ebe-185">In the list of results, in the **AMRunningMode** row, look for one of the following values:</span></span>   
   - `Normal`
   - `Passive Mode`  
   - `SxS Passive Mode`

<span data-ttu-id="85ebe-186">若要了解更多信息，请参阅 [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="85ebe-186">To learn more, see [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus).</span></span>

#### <a name="use-command-prompt"></a><span data-ttu-id="85ebe-187">使用命令提示符</span><span class="sxs-lookup"><span data-stu-id="85ebe-187">Use Command Prompt</span></span>

1. <span data-ttu-id="85ebe-188">选择"开始"菜单，开始键入 `Command Prompt` ，然后在结果中打开 Windows 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="85ebe-188">Select the Start menu, begin typing `Command Prompt`, and then open Windows Command Prompt in the results.</span></span>

2. <span data-ttu-id="85ebe-189">类型 `sc query windefend`。</span><span class="sxs-lookup"><span data-stu-id="85ebe-189">Type `sc query windefend`.</span></span>

3. <span data-ttu-id="85ebe-190">在结果列表中的 **"状态** "行中，确认服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="85ebe-190">In the list of results, in the **STATE** row, confirm that the service is running.</span></span>

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a><span data-ttu-id="85ebe-191">在阻止模式下禁用 EDR 需要的时间？</span><span class="sxs-lookup"><span data-stu-id="85ebe-191">How much time does it take for EDR in block mode to be disabled?</span></span>
<span data-ttu-id="85ebe-192">如果选择在阻止模式下禁用 EDR，则系统最多可能需要 30 分钟才能禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="85ebe-192">If you chose to disable EDR in block mode it can take up to 30 minutes for the system to disable this capability.</span></span>

## <a name="see-also"></a><span data-ttu-id="85ebe-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85ebe-193">See also</span></span>

- [<span data-ttu-id="85ebe-194">技术社区博客：在阻止模式下引入 EDR：停止其跟踪中的攻击</span><span class="sxs-lookup"><span data-stu-id="85ebe-194">Tech Community blog: Introducing EDR in block mode: Stopping attacks in their tracks</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [<span data-ttu-id="85ebe-195">行为阻止和抑制</span><span class="sxs-lookup"><span data-stu-id="85ebe-195">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)
- [<span data-ttu-id="85ebe-196">更好地结合：Microsoft Defender 防病毒和 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="85ebe-196">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

