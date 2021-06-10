---
title: 评估攻击面减少规则
description: 了解攻击面减少如何使用自定义演示工具阻止和阻止攻击。
keywords: 攻击面减少， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， 评估， 测试， 演示
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5d3cd7893af4c91807782c269231a280b413733e
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861211"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="18409-104">评估攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="18409-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="18409-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="18409-105">**Applies to:**</span></span>

- [<span data-ttu-id="18409-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="18409-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="18409-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18409-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="18409-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="18409-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="18409-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="18409-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="18409-110">攻击面减少规则有助于防止恶意软件通常用来危害设备或网络的操作。</span><span class="sxs-lookup"><span data-stu-id="18409-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="18409-111">攻击面减少规则有助于关闭恶意软件和勒索软件使用的许多常见入口点。</span><span class="sxs-lookup"><span data-stu-id="18409-111">Attack surface reduction rules help close off many of the common entry points used by malware and ransomware.</span></span> 

<span data-ttu-id="18409-112">为运行以下任一版本和版本的设备设置攻击面减少Windows：</span><span class="sxs-lookup"><span data-stu-id="18409-112">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="18409-113">Windows 10 专业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="18409-113">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="18409-114">Windows 10 企业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="18409-114">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="18409-115">Windows服务器版本[1803 (半年频道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本</span><span class="sxs-lookup"><span data-stu-id="18409-115">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="18409-116">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="18409-116">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

> [!WARNING]
> <span data-ttu-id="18409-117">在客户端上启用攻击服务Windows Server 2016可能会导致意外结果并影响服务器性能。</span><span class="sxs-lookup"><span data-stu-id="18409-117">Enabling attack service reduction rules on Windows Server 2016 may lead to unexpected results and impact server performance.</span></span> <span data-ttu-id="18409-118">建议不要启用攻击面减少规则或将攻击面减少规则部署到不受支持的平台。</span><span class="sxs-lookup"><span data-stu-id="18409-118">We do not recommend enabling or deploying attack surface reduction rules to unsupported platforms.</span></span>

<span data-ttu-id="18409-119">了解如何通过启用审核模式直接在你的组织中测试功能来评估攻击面减少规则。</span><span class="sxs-lookup"><span data-stu-id="18409-119">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="18409-120">还可以访问 Microsoft Defender for Endpoint 演示方案[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)网站，demo.wd.microsoft.com 确认功能是否正常工作并查看其工作方式。</span><span class="sxs-lookup"><span data-stu-id="18409-120">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="18409-121">使用审核模式衡量影响</span><span class="sxs-lookup"><span data-stu-id="18409-121">Use audit mode to measure impact</span></span>

<span data-ttu-id="18409-122">在审核模式下启用攻击面减少规则，以查看在功能完全启用时可能阻止的应用记录。</span><span class="sxs-lookup"><span data-stu-id="18409-122">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="18409-123">测试此功能在组织中如何工作，以确保它不会影响你的业务线应用。</span><span class="sxs-lookup"><span data-stu-id="18409-123">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="18409-124">您还可以了解规则在正常使用期间将多久发生一次。</span><span class="sxs-lookup"><span data-stu-id="18409-124">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="18409-125">若要在审核模式下启用攻击面减少规则，请使用以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="18409-125">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="18409-126">其中 `<rule ID>` 是 [攻击面减少规则的 GUID 值](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="18409-126">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="18409-127">若要在审核模式下启用所有添加的攻击面减少规则，请使用以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="18409-127">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="18409-128">如果你想要完全审核攻击面减少规则在组织中如何工作，你将需要使用管理工具将此设置部署到你的网络 (设备) 。</span><span class="sxs-lookup"><span data-stu-id="18409-128">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="18409-129">您还可以使用组策略、Intune 或移动设备管理 (MDM) 配置服务提供程序 () 配置和部署设置。</span><span class="sxs-lookup"><span data-stu-id="18409-129">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="18409-130">在主要的攻击 [面减少规则文章中了解更多信息](attack-surface-reduction.md) 。</span><span class="sxs-lookup"><span data-stu-id="18409-130">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="18409-131">查看事件查看器中的攻击Windows减少事件</span><span class="sxs-lookup"><span data-stu-id="18409-131">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="18409-132">若要查看已阻止的应用，请打开事件查看器，并筛选 Microsoft-Windows-Windows Defender/Operational 日志中的事件 ID 1121。</span><span class="sxs-lookup"><span data-stu-id="18409-132">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="18409-133">下表列出了所有网络保护事件。</span><span class="sxs-lookup"><span data-stu-id="18409-133">The following table lists all network protection events.</span></span>

<span data-ttu-id="18409-134">事件 ID</span><span class="sxs-lookup"><span data-stu-id="18409-134">Event ID</span></span> | <span data-ttu-id="18409-135">说明</span><span class="sxs-lookup"><span data-stu-id="18409-135">Description</span></span>
-|-
 <span data-ttu-id="18409-136">5007</span><span class="sxs-lookup"><span data-stu-id="18409-136">5007</span></span> | <span data-ttu-id="18409-137">更改设置时的事件</span><span class="sxs-lookup"><span data-stu-id="18409-137">Event when settings are changed</span></span>
 <span data-ttu-id="18409-138">1121</span><span class="sxs-lookup"><span data-stu-id="18409-138">1121</span></span> | <span data-ttu-id="18409-139">攻击面减少规则在阻止模式下触发时的事件</span><span class="sxs-lookup"><span data-stu-id="18409-139">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="18409-140">1122</span><span class="sxs-lookup"><span data-stu-id="18409-140">1122</span></span> | <span data-ttu-id="18409-141">在审核模式下触发攻击面减少规则时的事件</span><span class="sxs-lookup"><span data-stu-id="18409-141">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="18409-142">自定义减少攻击面规则</span><span class="sxs-lookup"><span data-stu-id="18409-142">Customize attack surface reduction rules</span></span>

<span data-ttu-id="18409-143">在评估过程中，你可能希望单独配置每个规则，或者将某些文件和进程排除在功能评估外。</span><span class="sxs-lookup"><span data-stu-id="18409-143">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="18409-144">有关 [使用管理工具（](customize-attack-surface-reduction.md) 包括组策略和 MDM CSP 策略）配置功能的信息，请参阅自定义攻击面减少规则。</span><span class="sxs-lookup"><span data-stu-id="18409-144">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="18409-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18409-145">See also</span></span>

* [<span data-ttu-id="18409-146">使用攻击面减少规则减少攻击面</span><span class="sxs-lookup"><span data-stu-id="18409-146">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="18409-147">使用审核模式评估Windows Defender</span><span class="sxs-lookup"><span data-stu-id="18409-147">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="18409-148">关于攻击面减少的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="18409-148">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
