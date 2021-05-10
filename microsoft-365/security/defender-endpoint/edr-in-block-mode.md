---
title: 阻止模式下的终结点检测和响应
description: 了解阻止模式下的终结点检测和响应
keywords: Microsoft Defender for Endpoint， mde， EDR处于阻止模式， 被动模式阻止
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
ms.date: 05/08/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 86bb27005365b625ee07feaa067c0ac488c3bb4b
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302036"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a><span data-ttu-id="9cce9-104">终结点检测和响应 (EDR) 阻止模式</span><span class="sxs-lookup"><span data-stu-id="9cce9-104">Endpoint detection and response (EDR) in block mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9cce9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9cce9-105">**Applies to:**</span></span>
- [<span data-ttu-id="9cce9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9cce9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9cce9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cce9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9cce9-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="9cce9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9cce9-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="9cce9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a><span data-ttu-id="9cce9-110">阻止EDR什么？</span><span class="sxs-lookup"><span data-stu-id="9cce9-110">What is EDR in block mode?</span></span>

<span data-ttu-id="9cce9-111">[在阻止模式下 (EDR) ](overview-endpoint-detection-response.md)终结点检测和响应功能可提供对恶意项目的保护，即使 Microsoft Defender 防病毒处于被动模式时。</span><span class="sxs-lookup"><span data-stu-id="9cce9-111">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="9cce9-112">打开后，EDR模式阻止在设备上检测到的恶意项目或行为。</span><span class="sxs-lookup"><span data-stu-id="9cce9-112">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="9cce9-113">EDR阻止模式在后台工作，以修正在泄露后检测到的恶意项目。</span><span class="sxs-lookup"><span data-stu-id="9cce9-113">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span> 

<span data-ttu-id="9cce9-114">EDR模式中的用户还集成了[威胁](next-gen-threat-and-vuln-mgt.md)& 漏洞管理。</span><span class="sxs-lookup"><span data-stu-id="9cce9-114">EDR in block mode is also integrated with [threat & vulnerability management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="9cce9-115">如果组织的安全团队尚未启用，EDR启用[](tvm-security-recommendation.md)阻止模式的安全建议。</span><span class="sxs-lookup"><span data-stu-id="9cce9-115">Your organization's security team will get a [security recommendation](tvm-security-recommendation.md) to turn EDR in block mode on if it isn't already enabled.</span></span> 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="建议在阻止EDR启用此模式":::

> [!NOTE]
> <span data-ttu-id="9cce9-117">若要获取最佳保护，请确保为终结点基线 **[部署 Microsoft Defender。](configure-machines-security-baseline.md)**</span><span class="sxs-lookup"><span data-stu-id="9cce9-117">To get the best protection, make sure to **[deploy Microsoft Defender for Endpoint baselines](configure-machines-security-baseline.md)**.</span></span>

## <a name="what-happens-when-something-is-detected"></a><span data-ttu-id="9cce9-118">检测到某些内容时会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="9cce9-118">What happens when something is detected?</span></span>

<span data-ttu-id="9cce9-119">当EDR模式启用后检测到恶意项目时，适用于终结点的 Microsoft Defender 将阻止并修正这些项目。</span><span class="sxs-lookup"><span data-stu-id="9cce9-119">When EDR in block mode is turned on, and a malicious artifact is detected, Microsoft Defender for Endpoint blocks and remediates that artifact.</span></span> <span data-ttu-id="9cce9-120">安全操作团队将在操作中心中将检测状态视为"已阻止"或[](respond-machine-alerts.md#check-activity-details-in-action-center)"已阻止"，列为已完成操作。 </span><span class="sxs-lookup"><span data-stu-id="9cce9-120">Your security operations team will see detection status as **Blocked** or **Prevented** in the [Action center](respond-machine-alerts.md#check-activity-details-in-action-center), listed as completed actions.</span></span>

<span data-ttu-id="9cce9-121">下图显示了一个不需要的软件的实例，这些软件在阻止模式下通过EDR阻止：</span><span class="sxs-lookup"><span data-stu-id="9cce9-121">The following image shows an instance of unwanted software that was detected and blocked through EDR in block mode:</span></span>

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR阻止模式下检测到某些内容":::


## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="9cce9-123">启用EDR阻止模式</span><span class="sxs-lookup"><span data-stu-id="9cce9-123">Enable EDR in block mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cce9-124">在以[阻止模式](#requirements-for-edr-in-block-mode)打开应用前，EDR满足要求。</span><span class="sxs-lookup"><span data-stu-id="9cce9-124">Make sure the [requirements](#requirements-for-edr-in-block-mode) are met before turning on EDR in block mode.</span></span>

1. <span data-ttu-id="9cce9-125">转到 [https://securitycenter.windows.com](https://securitycenter.windows.com) "Microsoft Defender 安全中心 () 并登录。</span><span class="sxs-lookup"><span data-stu-id="9cce9-125">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span> 

2. <span data-ttu-id="9cce9-126">选择 **设置**  >  **高级功能"。**</span><span class="sxs-lookup"><span data-stu-id="9cce9-126">Choose **Settings** > **Advanced features**.</span></span>

3. <span data-ttu-id="9cce9-127">在阻止 **EDR启用" "。**</span><span class="sxs-lookup"><span data-stu-id="9cce9-127">Turn on **EDR in block mode**.</span></span>

> [!NOTE]
> <span data-ttu-id="9cce9-128">EDR在阻止模式下只能打开Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="9cce9-128">EDR in block mode can be turned on only in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="9cce9-129">不能使用注册表项、Intune 或组策略启用或禁用EDR阻止模式。</span><span class="sxs-lookup"><span data-stu-id="9cce9-129">You cannot use registry keys, Intune, or group policies to enable or disable EDR in block mode.</span></span>

## <a name="requirements-for-edr-in-block-mode"></a><span data-ttu-id="9cce9-130">阻止模式下EDR应用的要求</span><span class="sxs-lookup"><span data-stu-id="9cce9-130">Requirements for EDR in block mode</span></span>

|<span data-ttu-id="9cce9-131">要求</span><span class="sxs-lookup"><span data-stu-id="9cce9-131">Requirement</span></span>  |<span data-ttu-id="9cce9-132">详细信息</span><span class="sxs-lookup"><span data-stu-id="9cce9-132">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="9cce9-133">权限</span><span class="sxs-lookup"><span data-stu-id="9cce9-133">Permissions</span></span> |<span data-ttu-id="9cce9-134">全局管理员或安全管理员角色在 Azure Active Directory 中[分配](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="9cce9-134">Global Administrator or Security Administrator role assigned in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span> <span data-ttu-id="9cce9-135">请参阅 [基本权限](basic-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="9cce9-135">See [Basic permissions](basic-permissions.md).</span></span> |
|<span data-ttu-id="9cce9-136">操作系统</span><span class="sxs-lookup"><span data-stu-id="9cce9-136">Operating system</span></span>     |<span data-ttu-id="9cce9-137">以下版本之一：</span><span class="sxs-lookup"><span data-stu-id="9cce9-137">One of the following versions:</span></span> <br/><span data-ttu-id="9cce9-138">- Windows 10 (所有) </span><span class="sxs-lookup"><span data-stu-id="9cce9-138">- Windows 10 (all releases)</span></span> <br/><span data-ttu-id="9cce9-139">- Windows Server 版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="9cce9-139">- Windows Server, version 1803 or newer</span></span> <br/><span data-ttu-id="9cce9-140">- Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="9cce9-140">- Windows Server 2019</span></span> <br/><span data-ttu-id="9cce9-141">- Windows Server 2016 (仅在Microsoft Defender 防病毒处于活动状态时) </span><span class="sxs-lookup"><span data-stu-id="9cce9-141">- Windows Server 2016 (only when Microsoft Defender Antivirus is in active mode)</span></span>     |
|<span data-ttu-id="9cce9-142">WindowsE5 注册</span><span class="sxs-lookup"><span data-stu-id="9cce9-142">Windows E5 enrollment</span></span>     |<span data-ttu-id="9cce9-143">WindowsE5 包含在以下订阅中：</span><span class="sxs-lookup"><span data-stu-id="9cce9-143">Windows E5 is included in the following subscriptions:</span></span> <br/><span data-ttu-id="9cce9-144">- Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="9cce9-144">- Microsoft 365 E5</span></span> <br/><span data-ttu-id="9cce9-145">- Microsoft 365 E3 Identity &威胁防护产品一起</span><span class="sxs-lookup"><span data-stu-id="9cce9-145">- Microsoft 365 E3 together with the Identity & Threat Protection offering</span></span> <br/><br/><span data-ttu-id="9cce9-146">请参阅[每个](/microsoft-365/enterprise/microsoft-365-overview#components)[计划的组件和功能](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="9cce9-146">See [Components](/microsoft-365/enterprise/microsoft-365-overview#components) and [features and capabilities for each plan](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>       |
|<span data-ttu-id="9cce9-147">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="9cce9-147">Microsoft Defender Antivirus</span></span>  |<span data-ttu-id="9cce9-148">Microsoft Defender 防病毒在主动模式或被动模式下安装和运行。</span><span class="sxs-lookup"><span data-stu-id="9cce9-148">Microsoft Defender Antivirus must be installed and running in either active mode or passive mode.</span></span> <span data-ttu-id="9cce9-149"> (可以一Microsoft Defender 防病毒 Microsoft 防病毒解决方案一起使用。) [确认Microsoft Defender 防病毒处于主动或被动模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="9cce9-149">(You can use Microsoft Defender Antivirus alongside a non-Microsoft antivirus solution.) [Confirm Microsoft Defender Antivirus is in active or passive mode](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).</span></span> |
|<span data-ttu-id="9cce9-150">云端保护</span><span class="sxs-lookup"><span data-stu-id="9cce9-150">Cloud-delivered protection</span></span> |<span data-ttu-id="9cce9-151">请确保Microsoft Defender 防病毒配置云保护，以[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="9cce9-151">Make sure Microsoft Defender Antivirus is configured such that [cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span> |
|<span data-ttu-id="9cce9-152">Microsoft Defender 防病毒反恶意软件客户端</span><span class="sxs-lookup"><span data-stu-id="9cce9-152">Microsoft Defender Antivirus antimalware client</span></span> |<span data-ttu-id="9cce9-153">确保你的客户端是最新的。</span><span class="sxs-lookup"><span data-stu-id="9cce9-153">Make sure your client is up to date.</span></span> <span data-ttu-id="9cce9-154">使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9cce9-154">Using PowerShell, run the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet as an administrator.</span></span> <span data-ttu-id="9cce9-155">在 **AMProductVersion** 行中，应该会看到 **4.18.2001.10** 或更上方。</span><span class="sxs-lookup"><span data-stu-id="9cce9-155">In the **AMProductVersion** line, you should see **4.18.2001.10** or above.</span></span> |
|<span data-ttu-id="9cce9-156">Microsoft Defender 防病毒引擎</span><span class="sxs-lookup"><span data-stu-id="9cce9-156">Microsoft Defender Antivirus engine</span></span> |<span data-ttu-id="9cce9-157">确保你的引擎是最新的。</span><span class="sxs-lookup"><span data-stu-id="9cce9-157">Make sure your engine is up to date.</span></span> <span data-ttu-id="9cce9-158">使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9cce9-158">Using PowerShell, run the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet as an administrator.</span></span> <span data-ttu-id="9cce9-159">在 **AMEngineVersion** 行中，应该会看到 **1.1.16700.2** 或更上方。</span><span class="sxs-lookup"><span data-stu-id="9cce9-159">In the **AMEngineVersion** line, you should see **1.1.16700.2** or above.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="9cce9-160">若要获取最佳保护值，请确保防病毒解决方案配置为接收定期更新和基本功能，并且已配置排除 [项](configure-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="9cce9-160">To get the best protection value, make sure your antivirus solution is configured to receive regular updates and essential features, and that your [exclusions are configured](configure-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="9cce9-161">EDR模式中的策略将遵守为阻止模式定义的Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="9cce9-161">EDR in block mode respects exclusions that are defined for Microsoft Defender Antivirus.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="9cce9-162">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="9cce9-162">Frequently asked questions</span></span> 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a><span data-ttu-id="9cce9-163">我是否需要在阻止EDR打开状态，即使我在设备上Microsoft Defender 防病毒运行？</span><span class="sxs-lookup"><span data-stu-id="9cce9-163">Do I need to turn EDR in block mode on even when I have Microsoft Defender Antivirus running on devices?</span></span>

<span data-ttu-id="9cce9-164">我们建议保持EDR模式处于打开状态，Microsoft Defender 防病毒被动模式还是主动模式运行。</span><span class="sxs-lookup"><span data-stu-id="9cce9-164">We recommend keeping EDR in block mode on, whether Microsoft Defender Antivirus is running in passive mode or in active mode.</span></span> <span data-ttu-id="9cce9-165">EDR模式使用 Microsoft Defender for Endpoint 提供另一层防御。</span><span class="sxs-lookup"><span data-stu-id="9cce9-165">EDR in block mode provides another layer of defense with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9cce9-166">它允许 Defender for Endpoint 根据攻破后的行为和检测EDR操作。</span><span class="sxs-lookup"><span data-stu-id="9cce9-166">It allows Defender for Endpoint to take actions based on post-breach behavioral EDR detections.</span></span> 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a><span data-ttu-id="9cce9-167">EDR模式是否对用户的防病毒保护有任何影响？</span><span class="sxs-lookup"><span data-stu-id="9cce9-167">Will EDR in block mode have any impact on a user's antivirus protection?</span></span> 

<span data-ttu-id="9cce9-168">EDR模式运行不会影响在用户设备上运行的第三方防病毒保护。</span><span class="sxs-lookup"><span data-stu-id="9cce9-168">EDR in block mode does not affect third-party antivirus protection running on users' devices.</span></span> <span data-ttu-id="9cce9-169">EDR如果主防病毒解决方案遗漏了某些内容，或者存在泄露后检测，则以阻止模式运行。</span><span class="sxs-lookup"><span data-stu-id="9cce9-169">EDR in block mode works if the primary antivirus solution misses something, or if there is a post-breach detection.</span></span> <span data-ttu-id="9cce9-170">EDR模式运行方式与被动Microsoft Defender 防病毒中的阻止操作类似，但它也会阻止和修正检测到的恶意项目或行为。</span><span class="sxs-lookup"><span data-stu-id="9cce9-170">EDR in block mode works just like Microsoft Defender Antivirus in passive mode, except it also blocks and remediates malicious artifacts or behaviors that are detected.</span></span>

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a><span data-ttu-id="9cce9-171">为什么我需要使Microsoft Defender 防病毒保持最新？</span><span class="sxs-lookup"><span data-stu-id="9cce9-171">Why do I need to keep Microsoft Defender Antivirus up to date?</span></span> 

<span data-ttu-id="9cce9-172">由于Microsoft Defender 防病毒检测并修正恶意项目，因此保持最新很重要。</span><span class="sxs-lookup"><span data-stu-id="9cce9-172">Because Microsoft Defender Antivirus detects and remediates malicious items, it's important to keep it up to date.</span></span> <span data-ttu-id="9cce9-173">为了EDR模式运行，它使用最新的设备学习模型、行为检测和启发。</span><span class="sxs-lookup"><span data-stu-id="9cce9-173">For EDR in block mode to be effective, it uses the latest device learning models, behavioral detections, and heuristics.</span></span> <span data-ttu-id="9cce9-174">[Defender for Endpoint](microsoft-defender-endpoint.md)功能堆栈以集成方式工作。</span><span class="sxs-lookup"><span data-stu-id="9cce9-174">The [Defender for Endpoint](microsoft-defender-endpoint.md) stack of capabilities works in an integrated manner.</span></span> <span data-ttu-id="9cce9-175">若要获得最佳保护值，Microsoft Defender 防病毒保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="9cce9-175">To get best protection value, you should keep Microsoft Defender Antivirus up to date.</span></span> <span data-ttu-id="9cce9-176">请参阅[管理Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="9cce9-176">See [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> 

### <a name="why-do-we-need-cloud-protection-on"></a><span data-ttu-id="9cce9-177">为什么需要云保护？</span><span class="sxs-lookup"><span data-stu-id="9cce9-177">Why do we need cloud protection on?</span></span> 

<span data-ttu-id="9cce9-178">需要云保护才能在设备上启用该功能。</span><span class="sxs-lookup"><span data-stu-id="9cce9-178">Cloud protection is needed to turn on the feature on the device.</span></span> <span data-ttu-id="9cce9-179">云保护 [允许 Defender for Endpoint](microsoft-defender-endpoint.md) 基于安全智能的广度和深度以及行为和设备学习模型提供最新且最丰富的保护。</span><span class="sxs-lookup"><span data-stu-id="9cce9-179">Cloud protection allows [Defender for Endpoint](microsoft-defender-endpoint.md) to deliver the latest and greatest protection based on our breadth and depth of security intelligence, along with behavioral and device learning models.</span></span>

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="9cce9-180">如何将用户Microsoft Defender 防病毒被动模式？</span><span class="sxs-lookup"><span data-stu-id="9cce9-180">How do I set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="9cce9-181">根据操作系统，当运行非 Microsoft 防病毒/反恶意软件解决方案的设备载入 Defender for Endpoint 时，Microsoft Defender 防病毒自动进入被动模式。</span><span class="sxs-lookup"><span data-stu-id="9cce9-181">Depending on operating systems, when devices that are running a non-Microsoft antivirus/antimalware solution are onboarded to Defender for Endpoint, Microsoft Defender Antivirus can go into passive mode automatically.</span></span> <span data-ttu-id="9cce9-182">有关详细信息，请参阅如何Microsoft Defender 防病毒[Defender for Endpoint 功能](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality)。</span><span class="sxs-lookup"><span data-stu-id="9cce9-182">For more information, see [How Microsoft Defender Antivirus affects Defender for Endpoint functionality](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality).</span></span> 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a><span data-ttu-id="9cce9-183">如何确认Microsoft Defender 防病毒处于主动或被动模式？</span><span class="sxs-lookup"><span data-stu-id="9cce9-183">How do I confirm Microsoft Defender Antivirus is in active or passive mode?</span></span>

<span data-ttu-id="9cce9-184">若要确认Microsoft Defender 防病毒处于主动或被动模式，可以在运行命令提示符或 PowerShell 的设备上Windows。</span><span class="sxs-lookup"><span data-stu-id="9cce9-184">To confirm whether Microsoft Defender Antivirus is running in active or passive mode, you can use Command Prompt or PowerShell on a device running Windows.</span></span>


|<span data-ttu-id="9cce9-185">方法</span><span class="sxs-lookup"><span data-stu-id="9cce9-185">Method</span></span>  |<span data-ttu-id="9cce9-186">Procedure</span><span class="sxs-lookup"><span data-stu-id="9cce9-186">Procedure</span></span>  |
|---------|---------|
| <span data-ttu-id="9cce9-187">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cce9-187">PowerShell</span></span>     | <span data-ttu-id="9cce9-188">1. 选择"开始"菜单，开始键入 `PowerShell` ，然后在Windows PowerShell中打开" 开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="9cce9-188">1. Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span> <p><span data-ttu-id="9cce9-189">2. 键入 `Get-MpComputerStatus` 。</span><span class="sxs-lookup"><span data-stu-id="9cce9-189">2. Type `Get-MpComputerStatus`.</span></span> <p><span data-ttu-id="9cce9-190">3. 在结果列表中，在 **AMRunningMode** 行中查找下列值之一：</span><span class="sxs-lookup"><span data-stu-id="9cce9-190">3. In the list of results, in the **AMRunningMode** row, look for one of the following values:</span></span> <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p><span data-ttu-id="9cce9-191">若要了解更多信息，请参阅 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="9cce9-191">To learn more, see [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span></span>        |
|<span data-ttu-id="9cce9-192">命令提示符</span><span class="sxs-lookup"><span data-stu-id="9cce9-192">Command Prompt</span></span>     | <span data-ttu-id="9cce9-193">1. 选择"开始"菜单，开始键入 ，然后在Windows `Command Prompt` 打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="9cce9-193">1. Select the Start menu, begin typing `Command Prompt`, and then open Windows Command Prompt in the results.</span></span> <p><span data-ttu-id="9cce9-194">2. 键入 `sc query windefend` 。</span><span class="sxs-lookup"><span data-stu-id="9cce9-194">2. Type `sc query windefend`.</span></span> <p><span data-ttu-id="9cce9-195">3. 在结果列表中的 **"状态** "行中，确认服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="9cce9-195">3. In the list of results, in the **STATE** row, confirm that the service is running.</span></span>         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a><span data-ttu-id="9cce9-196">在阻止模式下禁用EDR需要的时间？</span><span class="sxs-lookup"><span data-stu-id="9cce9-196">How much time does it take for EDR in block mode to be disabled?</span></span>

<span data-ttu-id="9cce9-197">如果选择在阻止EDR禁用此功能，则系统最多可能需要 30 分钟才能禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="9cce9-197">If you chose to disable EDR in block mode, it can take up to 30 minutes for the system to disable this capability.</span></span>

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a><span data-ttu-id="9cce9-198">EDR上是否支持阻止Windows Server 2016？</span><span class="sxs-lookup"><span data-stu-id="9cce9-198">Is EDR in block mode supported on Windows Server 2016?</span></span>

<span data-ttu-id="9cce9-199">如果Microsoft Defender 防病毒模式或被动模式下运行，EDR支持以下版本的 Windows：</span><span class="sxs-lookup"><span data-stu-id="9cce9-199">If Microsoft Defender Antivirus is running in active mode or passive mode, EDR in block mode is supported of the following versions of Windows:</span></span>

- <span data-ttu-id="9cce9-200">Windows 10 (所有版本) </span><span class="sxs-lookup"><span data-stu-id="9cce9-200">Windows 10 (all releases)</span></span>
- <span data-ttu-id="9cce9-201">Windows服务器版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="9cce9-201">Windows Server, version 1803 or newer</span></span> 
- <span data-ttu-id="9cce9-202">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="9cce9-202">Windows Server 2019</span></span> 

<span data-ttu-id="9cce9-203">如果Windows Server 2016在Microsoft Defender 防病毒模式下运行，并且终结点已载入到 Defender for Endpoint，则EDR支持以阻止模式运行。</span><span class="sxs-lookup"><span data-stu-id="9cce9-203">If Windows Server 2016 has Microsoft Defender Antivirus running in active mode, and the endpoint is onboarded to Defender for Endpoint, then EDR in block mode is technically supported.</span></span> <span data-ttu-id="9cce9-204">但是，EDR阻止模式旨在当终结点上不是Microsoft Defender 防病毒防病毒解决方案时提供额外保护。</span><span class="sxs-lookup"><span data-stu-id="9cce9-204">However, EDR in block mode is intended to be extra protection when Microsoft Defender Antivirus is not the primary antivirus solution on an endpoint.</span></span> <span data-ttu-id="9cce9-205">在这种情况下，Microsoft Defender 防病毒被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="9cce9-205">In those cases, Microsoft Defender Antivirus runs in passive mode.</span></span> <span data-ttu-id="9cce9-206">目前，Microsoft Defender 防病毒在被动模式下运行 Windows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="9cce9-206">Currently, running Microsoft Defender Antivirus in passive mode is not supported on Windows Server 2016.</span></span> <span data-ttu-id="9cce9-207">若要了解更多信息，请参阅[Microsoft Defender 防病毒和非 Microsoft 防病毒/反恶意软件解决方案](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)。</span><span class="sxs-lookup"><span data-stu-id="9cce9-207">To learn more, see [Microsoft Defender Antivirus and non-Microsoft antivirus/antimalware solutions](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions).</span></span>

## <a name="see-also"></a><span data-ttu-id="9cce9-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9cce9-208">See also</span></span>

- [<span data-ttu-id="9cce9-209">Tech Community博客：在EDR模式下进行介绍：停止跟踪攻击</span><span class="sxs-lookup"><span data-stu-id="9cce9-209">Tech Community blog: Introducing EDR in block mode: Stopping attacks in their tracks</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [<span data-ttu-id="9cce9-210">行为阻止和控制</span><span class="sxs-lookup"><span data-stu-id="9cce9-210">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

