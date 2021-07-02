---
title: 使用攻击面减少规则来避免感染恶意软件
description: 攻击面减少规则有助于防止攻击使用应用和脚本感染带恶意软件的设备。
keywords: 攻击面减少规则， asr， hips， 主机入侵防护系统， 防护规则， 反攻击， 攻击， 感染防护， Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ed6dc9956c3e78f8ed39dca9cd6bf0421dd28456
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276985"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="928fa-104">使用攻击面减少规则来避免感染恶意软件</span><span class="sxs-lookup"><span data-stu-id="928fa-104">Use attack surface reduction rules to prevent malware infection</span></span>

<span data-ttu-id="928fa-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="928fa-105">**Applies to:**</span></span>

- [<span data-ttu-id="928fa-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="928fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="928fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="928fa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="928fa-108">攻击面减少规则为什么很重要</span><span class="sxs-lookup"><span data-stu-id="928fa-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="928fa-109">组织的攻击面包括攻击者可能损害组织设备或网络的所有位置。</span><span class="sxs-lookup"><span data-stu-id="928fa-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="928fa-110">减少攻击面意味着保护组织的设备和网络，这使攻击者能够执行攻击的方法更少。</span><span class="sxs-lookup"><span data-stu-id="928fa-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="928fa-111">在 Microsoft Defender for Endpoint 中配置攻击面减少规则可以提供帮助！</span><span class="sxs-lookup"><span data-stu-id="928fa-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="928fa-112">攻击面减少规则针对某些软件行为，例如：</span><span class="sxs-lookup"><span data-stu-id="928fa-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="928fa-113">启动尝试下载或运行文件的可执行文件和脚本</span><span class="sxs-lookup"><span data-stu-id="928fa-113">Launching executable files and scripts that attempt to download or run files</span></span>
- <span data-ttu-id="928fa-114">运行混淆的或可疑的脚本</span><span class="sxs-lookup"><span data-stu-id="928fa-114">Running obfuscated or otherwise suspicious scripts</span></span>
- <span data-ttu-id="928fa-115">执行应用在正常日常工作期间通常不会启动的行为</span><span class="sxs-lookup"><span data-stu-id="928fa-115">Performing behaviors that apps don't usually initiate during normal day-to-day work</span></span>

<span data-ttu-id="928fa-116">此类软件行为有时在合法应用程序中可见。</span><span class="sxs-lookup"><span data-stu-id="928fa-116">Such software behaviors are sometimes seen in legitimate applications.</span></span> <span data-ttu-id="928fa-117">但是，这些行为通常被视为有风险，因为它们通常被攻击者通过恶意软件滥用。</span><span class="sxs-lookup"><span data-stu-id="928fa-117">However, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="928fa-118">攻击面减少规则可以限制基于软件的风险行为，并有助于确保组织安全。</span><span class="sxs-lookup"><span data-stu-id="928fa-118">Attack surface reduction rules can constrain software-based risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="928fa-119">有关配置攻击面减少规则的信息，请参阅启用 [攻击面减少规则](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="928fa-119">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="928fa-120">在部署之前评估规则影响</span><span class="sxs-lookup"><span data-stu-id="928fa-120">Assess rule impact before deployment</span></span>

<span data-ttu-id="928fa-121">你可以评估攻击面减少规则可能会如何影响你的网络，在 危险和漏洞管理 中打开该[规则的安全建议](/windows/security/threat-protection/#tvm)。</span><span class="sxs-lookup"><span data-stu-id="928fa-121">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](/windows/security/threat-protection/#tvm).</span></span>

:::image type="content" source="images/asrrecommendation.png" alt-text="攻击面减少规则的安全重新成本":::

<span data-ttu-id="928fa-123">在建议详细信息窗格中，检查用户影响以确定设备可接受在阻止模式下启用规则的新策略的百分比，而不会对工作效率产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="928fa-123">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

<span data-ttu-id="928fa-124">有关 [支持](enable-attack-surface-reduction.md#requirements) 的操作系统和其他要求信息的信息，请参阅"启用攻击面减少规则"文章中的要求。</span><span class="sxs-lookup"><span data-stu-id="928fa-124">See [Requirements](enable-attack-surface-reduction.md#requirements) in the "Enable attack surface reduction rules" article for information about supported operating systems and additional requirement information.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="928fa-125">评估审核模式</span><span class="sxs-lookup"><span data-stu-id="928fa-125">Audit mode for evaluation</span></span>

<span data-ttu-id="928fa-126">使用 [审核模式](audit-windows-defender.md) 评估攻击面减少规则在启用后对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="928fa-126">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if enabled.</span></span> <span data-ttu-id="928fa-127">首先在审核模式下运行所有规则，以便了解它们如何影响业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="928fa-127">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="928fa-128">许多业务线应用程序都是以有限的安全问题编写，它们执行任务的方式可能类似于恶意软件。</span><span class="sxs-lookup"><span data-stu-id="928fa-128">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="928fa-129">通过监视审核数据 [并添加](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 必要应用程序的排除项，你可以部署攻击面减少规则，而不会降低工作效率。</span><span class="sxs-lookup"><span data-stu-id="928fa-129">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="928fa-130">用户警告模式</span><span class="sxs-lookup"><span data-stu-id="928fa-130">Warn mode for users</span></span>

<span data-ttu-id="928fa-131"> (**新**！) 警告模式功能之前，已启用的攻击面减少规则可以设置为审核模式或阻止模式。</span><span class="sxs-lookup"><span data-stu-id="928fa-131">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="928fa-132">使用新的警告模式，只要内容被攻击面减少规则阻止，用户就会看到一个指示内容被阻止的对话框。</span><span class="sxs-lookup"><span data-stu-id="928fa-132">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="928fa-133">该对话框还允许用户选择取消阻止内容。</span><span class="sxs-lookup"><span data-stu-id="928fa-133">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="928fa-134">然后，用户可以重试其操作，操作完成。</span><span class="sxs-lookup"><span data-stu-id="928fa-134">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="928fa-135">当用户取消阻止内容时，该内容将保持取消阻止状态 24 小时，然后阻止恢复。</span><span class="sxs-lookup"><span data-stu-id="928fa-135">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="928fa-136">警告模式可帮助组织制定攻击面减少规则，而不会阻止用户访问执行其任务所需的内容。</span><span class="sxs-lookup"><span data-stu-id="928fa-136">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span>

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="928fa-137">警告模式运行的要求</span><span class="sxs-lookup"><span data-stu-id="928fa-137">Requirements for warn mode to work</span></span>

<span data-ttu-id="928fa-138">运行以下版本的警告的设备上支持警告Windows：</span><span class="sxs-lookup"><span data-stu-id="928fa-138">Warn mode is supported on devices running the following versions of Windows:</span></span>

- <span data-ttu-id="928fa-139">[Windows 10 版本 1809](/windows/whats-new/whats-new-windows-10-version-1809)或更高版本</span><span class="sxs-lookup"><span data-stu-id="928fa-139">[Windows 10, version 1809](/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="928fa-140">[Windows Server 版本 1809](/windows-server/get-started/whats-new-in-windows-server-1809)或更高版本</span><span class="sxs-lookup"><span data-stu-id="928fa-140">[Windows Server, version 1809](/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>

<span data-ttu-id="928fa-141">Microsoft Defender 防病毒必须在活动模式下使用实时[保护运行](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)。</span><span class="sxs-lookup"><span data-stu-id="928fa-141">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="928fa-142">此外，请确保[Microsoft Defender 防病毒反恶意软件更新](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。</span><span class="sxs-lookup"><span data-stu-id="928fa-142">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>

- <span data-ttu-id="928fa-143">最低平台发布要求： `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="928fa-143">Minimum platform release requirement: `4.18.2008.9`</span></span>
- <span data-ttu-id="928fa-144">最低引擎发布要求： `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="928fa-144">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="928fa-145">有关详细信息和获取更新，请参阅 [Microsoft Defender 反恶意软件平台的更新](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="928fa-145">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="928fa-146">不支持警告模式的情况</span><span class="sxs-lookup"><span data-stu-id="928fa-146">Cases where warn mode is not supported</span></span>

<span data-ttu-id="928fa-147">当你在三个攻击面减少规则中配置警告模式时，它们不受Microsoft Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="928fa-147">Warn mode is not supported for three attack surface reduction rules when you configure them in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="928fa-148"> (如果使用组策略配置攻击面减少规则，则支持警告模式。) 在 Microsoft Endpoint Manager 中配置时不支持警告模式的三个规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="928fa-148">(If you use Group Policy to configure your attack surface reduction rules, warn mode is supported.) The three rules that do not support warn mode when you configure them in Microsoft Endpoint Manager are as follows:</span></span>

- <span data-ttu-id="928fa-149">[阻止 JavaScript 或 VBScript 使用](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) GUID (下载的可执行 `d3e037e1-3eb8-44c8-a917-57927947596d`) </span><span class="sxs-lookup"><span data-stu-id="928fa-149">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="928fa-150">[通过 WMI 事件订阅和 GUID](#block-persistence-through-wmi-event-subscription) (阻止 `e6db77e5-3df2-4cf1-b95a-636979351e5b` 持久性) </span><span class="sxs-lookup"><span data-stu-id="928fa-150">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="928fa-151">[使用高级防护抵御勒索软件](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`) </span><span class="sxs-lookup"><span data-stu-id="928fa-151">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="928fa-152">此外，运行早期版本的 Windows 的设备上不支持警告Windows。</span><span class="sxs-lookup"><span data-stu-id="928fa-152">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="928fa-153">在这种情况下，配置为在警告模式下运行的攻击面减少规则将在阻止模式下运行。</span><span class="sxs-lookup"><span data-stu-id="928fa-153">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="928fa-154">通知和警报</span><span class="sxs-lookup"><span data-stu-id="928fa-154">Notifications and alerts</span></span>

<span data-ttu-id="928fa-155">每当触发攻击面减少规则时，都会在设备上显示通知。</span><span class="sxs-lookup"><span data-stu-id="928fa-155">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="928fa-156">你可以使用公司的详细信息和联系人信息[自定义通知](customize-attack-surface-reduction.md#customize-the-notification)。</span><span class="sxs-lookup"><span data-stu-id="928fa-156">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="928fa-157">此外，当触发某些攻击面减少规则时，将生成警报。</span><span class="sxs-lookup"><span data-stu-id="928fa-157">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span>

<span data-ttu-id="928fa-158">通知和生成的任何通知都可以在 Microsoft 365 Defender 门户 ()  (以前称为 Microsoft Defender 安全中心 [https://security.microsoft.com](https://security.microsoft.com)) 。 [](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="928fa-158">Notifications and any alerts that are generated can be viewed in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) (formerly called the [Microsoft Defender Security Center](microsoft-defender-security-center.md)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="928fa-159">高级搜寻和攻击面减少事件</span><span class="sxs-lookup"><span data-stu-id="928fa-159">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="928fa-160">可以使用高级搜寻来查看攻击面减少事件。</span><span class="sxs-lookup"><span data-stu-id="928fa-160">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="928fa-161">为了简化传入数据的数量，使用高级搜寻仅可查看每小时的唯一进程。</span><span class="sxs-lookup"><span data-stu-id="928fa-161">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="928fa-162">攻击面减少事件的时间是一小时内首次看到该事件。</span><span class="sxs-lookup"><span data-stu-id="928fa-162">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="928fa-163">例如，假设在下午 2：00 小时内在 10 台设备上发生攻击面减少事件。</span><span class="sxs-lookup"><span data-stu-id="928fa-163">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="928fa-164">假设第一个事件在 2：15 发生，最后一个事件在 2：45 发生。</span><span class="sxs-lookup"><span data-stu-id="928fa-164">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="928fa-165">借助高级搜寻，你将看到该事件的一个实例 (即使该事件实际发生在 10 台设备上) ，其时间戳将为下午 2：15。</span><span class="sxs-lookup"><span data-stu-id="928fa-165">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span>

<span data-ttu-id="928fa-166">有关高级搜寻详细信息，请参阅使用高级搜寻主动 [搜寻威胁](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="928fa-166">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="928fa-167">跨多个版本的攻击Windows功能</span><span class="sxs-lookup"><span data-stu-id="928fa-167">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="928fa-168">你可以为运行以下任一版本和版本的设备设置攻击面减少规则Windows：</span><span class="sxs-lookup"><span data-stu-id="928fa-168">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="928fa-169">Windows 10 专业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="928fa-169">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="928fa-170">Windows 10 企业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="928fa-170">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="928fa-171">Windows服务器版本[1803 (半年频道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本</span><span class="sxs-lookup"><span data-stu-id="928fa-171">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="928fa-172">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-172">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="928fa-173">尽管攻击面减少规则不需要使用 Windows [E5](/windows/deployment/deploy-enterprise-licenses)许可证，但如果已使用 Windows E5，则获得高级管理功能。</span><span class="sxs-lookup"><span data-stu-id="928fa-173">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="928fa-174">仅在 E5 中提供的高级Windows包括：</span><span class="sxs-lookup"><span data-stu-id="928fa-174">The advanced capabilities - available only in Windows E5 - include:</span></span>

- <span data-ttu-id="928fa-175">Defender for Endpoint 中提供的监视、 [分析和工作流](microsoft-defender-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="928fa-175">The monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md)</span></span>
- <span data-ttu-id="928fa-176">中的报告和配置[Microsoft 365 Defender。](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="928fa-176">The reporting and configuration capabilities in [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="928fa-177">这些高级功能不适用于 Windows Professional 或 Windows E3 许可证。</span><span class="sxs-lookup"><span data-stu-id="928fa-177">These advanced capabilities aren't available with a Windows Professional or Windows E3 license.</span></span> <span data-ttu-id="928fa-178">但是，如果你有这些许可证，可以使用事件查看器和Microsoft Defender 防病毒日志查看攻击面减少规则事件。</span><span class="sxs-lookup"><span data-stu-id="928fa-178">However, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="928fa-179">查看攻击门户中的攻击Microsoft 365 Defender事件</span><span class="sxs-lookup"><span data-stu-id="928fa-179">Review attack surface reduction events in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="928fa-180">Defender for Endpoint 提供事件和阻止的详细报告，作为警报调查方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="928fa-180">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="928fa-181">可以使用高级搜寻查询 defender 的终结点[Microsoft 365 Defender](microsoft-defender-security-center.md)中的[终结点数据](advanced-hunting-query-language.md)。</span><span class="sxs-lookup"><span data-stu-id="928fa-181">You can query Defender for Endpoint data in [Microsoft 365 Defender](microsoft-defender-security-center.md) by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="928fa-182">如果你运行的是审核 [模式](audit-windows-defender.md)，可以使用高级搜寻了解攻击面减少规则可能会如何影响你的环境。</span><span class="sxs-lookup"><span data-stu-id="928fa-182">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules might affect your environment.</span></span>

<span data-ttu-id="928fa-183">示例查询如下所示:</span><span class="sxs-lookup"><span data-stu-id="928fa-183">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="928fa-184">查看事件查看器中的攻击Windows减少事件</span><span class="sxs-lookup"><span data-stu-id="928fa-184">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="928fa-185">你可以查看攻击Windows日志以查看攻击面减少规则生成的事件：</span><span class="sxs-lookup"><span data-stu-id="928fa-185">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="928fa-186">下载 [评估包](https://aka.ms/mp7z2w) ，将文件 *cfa-events.xml* 到设备上易于访问的位置。</span><span class="sxs-lookup"><span data-stu-id="928fa-186">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>

2. <span data-ttu-id="928fa-187">在事件查看器 *中* 输入"开始"菜单事件查看器Windows事件查看器。</span><span class="sxs-lookup"><span data-stu-id="928fa-187">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>

3. <span data-ttu-id="928fa-188">在 **"操作"** 下，**选择"导入自定义视图..."。**</span><span class="sxs-lookup"><span data-stu-id="928fa-188">Under **Actions**, select **Import custom view...**.</span></span>

4. <span data-ttu-id="928fa-189">选择从 *cfa-events.xml* 文件的位置创建的文件。</span><span class="sxs-lookup"><span data-stu-id="928fa-189">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="928fa-190">或者，[直接复制 XML。](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="928fa-190">Alternatively, [copy the XML directly](event-views.md).</span></span>

5. <span data-ttu-id="928fa-191">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="928fa-191">Select **OK**.</span></span>

<span data-ttu-id="928fa-192">您可以创建一个自定义视图，该视图筛选事件以只显示下列事件，所有这些事件均与受控文件夹访问权限相关：</span><span class="sxs-lookup"><span data-stu-id="928fa-192">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="928fa-193">事件 ID</span><span class="sxs-lookup"><span data-stu-id="928fa-193">Event ID</span></span>|<span data-ttu-id="928fa-194">描述</span><span class="sxs-lookup"><span data-stu-id="928fa-194">Description</span></span>|
|---|---|
|<span data-ttu-id="928fa-195">5007</span><span class="sxs-lookup"><span data-stu-id="928fa-195">5007</span></span>|<span data-ttu-id="928fa-196">更改设置时的事件</span><span class="sxs-lookup"><span data-stu-id="928fa-196">Event when settings are changed</span></span>|
|<span data-ttu-id="928fa-197">1121</span><span class="sxs-lookup"><span data-stu-id="928fa-197">1121</span></span>|<span data-ttu-id="928fa-198">在阻止模式下触发规则时的事件</span><span class="sxs-lookup"><span data-stu-id="928fa-198">Event when rule fires in Block-mode</span></span>|
|<span data-ttu-id="928fa-199">1122</span><span class="sxs-lookup"><span data-stu-id="928fa-199">1122</span></span>|<span data-ttu-id="928fa-200">在审核模式下触发规则时的事件</span><span class="sxs-lookup"><span data-stu-id="928fa-200">Event when rule fires in Audit-mode</span></span>|

<span data-ttu-id="928fa-201">针对事件日志中的攻击面减少事件列出的"引擎版本"由 Defender for Endpoint 生成，而不是由操作系统生成。</span><span class="sxs-lookup"><span data-stu-id="928fa-201">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="928fa-202">Defender for Endpoint 与 Windows 10 集成，因此此功能适用于安装了 Windows 10 的所有设备。</span><span class="sxs-lookup"><span data-stu-id="928fa-202">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="928fa-203">攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="928fa-203">Attack surface reduction rules</span></span>

<span data-ttu-id="928fa-204">下表和子部分介绍了 16 个攻击面减少规则中的每个规则。</span><span class="sxs-lookup"><span data-stu-id="928fa-204">The following table and subsections describe each of the 16 attack surface reduction rules.</span></span> <span data-ttu-id="928fa-205">攻击面减少规则按规则名称的字母顺序列出。</span><span class="sxs-lookup"><span data-stu-id="928fa-205">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span>

<span data-ttu-id="928fa-206">如果要使用组策略或 PowerShell 配置攻击面减少规则，则需要 GUID。</span><span class="sxs-lookup"><span data-stu-id="928fa-206">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="928fa-207">另一方面，如果使用 Microsoft Endpoint Manager 或 Microsoft Intune，则不需要 GUID。</span><span class="sxs-lookup"><span data-stu-id="928fa-207">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>

|<span data-ttu-id="928fa-208">规则名称</span><span class="sxs-lookup"><span data-stu-id="928fa-208">Rule name</span></span>|<span data-ttu-id="928fa-209">GUID</span><span class="sxs-lookup"><span data-stu-id="928fa-209">GUID</span></span>|<span data-ttu-id="928fa-210">文件&文件夹排除项</span><span class="sxs-lookup"><span data-stu-id="928fa-210">File & folder exclusions</span></span>|<span data-ttu-id="928fa-211">支持的最低操作系统</span><span class="sxs-lookup"><span data-stu-id="928fa-211">Minimum OS supported</span></span>|
|---|:---:|---|---|
|[<span data-ttu-id="928fa-212">阻止滥用被攻击的易受攻击的已签名驱动程序</span><span class="sxs-lookup"><span data-stu-id="928fa-212">Block abuse of exploited vulnerable signed drivers</span></span>](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|<span data-ttu-id="928fa-213">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-213">Supported</span></span>|<span data-ttu-id="928fa-214">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或) </span><span class="sxs-lookup"><span data-stu-id="928fa-214">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater)</span></span> |
|[<span data-ttu-id="928fa-215">阻止 Adobe Reader 创建子进程</span><span class="sxs-lookup"><span data-stu-id="928fa-215">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|<span data-ttu-id="928fa-216">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-216">Supported</span></span>|<span data-ttu-id="928fa-217">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-217">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-218">阻止所有Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="928fa-218">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|<span data-ttu-id="928fa-219">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-219">Supported</span></span>|<span data-ttu-id="928fa-220">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-220">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-221">阻止本地安全机构子系统Windows凭据 (lsass.exe) </span><span class="sxs-lookup"><span data-stu-id="928fa-221">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|<span data-ttu-id="928fa-222">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-222">Supported</span></span>|<span data-ttu-id="928fa-223">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-223">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-224">阻止来自电子邮件客户端和 Webmail 的可执行内容</span><span class="sxs-lookup"><span data-stu-id="928fa-224">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|<span data-ttu-id="928fa-225">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-225">Supported</span></span>|<span data-ttu-id="928fa-226">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-226">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-227">阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件</span><span class="sxs-lookup"><span data-stu-id="928fa-227">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|<span data-ttu-id="928fa-228">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-228">Supported</span></span>|<span data-ttu-id="928fa-229">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-229">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-230">阻止执行可能混淆的脚本</span><span class="sxs-lookup"><span data-stu-id="928fa-230">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|<span data-ttu-id="928fa-231">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-231">Supported</span></span>|<span data-ttu-id="928fa-232">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-232">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-233">阻止 JavaScript 或 VBScript 启动下载的可执行内容</span><span class="sxs-lookup"><span data-stu-id="928fa-233">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|<span data-ttu-id="928fa-234">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-234">Supported</span></span>|<span data-ttu-id="928fa-235">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-235">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-236">阻止Office应用程序创建可执行内容</span><span class="sxs-lookup"><span data-stu-id="928fa-236">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|<span data-ttu-id="928fa-237">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-237">Supported</span></span>|<span data-ttu-id="928fa-238">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-238">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-239">阻止Office代码注入其他进程</span><span class="sxs-lookup"><span data-stu-id="928fa-239">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|<span data-ttu-id="928fa-240">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-240">Supported</span></span>|<span data-ttu-id="928fa-241">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-241">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-242">阻止Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="928fa-242">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|<span data-ttu-id="928fa-243">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-243">Supported</span></span>|<span data-ttu-id="928fa-244">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-244">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-245">通过 WMI 事件订阅阻止持久性</span><span class="sxs-lookup"><span data-stu-id="928fa-245">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|<span data-ttu-id="928fa-246">不支持</span><span class="sxs-lookup"><span data-stu-id="928fa-246">Not supported</span></span>|<span data-ttu-id="928fa-247">[Windows 10版本 1903 (](/windows/whats-new/whats-new-windows-10-version-1903)版本 18362) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-247">[Windows 10, version 1903](/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span>|
|[<span data-ttu-id="928fa-248">阻止源自 PSExec 和 WMI 命令的进程创建</span><span class="sxs-lookup"><span data-stu-id="928fa-248">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|<span data-ttu-id="928fa-249">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-249">Supported</span></span>|<span data-ttu-id="928fa-250">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-250">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-251">阻止从 USB 运行的不受信任的和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="928fa-251">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|<span data-ttu-id="928fa-252">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-252">Supported</span></span>|<span data-ttu-id="928fa-253">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-253">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-254">阻止从宏Office Win32 API 调用</span><span class="sxs-lookup"><span data-stu-id="928fa-254">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|<span data-ttu-id="928fa-255">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-255">Supported</span></span>|<span data-ttu-id="928fa-256">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-256">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="928fa-257">使用高级防护抵御勒索软件</span><span class="sxs-lookup"><span data-stu-id="928fa-257">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|<span data-ttu-id="928fa-258">支持</span><span class="sxs-lookup"><span data-stu-id="928fa-258">Supported</span></span>|<span data-ttu-id="928fa-259">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="928fa-259">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a><span data-ttu-id="928fa-260">阻止滥用被攻击的易受攻击的已签名驱动程序</span><span class="sxs-lookup"><span data-stu-id="928fa-260">Block abuse of exploited vulnerable signed drivers</span></span>

<span data-ttu-id="928fa-261">此规则阻止应用程序将易受攻击的已签名驱动程序写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="928fa-261">This rule prevents an application from writing a vulnerable signed driver to disk.</span></span> <span data-ttu-id="928fa-262">具有获取内核访问权限的足够权限的本地应用程序可能会利用通配符、易受攻击的已签名 \-  \- 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="928fa-262">In-the-wild, vulnerable signed drivers can be exploited by local applications \- _that have sufficient privileges_ \- to gain access to the kernel.</span></span> <span data-ttu-id="928fa-263">易受攻击的已签名驱动程序使攻击者能够禁用或规避安全解决方案，最终导致系统泄露。</span><span class="sxs-lookup"><span data-stu-id="928fa-263">Vulnerable signed drivers enable attackers to disable or circumvent security solutions, eventually leading to system compromise.</span></span>

<span data-ttu-id="928fa-264">阻止 **滥用被攻击的易受** 攻击的已签名驱动程序规则不会阻止加载系统中已存在的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="928fa-264">The **Block abuse of exploited vulnerable signed drivers** rule does not block a driver already existing on the system from being loaded.</span></span>

>[!NOTE]
>
> <span data-ttu-id="928fa-265">你可以为 [MEM OMA-URI 自定义规则过程信息使用此 MEM OMA-URI](enable-attack-surface-reduction.md#mem) 配置此规则。</span><span class="sxs-lookup"><span data-stu-id="928fa-265">You can configure this rule using [MEM OMA-URI](enable-attack-surface-reduction.md#mem) for MEM OMA-URI custom rules procedural information.</span></span>
>
> <span data-ttu-id="928fa-266">您还可以使用 [PowerShell](enable-attack-surface-reduction.md#powershell)配置此规则。</span><span class="sxs-lookup"><span data-stu-id="928fa-266">You can also configure this rule using [PowerShell](enable-attack-surface-reduction.md#powershell).</span></span>
>
> <span data-ttu-id="928fa-267">若要检查驱动程序，请使用此网站提交 [驱动程序进行分析](https://www.microsoft.com/en-us/wdsi/driversubmission)。</span><span class="sxs-lookup"><span data-stu-id="928fa-267">To have a driver examined, use this Web site to [Submit a driver for analysis](https://www.microsoft.com/en-us/wdsi/driversubmission).</span></span>

<span data-ttu-id="928fa-268">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-268">Supported operating systems:</span></span>

- <span data-ttu-id="928fa-269">[Windows 10 专业版版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="928fa-269">[Windows 10 Pro, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="928fa-270">[Windows 10 企业版版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="928fa-270">[Windows 10 Enterprise, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="928fa-271">[Windows Server 版本 1803 (半年频道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本</span><span class="sxs-lookup"><span data-stu-id="928fa-271">[Windows Server, version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="928fa-272">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-272">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="928fa-273">Intune 名称： `Block abuse of exploited vulnerable signed drivers`</span><span class="sxs-lookup"><span data-stu-id="928fa-273">Intune Name: `Block abuse of exploited vulnerable signed drivers`</span></span>

<span data-ttu-id="928fa-274">GUID：  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span><span class="sxs-lookup"><span data-stu-id="928fa-274">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span></span>

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="928fa-275">阻止 Adobe Reader 创建子进程</span><span class="sxs-lookup"><span data-stu-id="928fa-275">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="928fa-276">此规则通过阻止 Adobe Reader 创建进程来阻止攻击。</span><span class="sxs-lookup"><span data-stu-id="928fa-276">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="928fa-277">通过社交工程或攻击，恶意软件可以下载和启动有效负载，并退出 Adobe Reader。</span><span class="sxs-lookup"><span data-stu-id="928fa-277">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="928fa-278">通过阻止 Adobe Reader 生成子进程，尝试将其用作矢量的恶意软件可防止传播。</span><span class="sxs-lookup"><span data-stu-id="928fa-278">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="928fa-279">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-279">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-280">Windows 10 版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-280">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="928fa-281">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-281">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-282">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-282">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="928fa-283">Intune 名称： `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="928fa-283">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="928fa-284">Configuration Manager 名称：尚不可用</span><span class="sxs-lookup"><span data-stu-id="928fa-284">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="928fa-285">GUID：`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="928fa-285">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="928fa-286">阻止所有Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="928fa-286">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="928fa-287">此规则阻止Office创建子进程。</span><span class="sxs-lookup"><span data-stu-id="928fa-287">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="928fa-288">Office应用程序包括 Word、Excel、PowerPoint、OneNote 和 Access。</span><span class="sxs-lookup"><span data-stu-id="928fa-288">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="928fa-289">创建恶意子进程是常见的恶意软件策略。</span><span class="sxs-lookup"><span data-stu-id="928fa-289">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="928fa-290">滥用作为Office的恶意软件通常会运行 VBA 宏，并利用代码下载并尝试运行更多有效负载。</span><span class="sxs-lookup"><span data-stu-id="928fa-290">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="928fa-291">但是，某些合法的业务线应用程序也可能出于恶意目的生成子进程;例如生成命令提示符或使用 PowerShell 配置注册表设置。</span><span class="sxs-lookup"><span data-stu-id="928fa-291">However, some legitimate line-of-business applications might also generate child processes for benign purposes; such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="928fa-292">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-292">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-293">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="928fa-293">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="928fa-294">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-294">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-295">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-295">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="928fa-296">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="928fa-296">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="928fa-297">Intune 名称： `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="928fa-297">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="928fa-298">Configuration Manager 名称： `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="928fa-298">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="928fa-299">GUID：`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="928fa-299">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="928fa-300">阻止从本地安全Windows窃取凭据</span><span class="sxs-lookup"><span data-stu-id="928fa-300">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="928fa-301">此规则通过锁定 LSASS 应用程序的本地安全颁发机构子系统服务 (凭据) 。</span><span class="sxs-lookup"><span data-stu-id="928fa-301">This rule helps prevent credential stealing by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="928fa-302">LSASS 对登录 Windows进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="928fa-302">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="928fa-303">Microsoft Defender Credential Guard Windows 10通常会阻止尝试从 LSASS 提取凭据。</span><span class="sxs-lookup"><span data-stu-id="928fa-303">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="928fa-304">但是，某些组织无法在所有计算机上启用 Credential Guard，因为自定义智能卡驱动程序或其他加载到本地安全机构 (LSA) 的程序的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="928fa-304">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="928fa-305">在这些情况下，攻击者可以使用 Mimikatz 等黑客工具从 LSASS 中清除明文密码和 NTLM 哈希。</span><span class="sxs-lookup"><span data-stu-id="928fa-305">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="928fa-306">在某些应用中，该代码枚举所有正在运行的进程，并尝试以详尽的权限打开它们。</span><span class="sxs-lookup"><span data-stu-id="928fa-306">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="928fa-307">此规则拒绝应用的进程打开操作，将详细信息记录到安全事件日志中。</span><span class="sxs-lookup"><span data-stu-id="928fa-307">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="928fa-308">此规则会产生大量噪音。</span><span class="sxs-lookup"><span data-stu-id="928fa-308">This rule can generate a lot of noise.</span></span> <span data-ttu-id="928fa-309">如果你的应用仅枚举 LSASS，但在功能方面没有实际影响，则无需将其添加到排除列表。</span><span class="sxs-lookup"><span data-stu-id="928fa-309">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="928fa-310">此事件日志条目本身不一定表示恶意威胁。</span><span class="sxs-lookup"><span data-stu-id="928fa-310">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="928fa-311">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-311">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-312">Windows 10，版本 1803</span><span class="sxs-lookup"><span data-stu-id="928fa-312">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="928fa-313">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-313">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-314">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-314">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="928fa-315">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="928fa-315">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="928fa-316">Intune 名称： `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="928fa-316">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="928fa-317">Configuration Manager 名称： `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="928fa-317">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="928fa-318">GUID：`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="928fa-318">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="928fa-319">阻止来自电子邮件客户端和 Webmail 的可执行内容</span><span class="sxs-lookup"><span data-stu-id="928fa-319">Block executable content from email client and webmail</span></span>

<span data-ttu-id="928fa-320">此规则阻止从 Microsoft Outlook 应用程序或其他热门 webmail 提供程序Outlook打开的电子邮件启动以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="928fa-320">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="928fa-321">可执行文件 (，如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="928fa-321">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="928fa-322">脚本文件 (如 PowerShell .ps、Visual Basic .vbs 或 JavaScript .js文件) </span><span class="sxs-lookup"><span data-stu-id="928fa-322">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="928fa-323">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-323">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-324">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="928fa-324">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="928fa-325">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-325">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-326">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-326">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="928fa-327">Microsoft Endpoint ManagerCB 1710</span><span class="sxs-lookup"><span data-stu-id="928fa-327">Microsoft Endpoint Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="928fa-328">Intune 名称： `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="928fa-328">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="928fa-329">Microsoft Endpoint Manager名称：`Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="928fa-329">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="928fa-330">GUID：`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="928fa-330">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="928fa-331">规则 **"阻止来自电子邮件客户端和 Webmail** 的可执行内容"具有以下替代说明，具体取决于你使用的应用程序：</span><span class="sxs-lookup"><span data-stu-id="928fa-331">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
>
> - <span data-ttu-id="928fa-332">Intune (Configuration Profiles) ： Execution of executable content (exe， dll， ps， js， vbs， etc.) dropped from email (webmail/mail client)  (no exceptions) .</span><span class="sxs-lookup"><span data-stu-id="928fa-332">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="928fa-333">Endpoint Manager：阻止从电子邮件和 Webmail 客户端下载可执行内容。</span><span class="sxs-lookup"><span data-stu-id="928fa-333">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="928fa-334">组策略：阻止来自电子邮件客户端和 Webmail 的可执行内容。</span><span class="sxs-lookup"><span data-stu-id="928fa-334">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="928fa-335">阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件</span><span class="sxs-lookup"><span data-stu-id="928fa-335">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="928fa-336">此规则阻止可执行文件（.exe、.dll 或 .scr）启动，除非满足以下任一条件：</span><span class="sxs-lookup"><span data-stu-id="928fa-336">This rule blocks executable files, such as .exe, .dll, or .scr, from launching unless any of the following conditions are met:</span></span>

- <span data-ttu-id="928fa-337">普遍：可执行文件在 1，000 多个终结点上找到</span><span class="sxs-lookup"><span data-stu-id="928fa-337">Prevalence: The executable files are found on more than 1,000 endpoints</span></span>
- <span data-ttu-id="928fa-338">年龄：可执行文件在 24 小时之前发布</span><span class="sxs-lookup"><span data-stu-id="928fa-338">Age: The executable files were released more than 24 hours ago</span></span>
- <span data-ttu-id="928fa-339">位置：可执行文件包含在受信任的列表或排除列表中</span><span class="sxs-lookup"><span data-stu-id="928fa-339">Location: The executable files are included in a trusted list or an exclusion list</span></span>

<span data-ttu-id="928fa-340">启动不受信任的或未知的可执行文件可能会带来风险，因为最初可能不明确这些文件是否恶意。</span><span class="sxs-lookup"><span data-stu-id="928fa-340">Launching untrusted or unknown executable files can be risky, as it might not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="928fa-341">必须 [启用云保护才能](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 使用此规则。</span><span class="sxs-lookup"><span data-stu-id="928fa-341">You must [enable cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>
>
> <span data-ttu-id="928fa-342">规则 **阻止可执行文件运行** ，除非它们符合普遍标准、年龄或受信任列表条件（具有 GUID）归 Microsoft 所有，且未由管理员 `01443614-cd74-433a-b99e-2ecdc07bfc25` 指定。</span><span class="sxs-lookup"><span data-stu-id="928fa-342">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="928fa-343">此规则使用云提供的保护定期更新其受信任的列表。</span><span class="sxs-lookup"><span data-stu-id="928fa-343">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
> <span data-ttu-id="928fa-344">可以使用文件夹路径或完全限定的资源 (指定单个文件或文件夹) 但无法指定适用于哪些规则或排除项。</span><span class="sxs-lookup"><span data-stu-id="928fa-344">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="928fa-345">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-345">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-346">Windows 10，版本 1803</span><span class="sxs-lookup"><span data-stu-id="928fa-346">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="928fa-347">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-347">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-348">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-348">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="928fa-349">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="928fa-349">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="928fa-350">Intune 名称： `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="928fa-350">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="928fa-351">Configuration Manager 名称： `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="928fa-351">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="928fa-352">GUID：`01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="928fa-352">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="928fa-353">阻止执行可能混淆的脚本</span><span class="sxs-lookup"><span data-stu-id="928fa-353">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="928fa-354">此规则在混淆的脚本中检测可疑属性。</span><span class="sxs-lookup"><span data-stu-id="928fa-354">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="928fa-355">脚本模糊处理是恶意软件作者和合法应用程序都用于隐藏知识产权或缩短脚本加载次数的常见技术。</span><span class="sxs-lookup"><span data-stu-id="928fa-355">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="928fa-356">恶意软件作者还使用模糊处理使恶意代码更难阅读，这可防止人员和安全软件进行严格的审查。</span><span class="sxs-lookup"><span data-stu-id="928fa-356">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="928fa-357">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-357">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-358">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="928fa-358">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="928fa-359">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-359">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-360">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-360">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="928fa-361">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="928fa-361">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="928fa-362">Intune 名称： `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="928fa-362">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="928fa-363">Configuration Manager 名称： `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="928fa-363">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="928fa-364">GUID：`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="928fa-364">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="928fa-365">阻止 JavaScript 或 VBScript 启动下载的可执行内容</span><span class="sxs-lookup"><span data-stu-id="928fa-365">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="928fa-366">此规则阻止脚本启动潜在恶意下载的内容。</span><span class="sxs-lookup"><span data-stu-id="928fa-366">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="928fa-367">用 JavaScript 或 VBScript 编写的恶意软件通常充当从 Internet 提取和启动其他恶意软件的下载程序。</span><span class="sxs-lookup"><span data-stu-id="928fa-367">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="928fa-368">虽然不常见，但业务线应用程序有时会使用脚本下载和启动安装程序。</span><span class="sxs-lookup"><span data-stu-id="928fa-368">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="928fa-369">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-369">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-370">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="928fa-370">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="928fa-371">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-371">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-372">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-372">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="928fa-373">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="928fa-373">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="928fa-374">Intune 名称： `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="928fa-374">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="928fa-375">Configuration Manager 名称： `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="928fa-375">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="928fa-376">GUID：`D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="928fa-376">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="928fa-377">阻止Office应用程序创建可执行内容</span><span class="sxs-lookup"><span data-stu-id="928fa-377">Block Office applications from creating executable content</span></span>

<span data-ttu-id="928fa-378">此规则Office Word、Excel 和 PowerPoint 等应用阻止恶意代码写入磁盘，从而阻止其创建潜在恶意可执行内容。</span><span class="sxs-lookup"><span data-stu-id="928fa-378">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="928fa-379">滥用作为Office的恶意软件可能会尝试破坏Office，将恶意组件保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="928fa-379">Malware that abuses Office as a vector might attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="928fa-380">这些恶意组件在计算机重新启动后将一直保留于系统。</span><span class="sxs-lookup"><span data-stu-id="928fa-380">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="928fa-381">因此，此规则可防御常见的持久性技术。</span><span class="sxs-lookup"><span data-stu-id="928fa-381">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="928fa-382">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-382">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-383">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="928fa-383">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="928fa-384">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-384">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-385">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-385">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="928fa-386">[System Center Configuration Manager (](/configmgr/core/servers/manage/updates) SCCM) CB 1710 (SCCM 现已Microsoft Endpoint Configuration Manager) </span><span class="sxs-lookup"><span data-stu-id="928fa-386">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="928fa-387">Intune 名称： `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="928fa-387">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="928fa-388">SCCM 名称： `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="928fa-388">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="928fa-389">GUID：`3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="928fa-389">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="928fa-390">阻止Office代码注入其他进程</span><span class="sxs-lookup"><span data-stu-id="928fa-390">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="928fa-391">此规则阻止代码注入尝试Office应用注入其他进程。</span><span class="sxs-lookup"><span data-stu-id="928fa-391">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="928fa-392">攻击者可能会尝试使用Office代码注入将恶意代码迁移到其他进程中，因此代码可以伪装成一个干净流程。</span><span class="sxs-lookup"><span data-stu-id="928fa-392">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="928fa-393">使用代码注入没有已知的合法业务用途。</span><span class="sxs-lookup"><span data-stu-id="928fa-393">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="928fa-394">此规则适用于 Word、Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="928fa-394">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="928fa-395">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-395">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-396">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="928fa-396">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="928fa-397">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-397">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-398">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-398">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="928fa-399">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="928fa-399">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="928fa-400">Intune 名称： `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="928fa-400">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="928fa-401">Configuration Manager 名称： `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="928fa-401">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="928fa-402">GUID：`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="928fa-402">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="928fa-403">阻止Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="928fa-403">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="928fa-404">此规则阻止Outlook子进程，同时仍允许合法Outlook进程。</span><span class="sxs-lookup"><span data-stu-id="928fa-404">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="928fa-405">此规则可防止社会工程攻击，并防止利用代码滥用Outlook。</span><span class="sxs-lookup"><span data-stu-id="928fa-405">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="928fa-406">它还[可Outlook用户](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)凭据泄露时攻击者可能使用的规则和表单攻击。</span><span class="sxs-lookup"><span data-stu-id="928fa-406">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="928fa-407">此规则阻止 DLP 策略提示和工具提示Outlook。</span><span class="sxs-lookup"><span data-stu-id="928fa-407">This rule blocks DLP policy tips and ToolTips in Outlook.</span></span> <span data-ttu-id="928fa-408">此规则仅适用于 Outlook Outlook.com。</span><span class="sxs-lookup"><span data-stu-id="928fa-408">This rule applies to Outlook and Outlook.com only.</span></span>

<span data-ttu-id="928fa-409">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-409">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-410">Windows 10 版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-410">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="928fa-411">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-411">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-412">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-412">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="928fa-413">Intune 名称： `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="928fa-413">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="928fa-414">Configuration Manager 名称：不可用</span><span class="sxs-lookup"><span data-stu-id="928fa-414">Configuration Manager name: Not available</span></span>

<span data-ttu-id="928fa-415">GUID：`26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="928fa-415">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="928fa-416">通过 WMI 事件订阅阻止持久性</span><span class="sxs-lookup"><span data-stu-id="928fa-416">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="928fa-417">此规则可防止恶意软件滥用 WMI 在设备上获得持久性。</span><span class="sxs-lookup"><span data-stu-id="928fa-417">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="928fa-418">文件和文件夹排除项不适用于此攻击面减少规则。</span><span class="sxs-lookup"><span data-stu-id="928fa-418">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="928fa-419">无文件威胁采用各种策略来保持隐藏，以避免在文件系统中可见，并获得定期执行控制。</span><span class="sxs-lookup"><span data-stu-id="928fa-419">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="928fa-420">某些威胁可能会滥用 WMI 存储库和事件模型来保持隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="928fa-420">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="928fa-421">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-421">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-422">Windows 10，版本 1903</span><span class="sxs-lookup"><span data-stu-id="928fa-422">Windows 10, version 1903</span></span>](/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="928fa-423">Windows服务器 1903</span><span class="sxs-lookup"><span data-stu-id="928fa-423">Windows Server 1903</span></span>](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="928fa-424">Intune 名称：不可用</span><span class="sxs-lookup"><span data-stu-id="928fa-424">Intune name: Not available</span></span>

<span data-ttu-id="928fa-425">Configuration Manager 名称：不可用</span><span class="sxs-lookup"><span data-stu-id="928fa-425">Configuration Manager name: Not available</span></span>

<span data-ttu-id="928fa-426">GUID：`e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="928fa-426">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="928fa-427">阻止源自 PSExec 和 WMI 命令的进程创建</span><span class="sxs-lookup"><span data-stu-id="928fa-427">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="928fa-428">此规则阻止通过 [PsExec](/sysinternals/downloads/psexec) 和 [WMI 创建](/windows/win32/wmisdk/about-wmi) 的进程运行。</span><span class="sxs-lookup"><span data-stu-id="928fa-428">This rule blocks processes created through [PsExec](/sysinternals/downloads/psexec) and [WMI](/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="928fa-429">PsExec 和 WMI 都可以远程执行代码，因此存在恶意软件滥用此功能以用于命令和控制目的，或在整个组织的网络中传播感染的风险。</span><span class="sxs-lookup"><span data-stu-id="928fa-429">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="928fa-430">仅在使用 [Intune](/intune) 或其他 MDM 解决方案管理设备时使用此规则。</span><span class="sxs-lookup"><span data-stu-id="928fa-430">Only use this rule if you're managing your devices with [Intune](/intune) or another MDM solution.</span></span> <span data-ttu-id="928fa-431">此规则与通过配置[管理器Microsoft Endpoint Configuration Manager管理](/configmgr)不兼容，因为此规则会阻止 Configuration Manager 客户端用于正常运行的 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="928fa-431">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="928fa-432">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-432">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-433">Windows 10，版本 1803</span><span class="sxs-lookup"><span data-stu-id="928fa-433">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="928fa-434">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-434">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-435">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-435">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="928fa-436">Intune 名称： `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="928fa-436">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="928fa-437">Configuration Manager 名称：不适用</span><span class="sxs-lookup"><span data-stu-id="928fa-437">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="928fa-438">GUID：`d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="928fa-438">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="928fa-439">阻止从 USB 运行的不受信任的和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="928fa-439">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="928fa-440">通过此规则，管理员可以阻止未签名或不受信任的可执行文件从 USB 可移动驱动器（包括 SD 卡）运行。</span><span class="sxs-lookup"><span data-stu-id="928fa-440">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="928fa-441">阻止的文件类型包括可执行 (文件，.exe、.dll或 .scr) </span><span class="sxs-lookup"><span data-stu-id="928fa-441">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="928fa-442">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-442">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-443">Windows 10，版本 1803</span><span class="sxs-lookup"><span data-stu-id="928fa-443">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="928fa-444">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-444">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-445">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-445">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="928fa-446">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="928fa-446">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="928fa-447">Intune 名称： `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="928fa-447">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="928fa-448">Configuration Manager 名称： `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="928fa-448">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="928fa-449">GUID：`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="928fa-449">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="928fa-450">阻止从宏Office Win32 API 调用</span><span class="sxs-lookup"><span data-stu-id="928fa-450">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="928fa-451">此规则阻止 VBA 宏调用 Win32 API。</span><span class="sxs-lookup"><span data-stu-id="928fa-451">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="928fa-452">OfficeVBA 启用 Win32 API 调用。</span><span class="sxs-lookup"><span data-stu-id="928fa-452">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="928fa-453">恶意软件可能会滥用此功能，例如调用 [Win32 API 以启动恶意 shellcode，](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) 而无需将任何内容直接写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="928fa-453">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="928fa-454">大多数组织不依赖于在日常运行中调用 Win32 API 的功能，即使它们以其他方式使用宏。</span><span class="sxs-lookup"><span data-stu-id="928fa-454">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="928fa-455">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-455">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-456">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="928fa-456">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="928fa-457">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-457">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-458">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-458">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="928fa-459">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="928fa-459">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="928fa-460">Intune 名称： `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="928fa-460">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="928fa-461">Configuration Manager 名称： `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="928fa-461">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="928fa-462">GUID：`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="928fa-462">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="928fa-463">使用高级防护抵御勒索软件</span><span class="sxs-lookup"><span data-stu-id="928fa-463">Use advanced protection against ransomware</span></span>

<span data-ttu-id="928fa-464">此规则提供针对勒索软件的额外保护层。</span><span class="sxs-lookup"><span data-stu-id="928fa-464">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="928fa-465">它使用客户端和云启发来确定文件是否类似于勒索软件。</span><span class="sxs-lookup"><span data-stu-id="928fa-465">It uses both client and cloud heuristics to determine whether a file resembles ransomware.</span></span> <span data-ttu-id="928fa-466">此规则不会阻止具有以下一个或多个特征的文件：</span><span class="sxs-lookup"><span data-stu-id="928fa-466">This rule does not block files that have one or more of the following characteristics:</span></span>

- <span data-ttu-id="928fa-467">已在 Microsoft 云中发现该文件未共享。</span><span class="sxs-lookup"><span data-stu-id="928fa-467">The file has already been found to be unharmful in the Microsoft cloud.</span></span>
- <span data-ttu-id="928fa-468">文件是有效的签名文件。</span><span class="sxs-lookup"><span data-stu-id="928fa-468">The file is a valid signed file.</span></span>
- <span data-ttu-id="928fa-469">该文件非常流行，不被视为勒索软件。</span><span class="sxs-lookup"><span data-stu-id="928fa-469">The file is prevalent enough to not be considered as ransomware.</span></span>

<span data-ttu-id="928fa-470">该规则倾向于谨慎阻止勒索软件。</span><span class="sxs-lookup"><span data-stu-id="928fa-470">The rule tends to err on the side of caution to prevent ransomware.</span></span>

> [!NOTE]
> <span data-ttu-id="928fa-471">必须 [启用云保护才能](enable-cloud-protection-microsoft-defender-antivirus.md) 使用此规则。</span><span class="sxs-lookup"><span data-stu-id="928fa-471">You must [enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) to use this rule.</span></span>

<span data-ttu-id="928fa-472">支持的操作系统：</span><span class="sxs-lookup"><span data-stu-id="928fa-472">Supported operating systems:</span></span>

- [<span data-ttu-id="928fa-473">Windows 10，版本 1803</span><span class="sxs-lookup"><span data-stu-id="928fa-473">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="928fa-474">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="928fa-474">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="928fa-475">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="928fa-475">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="928fa-476">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="928fa-476">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="928fa-477">Intune 名称： `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="928fa-477">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="928fa-478">Configuration Manager 名称： `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="928fa-478">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="928fa-479">GUID：`c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="928fa-479">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>
