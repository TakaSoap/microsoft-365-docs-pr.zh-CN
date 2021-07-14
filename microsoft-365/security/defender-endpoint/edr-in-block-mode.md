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
ms.date: 07/13/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 1915a57becb1cba14605f4512ff123c1bca846bb
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415595"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a><span data-ttu-id="563c1-104">终结点检测和响应 (EDR) 阻止模式</span><span class="sxs-lookup"><span data-stu-id="563c1-104">Endpoint detection and response (EDR) in block mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="563c1-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="563c1-105">**Applies to:**</span></span>
- [<span data-ttu-id="563c1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="563c1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="563c1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="563c1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="563c1-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="563c1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="563c1-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="563c1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a><span data-ttu-id="563c1-110">阻止EDR什么？</span><span class="sxs-lookup"><span data-stu-id="563c1-110">What is EDR in block mode?</span></span>

<span data-ttu-id="563c1-111">[当终结点检测和响应](overview-endpoint-detection-response.md) (EDR) 处于阻止模式时，如果终结点Microsoft Defender 防病毒防病毒产品，并且正在被动模式下运行，可以针对恶意项目提供额外的保护。</span><span class="sxs-lookup"><span data-stu-id="563c1-111">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR) in block mode provides added protection from malicious artifacts when Microsoft Defender Antivirus is not the primary antivirus product and is running in passive mode.</span></span> <span data-ttu-id="563c1-112">EDR阻止模式修复使用阻止模式检测到的恶意EDR。</span><span class="sxs-lookup"><span data-stu-id="563c1-112">EDR in block mode remediates malicious artifacts that are detected using EDR.</span></span> <span data-ttu-id="563c1-113">此类项目可能已被主要的非 Microsoft 防病毒产品错过。</span><span class="sxs-lookup"><span data-stu-id="563c1-113">Such artifacts might have been missed by the primary, non-Microsoft antivirus product.</span></span> <span data-ttu-id="563c1-114">EDR阻止模式在后台工作，以修正在设备中检测到的泄露后的恶意项目。</span><span class="sxs-lookup"><span data-stu-id="563c1-114">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected, post breach, on a device.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="563c1-115">EDR阻止模式时，不会提供启用实时Microsoft Defender 防病毒时可用的所有保护。</span><span class="sxs-lookup"><span data-stu-id="563c1-115">EDR in block mode does not provide all the protection that is available when Microsoft Defender Antivirus real-time protection is enabled.</span></span> <span data-ttu-id="563c1-116">依赖于要成为Microsoft Defender 防病毒防病毒解决方案的所有功能将不起作用，包括以下关键示例：</span><span class="sxs-lookup"><span data-stu-id="563c1-116">All features that depend on Microsoft Defender Antivirus to be the active antivirus solution will not work, including the following key examples:</span></span> 
> 
> - <span data-ttu-id="563c1-117">实时保护（包括访问时扫描）在用户处于被动Microsoft Defender 防病毒不可用。</span><span class="sxs-lookup"><span data-stu-id="563c1-117">Real-time protection, including on-access scanning, is not available when Microsoft Defender Antivirus is in passive mode.</span></span> <span data-ttu-id="563c1-118">若要了解有关实时保护策略设置的信息，请参阅启用 **[和配置Microsoft Defender 防病毒始终启用保护](configure-real-time-protection-microsoft-defender-antivirus.md)**。</span><span class="sxs-lookup"><span data-stu-id="563c1-118">To learn more about real-time protection policy settings, see **[Enable and configure Microsoft Defender Antivirus always-on protection](configure-real-time-protection-microsoft-defender-antivirus.md)**.</span></span>
> - <span data-ttu-id="563c1-119">网络 **[保护和](network-protection.md)** 攻击面减少 **[规则](attack-surface-reduction.md)** 等功能仅在网络Microsoft Defender 防病毒模式运行时可用。</span><span class="sxs-lookup"><span data-stu-id="563c1-119">Features like **[network protection](network-protection.md)** and **[attack surface reduction rules](attack-surface-reduction.md)** are only available when Microsoft Defender Antivirus is running in active mode.</span></span> 
> 
> <span data-ttu-id="563c1-120">预计非 Microsoft 防病毒解决方案会提供这些功能。</span><span class="sxs-lookup"><span data-stu-id="563c1-120">It is expected that your non-Microsoft antivirus solution provides these capabilities.</span></span> 

<span data-ttu-id="563c1-121">EDR阻止模式下的已与威胁& 漏洞管理[集成](next-gen-threat-and-vuln-mgt.md)。</span><span class="sxs-lookup"><span data-stu-id="563c1-121">EDR in block mode is integrated with [threat & vulnerability management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="563c1-122">如果组织的安全团队尚未启用，EDR启用[](tvm-security-recommendation.md)阻止模式的安全建议。</span><span class="sxs-lookup"><span data-stu-id="563c1-122">Your organization's security team will get a [security recommendation](tvm-security-recommendation.md) to turn EDR in block mode on if it isn't already enabled.</span></span> 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="建议在阻止EDR启用此模式":::

> [!TIP]
> <span data-ttu-id="563c1-124">若要获取最佳保护，请确保为终结点基线 **[部署 Microsoft Defender。](configure-machines-security-baseline.md)**</span><span class="sxs-lookup"><span data-stu-id="563c1-124">To get the best protection, make sure to **[deploy Microsoft Defender for Endpoint baselines](configure-machines-security-baseline.md)**.</span></span>

## <a name="what-happens-when-something-is-detected"></a><span data-ttu-id="563c1-125">检测到某些内容时会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="563c1-125">What happens when something is detected?</span></span>

<span data-ttu-id="563c1-126">当EDR模式启用后检测到恶意项目时，适用于终结点的 Microsoft Defender 将阻止并修正这些项目。</span><span class="sxs-lookup"><span data-stu-id="563c1-126">When EDR in block mode is turned on, and a malicious artifact is detected, Microsoft Defender for Endpoint blocks and remediates that artifact.</span></span> <span data-ttu-id="563c1-127">安全操作团队将在操作中心中将检测状态视为"已阻止"或[](respond-machine-alerts.md#check-activity-details-in-action-center)"已阻止"，列为已完成操作。 </span><span class="sxs-lookup"><span data-stu-id="563c1-127">Your security operations team will see detection status as **Blocked** or **Prevented** in the [Action center](respond-machine-alerts.md#check-activity-details-in-action-center), listed as completed actions.</span></span>

<span data-ttu-id="563c1-128">下图显示了一个不需要的软件的实例，这些软件在阻止模式下通过EDR阻止：</span><span class="sxs-lookup"><span data-stu-id="563c1-128">The following image shows an instance of unwanted software that was detected and blocked through EDR in block mode:</span></span>

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR阻止模式下检测到某些内容":::


## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="563c1-130">启用EDR阻止模式</span><span class="sxs-lookup"><span data-stu-id="563c1-130">Enable EDR in block mode</span></span>

> [!TIP]
> <span data-ttu-id="563c1-131">在以[阻止模式](#requirements-for-edr-in-block-mode)打开应用前，EDR满足要求。</span><span class="sxs-lookup"><span data-stu-id="563c1-131">Make sure the [requirements](#requirements-for-edr-in-block-mode) are met before turning on EDR in block mode.</span></span>

1. <span data-ttu-id="563c1-132">转到"Microsoft 365 Defender门户 [https://security.microsoft.com/](https://security.microsoft.com/) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="563c1-132">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com/](https://security.microsoft.com/)) and sign in.</span></span> 

2. <span data-ttu-id="563c1-133">Choose **设置**  >  **Endpoints**  >  **General**  >  **Advanced features**.</span><span class="sxs-lookup"><span data-stu-id="563c1-133">Choose **Settings** > **Endpoints** > **General** > **Advanced features**.</span></span>

3. <span data-ttu-id="563c1-134">向下滚动，然后在"在块EDR **启用 urln。**</span><span class="sxs-lookup"><span data-stu-id="563c1-134">Scroll down, and then urn on **Enable EDR in block mode**.</span></span>

> [!NOTE]
> <span data-ttu-id="563c1-135">EDR在阻止模式下只能打开 Microsoft 365 Defender 门户 () [https://security.microsoft.com](https://security.microsoft.com) 或之前 [https://securitycenter.windows.com](https://securitycenter.windows.com) Microsoft Defender 安全中心 () 。</span><span class="sxs-lookup"><span data-stu-id="563c1-135">EDR in block mode can be turned on only in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) or the former Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span> <span data-ttu-id="563c1-136">不能使用注册表项、Microsoft Intune或组策略来启用或禁用EDR阻止模式。</span><span class="sxs-lookup"><span data-stu-id="563c1-136">You cannot use registry keys, Microsoft Intune, or Group Policy to enable or disable EDR in block mode.</span></span>

## <a name="requirements-for-edr-in-block-mode"></a><span data-ttu-id="563c1-137">阻止模式下EDR应用的要求</span><span class="sxs-lookup"><span data-stu-id="563c1-137">Requirements for EDR in block mode</span></span>

| <span data-ttu-id="563c1-138">要求</span><span class="sxs-lookup"><span data-stu-id="563c1-138">Requirement</span></span>  | <span data-ttu-id="563c1-139">详细信息</span><span class="sxs-lookup"><span data-stu-id="563c1-139">Details</span></span>  |
|---------|---------|
| <span data-ttu-id="563c1-140">权限</span><span class="sxs-lookup"><span data-stu-id="563c1-140">Permissions</span></span> | <span data-ttu-id="563c1-141">您必须具有全局管理员或安全管理员角色分配[在Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="563c1-141">You must have the Global Administrator or Security Administrator role assigned in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span> <span data-ttu-id="563c1-142">有关详细信息，请参阅 [基本权限](basic-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="563c1-142">For more information, see [Basic permissions](basic-permissions.md).</span></span> |
| <span data-ttu-id="563c1-143">操作系统</span><span class="sxs-lookup"><span data-stu-id="563c1-143">Operating system</span></span>     | <span data-ttu-id="563c1-144">设备必须运行以下版本之一Windows：</span><span class="sxs-lookup"><span data-stu-id="563c1-144">Devices must be running one of the following versions of Windows:</span></span> <br/><span data-ttu-id="563c1-145">- Windows 10 (所有) </span><span class="sxs-lookup"><span data-stu-id="563c1-145">- Windows 10 (all releases)</span></span> <br/><span data-ttu-id="563c1-146">- Windows Server 版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="563c1-146">- Windows Server, version 1803 or newer</span></span> <br/><span data-ttu-id="563c1-147">- Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="563c1-147">- Windows Server 2019</span></span> <br/><span data-ttu-id="563c1-148">- Windows Server 2016 (仅在Microsoft Defender 防病毒处于活动状态时) </span><span class="sxs-lookup"><span data-stu-id="563c1-148">- Windows Server 2016 (only when Microsoft Defender Antivirus is in active mode)</span></span>     |
| <span data-ttu-id="563c1-149">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="563c1-149">Microsoft Defender for Endpoint</span></span>     | <span data-ttu-id="563c1-150">设备必须载入到适用于终结点的 Defender。</span><span class="sxs-lookup"><span data-stu-id="563c1-150">Devices must be onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="563c1-151">请参阅 [Microsoft Defender for Endpoint 的最低要求](minimum-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="563c1-151">See [Minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md).</span></span>       |
| <span data-ttu-id="563c1-152">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="563c1-152">Microsoft Defender Antivirus</span></span>  | <span data-ttu-id="563c1-153">设备必须已安装Microsoft Defender 防病毒在主动模式或被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="563c1-153">Devices must have Microsoft Defender Antivirus installed and running in either active mode or passive mode.</span></span> <span data-ttu-id="563c1-154">[确认Microsoft Defender 防病毒处于主动或被动模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="563c1-154">[Confirm Microsoft Defender Antivirus is in active or passive mode](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).</span></span> |
| <span data-ttu-id="563c1-155">云端保护</span><span class="sxs-lookup"><span data-stu-id="563c1-155">Cloud-delivered protection</span></span> | <span data-ttu-id="563c1-156">Microsoft Defender 防病毒配置云保护，以[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="563c1-156">Microsoft Defender Antivirus must be configured such that [cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span> |
| <span data-ttu-id="563c1-157">Microsoft Defender 防病毒平台</span><span class="sxs-lookup"><span data-stu-id="563c1-157">Microsoft Defender Antivirus platform</span></span> | <span data-ttu-id="563c1-158">设备必须是最新的。</span><span class="sxs-lookup"><span data-stu-id="563c1-158">Devices must be up to date.</span></span> <span data-ttu-id="563c1-159">若要确认，使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="563c1-159">To confirm, using PowerShell, run the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet as an administrator.</span></span> <span data-ttu-id="563c1-160">在 **AMProductVersion** 行中，应该会看到 **4.18.2001.10** 或更上方。</span><span class="sxs-lookup"><span data-stu-id="563c1-160">In the **AMProductVersion** line, you should see **4.18.2001.10** or above.</span></span> <p> <span data-ttu-id="563c1-161">要了解详细信息，请参阅 [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="563c1-161">To learn more, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> |
| <span data-ttu-id="563c1-162">Microsoft Defender 防病毒引擎</span><span class="sxs-lookup"><span data-stu-id="563c1-162">Microsoft Defender Antivirus engine</span></span> | <span data-ttu-id="563c1-163">设备必须是最新的。</span><span class="sxs-lookup"><span data-stu-id="563c1-163">Devices must be up to date.</span></span> <span data-ttu-id="563c1-164">若要确认，使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="563c1-164">To confirm, using PowerShell, run the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet as an administrator.</span></span> <span data-ttu-id="563c1-165">在 **AMEngineVersion** 行中，应该会看到 **1.1.16700.2** 或更上方。</span><span class="sxs-lookup"><span data-stu-id="563c1-165">In the **AMEngineVersion** line, you should see **1.1.16700.2** or above.</span></span> <p> <span data-ttu-id="563c1-166">要了解详细信息，请参阅 [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="563c1-166">To learn more, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="563c1-167">若要获取最佳保护值，请确保防病毒解决方案配置为接收定期更新和基本功能，并且已配置排除 [项](configure-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="563c1-167">To get the best protection value, make sure your antivirus solution is configured to receive regular updates and essential features, and that your [exclusions are configured](configure-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="563c1-168">EDR模式配置遵守为用户定义的排除Microsoft Defender 防病毒，但不包括为 Microsoft Defender for Endpoint[](manage-indicators.md)定义的指示器。</span><span class="sxs-lookup"><span data-stu-id="563c1-168">EDR in block mode respects exclusions that are defined for Microsoft Defender Antivirus, but not [indicators](manage-indicators.md) that are defined for Microsoft Defender for Endpoint.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="563c1-169">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="563c1-169">Frequently asked questions</span></span> 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a><span data-ttu-id="563c1-170">如果我在设备上运行EDR，是否需要在阻止Microsoft Defender 防病毒打开？</span><span class="sxs-lookup"><span data-stu-id="563c1-170">Do I need to turn EDR in block mode on if I have Microsoft Defender Antivirus running on devices?</span></span>

<span data-ttu-id="563c1-171">在阻止模式下EDR的主要用途是修正非 Microsoft 防病毒产品错过的泄露后检测。</span><span class="sxs-lookup"><span data-stu-id="563c1-171">The primary purpose of EDR in block mode is to remediate post-breach detections that were missed by a non-Microsoft antivirus product.</span></span> <span data-ttu-id="563c1-172">但是，我们建议保持EDR模式处于打开状态，Microsoft Defender 防病毒被动模式还是主动模式运行。</span><span class="sxs-lookup"><span data-stu-id="563c1-172">However, we recommend keeping EDR in block mode turned on, whether Microsoft Defender Antivirus is running in passive mode or in active mode.</span></span> 

- <span data-ttu-id="563c1-173">当Microsoft Defender 防病毒处于被动模式时，EDR模式中的用户与 Microsoft Defender for Endpoint 一起提供另一层防御。</span><span class="sxs-lookup"><span data-stu-id="563c1-173">When Microsoft Defender Antivirus is in passive mode, EDR in block mode provides another layer of defense together with Microsoft Defender for Endpoint.</span></span> 
- <span data-ttu-id="563c1-174">当Microsoft Defender 防病毒活动模式时，EDR阻止模式不会提供额外的扫描，但它允许 Defender for Endpoint 对攻破后的行为和检测自动EDR操作。</span><span class="sxs-lookup"><span data-stu-id="563c1-174">When Microsoft Defender Antivirus is in active mode, EDR in block mode does not provide extra scanning, but it does allow Defender for Endpoint to take automatic actions on post-breach, behavioral EDR detections.</span></span>

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a><span data-ttu-id="563c1-175">EDR阻止模式是否会影响用户的防病毒保护？</span><span class="sxs-lookup"><span data-stu-id="563c1-175">Will EDR in block mode affect a user's antivirus protection?</span></span> 

<span data-ttu-id="563c1-176">EDR模式运行不会影响在用户设备上运行的第三方防病毒保护。</span><span class="sxs-lookup"><span data-stu-id="563c1-176">EDR in block mode does not affect third-party antivirus protection running on users' devices.</span></span> <span data-ttu-id="563c1-177">EDR如果主防病毒解决方案遗漏了某些内容，或者存在泄露后检测，则以阻止模式运行。</span><span class="sxs-lookup"><span data-stu-id="563c1-177">EDR in block mode works if the primary antivirus solution misses something, or if there is a post-breach detection.</span></span> <span data-ttu-id="563c1-178">EDR模式配置的工作方式与被动模式下Microsoft Defender 防病毒一样，只不过EDR模式下的阻止模式也会阻止和修正检测到的恶意项目或行为。</span><span class="sxs-lookup"><span data-stu-id="563c1-178">EDR in block mode works just like Microsoft Defender Antivirus in passive mode, except that EDR in block mode also blocks and remediates malicious artifacts or behaviors that are detected.</span></span>

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a><span data-ttu-id="563c1-179">为什么我需要使Microsoft Defender 防病毒保持最新？</span><span class="sxs-lookup"><span data-stu-id="563c1-179">Why do I need to keep Microsoft Defender Antivirus up to date?</span></span> 

<span data-ttu-id="563c1-180">由于Microsoft Defender 防病毒检测并修正恶意项目，因此保持最新很重要。</span><span class="sxs-lookup"><span data-stu-id="563c1-180">Because Microsoft Defender Antivirus detects and remediates malicious items, it's important to keep it up to date.</span></span> <span data-ttu-id="563c1-181">为了EDR模式运行，它使用最新的设备学习模型、行为检测和启发。</span><span class="sxs-lookup"><span data-stu-id="563c1-181">For EDR in block mode to be effective, it uses the latest device learning models, behavioral detections, and heuristics.</span></span> <span data-ttu-id="563c1-182">[Defender for Endpoint](microsoft-defender-endpoint.md)功能堆栈以集成方式工作。</span><span class="sxs-lookup"><span data-stu-id="563c1-182">The [Defender for Endpoint](microsoft-defender-endpoint.md) stack of capabilities works in an integrated manner.</span></span> <span data-ttu-id="563c1-183">若要获得最佳保护值，Microsoft Defender 防病毒保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="563c1-183">To get best protection value, you should keep Microsoft Defender Antivirus up to date.</span></span> <span data-ttu-id="563c1-184">请参阅[管理Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="563c1-184">See [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> 

### <a name="why-do-we-need-cloud-protection-maps-on"></a><span data-ttu-id="563c1-185">为什么需要云保护 (MAPS) 打开？</span><span class="sxs-lookup"><span data-stu-id="563c1-185">Why do we need cloud protection (MAPS) on?</span></span> 

<span data-ttu-id="563c1-186">需要云保护才能在设备上启用该功能。</span><span class="sxs-lookup"><span data-stu-id="563c1-186">Cloud protection is needed to turn on the feature on the device.</span></span> <span data-ttu-id="563c1-187">云保护 [允许 Defender for Endpoint](microsoft-defender-endpoint.md) 基于安全智能的广度和深度以及行为和设备学习模型提供最新且最丰富的保护。</span><span class="sxs-lookup"><span data-stu-id="563c1-187">Cloud protection allows [Defender for Endpoint](microsoft-defender-endpoint.md) to deliver the latest and greatest protection based on our breadth and depth of security intelligence, along with behavioral and device learning models.</span></span>

### <a name="what-is-the-difference-between-active-and-passive-mode"></a><span data-ttu-id="563c1-188">主动模式和被动模式之间有什么区别？</span><span class="sxs-lookup"><span data-stu-id="563c1-188">What is the difference between active and passive mode?</span></span>

<span data-ttu-id="563c1-189">对于运行 Windows 10、Windows Server 版本 1803 或更高版本或 Windows Server 2019 的终结点，当 Microsoft Defender 防病毒 处于活动状态时，它将用作设备上的主要防病毒。</span><span class="sxs-lookup"><span data-stu-id="563c1-189">For endpoints running Windows 10, Windows Server, version 1803 or later, or Windows Server 2019, when Microsoft Defender Antivirus is in active mode, it is used as the primary antivirus on the device.</span></span> <span data-ttu-id="563c1-190">在被动模式下运行时，Microsoft Defender 防病毒不是主要的防病毒产品。</span><span class="sxs-lookup"><span data-stu-id="563c1-190">When running in passive mode, Microsoft Defender Antivirus is not the primary antivirus product.</span></span> <span data-ttu-id="563c1-191">在这种情况下，威胁不会由Microsoft Defender 防病毒进行修正。</span><span class="sxs-lookup"><span data-stu-id="563c1-191">In this case, threats are not remediated by Microsoft Defender Antivirus in real time.</span></span>

> [!NOTE]
> <span data-ttu-id="563c1-192">Microsoft Defender 防病毒设备载入 Microsoft Defender for Endpoint 时，才能在被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="563c1-192">Microsoft Defender Antivirus can run in passive mode only when the device is onboarded to Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="563c1-193">有关详细信息，请参阅兼容性[Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="563c1-193">For more information, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a><span data-ttu-id="563c1-194">如何确认Microsoft Defender 防病毒处于主动或被动模式？</span><span class="sxs-lookup"><span data-stu-id="563c1-194">How do I confirm Microsoft Defender Antivirus is in active or passive mode?</span></span>

<span data-ttu-id="563c1-195">若要确认Microsoft Defender 防病毒处于主动或被动模式，可以在运行命令提示符或 PowerShell 的设备上Windows。</span><span class="sxs-lookup"><span data-stu-id="563c1-195">To confirm whether Microsoft Defender Antivirus is running in active or passive mode, you can use Command Prompt or PowerShell on a device running Windows.</span></span>

|<span data-ttu-id="563c1-196">方法</span><span class="sxs-lookup"><span data-stu-id="563c1-196">Method</span></span>  |<span data-ttu-id="563c1-197">Procedure</span><span class="sxs-lookup"><span data-stu-id="563c1-197">Procedure</span></span>  |
|---------|---------|
| <span data-ttu-id="563c1-198">PowerShell</span><span class="sxs-lookup"><span data-stu-id="563c1-198">PowerShell</span></span>     | <span data-ttu-id="563c1-199">1. 选择"开始"菜单，开始键入 `PowerShell` ，然后在Windows PowerShell中打开" "。</span><span class="sxs-lookup"><span data-stu-id="563c1-199">1. Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span> <p><span data-ttu-id="563c1-200">2. 键入 `Get-MpComputerStatus` 。</span><span class="sxs-lookup"><span data-stu-id="563c1-200">2. Type `Get-MpComputerStatus`.</span></span> <p><span data-ttu-id="563c1-201">3. 在结果列表中，在 **AMRunningMode** 行中查找下列值之一：</span><span class="sxs-lookup"><span data-stu-id="563c1-201">3. In the list of results, in the **AMRunningMode** row, look for one of the following values:</span></span> <br/>- `Normal` <br/>- `Passive Mode` <p><span data-ttu-id="563c1-202">若要了解更多信息，请参阅 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="563c1-202">To learn more, see [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span></span>        |
|<span data-ttu-id="563c1-203">命令提示符</span><span class="sxs-lookup"><span data-stu-id="563c1-203">Command Prompt</span></span>     | <span data-ttu-id="563c1-204">1. 选择"开始"菜单，开始键入 ，然后打开Windows `Command Prompt` 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="563c1-204">1. Select the Start menu, begin typing `Command Prompt`, and then open Windows Command Prompt in the results.</span></span> <p><span data-ttu-id="563c1-205">2. 键入 `sc query windefend` 。</span><span class="sxs-lookup"><span data-stu-id="563c1-205">2. Type `sc query windefend`.</span></span> <p><span data-ttu-id="563c1-206">3. 在结果列表中的 **"状态** "行中，确认服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="563c1-206">3. In the list of results, in the **STATE** row, confirm that the service is running.</span></span>         |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a><span data-ttu-id="563c1-207">如何确认阻止EDR处于阻止模式时处于打开状态，Microsoft Defender 防病毒处于被动模式？</span><span class="sxs-lookup"><span data-stu-id="563c1-207">How do I confirm that EDR in block mode is turned on with Microsoft Defender Antivirus in passive mode?</span></span>

<span data-ttu-id="563c1-208">可以使用 PowerShell 确认阻止EDR处于阻止模式时处于打开状态，Microsoft Defender 防病毒被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="563c1-208">You can use PowerShell to confirm that EDR in block mode is turned on with Microsoft Defender Antivirus running in passive mode.</span></span>

1. <span data-ttu-id="563c1-209">选择"开始"菜单，开始键入 `PowerShell` ，然后在Windows PowerShell中打开" "。</span><span class="sxs-lookup"><span data-stu-id="563c1-209">Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span> 

2. <span data-ttu-id="563c1-210">类型 `Get-MPComputerStatus | select AMRunningMode`。</span><span class="sxs-lookup"><span data-stu-id="563c1-210">Type `Get-MPComputerStatus | select AMRunningMode`.</span></span>

3. <span data-ttu-id="563c1-211">确认显示结果 `EDR Block Mode` 。</span><span class="sxs-lookup"><span data-stu-id="563c1-211">Confirm that the result, `EDR Block Mode`, is displayed.</span></span>

   > [!TIP]
   > <span data-ttu-id="563c1-212">如果Microsoft Defender 防病毒处于活动状态，你将看到 `Normal` 而不是 `EDR Block Mode` 。</span><span class="sxs-lookup"><span data-stu-id="563c1-212">If Microsoft Defender Antivirus is in active mode, you will see `Normal` instead of `EDR Block Mode`.</span></span> <span data-ttu-id="563c1-213">若要了解更多信息，请参阅 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="563c1-213">To learn more, see [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span></span>

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a><span data-ttu-id="563c1-214">EDR上是否支持阻止Windows Server 2016？</span><span class="sxs-lookup"><span data-stu-id="563c1-214">Is EDR in block mode supported on Windows Server 2016?</span></span>

<span data-ttu-id="563c1-215">如果Microsoft Defender 防病毒模式或被动模式下运行，EDR支持以下版本的 Windows：</span><span class="sxs-lookup"><span data-stu-id="563c1-215">If Microsoft Defender Antivirus is running in active mode or passive mode, EDR in block mode is supported of the following versions of Windows:</span></span>

- <span data-ttu-id="563c1-216">Windows 10 (所有版本) </span><span class="sxs-lookup"><span data-stu-id="563c1-216">Windows 10 (all releases)</span></span>
- <span data-ttu-id="563c1-217">Windows服务器版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="563c1-217">Windows Server, version 1803 or newer</span></span> 
- <span data-ttu-id="563c1-218">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="563c1-218">Windows Server 2019</span></span> 

#### <a name="what-about-windows-server-2016"></a><span data-ttu-id="563c1-219">如何Windows Server 2016？</span><span class="sxs-lookup"><span data-stu-id="563c1-219">What about Windows Server 2016?</span></span> 

<span data-ttu-id="563c1-220">如果Windows Server 2016在Microsoft Defender 防病毒模式下运行，并且终结点已载入到 Defender for Endpoint，则EDR支持以阻止模式运行。</span><span class="sxs-lookup"><span data-stu-id="563c1-220">If Windows Server 2016 has Microsoft Defender Antivirus running in active mode, and the endpoint is onboarded to Defender for Endpoint, then EDR in block mode is technically supported.</span></span> <span data-ttu-id="563c1-221">但是，EDR阻止模式旨在当终结点上不是Microsoft Defender 防病毒防病毒解决方案时提供额外保护。</span><span class="sxs-lookup"><span data-stu-id="563c1-221">However, EDR in block mode is intended to be extra protection when Microsoft Defender Antivirus is not the primary antivirus solution on an endpoint.</span></span> <span data-ttu-id="563c1-222">在这种情况下，Microsoft Defender 防病毒被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="563c1-222">In those cases, Microsoft Defender Antivirus runs in passive mode.</span></span> 

<span data-ttu-id="563c1-223">目前，Microsoft Defender 防病毒在被动模式下运行 Windows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="563c1-223">Currently, running Microsoft Defender Antivirus in passive mode is not supported on Windows Server 2016.</span></span> <span data-ttu-id="563c1-224">若要了解更多信息，请参阅[Microsoft Defender 防病毒和非 Microsoft 防病毒/反恶意软件解决方案](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)。</span><span class="sxs-lookup"><span data-stu-id="563c1-224">To learn more, see [Microsoft Defender Antivirus and non-Microsoft antivirus/antimalware solutions](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions).</span></span>

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a><span data-ttu-id="563c1-225">在阻止模式下禁用EDR需要的时间？</span><span class="sxs-lookup"><span data-stu-id="563c1-225">How much time does it take for EDR in block mode to be disabled?</span></span>

<span data-ttu-id="563c1-226">如果选择在阻止EDR禁用此功能，则系统最多可能需要 30 分钟才能禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="563c1-226">If you choose to disable EDR in block mode, it can take up to 30 minutes for the system to disable this capability.</span></span>

## <a name="see-also"></a><span data-ttu-id="563c1-227">另请参阅</span><span class="sxs-lookup"><span data-stu-id="563c1-227">See also</span></span>

- [<span data-ttu-id="563c1-228">Tech Community博客：在EDR模式下进行介绍：停止跟踪攻击</span><span class="sxs-lookup"><span data-stu-id="563c1-228">Tech Community blog: Introducing EDR in block mode: Stopping attacks in their tracks</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [<span data-ttu-id="563c1-229">行为阻止和控制</span><span class="sxs-lookup"><span data-stu-id="563c1-229">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

