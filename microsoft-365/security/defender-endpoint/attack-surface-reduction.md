---
title: 使用攻击面减少规则防止恶意软件感染
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
ms.openlocfilehash: 7360087e1863e81e4dc9e8acc2817e1320d6f4d8
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028783"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="218fa-104">使用攻击面减少规则防止恶意软件感染</span><span class="sxs-lookup"><span data-stu-id="218fa-104">Use attack surface reduction rules to prevent malware infection</span></span>

<span data-ttu-id="218fa-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="218fa-105">**Applies to:**</span></span>

- [<span data-ttu-id="218fa-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="218fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="218fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="218fa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="218fa-108">攻击面减少规则为什么很重要</span><span class="sxs-lookup"><span data-stu-id="218fa-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="218fa-109">组织的攻击面包括攻击者可能损害组织设备或网络的所有位置。</span><span class="sxs-lookup"><span data-stu-id="218fa-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="218fa-110">减少攻击面意味着保护组织的设备和网络，这使攻击者能够执行攻击的方法更少。</span><span class="sxs-lookup"><span data-stu-id="218fa-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="218fa-111">在 Microsoft Defender for Endpoint 中配置攻击面减少规则可以提供帮助！</span><span class="sxs-lookup"><span data-stu-id="218fa-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="218fa-112">攻击面减少规则针对某些软件行为，例如：</span><span class="sxs-lookup"><span data-stu-id="218fa-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="218fa-113">启动尝试下载或运行文件的可执行文件和脚本</span><span class="sxs-lookup"><span data-stu-id="218fa-113">Launching executable files and scripts that attempt to download or run files</span></span>
- <span data-ttu-id="218fa-114">运行混淆的或可疑的脚本</span><span class="sxs-lookup"><span data-stu-id="218fa-114">Running obfuscated or otherwise suspicious scripts</span></span>
- <span data-ttu-id="218fa-115">执行应用在正常日常工作期间通常不会启动的行为</span><span class="sxs-lookup"><span data-stu-id="218fa-115">Performing behaviors that apps don't usually initiate during normal day-to-day work</span></span>

<span data-ttu-id="218fa-116">此类软件行为有时在合法应用程序中可见。</span><span class="sxs-lookup"><span data-stu-id="218fa-116">Such software behaviors are sometimes seen in legitimate applications.</span></span> <span data-ttu-id="218fa-117">但是，这些行为通常被视为有风险，因为它们通常被攻击者通过恶意软件滥用。</span><span class="sxs-lookup"><span data-stu-id="218fa-117">However, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="218fa-118">攻击面减少规则可以限制基于软件的风险行为，并有助于确保组织安全。</span><span class="sxs-lookup"><span data-stu-id="218fa-118">Attack surface reduction rules can constrain software-based risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="218fa-119">有关配置攻击面减少规则的信息，请参阅启用 [攻击面减少规则](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="218fa-119">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="218fa-120">在部署之前评估规则影响</span><span class="sxs-lookup"><span data-stu-id="218fa-120">Assess rule impact before deployment</span></span>

<span data-ttu-id="218fa-121">你可以评估攻击面减少规则可能会如何影响你的网络，在 危险和漏洞管理 中打开该[规则的安全建议](/windows/security/threat-protection/#tvm)。</span><span class="sxs-lookup"><span data-stu-id="218fa-121">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](/windows/security/threat-protection/#tvm).</span></span>

:::image type="content" source="images/asrrecommendation.png" alt-text="攻击面减少规则的安全重新成本":::

<span data-ttu-id="218fa-123">在建议详细信息窗格中，检查用户影响以确定设备可接受在阻止模式下启用规则的新策略的百分比，而不会对工作效率产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="218fa-123">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="218fa-124">评估审核模式</span><span class="sxs-lookup"><span data-stu-id="218fa-124">Audit mode for evaluation</span></span>

<span data-ttu-id="218fa-125">使用 [审核模式](audit-windows-defender.md) 评估攻击面减少规则在启用后对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="218fa-125">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if enabled.</span></span> <span data-ttu-id="218fa-126">首先在审核模式下运行所有规则，以便了解它们如何影响业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="218fa-126">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="218fa-127">许多业务线应用程序都是以有限的安全问题编写，它们执行任务的方式可能类似于恶意软件。</span><span class="sxs-lookup"><span data-stu-id="218fa-127">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="218fa-128">通过监视审核数据 [并添加](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 必要应用程序的排除项，你可以部署攻击面减少规则，而不会降低工作效率。</span><span class="sxs-lookup"><span data-stu-id="218fa-128">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="218fa-129">用户警告模式</span><span class="sxs-lookup"><span data-stu-id="218fa-129">Warn mode for users</span></span>

<span data-ttu-id="218fa-130"> (**新**！) 警告模式功能之前，已启用的攻击面减少规则可以设置为审核模式或阻止模式。</span><span class="sxs-lookup"><span data-stu-id="218fa-130">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="218fa-131">使用新的警告模式，只要内容被攻击面减少规则阻止，用户就会看到一个指示内容被阻止的对话框。</span><span class="sxs-lookup"><span data-stu-id="218fa-131">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="218fa-132">该对话框还允许用户选择取消阻止内容。</span><span class="sxs-lookup"><span data-stu-id="218fa-132">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="218fa-133">然后，用户可以重试其操作，操作完成。</span><span class="sxs-lookup"><span data-stu-id="218fa-133">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="218fa-134">当用户取消阻止内容时，该内容将保持取消阻止状态 24 小时，然后阻止恢复。</span><span class="sxs-lookup"><span data-stu-id="218fa-134">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="218fa-135">警告模式可帮助组织制定攻击面减少规则，而不会阻止用户访问执行其任务所需的内容。</span><span class="sxs-lookup"><span data-stu-id="218fa-135">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span>

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="218fa-136">警告模式运行的要求</span><span class="sxs-lookup"><span data-stu-id="218fa-136">Requirements for warn mode to work</span></span>

<span data-ttu-id="218fa-137">运行以下版本的警告的设备上支持警告Windows：</span><span class="sxs-lookup"><span data-stu-id="218fa-137">Warn mode is supported on devices running the following versions of Windows:</span></span>

- <span data-ttu-id="218fa-138">[Windows 10 版本 1809](/windows/whats-new/whats-new-windows-10-version-1809)或更高版本</span><span class="sxs-lookup"><span data-stu-id="218fa-138">[Windows 10, version 1809](/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="218fa-139">[Windows Server 版本 1809](/windows-server/get-started/whats-new-in-windows-server-1809)或更高版本</span><span class="sxs-lookup"><span data-stu-id="218fa-139">[Windows Server, version 1809](/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>

<span data-ttu-id="218fa-140">Microsoft Defender 防病毒必须在活动模式下使用实时[保护运行](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)。</span><span class="sxs-lookup"><span data-stu-id="218fa-140">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="218fa-141">此外，请确保[Microsoft Defender 防病毒反恶意软件更新](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。</span><span class="sxs-lookup"><span data-stu-id="218fa-141">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>

- <span data-ttu-id="218fa-142">最低平台发布要求： `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="218fa-142">Minimum platform release requirement: `4.18.2008.9`</span></span>
- <span data-ttu-id="218fa-143">最低引擎发布要求： `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="218fa-143">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="218fa-144">有关详细信息和获取更新，请参阅 [Microsoft Defender 反恶意软件平台的更新](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="218fa-144">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="218fa-145">不支持警告模式的情况</span><span class="sxs-lookup"><span data-stu-id="218fa-145">Cases where warn mode is not supported</span></span>

<span data-ttu-id="218fa-146">当你在三个攻击面减少规则中配置警告模式时，它们不受Microsoft Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="218fa-146">Warn mode is not supported for three attack surface reduction rules when you configure them in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="218fa-147"> (如果使用组策略配置攻击面减少规则，则支持警告模式。) 在 Microsoft Endpoint Manager 中配置时不支持警告模式的三个规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="218fa-147">(If you use Group Policy to configure your attack surface reduction rules, warn mode is supported.) The three rules that do not support warn mode when you configure them in Microsoft Endpoint Manager are as follows:</span></span>

- <span data-ttu-id="218fa-148">[阻止 JavaScript 或 VBScript 使用](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) GUID (下载的可执行 `d3e037e1-3eb8-44c8-a917-57927947596d`) </span><span class="sxs-lookup"><span data-stu-id="218fa-148">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="218fa-149">[通过 WMI 事件订阅和 GUID](#block-persistence-through-wmi-event-subscription) (阻止 `e6db77e5-3df2-4cf1-b95a-636979351e5b` 持久性) </span><span class="sxs-lookup"><span data-stu-id="218fa-149">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="218fa-150">[使用高级防护抵御勒索软件](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`) </span><span class="sxs-lookup"><span data-stu-id="218fa-150">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="218fa-151">此外，运行早期版本的 Windows 的设备上不支持警告Windows。</span><span class="sxs-lookup"><span data-stu-id="218fa-151">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="218fa-152">在这种情况下，配置为在警告模式下运行的攻击面减少规则将在阻止模式下运行。</span><span class="sxs-lookup"><span data-stu-id="218fa-152">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="218fa-153">通知和警报</span><span class="sxs-lookup"><span data-stu-id="218fa-153">Notifications and alerts</span></span>

<span data-ttu-id="218fa-154">每当触发攻击面减少规则时，都会在设备上显示通知。</span><span class="sxs-lookup"><span data-stu-id="218fa-154">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="218fa-155">你可以使用公司的详细信息和联系人信息[自定义通知](customize-attack-surface-reduction.md#customize-the-notification)。</span><span class="sxs-lookup"><span data-stu-id="218fa-155">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="218fa-156">此外，当触发某些攻击面减少规则时，将生成警报。</span><span class="sxs-lookup"><span data-stu-id="218fa-156">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span>

<span data-ttu-id="218fa-157">通知和生成的任何通知都可以在 Microsoft 365 Defender 门户 ()  (以前称为 Microsoft Defender 安全中心 [https://security.microsoft.com](https://security.microsoft.com)) 。 [](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="218fa-157">Notifications and any alerts that are generated can be viewed in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) (formerly called the [Microsoft Defender Security Center](microsoft-defender-security-center.md)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="218fa-158">高级搜寻和攻击面减少事件</span><span class="sxs-lookup"><span data-stu-id="218fa-158">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="218fa-159">可以使用高级搜寻来查看攻击面减少事件。</span><span class="sxs-lookup"><span data-stu-id="218fa-159">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="218fa-160">为了简化传入数据的数量，使用高级搜寻仅可查看每小时的唯一进程。</span><span class="sxs-lookup"><span data-stu-id="218fa-160">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="218fa-161">攻击面减少事件的时间是一小时内首次看到该事件。</span><span class="sxs-lookup"><span data-stu-id="218fa-161">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="218fa-162">例如，假设在下午 2：00 小时内在 10 台设备上发生攻击面减少事件。</span><span class="sxs-lookup"><span data-stu-id="218fa-162">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="218fa-163">假设第一个事件在 2：15 发生，最后一个事件在 2：45 发生。</span><span class="sxs-lookup"><span data-stu-id="218fa-163">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="218fa-164">借助高级搜寻，你将看到该事件的一个实例 (即使该事件实际发生在 10 台设备上) ，其时间戳将为下午 2：15。</span><span class="sxs-lookup"><span data-stu-id="218fa-164">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span>

<span data-ttu-id="218fa-165">有关高级搜寻详细信息，请参阅使用高级搜寻主动 [搜寻威胁](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="218fa-165">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="218fa-166">跨多个版本的攻击Windows功能</span><span class="sxs-lookup"><span data-stu-id="218fa-166">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="218fa-167">你可以为运行以下任一版本和版本的设备设置攻击面减少规则Windows：</span><span class="sxs-lookup"><span data-stu-id="218fa-167">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="218fa-168">Windows 10 专业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="218fa-168">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="218fa-169">Windows 10 企业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="218fa-169">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="218fa-170">Windows服务器版本[1803 (半年频道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本</span><span class="sxs-lookup"><span data-stu-id="218fa-170">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="218fa-171">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-171">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="218fa-172">尽管攻击面减少规则不需要使用 Windows [E5](/windows/deployment/deploy-enterprise-licenses)许可证，但如果已使用 Windows E5，则获得高级管理功能。</span><span class="sxs-lookup"><span data-stu-id="218fa-172">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="218fa-173">仅在 E5 中提供的高级Windows包括：</span><span class="sxs-lookup"><span data-stu-id="218fa-173">The advanced capabilities - available only in Windows E5 - include:</span></span>

- <span data-ttu-id="218fa-174">Defender for Endpoint 中提供的监视、 [分析和工作流](microsoft-defender-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="218fa-174">The monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md)</span></span>
- <span data-ttu-id="218fa-175">中的报告和配置[Microsoft 365 Defender。](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="218fa-175">The reporting and configuration capabilities in [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="218fa-176">这些高级功能不适用于 Windows Professional 或 Windows E3 许可证。</span><span class="sxs-lookup"><span data-stu-id="218fa-176">These advanced capabilities aren't available with a Windows Professional or Windows E3 license.</span></span> <span data-ttu-id="218fa-177">但是，如果你有这些许可证，可以使用事件查看器和Microsoft Defender 防病毒日志查看攻击面减少规则事件。</span><span class="sxs-lookup"><span data-stu-id="218fa-177">However, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="218fa-178">查看攻击门户中的攻击Microsoft 365 Defender事件</span><span class="sxs-lookup"><span data-stu-id="218fa-178">Review attack surface reduction events in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="218fa-179">Defender for Endpoint 提供事件和阻止的详细报告，作为警报调查方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="218fa-179">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="218fa-180">可以使用高级搜寻查询 defender 的终结点[Microsoft 365 Defender](microsoft-defender-security-center.md)中的[终结点数据](advanced-hunting-query-language.md)。</span><span class="sxs-lookup"><span data-stu-id="218fa-180">You can query Defender for Endpoint data in [Microsoft 365 Defender](microsoft-defender-security-center.md) by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="218fa-181">如果你运行的是审核 [模式](audit-windows-defender.md)，可以使用高级搜寻了解攻击面减少规则可能会如何影响你的环境。</span><span class="sxs-lookup"><span data-stu-id="218fa-181">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules might affect your environment.</span></span>

<span data-ttu-id="218fa-182">示例查询如下所示:</span><span class="sxs-lookup"><span data-stu-id="218fa-182">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="218fa-183">查看事件查看器中的攻击Windows减少事件</span><span class="sxs-lookup"><span data-stu-id="218fa-183">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="218fa-184">你可以查看攻击Windows日志以查看攻击面减少规则生成的事件：</span><span class="sxs-lookup"><span data-stu-id="218fa-184">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="218fa-185">下载 [评估包](https://aka.ms/mp7z2w) ，将文件 *cfa-events.xml* 到设备上易于访问的位置。</span><span class="sxs-lookup"><span data-stu-id="218fa-185">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>

2. <span data-ttu-id="218fa-186">在事件查看器 *中* 输入"开始"菜单事件查看器Windows事件查看器。</span><span class="sxs-lookup"><span data-stu-id="218fa-186">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>

3. <span data-ttu-id="218fa-187">在 **"操作"** 下，**选择"导入自定义视图..."。**</span><span class="sxs-lookup"><span data-stu-id="218fa-187">Under **Actions**, select **Import custom view...**.</span></span>

4. <span data-ttu-id="218fa-188">选择从 *cfa-events.xml* 文件的位置创建的文件。</span><span class="sxs-lookup"><span data-stu-id="218fa-188">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="218fa-189">或者，[直接复制 XML。](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="218fa-189">Alternatively, [copy the XML directly](event-views.md).</span></span>

5. <span data-ttu-id="218fa-190">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="218fa-190">Select **OK**.</span></span>

<span data-ttu-id="218fa-191">您可以创建一个自定义视图，该视图筛选事件以只显示下列事件，所有这些事件均与受控文件夹访问权限相关：</span><span class="sxs-lookup"><span data-stu-id="218fa-191">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="218fa-192">事件 ID</span><span class="sxs-lookup"><span data-stu-id="218fa-192">Event ID</span></span>|<span data-ttu-id="218fa-193">描述</span><span class="sxs-lookup"><span data-stu-id="218fa-193">Description</span></span>|
|---|---|
|<span data-ttu-id="218fa-194">5007</span><span class="sxs-lookup"><span data-stu-id="218fa-194">5007</span></span>|<span data-ttu-id="218fa-195">更改设置时的事件</span><span class="sxs-lookup"><span data-stu-id="218fa-195">Event when settings are changed</span></span>|
|<span data-ttu-id="218fa-196">1121</span><span class="sxs-lookup"><span data-stu-id="218fa-196">1121</span></span>|<span data-ttu-id="218fa-197">在阻止模式下触发规则时的事件</span><span class="sxs-lookup"><span data-stu-id="218fa-197">Event when rule fires in Block-mode</span></span>|
|<span data-ttu-id="218fa-198">1122</span><span class="sxs-lookup"><span data-stu-id="218fa-198">1122</span></span>|<span data-ttu-id="218fa-199">在审核模式下触发规则时的事件</span><span class="sxs-lookup"><span data-stu-id="218fa-199">Event when rule fires in Audit-mode</span></span>|

<span data-ttu-id="218fa-200">针对事件日志中的攻击面减少事件列出的"引擎版本"由 Defender for Endpoint 生成，而不是由操作系统生成。</span><span class="sxs-lookup"><span data-stu-id="218fa-200">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="218fa-201">Defender for Endpoint 与 Windows 10 集成，因此此功能适用于安装了 Windows 10 的所有设备。</span><span class="sxs-lookup"><span data-stu-id="218fa-201">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="218fa-202">攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="218fa-202">Attack surface reduction rules</span></span>

<span data-ttu-id="218fa-203">下表和子部分介绍了 16 个攻击面减少规则中的每个规则。</span><span class="sxs-lookup"><span data-stu-id="218fa-203">The following table and subsections describe each of the 16 attack surface reduction rules.</span></span> <span data-ttu-id="218fa-204">攻击面减少规则按规则名称的字母顺序列出。</span><span class="sxs-lookup"><span data-stu-id="218fa-204">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span>

<span data-ttu-id="218fa-205">如果要使用组策略或 PowerShell 配置攻击面减少规则，则需要 GUID。</span><span class="sxs-lookup"><span data-stu-id="218fa-205">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="218fa-206">另一方面，如果使用 Microsoft Endpoint Manager 或 Microsoft Intune，则不需要 GUID。</span><span class="sxs-lookup"><span data-stu-id="218fa-206">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>

|<span data-ttu-id="218fa-207">规则名称</span><span class="sxs-lookup"><span data-stu-id="218fa-207">Rule name</span></span>|<span data-ttu-id="218fa-208">GUID</span><span class="sxs-lookup"><span data-stu-id="218fa-208">GUID</span></span>|<span data-ttu-id="218fa-209">文件&文件夹排除项</span><span class="sxs-lookup"><span data-stu-id="218fa-209">File & folder exclusions</span></span>|<span data-ttu-id="218fa-210">支持的最低操作系统</span><span class="sxs-lookup"><span data-stu-id="218fa-210">Minimum OS supported</span></span>|
|---|:---:|---|---|
|[<span data-ttu-id="218fa-211">阻止滥用被攻击的易受攻击的已签名驱动程序</span><span class="sxs-lookup"><span data-stu-id="218fa-211">Block abuse of exploited vulnerable signed drivers</span></span>](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|<span data-ttu-id="218fa-212">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-212">Supported</span></span>|<span data-ttu-id="218fa-213">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或) </span><span class="sxs-lookup"><span data-stu-id="218fa-213">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater)</span></span> |
|[<span data-ttu-id="218fa-214">阻止 Adobe Reader 创建子进程</span><span class="sxs-lookup"><span data-stu-id="218fa-214">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|<span data-ttu-id="218fa-215">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-215">Supported</span></span>|<span data-ttu-id="218fa-216">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-216">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-217">阻止所有Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="218fa-217">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|<span data-ttu-id="218fa-218">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-218">Supported</span></span>|<span data-ttu-id="218fa-219">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-219">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-220">阻止本地安全机构子系统Windows凭据 (lsass.exe) </span><span class="sxs-lookup"><span data-stu-id="218fa-220">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|<span data-ttu-id="218fa-221">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-221">Supported</span></span>|<span data-ttu-id="218fa-222">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-222">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-223">阻止来自电子邮件客户端和 Webmail 的可执行内容</span><span class="sxs-lookup"><span data-stu-id="218fa-223">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|<span data-ttu-id="218fa-224">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-224">Supported</span></span>|<span data-ttu-id="218fa-225">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-225">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-226">阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件</span><span class="sxs-lookup"><span data-stu-id="218fa-226">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|<span data-ttu-id="218fa-227">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-227">Supported</span></span>|<span data-ttu-id="218fa-228">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-228">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-229">阻止执行可能混淆的脚本</span><span class="sxs-lookup"><span data-stu-id="218fa-229">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|<span data-ttu-id="218fa-230">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-230">Supported</span></span>|<span data-ttu-id="218fa-231">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-231">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-232">阻止 JavaScript 或 VBScript 启动下载的可执行内容</span><span class="sxs-lookup"><span data-stu-id="218fa-232">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|<span data-ttu-id="218fa-233">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-233">Supported</span></span>|<span data-ttu-id="218fa-234">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-234">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-235">阻止Office应用程序创建可执行内容</span><span class="sxs-lookup"><span data-stu-id="218fa-235">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|<span data-ttu-id="218fa-236">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-236">Supported</span></span>|<span data-ttu-id="218fa-237">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-237">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-238">阻止Office代码注入其他进程</span><span class="sxs-lookup"><span data-stu-id="218fa-238">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|<span data-ttu-id="218fa-239">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-239">Supported</span></span>|<span data-ttu-id="218fa-240">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-240">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-241">阻止Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="218fa-241">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|<span data-ttu-id="218fa-242">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-242">Supported</span></span>|<span data-ttu-id="218fa-243">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-243">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-244">通过 WMI 事件订阅阻止持久性</span><span class="sxs-lookup"><span data-stu-id="218fa-244">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|<span data-ttu-id="218fa-245">不支持</span><span class="sxs-lookup"><span data-stu-id="218fa-245">Not supported</span></span>|<span data-ttu-id="218fa-246">[Windows 10版本 1903 (](/windows/whats-new/whats-new-windows-10-version-1903)版本 18362) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-246">[Windows 10, version 1903](/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span>|
|[<span data-ttu-id="218fa-247">阻止源自 PSExec 和 WMI 命令的进程创建</span><span class="sxs-lookup"><span data-stu-id="218fa-247">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|<span data-ttu-id="218fa-248">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-248">Supported</span></span>|<span data-ttu-id="218fa-249">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-249">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-250">阻止从 USB 运行的不受信任的和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="218fa-250">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|<span data-ttu-id="218fa-251">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-251">Supported</span></span>|<span data-ttu-id="218fa-252">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-252">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-253">阻止从宏Office Win32 API 调用</span><span class="sxs-lookup"><span data-stu-id="218fa-253">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|<span data-ttu-id="218fa-254">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-254">Supported</span></span>|<span data-ttu-id="218fa-255">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-255">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="218fa-256">使用高级防护抵御勒索软件</span><span class="sxs-lookup"><span data-stu-id="218fa-256">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|<span data-ttu-id="218fa-257">支持</span><span class="sxs-lookup"><span data-stu-id="218fa-257">Supported</span></span>|<span data-ttu-id="218fa-258">[Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，内部版本 16299) 或更高</span><span class="sxs-lookup"><span data-stu-id="218fa-258">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a><span data-ttu-id="218fa-259">阻止滥用被攻击的易受攻击的已签名驱动程序</span><span class="sxs-lookup"><span data-stu-id="218fa-259">Block abuse of exploited vulnerable signed drivers</span></span>

<span data-ttu-id="218fa-260">此规则阻止应用程序将易受攻击的已签名驱动程序写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="218fa-260">This rule prevents an application from writing a vulnerable signed driver to disk.</span></span> <span data-ttu-id="218fa-261">具有获取内核访问权限的足够权限的本地应用程序可能会利用通配符、易受攻击的已签名 \-  \- 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="218fa-261">In-the-wild, vulnerable signed drivers can be exploited by local applications \- _that have sufficient privileges_ \- to gain access to the kernel.</span></span> <span data-ttu-id="218fa-262">易受攻击的已签名驱动程序使攻击者能够禁用或规避安全解决方案，最终导致系统泄露。</span><span class="sxs-lookup"><span data-stu-id="218fa-262">Vulnerable signed drivers enable attackers to disable or circumvent security solutions, eventually leading to system compromise.</span></span>

<span data-ttu-id="218fa-263">阻止 **滥用被攻击的易受** 攻击的已签名驱动程序规则不会阻止加载系统中已存在的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="218fa-263">The **Block abuse of exploited vulnerable signed drivers** rule does not block a driver already existing on the system from being loaded.</span></span>

>[!NOTE]
>
> <span data-ttu-id="218fa-264">你可以为 [MEM OMA-URI 自定义规则过程信息使用此 MEM OMA-URI](enable-attack-surface-reduction.md#mem) 配置此规则。</span><span class="sxs-lookup"><span data-stu-id="218fa-264">You can configure this rule using [MEM OMA-URI](enable-attack-surface-reduction.md#mem) for MEM OMA-URI custom rules procedural information.</span></span>
>
> <span data-ttu-id="218fa-265">您还可以使用 [PowerShell](enable-attack-surface-reduction.md#powershell)配置此规则。</span><span class="sxs-lookup"><span data-stu-id="218fa-265">You can also configure this rule using [PowerShell](enable-attack-surface-reduction.md#powershell).</span></span>
>
> <span data-ttu-id="218fa-266">若要检查驱动程序，请使用此网站提交 [驱动程序进行分析](https://www.microsoft.com/en-us/wdsi/driversubmission)。</span><span class="sxs-lookup"><span data-stu-id="218fa-266">To have a driver examined, use this Web site to [Submit a driver for analysis](https://www.microsoft.com/en-us/wdsi/driversubmission).</span></span>

<span data-ttu-id="218fa-267">此规则在支持 ASR 的所有版本中均受支持;即：</span><span class="sxs-lookup"><span data-stu-id="218fa-267">This rule is supported in all versions in which ASR is supported; which is:</span></span>

- <span data-ttu-id="218fa-268">[Windows 10 专业版版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="218fa-268">[Windows 10 Pro, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="218fa-269">[Windows 10 企业版版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="218fa-269">[Windows 10 Enterprise, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="218fa-270">[Windows Server 版本 1803 (半年频道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本</span><span class="sxs-lookup"><span data-stu-id="218fa-270">[Windows Server, version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="218fa-271">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-271">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="218fa-272">Intune 名称： `Block abuse of exploited vulnerable signed drivers`</span><span class="sxs-lookup"><span data-stu-id="218fa-272">Intune Name: `Block abuse of exploited vulnerable signed drivers`</span></span>

<span data-ttu-id="218fa-273">GUID：  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span><span class="sxs-lookup"><span data-stu-id="218fa-273">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span></span>

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="218fa-274">阻止 Adobe Reader 创建子进程</span><span class="sxs-lookup"><span data-stu-id="218fa-274">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="218fa-275">此规则通过阻止 Adobe Reader 创建进程来阻止攻击。</span><span class="sxs-lookup"><span data-stu-id="218fa-275">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="218fa-276">通过社交工程或攻击，恶意软件可以下载和启动有效负载，并退出 Adobe Reader。</span><span class="sxs-lookup"><span data-stu-id="218fa-276">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="218fa-277">通过阻止 Adobe Reader 生成子进程，尝试将其用作矢量的恶意软件可防止传播。</span><span class="sxs-lookup"><span data-stu-id="218fa-277">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="218fa-278">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-278">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-279">Windows 10 版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-279">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="218fa-280">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-280">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-281">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-281">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="218fa-282">Intune 名称： `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="218fa-282">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="218fa-283">Configuration Manager 名称：尚不可用</span><span class="sxs-lookup"><span data-stu-id="218fa-283">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="218fa-284">GUID：`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="218fa-284">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="218fa-285">阻止所有Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="218fa-285">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="218fa-286">此规则阻止Office创建子进程。</span><span class="sxs-lookup"><span data-stu-id="218fa-286">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="218fa-287">Office应用程序包括 Word、Excel、PowerPoint、OneNote 和 Access。</span><span class="sxs-lookup"><span data-stu-id="218fa-287">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="218fa-288">创建恶意子进程是常见的恶意软件策略。</span><span class="sxs-lookup"><span data-stu-id="218fa-288">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="218fa-289">滥用作为Office的恶意软件通常会运行 VBA 宏，并利用代码下载并尝试运行更多有效负载。</span><span class="sxs-lookup"><span data-stu-id="218fa-289">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="218fa-290">但是，某些合法的业务线应用程序也可能出于恶意目的生成子进程;例如生成命令提示符或使用 PowerShell 配置注册表设置。</span><span class="sxs-lookup"><span data-stu-id="218fa-290">However, some legitimate line-of-business applications might also generate child processes for benign purposes; such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="218fa-291">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-291">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-292">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="218fa-292">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="218fa-293">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-293">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-294">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-294">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="218fa-295">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="218fa-295">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="218fa-296">Intune 名称： `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="218fa-296">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="218fa-297">Configuration Manager 名称： `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="218fa-297">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="218fa-298">GUID：`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="218fa-298">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="218fa-299">阻止从本地安全Windows窃取凭据</span><span class="sxs-lookup"><span data-stu-id="218fa-299">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="218fa-300">此规则通过锁定 LSASS 应用程序的本地安全颁发机构子系统服务 (凭据) 。</span><span class="sxs-lookup"><span data-stu-id="218fa-300">This rule helps prevent credential stealing by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="218fa-301">LSASS 对登录 Windows进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="218fa-301">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="218fa-302">Microsoft Defender Credential Guard Windows 10通常会阻止尝试从 LSASS 提取凭据。</span><span class="sxs-lookup"><span data-stu-id="218fa-302">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="218fa-303">但是，某些组织无法在所有计算机上启用 Credential Guard，因为自定义智能卡驱动程序或其他加载到本地安全机构 (LSA) 的程序的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="218fa-303">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="218fa-304">在这些情况下，攻击者可以使用 Mimikatz 等黑客工具从 LSASS 中清除明文密码和 NTLM 哈希。</span><span class="sxs-lookup"><span data-stu-id="218fa-304">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="218fa-305">在某些应用中，该代码枚举所有正在运行的进程，并尝试以详尽的权限打开它们。</span><span class="sxs-lookup"><span data-stu-id="218fa-305">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="218fa-306">此规则拒绝应用的进程打开操作，将详细信息记录到安全事件日志中。</span><span class="sxs-lookup"><span data-stu-id="218fa-306">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="218fa-307">此规则会产生大量噪音。</span><span class="sxs-lookup"><span data-stu-id="218fa-307">This rule can generate a lot of noise.</span></span> <span data-ttu-id="218fa-308">如果你的应用仅枚举 LSASS，但在功能方面没有实际影响，则无需将其添加到排除列表。</span><span class="sxs-lookup"><span data-stu-id="218fa-308">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="218fa-309">此事件日志条目本身不一定表示恶意威胁。</span><span class="sxs-lookup"><span data-stu-id="218fa-309">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="218fa-310">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-310">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-311">Windows 10，版本 1803</span><span class="sxs-lookup"><span data-stu-id="218fa-311">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="218fa-312">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-312">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-313">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-313">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="218fa-314">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="218fa-314">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="218fa-315">Intune 名称： `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="218fa-315">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="218fa-316">Configuration Manager 名称： `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="218fa-316">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="218fa-317">GUID：`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="218fa-317">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="218fa-318">阻止来自电子邮件客户端和 Webmail 的可执行内容</span><span class="sxs-lookup"><span data-stu-id="218fa-318">Block executable content from email client and webmail</span></span>

<span data-ttu-id="218fa-319">此规则阻止从 Microsoft Outlook 应用程序或其他热门 webmail 提供程序Outlook打开的电子邮件启动以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="218fa-319">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="218fa-320">可执行文件 (，如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="218fa-320">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="218fa-321">脚本文件 (如 PowerShell .ps、Visual Basic .vbs 或 JavaScript .js文件) </span><span class="sxs-lookup"><span data-stu-id="218fa-321">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="218fa-322">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-322">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-323">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="218fa-323">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="218fa-324">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-324">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-325">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-325">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="218fa-326">Microsoft Endpoint ManagerCB 1710</span><span class="sxs-lookup"><span data-stu-id="218fa-326">Microsoft Endpoint Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="218fa-327">Intune 名称： `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="218fa-327">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="218fa-328">Microsoft Endpoint Manager名称：`Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="218fa-328">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="218fa-329">GUID：`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="218fa-329">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="218fa-330">规则 **"阻止来自电子邮件客户端和 Webmail** 的可执行内容"具有以下替代说明，具体取决于你使用的应用程序：</span><span class="sxs-lookup"><span data-stu-id="218fa-330">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
>
> - <span data-ttu-id="218fa-331">Intune (Configuration Profiles) ： Execution of executable content (exe， dll， ps， js， vbs， etc.) dropped from email (webmail/mail client)  (no exceptions) .</span><span class="sxs-lookup"><span data-stu-id="218fa-331">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="218fa-332">Endpoint Manager：阻止从电子邮件和 Webmail 客户端下载可执行内容。</span><span class="sxs-lookup"><span data-stu-id="218fa-332">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="218fa-333">组策略：阻止来自电子邮件客户端和 Webmail 的可执行内容。</span><span class="sxs-lookup"><span data-stu-id="218fa-333">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="218fa-334">阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件</span><span class="sxs-lookup"><span data-stu-id="218fa-334">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="218fa-335">此规则阻止启动以下文件类型，除非它们符合普遍或年龄条件，或者它们位于受信任的列表或排除列表中：</span><span class="sxs-lookup"><span data-stu-id="218fa-335">This rule blocks the following file types from launching unless they meet prevalence or age criteria, or they're in a trusted list or an exclusion list:</span></span>

- <span data-ttu-id="218fa-336">可执行文件 (，如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="218fa-336">Executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="218fa-337">启动不受信任的或未知的可执行文件可能会带来风险，因为最初可能不明确这些文件是否恶意。</span><span class="sxs-lookup"><span data-stu-id="218fa-337">Launching untrusted or unknown executable files can be risky, as it might not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="218fa-338">必须 [启用云保护才能](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 使用此规则。</span><span class="sxs-lookup"><span data-stu-id="218fa-338">You must [enable cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>
>
> <span data-ttu-id="218fa-339">规则 **阻止可执行文件运行** ，除非它们符合普遍标准、年龄或受信任列表条件（具有 GUID）归 Microsoft 所有，且未由管理员 `01443614-cd74-433a-b99e-2ecdc07bfc25` 指定。</span><span class="sxs-lookup"><span data-stu-id="218fa-339">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="218fa-340">此规则使用云提供的保护定期更新其受信任的列表。</span><span class="sxs-lookup"><span data-stu-id="218fa-340">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
> <span data-ttu-id="218fa-341">可以使用文件夹路径或完全限定的资源 (指定单个文件或文件夹) 但无法指定适用于哪些规则或排除项。</span><span class="sxs-lookup"><span data-stu-id="218fa-341">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="218fa-342">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-342">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-343">Windows 10，版本 1803</span><span class="sxs-lookup"><span data-stu-id="218fa-343">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="218fa-344">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-344">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-345">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-345">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="218fa-346">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="218fa-346">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="218fa-347">Intune 名称： `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="218fa-347">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="218fa-348">Configuration Manager 名称： `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="218fa-348">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="218fa-349">GUID：`01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="218fa-349">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="218fa-350">阻止执行可能混淆的脚本</span><span class="sxs-lookup"><span data-stu-id="218fa-350">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="218fa-351">此规则在混淆的脚本中检测可疑属性。</span><span class="sxs-lookup"><span data-stu-id="218fa-351">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="218fa-352">脚本模糊处理是恶意软件作者和合法应用程序都用于隐藏知识产权或缩短脚本加载次数的常见技术。</span><span class="sxs-lookup"><span data-stu-id="218fa-352">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="218fa-353">恶意软件作者还使用模糊处理使恶意代码更难阅读，这可防止人员和安全软件进行严格的审查。</span><span class="sxs-lookup"><span data-stu-id="218fa-353">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="218fa-354">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-354">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-355">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="218fa-355">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="218fa-356">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-356">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-357">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-357">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="218fa-358">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="218fa-358">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="218fa-359">Intune 名称： `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="218fa-359">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="218fa-360">Configuration Manager 名称： `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="218fa-360">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="218fa-361">GUID：`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="218fa-361">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="218fa-362">阻止 JavaScript 或 VBScript 启动下载的可执行内容</span><span class="sxs-lookup"><span data-stu-id="218fa-362">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="218fa-363">此规则阻止脚本启动潜在恶意下载的内容。</span><span class="sxs-lookup"><span data-stu-id="218fa-363">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="218fa-364">用 JavaScript 或 VBScript 编写的恶意软件通常充当从 Internet 提取和启动其他恶意软件的下载程序。</span><span class="sxs-lookup"><span data-stu-id="218fa-364">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="218fa-365">虽然不常见，但业务线应用程序有时会使用脚本下载和启动安装程序。</span><span class="sxs-lookup"><span data-stu-id="218fa-365">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="218fa-366">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-366">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-367">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="218fa-367">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="218fa-368">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-368">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-369">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-369">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="218fa-370">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="218fa-370">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="218fa-371">Intune 名称： `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="218fa-371">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="218fa-372">Configuration Manager 名称： `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="218fa-372">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="218fa-373">GUID：`D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="218fa-373">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="218fa-374">阻止Office应用程序创建可执行内容</span><span class="sxs-lookup"><span data-stu-id="218fa-374">Block Office applications from creating executable content</span></span>

<span data-ttu-id="218fa-375">此规则Office Word、Excel 和 PowerPoint 等应用阻止恶意代码写入磁盘，从而阻止其创建潜在恶意可执行内容。</span><span class="sxs-lookup"><span data-stu-id="218fa-375">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="218fa-376">滥用作为Office的恶意软件可能会尝试破坏Office，将恶意组件保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="218fa-376">Malware that abuses Office as a vector might attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="218fa-377">这些恶意组件在计算机重新启动后将一直保留于系统。</span><span class="sxs-lookup"><span data-stu-id="218fa-377">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="218fa-378">因此，此规则可防御常见的持久性技术。</span><span class="sxs-lookup"><span data-stu-id="218fa-378">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="218fa-379">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-379">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-380">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="218fa-380">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="218fa-381">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-381">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-382">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-382">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="218fa-383">[System Center Configuration Manager (](/configmgr/core/servers/manage/updates) SCCM) CB 1710 (SCCM 现已Microsoft Endpoint Configuration Manager) </span><span class="sxs-lookup"><span data-stu-id="218fa-383">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="218fa-384">Intune 名称： `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="218fa-384">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="218fa-385">SCCM 名称： `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="218fa-385">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="218fa-386">GUID：`3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="218fa-386">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="218fa-387">阻止Office代码注入其他进程</span><span class="sxs-lookup"><span data-stu-id="218fa-387">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="218fa-388">此规则阻止代码注入尝试Office应用注入其他进程。</span><span class="sxs-lookup"><span data-stu-id="218fa-388">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="218fa-389">攻击者可能会尝试使用Office代码注入将恶意代码迁移到其他进程中，因此代码可以伪装成一个干净流程。</span><span class="sxs-lookup"><span data-stu-id="218fa-389">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="218fa-390">使用代码注入没有已知的合法业务用途。</span><span class="sxs-lookup"><span data-stu-id="218fa-390">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="218fa-391">此规则适用于 Word、Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="218fa-391">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="218fa-392">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-392">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-393">Windows 10，版本 1709</span><span class="sxs-lookup"><span data-stu-id="218fa-393">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="218fa-394">Windows服务器版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-394">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-395">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-395">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="218fa-396">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="218fa-396">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="218fa-397">Intune 名称： `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="218fa-397">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="218fa-398">Configuration Manager 名称： `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="218fa-398">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="218fa-399">GUID：`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="218fa-399">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="218fa-400">阻止Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="218fa-400">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="218fa-401">此规则阻止 Outlook 创建子进程，同时仍允许合法的 Outlook 功能。</span><span class="sxs-lookup"><span data-stu-id="218fa-401">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="218fa-402">此规则可防止社会工程攻击，并防止利用代码滥用 Outlook 中的漏洞。</span><span class="sxs-lookup"><span data-stu-id="218fa-402">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="218fa-403">它还可抵御 [Outlook](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) 规则和表单攻击，攻击者可以在用户凭据遭到泄露时使用这些漏洞。</span><span class="sxs-lookup"><span data-stu-id="218fa-403">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="218fa-404">此规则阻止 Outlook 中的 DLP 策略提示和工具提示。</span><span class="sxs-lookup"><span data-stu-id="218fa-404">This rule blocks DLP policy tips and ToolTips in Outlook.</span></span> <span data-ttu-id="218fa-405">此规则仅适用于 Outlook 和 Outlook.com。</span><span class="sxs-lookup"><span data-stu-id="218fa-405">This rule applies to Outlook and Outlook.com only.</span></span>

<span data-ttu-id="218fa-406">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-406">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-407">Windows 10 版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-407">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="218fa-408">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-408">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-409">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-409">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="218fa-410">Intune 名称： `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="218fa-410">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="218fa-411">Configuration Manager 名称：不可用</span><span class="sxs-lookup"><span data-stu-id="218fa-411">Configuration Manager name: Not available</span></span>

<span data-ttu-id="218fa-412">GUID：`26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="218fa-412">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="218fa-413">通过 WMI 事件订阅阻止持久性</span><span class="sxs-lookup"><span data-stu-id="218fa-413">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="218fa-414">此规则可防止恶意软件滥用 WMI 在设备上获得持久性。</span><span class="sxs-lookup"><span data-stu-id="218fa-414">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="218fa-415">文件和文件夹排除项不适用于此攻击面减少规则。</span><span class="sxs-lookup"><span data-stu-id="218fa-415">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="218fa-416">无文件威胁采用各种策略来保持隐藏，以避免在文件系统中可见，并获得定期执行控制。</span><span class="sxs-lookup"><span data-stu-id="218fa-416">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="218fa-417">某些威胁可能会滥用 WMI 存储库和事件模型来保持隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="218fa-417">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="218fa-418">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-418">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-419">Windows 10 版本 1903</span><span class="sxs-lookup"><span data-stu-id="218fa-419">Windows 10, version 1903</span></span>](/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="218fa-420">Windows Server 1903</span><span class="sxs-lookup"><span data-stu-id="218fa-420">Windows Server 1903</span></span>](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="218fa-421">Intune 名称：不可用</span><span class="sxs-lookup"><span data-stu-id="218fa-421">Intune name: Not available</span></span>

<span data-ttu-id="218fa-422">Configuration Manager 名称：不可用</span><span class="sxs-lookup"><span data-stu-id="218fa-422">Configuration Manager name: Not available</span></span>

<span data-ttu-id="218fa-423">GUID：`e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="218fa-423">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="218fa-424">阻止源自 PSExec 和 WMI 命令的进程创建</span><span class="sxs-lookup"><span data-stu-id="218fa-424">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="218fa-425">此规则阻止通过 [PsExec](/sysinternals/downloads/psexec) 和 [WMI 创建](/windows/win32/wmisdk/about-wmi) 的进程运行。</span><span class="sxs-lookup"><span data-stu-id="218fa-425">This rule blocks processes created through [PsExec](/sysinternals/downloads/psexec) and [WMI](/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="218fa-426">PsExec 和 WMI 都可以远程执行代码，因此存在恶意软件滥用此功能以用于命令和控制目的，或在整个组织的网络中传播感染的风险。</span><span class="sxs-lookup"><span data-stu-id="218fa-426">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="218fa-427">仅在使用 [Intune](/intune) 或其他 MDM 解决方案管理设备时使用此规则。</span><span class="sxs-lookup"><span data-stu-id="218fa-427">Only use this rule if you're managing your devices with [Intune](/intune) or another MDM solution.</span></span> <span data-ttu-id="218fa-428">此规则与通过 Microsoft [Endpoint Configuration Manager](/configmgr) 管理不兼容，因为此规则会阻止 Configuration Manager 客户端用于正常运行的 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="218fa-428">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="218fa-429">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-429">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-430">Windows 10 版本 1803</span><span class="sxs-lookup"><span data-stu-id="218fa-430">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="218fa-431">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-431">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-432">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-432">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="218fa-433">Intune 名称： `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="218fa-433">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="218fa-434">Configuration Manager 名称：不适用</span><span class="sxs-lookup"><span data-stu-id="218fa-434">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="218fa-435">GUID：`d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="218fa-435">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="218fa-436">阻止从 USB 运行的不受信任的和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="218fa-436">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="218fa-437">通过此规则，管理员可以阻止未签名或不受信任的可执行文件从 USB 可移动驱动器（包括 SD 卡）运行。</span><span class="sxs-lookup"><span data-stu-id="218fa-437">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="218fa-438">阻止的文件类型包括可执行 (文件，.exe、.dll或 .scr) </span><span class="sxs-lookup"><span data-stu-id="218fa-438">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="218fa-439">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-439">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-440">Windows 10 版本 1803</span><span class="sxs-lookup"><span data-stu-id="218fa-440">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="218fa-441">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-441">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-442">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-442">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="218fa-443">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="218fa-443">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="218fa-444">Intune 名称： `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="218fa-444">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="218fa-445">Configuration Manager 名称： `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="218fa-445">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="218fa-446">GUID：`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="218fa-446">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="218fa-447">阻止从 Office 宏调用 Win32 API</span><span class="sxs-lookup"><span data-stu-id="218fa-447">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="218fa-448">此规则阻止 VBA 宏调用 Win32 API。</span><span class="sxs-lookup"><span data-stu-id="218fa-448">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="218fa-449">Office VBA 支持 Win32 API 调用。</span><span class="sxs-lookup"><span data-stu-id="218fa-449">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="218fa-450">恶意软件可能会滥用此功能，例如调用 [Win32 API 以启动恶意 shellcode，](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) 而无需将任何内容直接写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="218fa-450">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="218fa-451">大多数组织不依赖于在日常运行中调用 Win32 API 的功能，即使它们以其他方式使用宏。</span><span class="sxs-lookup"><span data-stu-id="218fa-451">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="218fa-452">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-452">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-453">Windows 10 版本 1709</span><span class="sxs-lookup"><span data-stu-id="218fa-453">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="218fa-454">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-454">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-455">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-455">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="218fa-456">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="218fa-456">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="218fa-457">Intune 名称： `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="218fa-457">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="218fa-458">Configuration Manager 名称： `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="218fa-458">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="218fa-459">GUID：`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="218fa-459">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="218fa-460">使用高级防护抵御勒索软件</span><span class="sxs-lookup"><span data-stu-id="218fa-460">Use advanced protection against ransomware</span></span>

<span data-ttu-id="218fa-461">此规则提供针对勒索软件的额外保护层。</span><span class="sxs-lookup"><span data-stu-id="218fa-461">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="218fa-462">它使用客户端和云启发来确定文件是否类似于勒索软件。</span><span class="sxs-lookup"><span data-stu-id="218fa-462">It uses both client and cloud heuristics to determine whether a file resembles ransomware.</span></span> <span data-ttu-id="218fa-463">此规则不会阻止具有以下一个或多个特征的文件：</span><span class="sxs-lookup"><span data-stu-id="218fa-463">This rule does not block files that have one or more of the following characteristics:</span></span>

- <span data-ttu-id="218fa-464">已在 Microsoft 云中发现该文件未共享。</span><span class="sxs-lookup"><span data-stu-id="218fa-464">The file has already been found to be unharmful in the Microsoft cloud.</span></span>
- <span data-ttu-id="218fa-465">文件是有效的签名文件。</span><span class="sxs-lookup"><span data-stu-id="218fa-465">The file is a valid signed file.</span></span>
- <span data-ttu-id="218fa-466">该文件非常流行，不被视为勒索软件。</span><span class="sxs-lookup"><span data-stu-id="218fa-466">The file is prevalent enough to not be considered as ransomware.</span></span>

<span data-ttu-id="218fa-467">该规则倾向于谨慎阻止勒索软件。</span><span class="sxs-lookup"><span data-stu-id="218fa-467">The rule tends to err on the side of caution to prevent ransomware.</span></span>

> [!NOTE]
> <span data-ttu-id="218fa-468">必须 [启用云保护才能](enable-cloud-protection-microsoft-defender-antivirus.md) 使用此规则。</span><span class="sxs-lookup"><span data-stu-id="218fa-468">You must [enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) to use this rule.</span></span>

<span data-ttu-id="218fa-469">此规则是在：</span><span class="sxs-lookup"><span data-stu-id="218fa-469">This rule was introduced in:</span></span>

- [<span data-ttu-id="218fa-470">Windows 10 版本 1803</span><span class="sxs-lookup"><span data-stu-id="218fa-470">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="218fa-471">Windows Server 版本 1809</span><span class="sxs-lookup"><span data-stu-id="218fa-471">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="218fa-472">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="218fa-472">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="218fa-473">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="218fa-473">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="218fa-474">Intune 名称： `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="218fa-474">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="218fa-475">Configuration Manager 名称： `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="218fa-475">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="218fa-476">GUID：`c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="218fa-476">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>
