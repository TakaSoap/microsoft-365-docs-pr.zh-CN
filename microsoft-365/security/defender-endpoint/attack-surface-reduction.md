---
title: 使用攻击面减少规则防止恶意软件感染
description: 攻击面减少规则有助于防止攻击使用应用和脚本感染带恶意软件的设备。
keywords: 攻击面减少规则， asr， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， Microsoft Defender for Endpoint， Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 62f1f5f2d47482f642f00c870b3e0f3112f5f639
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185763"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="8e906-104">使用攻击面减少规则防止恶意软件感染</span><span class="sxs-lookup"><span data-stu-id="8e906-104">Use attack surface reduction rules to prevent malware infection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8e906-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8e906-105">**Applies to:**</span></span>
- [<span data-ttu-id="8e906-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8e906-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8e906-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e906-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="8e906-108">攻击面减少规则为什么很重要</span><span class="sxs-lookup"><span data-stu-id="8e906-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="8e906-109">组织的攻击面包括攻击者可能损害组织设备或网络的所有位置。</span><span class="sxs-lookup"><span data-stu-id="8e906-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="8e906-110">减少攻击面意味着保护组织的设备和网络，这使攻击者能够执行攻击的方法更少。</span><span class="sxs-lookup"><span data-stu-id="8e906-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="8e906-111">在 Microsoft Defender for Endpoint 中配置攻击面减少规则可以提供帮助！</span><span class="sxs-lookup"><span data-stu-id="8e906-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="8e906-112">攻击面减少规则针对某些软件行为，例如：</span><span class="sxs-lookup"><span data-stu-id="8e906-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="8e906-113">启动尝试下载或运行文件的可执行文件和脚本;</span><span class="sxs-lookup"><span data-stu-id="8e906-113">Launching executable files and scripts that attempt to download or run files;</span></span>
- <span data-ttu-id="8e906-114">运行混淆的或可疑的脚本;和</span><span class="sxs-lookup"><span data-stu-id="8e906-114">Running obfuscated or otherwise suspicious scripts; and</span></span> 
- <span data-ttu-id="8e906-115">执行应用在正常日常工作期间通常不会启动的行为。</span><span class="sxs-lookup"><span data-stu-id="8e906-115">Performing behaviors that apps don't usually initiate during normal day-to-day work.</span></span>

<span data-ttu-id="8e906-116">此类软件行为有时在合法应用程序中可见;但是，这些行为通常被视为有风险，因为它们通常被攻击者通过恶意软件滥用。</span><span class="sxs-lookup"><span data-stu-id="8e906-116">Such software behaviors are sometimes seen in legitimate applications; however, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="8e906-117">攻击面减少规则可以限制风险行为，并有助于保证组织安全。</span><span class="sxs-lookup"><span data-stu-id="8e906-117">Attack surface reduction rules can constrain risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="8e906-118">有关配置攻击面减少规则的信息，请参阅启用 [攻击面减少规则](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="8e906-118">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="8e906-119">在部署之前评估规则影响</span><span class="sxs-lookup"><span data-stu-id="8e906-119">Assess rule impact before deployment</span></span>  

<span data-ttu-id="8e906-120">可以通过在威胁和漏洞管理中打开该规则的安全建议来评估攻击面减少规则可能会 [如何影响你的网络](https://docs.microsoft.com/windows/security/threat-protection/#tvm)。</span><span class="sxs-lookup"><span data-stu-id="8e906-120">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](https://docs.microsoft.com/windows/security/threat-protection/#tvm).</span></span> 

:::image type="content" source="images/asrrecommendation.png" alt-text="攻击面减少规则的安全重新成本":::

<span data-ttu-id="8e906-122">在建议详细信息窗格中，检查用户影响以确定设备可接受在阻止模式下启用规则的新策略的百分比，而不会对工作效率产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="8e906-122">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="8e906-123">评估审核模式</span><span class="sxs-lookup"><span data-stu-id="8e906-123">Audit mode for evaluation</span></span>

<span data-ttu-id="8e906-124">使用 [审核模式](audit-windows-defender.md) 评估攻击面减少规则启用后对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="8e906-124">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if they were enabled.</span></span> <span data-ttu-id="8e906-125">首先在审核模式下运行所有规则，以便了解它们如何影响业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="8e906-125">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="8e906-126">许多业务线应用程序都是以有限的安全问题编写，它们执行任务的方式可能类似于恶意软件。</span><span class="sxs-lookup"><span data-stu-id="8e906-126">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="8e906-127">通过监视审核数据 [并添加](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 必要应用程序的排除项，你可以部署攻击面减少规则，而不会降低工作效率。</span><span class="sxs-lookup"><span data-stu-id="8e906-127">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="8e906-128">用户警告模式</span><span class="sxs-lookup"><span data-stu-id="8e906-128">Warn mode for users</span></span>

<span data-ttu-id="8e906-129"> (**新**！) 警告模式功能之前，已启用的攻击面减少规则可以设置为审核模式或阻止模式。</span><span class="sxs-lookup"><span data-stu-id="8e906-129">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="8e906-130">使用新的警告模式，只要内容被攻击面减少规则阻止，用户就会看到一个指示内容被阻止的对话框。</span><span class="sxs-lookup"><span data-stu-id="8e906-130">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="8e906-131">该对话框还允许用户选择取消阻止内容。</span><span class="sxs-lookup"><span data-stu-id="8e906-131">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="8e906-132">然后，用户可以重试其操作，操作完成。</span><span class="sxs-lookup"><span data-stu-id="8e906-132">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="8e906-133">当用户取消阻止内容时，该内容将保持取消阻止状态 24 小时，然后阻止恢复。</span><span class="sxs-lookup"><span data-stu-id="8e906-133">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="8e906-134">警告模式可帮助组织制定攻击面减少规则，而不会阻止用户访问执行其任务所需的内容。</span><span class="sxs-lookup"><span data-stu-id="8e906-134">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span> 

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="8e906-135">警告模式运行的要求</span><span class="sxs-lookup"><span data-stu-id="8e906-135">Requirements for warn mode to work</span></span>

<span data-ttu-id="8e906-136">运行以下版本的 Windows 的设备支持警告模式：</span><span class="sxs-lookup"><span data-stu-id="8e906-136">Warn mode is supported on devices running the following versions of Windows:</span></span>
- <span data-ttu-id="8e906-137">[Windows 10 版本 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8e906-137">[Windows 10, version 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="8e906-138">[Windows Server 版本 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8e906-138">[Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>
 
<span data-ttu-id="8e906-139">Microsoft Defender 防病毒必须在活动模式下使用实时 [保护运行](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)。</span><span class="sxs-lookup"><span data-stu-id="8e906-139">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="8e906-140">此外，请确保安装了 [Microsoft Defender 防病毒和](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) 反恶意软件更新。</span><span class="sxs-lookup"><span data-stu-id="8e906-140">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>
- <span data-ttu-id="8e906-141">最低平台发布要求： `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="8e906-141">Minimum platform release requirement: `4.18.2008.9`</span></span>  
- <span data-ttu-id="8e906-142">最低引擎发布要求： `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="8e906-142">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="8e906-143">有关详细信息和获取更新，请参阅 [Microsoft Defender 反恶意软件平台的更新](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="8e906-143">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="8e906-144">不支持警告模式的情况</span><span class="sxs-lookup"><span data-stu-id="8e906-144">Cases where warn mode is not supported</span></span>

<span data-ttu-id="8e906-145">以下攻击面减少规则不支持警告模式：</span><span class="sxs-lookup"><span data-stu-id="8e906-145">Warn mode is not supported for the following attack surface reduction rules:</span></span>

- <span data-ttu-id="8e906-146">[阻止 JavaScript 或 VBScript 使用](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) GUID (下载的可执行 `d3e037e1-3eb8-44c8-a917-57927947596d`) </span><span class="sxs-lookup"><span data-stu-id="8e906-146">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="8e906-147">[通过 WMI 事件订阅和 GUID](#block-persistence-through-wmi-event-subscription) (阻止 `e6db77e5-3df2-4cf1-b95a-636979351e5b` 持久性) </span><span class="sxs-lookup"><span data-stu-id="8e906-147">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="8e906-148">[使用高级防护抵御勒索软件](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`) </span><span class="sxs-lookup"><span data-stu-id="8e906-148">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="8e906-149">此外，运行较早版本的 Windows 的设备上不支持警告模式。</span><span class="sxs-lookup"><span data-stu-id="8e906-149">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="8e906-150">在这种情况下，配置为在警告模式下运行的攻击面减少规则将在阻止模式下运行。</span><span class="sxs-lookup"><span data-stu-id="8e906-150">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="8e906-151">通知和警报</span><span class="sxs-lookup"><span data-stu-id="8e906-151">Notifications and alerts</span></span>

<span data-ttu-id="8e906-152">每当触发攻击面减少规则时，都会在设备上显示通知。</span><span class="sxs-lookup"><span data-stu-id="8e906-152">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="8e906-153">可以使用 [公司详细信息和](customize-attack-surface-reduction.md#customize-the-notification) 联系信息自定义通知。</span><span class="sxs-lookup"><span data-stu-id="8e906-153">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="8e906-154">此外，当触发某些攻击面减少规则时，将生成警报。</span><span class="sxs-lookup"><span data-stu-id="8e906-154">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span> 

<span data-ttu-id="8e906-155">可在 Microsoft Defender 安全中心 () 和 Microsoft 365 安全中心 () 中查看生成的通知 [https://securitycenter.windows.com](https://securitycenter.windows.com) [https://security.microsoft.com](https://security.microsoft.com) 和任何警报。</span><span class="sxs-lookup"><span data-stu-id="8e906-155">Notifications and any alerts that are generated can be viewed in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and in the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="8e906-156">高级搜寻和攻击面减少事件</span><span class="sxs-lookup"><span data-stu-id="8e906-156">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="8e906-157">可以使用高级搜寻来查看攻击面减少事件。</span><span class="sxs-lookup"><span data-stu-id="8e906-157">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="8e906-158">为了简化传入数据的数量，使用高级搜寻仅可查看每小时的唯一进程。</span><span class="sxs-lookup"><span data-stu-id="8e906-158">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="8e906-159">攻击面减少事件的时间是一小时内首次看到该事件。</span><span class="sxs-lookup"><span data-stu-id="8e906-159">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="8e906-160">例如，假设在下午 2：00 小时内在 10 台设备上发生攻击面减少事件。</span><span class="sxs-lookup"><span data-stu-id="8e906-160">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="8e906-161">假设第一个事件在 2：15 发生，最后一个事件在 2：45 发生。</span><span class="sxs-lookup"><span data-stu-id="8e906-161">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="8e906-162">借助高级搜寻，你将看到该事件的一个实例 (即使该事件实际发生在 10 台设备上) ，其时间戳将为下午 2：15。</span><span class="sxs-lookup"><span data-stu-id="8e906-162">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span> 

<span data-ttu-id="8e906-163">有关高级搜寻详细信息，请参阅使用高级搜寻主动 [搜寻威胁](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8e906-163">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="8e906-164">跨 Windows 版本的攻击面减少功能</span><span class="sxs-lookup"><span data-stu-id="8e906-164">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="8e906-165">你可以为运行以下任一版本的 Windows 的设备设置攻击面减少规则：</span><span class="sxs-lookup"><span data-stu-id="8e906-165">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="8e906-166">Windows 10 专业 [版版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8e906-166">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="8e906-167">Windows 10 企业版 [版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8e906-167">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="8e906-168">Windows Server [版本 1803 (半年 ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 频道) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8e906-168">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="8e906-169">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-169">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="8e906-170">尽管攻击面减少规则不需要 [Windows E5](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses)许可证，但如果拥有 Windows E5，则获得高级管理功能。</span><span class="sxs-lookup"><span data-stu-id="8e906-170">Although attack surface reduction rules don't require a [Windows E5 license](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="8e906-171">这些功能仅在 Windows E5 中可用，包括 [Defender for Endpoint](microsoft-defender-endpoint.md)中提供的监视、分析和工作流，以及 Microsoft [365](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center)安全中心中的报告和配置功能。</span><span class="sxs-lookup"><span data-stu-id="8e906-171">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md), as well as reporting and configuration capabilities in the [Microsoft 365 security center](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center).</span></span> <span data-ttu-id="8e906-172">这些高级功能不适用于 Windows Professional 或 Windows E3 许可证;但是，如果你有这些许可证，可以使用事件查看器和 Microsoft Defender 防病毒日志查看攻击面减少规则事件。</span><span class="sxs-lookup"><span data-stu-id="8e906-172">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="8e906-173">查看 Microsoft Defender 安全中心的攻击面减少事件</span><span class="sxs-lookup"><span data-stu-id="8e906-173">Review attack surface reduction events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="8e906-174">Defender for Endpoint 提供事件和阻止的详细报告，作为警报调查方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="8e906-174">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="8e906-175">可以使用高级搜寻查询 Defender 的终结点 [数据](advanced-hunting-query-language.md)。</span><span class="sxs-lookup"><span data-stu-id="8e906-175">You can query Defender for Endpoint data by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="8e906-176">如果你运行的是审核 [模式](audit-windows-defender.md)，可以使用高级搜寻了解攻击面减少规则可能会如何影响你的环境。</span><span class="sxs-lookup"><span data-stu-id="8e906-176">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules could affect your environment.</span></span>

<span data-ttu-id="8e906-177">下面是一个示例查询：</span><span class="sxs-lookup"><span data-stu-id="8e906-177">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="8e906-178">在 Windows 事件查看器中查看攻击面减少事件</span><span class="sxs-lookup"><span data-stu-id="8e906-178">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="8e906-179">你可以查看 Windows 事件日志以查看攻击面减少规则生成的事件：</span><span class="sxs-lookup"><span data-stu-id="8e906-179">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="8e906-180">下载 [评估包](https://aka.ms/mp7z2w) ，将文件 *cfa-events.xml* 到设备上易于访问的位置。</span><span class="sxs-lookup"><span data-stu-id="8e906-180">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="8e906-181">在"开始"菜单中 *输入单词"事件* 查看器"以打开 Windows 事件查看器。</span><span class="sxs-lookup"><span data-stu-id="8e906-181">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="8e906-182">在 **"操作"** 下，**选择"导入自定义视图..."。**</span><span class="sxs-lookup"><span data-stu-id="8e906-182">Under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="8e906-183">选择从 *cfa-events.xml* 文件的位置创建的文件。</span><span class="sxs-lookup"><span data-stu-id="8e906-183">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="8e906-184">或者，[直接复制 XML。](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="8e906-184">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="8e906-185">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="8e906-185">Select **OK**.</span></span>

<span data-ttu-id="8e906-186">您可以创建一个自定义视图，该视图筛选事件以只显示下列事件，所有这些事件均与受控文件夹访问权限相关：</span><span class="sxs-lookup"><span data-stu-id="8e906-186">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="8e906-187">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8e906-187">Event ID</span></span> | <span data-ttu-id="8e906-188">说明</span><span class="sxs-lookup"><span data-stu-id="8e906-188">Description</span></span> |
|:---|:---|
|<span data-ttu-id="8e906-189">5007</span><span class="sxs-lookup"><span data-stu-id="8e906-189">5007</span></span> | <span data-ttu-id="8e906-190">更改设置时的事件</span><span class="sxs-lookup"><span data-stu-id="8e906-190">Event when settings are changed</span></span> |
|<span data-ttu-id="8e906-191">1121</span><span class="sxs-lookup"><span data-stu-id="8e906-191">1121</span></span> | <span data-ttu-id="8e906-192">在阻止模式下触发规则时的事件</span><span class="sxs-lookup"><span data-stu-id="8e906-192">Event when rule fires in Block-mode</span></span> |
|<span data-ttu-id="8e906-193">1122</span><span class="sxs-lookup"><span data-stu-id="8e906-193">1122</span></span> | <span data-ttu-id="8e906-194">在审核模式下触发规则时的事件</span><span class="sxs-lookup"><span data-stu-id="8e906-194">Event when rule fires in Audit-mode</span></span> |

<span data-ttu-id="8e906-195">针对事件日志中的攻击面减少事件列出的"引擎版本"由 Defender for Endpoint 生成，而不是由操作系统生成。</span><span class="sxs-lookup"><span data-stu-id="8e906-195">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="8e906-196">Defender for Endpoint 与 Windows 10 集成，因此此功能适用于安装了 Windows 10 的所有设备。</span><span class="sxs-lookup"><span data-stu-id="8e906-196">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="8e906-197">攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="8e906-197">Attack surface reduction rules</span></span>

<span data-ttu-id="8e906-198">下表和子部分介绍了 15 个攻击面减少规则中的每个规则。</span><span class="sxs-lookup"><span data-stu-id="8e906-198">The following table and subsections describe each of the 15 attack surface reduction rules.</span></span> <span data-ttu-id="8e906-199">攻击面减少规则按规则名称的字母顺序列出。</span><span class="sxs-lookup"><span data-stu-id="8e906-199">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span> 

<span data-ttu-id="8e906-200">如果要使用组策略或 PowerShell 配置攻击面减少规则，则需要 GUID。</span><span class="sxs-lookup"><span data-stu-id="8e906-200">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="8e906-201">另一方面，如果你使用 Microsoft Endpoint Manager 或 Microsoft Intune，则不需要 GUID。</span><span class="sxs-lookup"><span data-stu-id="8e906-201">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>


| <span data-ttu-id="8e906-202">规则名称</span><span class="sxs-lookup"><span data-stu-id="8e906-202">Rule name</span></span> | <span data-ttu-id="8e906-203">GUID</span><span class="sxs-lookup"><span data-stu-id="8e906-203">GUID</span></span> | <span data-ttu-id="8e906-204">文件&文件夹排除项</span><span class="sxs-lookup"><span data-stu-id="8e906-204">File & folder exclusions</span></span> | <span data-ttu-id="8e906-205">支持的最低操作系统</span><span class="sxs-lookup"><span data-stu-id="8e906-205">Minimum OS supported</span></span> |
|:-----|:-----:|:-----|:-----|
|[<span data-ttu-id="8e906-206">阻止 Adobe Reader 创建子进程</span><span class="sxs-lookup"><span data-stu-id="8e906-206">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes) | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` | <span data-ttu-id="8e906-207">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-207">Supported</span></span> | <span data-ttu-id="8e906-208">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-208">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-209">阻止所有 Office 应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="8e906-209">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes) | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` | <span data-ttu-id="8e906-210">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-210">Supported</span></span> | <span data-ttu-id="8e906-211">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-211">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-212">阻止从 Windows 本地安全机构子系统中窃取 (lsass.exe) </span><span class="sxs-lookup"><span data-stu-id="8e906-212">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` | <span data-ttu-id="8e906-213">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-213">Supported</span></span> | <span data-ttu-id="8e906-214">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-214">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-215">阻止来自电子邮件客户端和 Webmail 的可执行内容</span><span class="sxs-lookup"><span data-stu-id="8e906-215">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail) | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` | <span data-ttu-id="8e906-216">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-216">Supported</span></span> | <span data-ttu-id="8e906-217">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-217">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-218">阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件</span><span class="sxs-lookup"><span data-stu-id="8e906-218">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | `01443614-cd74-433a-b99e-2ecdc07bfc25` | <span data-ttu-id="8e906-219">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-219">Supported</span></span> | <span data-ttu-id="8e906-220">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-220">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-221">阻止执行可能混淆的脚本</span><span class="sxs-lookup"><span data-stu-id="8e906-221">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts) | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` | <span data-ttu-id="8e906-222">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-222">Supported</span></span> | <span data-ttu-id="8e906-223">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-223">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-224">阻止 JavaScript 或 VBScript 启动下载的可执行内容</span><span class="sxs-lookup"><span data-stu-id="8e906-224">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | `D3E037E1-3EB8-44C8-A917-57927947596D` | <span data-ttu-id="8e906-225">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-225">Supported</span></span> | <span data-ttu-id="8e906-226">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-226">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-227">阻止 Office 应用程序创建可执行内容</span><span class="sxs-lookup"><span data-stu-id="8e906-227">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content) | `3B576869-A4EC-4529-8536-B80A7769E899` | <span data-ttu-id="8e906-228">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-228">Supported</span></span> | <span data-ttu-id="8e906-229">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-229">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-230">阻止 Office 应用程序将代码注入其他进程</span><span class="sxs-lookup"><span data-stu-id="8e906-230">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes) | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` | <span data-ttu-id="8e906-231">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-231">Supported</span></span> | <span data-ttu-id="8e906-232">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-232">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-233">阻止 Office 通信应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="8e906-233">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes) |`26190899-1602-49e8-8b27-eb1d0a1ce869` |<span data-ttu-id="8e906-234">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-234">Supported</span></span> |<span data-ttu-id="8e906-235">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-235">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>  |
|[<span data-ttu-id="8e906-236">通过 WMI 事件订阅阻止持久性</span><span class="sxs-lookup"><span data-stu-id="8e906-236">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription) | `e6db77e5-3df2-4cf1-b95a-636979351e5b` | <span data-ttu-id="8e906-237">不支持</span><span class="sxs-lookup"><span data-stu-id="8e906-237">Not supported</span></span> | <span data-ttu-id="8e906-238">[Windows 10 版本 1903 (](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) 版本 18362) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-238">[Windows 10, version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span> |
|[<span data-ttu-id="8e906-239">阻止源自 PSExec 和 WMI 命令的进程创建</span><span class="sxs-lookup"><span data-stu-id="8e906-239">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands) | `d1e49aac-8f56-4280-b9ba-993a6d77406c` | <span data-ttu-id="8e906-240">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-240">Supported</span></span> | <span data-ttu-id="8e906-241">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-241">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-242">阻止从 USB 运行的不受信任的和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="8e906-242">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb) | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` | <span data-ttu-id="8e906-243">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-243">Supported</span></span> | <span data-ttu-id="8e906-244">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-244">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-245">阻止从 Office 宏调用 Win32 API</span><span class="sxs-lookup"><span data-stu-id="8e906-245">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros) | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` | <span data-ttu-id="8e906-246">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-246">Supported</span></span> | <span data-ttu-id="8e906-247">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-247">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="8e906-248">使用高级防护抵御勒索软件</span><span class="sxs-lookup"><span data-stu-id="8e906-248">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware) | `c1db55ab-c21a-4637-bb3f-a12568109d35` | <span data-ttu-id="8e906-249">支持</span><span class="sxs-lookup"><span data-stu-id="8e906-249">Supported</span></span> | <span data-ttu-id="8e906-250">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="8e906-250">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="8e906-251">阻止 Adobe Reader 创建子进程</span><span class="sxs-lookup"><span data-stu-id="8e906-251">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="8e906-252">此规则通过阻止 Adobe Reader 创建进程来阻止攻击。</span><span class="sxs-lookup"><span data-stu-id="8e906-252">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="8e906-253">通过社交工程或攻击，恶意软件可以下载和启动有效负载，并退出 Adobe Reader。</span><span class="sxs-lookup"><span data-stu-id="8e906-253">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="8e906-254">通过阻止 Adobe Reader 生成子进程，尝试将其用作矢量的恶意软件可防止传播。</span><span class="sxs-lookup"><span data-stu-id="8e906-254">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="8e906-255">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-255">This rule was introduced in:</span></span> 
- [<span data-ttu-id="8e906-256">Windows 10 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-256">Windows 10, version 1809</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="8e906-257">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-257">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-258">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-258">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="8e906-259">Intune 名称： `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="8e906-259">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="8e906-260">Configuration Manager 名称：尚不可用</span><span class="sxs-lookup"><span data-stu-id="8e906-260">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="8e906-261">GUID：`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="8e906-261">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="8e906-262">阻止所有 Office 应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="8e906-262">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="8e906-263">此规则阻止 Office 应用创建子进程。</span><span class="sxs-lookup"><span data-stu-id="8e906-263">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="8e906-264">Office 应用程序包括 Word、Excel、PowerPoint、OneNote 和 Access。</span><span class="sxs-lookup"><span data-stu-id="8e906-264">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="8e906-265">创建恶意子进程是常见的恶意软件策略。</span><span class="sxs-lookup"><span data-stu-id="8e906-265">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="8e906-266">滥用 Office 作为矢量的恶意软件通常会运行 VBA 宏并攻击代码以下载并尝试运行更多有效负载。</span><span class="sxs-lookup"><span data-stu-id="8e906-266">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="8e906-267">但是，某些合法的业务线应用程序也可能出于恶意目的生成子进程，例如生成命令提示符或使用 PowerShell 配置注册表设置。</span><span class="sxs-lookup"><span data-stu-id="8e906-267">However, some legitimate line-of-business applications might also generate child processes for benign purposes, such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="8e906-268">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-268">This rule was introduced in:</span></span> 
- [<span data-ttu-id="8e906-269">Windows 10 版本 1709</span><span class="sxs-lookup"><span data-stu-id="8e906-269">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="8e906-270">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-270">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-271">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-271">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="8e906-272">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="8e906-272">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="8e906-273">Intune 名称： `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="8e906-273">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="8e906-274">Configuration Manager 名称： `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="8e906-274">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="8e906-275">GUID：`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="8e906-275">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="8e906-276">阻止从 Windows 本地安全机构子系统窃取凭据</span><span class="sxs-lookup"><span data-stu-id="8e906-276">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="8e906-277">此规则通过锁定 LSASS 服务中的本地安全机构子系统服务 (凭据) 。</span><span class="sxs-lookup"><span data-stu-id="8e906-277">This rule helps prevent credential stealing, by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="8e906-278">LSASS 对在 Windows 计算机上登录的用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8e906-278">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="8e906-279">Windows 10 中的 Microsoft Defender Credential Guard 通常会阻止尝试从 LSASS 提取凭据。</span><span class="sxs-lookup"><span data-stu-id="8e906-279">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="8e906-280">但是，某些组织无法在所有计算机上启用 Credential Guard，因为自定义智能卡驱动程序或其他加载到本地安全机构 (LSA) 的程序的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="8e906-280">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="8e906-281">在这些情况下，攻击者可以使用 Mimikatz 等黑客工具从 LSASS 中清除明文密码和 NTLM 哈希。</span><span class="sxs-lookup"><span data-stu-id="8e906-281">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="8e906-282">在某些应用中，该代码枚举所有正在运行的进程，并尝试以详尽的权限打开它们。</span><span class="sxs-lookup"><span data-stu-id="8e906-282">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="8e906-283">此规则拒绝应用的进程打开操作，将详细信息记录到安全事件日志中。</span><span class="sxs-lookup"><span data-stu-id="8e906-283">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="8e906-284">此规则会产生大量噪音。</span><span class="sxs-lookup"><span data-stu-id="8e906-284">This rule can generate a lot of noise.</span></span> <span data-ttu-id="8e906-285">如果你的应用仅枚举 LSASS，但在功能方面没有实际影响，则无需将其添加到排除列表。</span><span class="sxs-lookup"><span data-stu-id="8e906-285">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="8e906-286">此事件日志条目本身不一定表示恶意威胁。</span><span class="sxs-lookup"><span data-stu-id="8e906-286">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="8e906-287">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-287">This rule was introduced in:</span></span>
- [<span data-ttu-id="8e906-288">Windows 10 版本 1803</span><span class="sxs-lookup"><span data-stu-id="8e906-288">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="8e906-289">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-289">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-290">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-290">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="8e906-291">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="8e906-291">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="8e906-292">Intune 名称： `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="8e906-292">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="8e906-293">Configuration Manager 名称： `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="8e906-293">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="8e906-294">GUID：`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="8e906-294">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="8e906-295">阻止来自电子邮件客户端和 Webmail 的可执行内容</span><span class="sxs-lookup"><span data-stu-id="8e906-295">Block executable content from email client and webmail</span></span>

<span data-ttu-id="8e906-296">此规则阻止以下文件类型从 Microsoft Outlook 应用程序内打开的电子邮件启动，Outlook.com 其他热门 Web 邮件提供程序启动：</span><span class="sxs-lookup"><span data-stu-id="8e906-296">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="8e906-297">可执行文件 (.exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="8e906-297">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="8e906-298">脚本文件 (如 PowerShell .ps、Visual Basic .vbs 或 JavaScript .js) </span><span class="sxs-lookup"><span data-stu-id="8e906-298">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="8e906-299">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-299">This rule was introduced in:</span></span> 
- [<span data-ttu-id="8e906-300">Windows 10 版本 1709</span><span class="sxs-lookup"><span data-stu-id="8e906-300">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="8e906-301">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-301">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-302">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-302">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="8e906-303">Microsoft Endpoint Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="8e906-303">Microsoft Endpoint Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="8e906-304">Intune 名称： `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="8e906-304">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="8e906-305">Microsoft Endpoint Manager 名称： `Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="8e906-305">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="8e906-306">GUID：`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="8e906-306">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="8e906-307">规则 **"阻止来自电子邮件客户端和 Webmail** 的可执行内容"具有以下替代说明，具体取决于你使用的应用程序：</span><span class="sxs-lookup"><span data-stu-id="8e906-307">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
> - <span data-ttu-id="8e906-308">Intune (Configuration Profiles) ： Execution of executable content (exe， dll， ps， js， vbs， etc.) dropped from email (webmail/mail client)  (no exceptions) .</span><span class="sxs-lookup"><span data-stu-id="8e906-308">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="8e906-309">终结点管理器：阻止从电子邮件和 Webmail 客户端下载可执行内容。</span><span class="sxs-lookup"><span data-stu-id="8e906-309">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="8e906-310">组策略：阻止来自电子邮件客户端和 Webmail 的可执行内容。</span><span class="sxs-lookup"><span data-stu-id="8e906-310">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="8e906-311">阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件</span><span class="sxs-lookup"><span data-stu-id="8e906-311">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="8e906-312">此规则阻止启动以下文件类型，除非它们符合普遍或年龄条件，或者它们位于受信任的列表或排除列表中：</span><span class="sxs-lookup"><span data-stu-id="8e906-312">This rule blocks the following file types from launching unless they meet prevalence or age criteria, or they're in a trusted list or an exclusion list:</span></span>

- <span data-ttu-id="8e906-313">可执行文件 (.exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="8e906-313">Executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="8e906-314">启动不受信任的或未知的可执行文件可能会存在风险，因为最初可能不明确这些文件是否恶意。</span><span class="sxs-lookup"><span data-stu-id="8e906-314">Launching untrusted or unknown executable files can be risky, as it may not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e906-315">必须 [启用云保护才能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 使用此规则。</span><span class="sxs-lookup"><span data-stu-id="8e906-315">You must [enable cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span> <br/><br/> <span data-ttu-id="8e906-316">规则 **阻止可执行文件运行** ，除非它们符合普遍标准、年龄或受信任列表条件（具有 GUID）归 Microsoft 所有，且未由管理员 `01443614-cd74-433a-b99e-2ecdc07bfc25` 指定。</span><span class="sxs-lookup"><span data-stu-id="8e906-316">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="8e906-317">此规则使用云提供的保护定期更新其受信任的列表。</span><span class="sxs-lookup"><span data-stu-id="8e906-317">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
><span data-ttu-id="8e906-318">可以使用文件夹路径或完全限定的资源 (指定单个文件或文件夹) 但无法指定适用于哪些规则或排除项。</span><span class="sxs-lookup"><span data-stu-id="8e906-318">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="8e906-319">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-319">This rule was introduced in:</span></span> 
- [<span data-ttu-id="8e906-320">Windows 10 版本 1803</span><span class="sxs-lookup"><span data-stu-id="8e906-320">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="8e906-321">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-321">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-322">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-322">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="8e906-323">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="8e906-323">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="8e906-324">Intune 名称： `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="8e906-324">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="8e906-325">Configuration Manager 名称： `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="8e906-325">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="8e906-326">GUID：`01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="8e906-326">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="8e906-327">阻止执行可能混淆的脚本</span><span class="sxs-lookup"><span data-stu-id="8e906-327">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="8e906-328">此规则在混淆的脚本中检测可疑属性。</span><span class="sxs-lookup"><span data-stu-id="8e906-328">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="8e906-329">脚本模糊处理是恶意软件作者和合法应用程序都用于隐藏知识产权或缩短脚本加载次数的常见技术。</span><span class="sxs-lookup"><span data-stu-id="8e906-329">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="8e906-330">恶意软件作者还使用模糊处理使恶意代码更难阅读，这可防止人员和安全软件进行严格的审查。</span><span class="sxs-lookup"><span data-stu-id="8e906-330">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="8e906-331">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-331">This rule was introduced in:</span></span>
- [<span data-ttu-id="8e906-332">Windows 10 版本 1709</span><span class="sxs-lookup"><span data-stu-id="8e906-332">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="8e906-333">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-333">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-334">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-334">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="8e906-335">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="8e906-335">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="8e906-336">Intune 名称： `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="8e906-336">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="8e906-337">Configuration Manager 名称： `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="8e906-337">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="8e906-338">GUID：`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="8e906-338">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="8e906-339">阻止 JavaScript 或 VBScript 启动下载的可执行内容</span><span class="sxs-lookup"><span data-stu-id="8e906-339">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="8e906-340">此规则阻止脚本启动潜在恶意下载的内容。</span><span class="sxs-lookup"><span data-stu-id="8e906-340">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="8e906-341">用 JavaScript 或 VBScript 编写的恶意软件通常充当从 Internet 提取和启动其他恶意软件的下载程序。</span><span class="sxs-lookup"><span data-stu-id="8e906-341">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="8e906-342">虽然不常见，但业务线应用程序有时会使用脚本下载和启动安装程序。</span><span class="sxs-lookup"><span data-stu-id="8e906-342">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="8e906-343">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-343">This rule was introduced in:</span></span>  
- [<span data-ttu-id="8e906-344">Windows 10 版本 1709</span><span class="sxs-lookup"><span data-stu-id="8e906-344">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="8e906-345">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-345">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-346">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-346">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="8e906-347">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="8e906-347">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="8e906-348">Intune 名称： `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="8e906-348">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="8e906-349">Configuration Manager 名称： `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="8e906-349">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="8e906-350">GUID：`D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="8e906-350">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="8e906-351">阻止 Office 应用程序创建可执行内容</span><span class="sxs-lookup"><span data-stu-id="8e906-351">Block Office applications from creating executable content</span></span>

<span data-ttu-id="8e906-352">此规则阻止将恶意代码写入磁盘，从而阻止 Office 应用（包括 Word、Excel 和 PowerPoint）创建潜在恶意可执行内容。</span><span class="sxs-lookup"><span data-stu-id="8e906-352">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="8e906-353">滥用 Office 作为矢量的恶意软件可能会尝试从 Office 中中断，将恶意组件保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="8e906-353">Malware that abuses Office as a vector may attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="8e906-354">这些恶意组件在计算机重新启动后将一直保留于系统。</span><span class="sxs-lookup"><span data-stu-id="8e906-354">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="8e906-355">因此，此规则可防御常见的持久性技术。</span><span class="sxs-lookup"><span data-stu-id="8e906-355">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="8e906-356">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-356">This rule was introduced in:</span></span> 
- [<span data-ttu-id="8e906-357">Windows 10 版本 1709</span><span class="sxs-lookup"><span data-stu-id="8e906-357">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="8e906-358">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-358">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-359">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-359">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="8e906-360">[System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM 现在是 Microsoft Endpoint Configuration Manager) </span><span class="sxs-lookup"><span data-stu-id="8e906-360">[System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="8e906-361">Intune 名称： `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="8e906-361">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="8e906-362">SCCM 名称： `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="8e906-362">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="8e906-363">GUID：`3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="8e906-363">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="8e906-364">阻止 Office 应用程序将代码注入其他进程</span><span class="sxs-lookup"><span data-stu-id="8e906-364">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="8e906-365">此规则阻止从 Office 应用向其他进程注入代码的尝试。</span><span class="sxs-lookup"><span data-stu-id="8e906-365">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="8e906-366">攻击者可能会尝试使用 Office 应用通过代码注入将恶意代码迁移到其他进程中，因此代码可以伪装成一个干净流程。</span><span class="sxs-lookup"><span data-stu-id="8e906-366">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="8e906-367">使用代码注入没有已知的合法业务用途。</span><span class="sxs-lookup"><span data-stu-id="8e906-367">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="8e906-368">此规则适用于 Word、Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="8e906-368">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="8e906-369">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-369">This rule was introduced in:</span></span> 
- [<span data-ttu-id="8e906-370">Windows 10 版本 1709</span><span class="sxs-lookup"><span data-stu-id="8e906-370">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="8e906-371">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-371">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-372">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-372">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="8e906-373">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="8e906-373">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="8e906-374">Intune 名称： `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="8e906-374">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="8e906-375">Configuration Manager 名称： `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="8e906-375">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="8e906-376">GUID：`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="8e906-376">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="8e906-377">阻止 Office 通信应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="8e906-377">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="8e906-378">此规则阻止 Outlook 创建子进程，同时仍允许合法的 Outlook 功能。</span><span class="sxs-lookup"><span data-stu-id="8e906-378">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="8e906-379">此规则可防止社会工程攻击，并防止利用代码滥用 Outlook 中的漏洞。</span><span class="sxs-lookup"><span data-stu-id="8e906-379">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="8e906-380">它还可抵御 [Outlook](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) 规则和表单攻击，攻击者可以在用户凭据遭到泄露时使用这些漏洞。</span><span class="sxs-lookup"><span data-stu-id="8e906-380">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="8e906-381">此规则仅适用于 Outlook 和 Outlook.com。</span><span class="sxs-lookup"><span data-stu-id="8e906-381">This rule applies to Outlook and Outlook.com only.</span></span>

<span data-ttu-id="8e906-382">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-382">This rule was introduced in:</span></span> 
- [<span data-ttu-id="8e906-383">Windows 10 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-383">Windows 10, version 1809</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="8e906-384">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-384">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-385">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-385">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="8e906-386">Intune 名称： `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="8e906-386">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="8e906-387">Configuration Manager 名称：不可用</span><span class="sxs-lookup"><span data-stu-id="8e906-387">Configuration Manager name: Not available</span></span>

<span data-ttu-id="8e906-388">GUID：`26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="8e906-388">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="8e906-389">通过 WMI 事件订阅阻止持久性</span><span class="sxs-lookup"><span data-stu-id="8e906-389">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="8e906-390">此规则可防止恶意软件滥用 WMI 在设备上获得持久性。</span><span class="sxs-lookup"><span data-stu-id="8e906-390">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e906-391">文件和文件夹排除项不适用于此攻击面减少规则。</span><span class="sxs-lookup"><span data-stu-id="8e906-391">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="8e906-392">无文件威胁采用各种策略来保持隐藏，以避免在文件系统中可见，并获得定期执行控制。</span><span class="sxs-lookup"><span data-stu-id="8e906-392">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="8e906-393">某些威胁可能会滥用 WMI 存储库和事件模型来保持隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="8e906-393">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="8e906-394">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-394">This rule was introduced in:</span></span> 
- [<span data-ttu-id="8e906-395">Windows 10 版本 1903</span><span class="sxs-lookup"><span data-stu-id="8e906-395">Windows 10, version 1903</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="8e906-396">Windows Server 1903</span><span class="sxs-lookup"><span data-stu-id="8e906-396">Windows Server 1903</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="8e906-397">Intune 名称：不可用</span><span class="sxs-lookup"><span data-stu-id="8e906-397">Intune name: Not available</span></span>

<span data-ttu-id="8e906-398">Configuration Manager 名称：不可用</span><span class="sxs-lookup"><span data-stu-id="8e906-398">Configuration Manager name: Not available</span></span>

<span data-ttu-id="8e906-399">GUID：`e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="8e906-399">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="8e906-400">阻止源自 PSExec 和 WMI 命令的进程创建</span><span class="sxs-lookup"><span data-stu-id="8e906-400">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="8e906-401">此规则阻止通过 [PsExec](https://docs.microsoft.com/sysinternals/downloads/psexec) 和 [WMI 创建](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) 的进程运行。</span><span class="sxs-lookup"><span data-stu-id="8e906-401">This rule blocks processes created through [PsExec](https://docs.microsoft.com/sysinternals/downloads/psexec) and [WMI](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="8e906-402">PsExec 和 WMI 都可以远程执行代码，因此存在恶意软件滥用此功能以用于命令和控制目的，或在整个组织的网络中传播感染的风险。</span><span class="sxs-lookup"><span data-stu-id="8e906-402">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="8e906-403">仅在使用 [Intune](https://docs.microsoft.com/intune) 或其他 MDM 解决方案管理设备时使用此规则。</span><span class="sxs-lookup"><span data-stu-id="8e906-403">Only use this rule if you're managing your devices with [Intune](https://docs.microsoft.com/intune) or another MDM solution.</span></span> <span data-ttu-id="8e906-404">此规则与通过 Microsoft [Endpoint Configuration Manager](https://docs.microsoft.com/configmgr) 管理不兼容，因为此规则会阻止 Configuration Manager 客户端用于正常运行的 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="8e906-404">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="8e906-405">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-405">This rule was introduced in:</span></span> 
- [<span data-ttu-id="8e906-406">Windows 10 版本 1803</span><span class="sxs-lookup"><span data-stu-id="8e906-406">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="8e906-407">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-407">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-408">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-408">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="8e906-409">Intune 名称： `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="8e906-409">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="8e906-410">Configuration Manager 名称：不适用</span><span class="sxs-lookup"><span data-stu-id="8e906-410">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="8e906-411">GUID：`d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="8e906-411">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="8e906-412">阻止从 USB 运行的不受信任的和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="8e906-412">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="8e906-413">通过此规则，管理员可以阻止未签名或不受信任的可执行文件从 USB 可移动驱动器（包括 SD 卡）运行。</span><span class="sxs-lookup"><span data-stu-id="8e906-413">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="8e906-414">阻止的文件类型包括可执行 (文件，如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="8e906-414">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="8e906-415">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-415">This rule was introduced in:</span></span> 
- [<span data-ttu-id="8e906-416">Windows 10 版本 1803</span><span class="sxs-lookup"><span data-stu-id="8e906-416">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="8e906-417">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-417">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-418">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-418">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="8e906-419">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="8e906-419">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="8e906-420">Intune 名称： `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="8e906-420">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="8e906-421">Configuration Manager 名称： `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="8e906-421">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="8e906-422">GUID：`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="8e906-422">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="8e906-423">阻止从 Office 宏调用 Win32 API</span><span class="sxs-lookup"><span data-stu-id="8e906-423">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="8e906-424">此规则阻止 VBA 宏调用 Win32 API。</span><span class="sxs-lookup"><span data-stu-id="8e906-424">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="8e906-425">Office VBA 支持 Win32 API 调用。</span><span class="sxs-lookup"><span data-stu-id="8e906-425">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="8e906-426">恶意软件可能会滥用此功能，例如调用 [Win32 API 以启动恶意 shellcode，](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) 而无需将任何内容直接写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="8e906-426">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="8e906-427">大多数组织不依赖于在日常运行中调用 Win32 API 的功能，即使它们以其他方式使用宏。</span><span class="sxs-lookup"><span data-stu-id="8e906-427">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="8e906-428">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-428">This rule was introduced in:</span></span>
- [<span data-ttu-id="8e906-429">Windows 10 版本 1709</span><span class="sxs-lookup"><span data-stu-id="8e906-429">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="8e906-430">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-430">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-431">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-431">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="8e906-432">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="8e906-432">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="8e906-433">Intune 名称： `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="8e906-433">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="8e906-434">Configuration Manager 名称： `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="8e906-434">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="8e906-435">GUID：`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="8e906-435">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="8e906-436">使用高级防护抵御勒索软件</span><span class="sxs-lookup"><span data-stu-id="8e906-436">Use advanced protection against ransomware</span></span>

<span data-ttu-id="8e906-437">此规则提供针对勒索软件的额外保护层。</span><span class="sxs-lookup"><span data-stu-id="8e906-437">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="8e906-438">它会扫描进入系统的可执行文件，以确定它们是否可信。</span><span class="sxs-lookup"><span data-stu-id="8e906-438">It scans executable files entering the system to determine whether they're trustworthy.</span></span> <span data-ttu-id="8e906-439">如果文件与勒索软件非常类似，此规则会阻止它们运行，除非它们位于受信任的列表或排除列表中。</span><span class="sxs-lookup"><span data-stu-id="8e906-439">If the files closely resemble ransomware, this rule blocks them from running, unless they're in a trusted list or an exclusion list.</span></span>

> [!NOTE]
> <span data-ttu-id="8e906-440">必须 [启用云保护才能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 使用此规则。</span><span class="sxs-lookup"><span data-stu-id="8e906-440">You must [enable cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>

<span data-ttu-id="8e906-441">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="8e906-441">This rule was introduced in:</span></span> 
- [<span data-ttu-id="8e906-442">Windows 10 版本 1803</span><span class="sxs-lookup"><span data-stu-id="8e906-442">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="8e906-443">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="8e906-443">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="8e906-444">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e906-444">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="8e906-445">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="8e906-445">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="8e906-446">Intune 名称： `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="8e906-446">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="8e906-447">Configuration Manager 名称： `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="8e906-447">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="8e906-448">GUID：`c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="8e906-448">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>

## <a name="see-also"></a><span data-ttu-id="8e906-449">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e906-449">See also</span></span>

- [<span data-ttu-id="8e906-450">攻击面减少常见问题解答</span><span class="sxs-lookup"><span data-stu-id="8e906-450">Attack surface reduction FAQ</span></span>](attack-surface-reduction-faq.md)
- [<span data-ttu-id="8e906-451">启用攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="8e906-451">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
- [<span data-ttu-id="8e906-452">评估攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="8e906-452">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
- [<span data-ttu-id="8e906-453">Microsoft Defender 防病毒与其他防病毒/反恶意软件解决方案的兼容性</span><span class="sxs-lookup"><span data-stu-id="8e906-453">Compatibility of Microsoft Defender Antivirus with other antivirus/antimalware solutions</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
