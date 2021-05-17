---
title: 步骤 2. 修正第一个事件
description: 如何开始修正 Microsoft 365 Defender 中的第一个事件。
keywords: 事件， 警报， 调查， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ed597c55a646eb00d6e6d256c287b22c119f8148
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297340"
---
# <a name="step-2-remediate-your-first-incident"></a><span data-ttu-id="c5e6c-105">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="c5e6c-105">Step 2.</span></span> <span data-ttu-id="c5e6c-106">修正第一个事件</span><span class="sxs-lookup"><span data-stu-id="c5e6c-106">Remediate your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c5e6c-107">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c5e6c-107">**Applies to:**</span></span>
- <span data-ttu-id="c5e6c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5e6c-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="c5e6c-109">Microsoft 365 Defender 不仅提供检测和分析功能，而且还提供恶意软件的控制和侵害。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-109">Microsoft 365 Defender not only provides detection and analysis capabilities but also provides containment and eradication of malware.</span></span> <span data-ttu-id="c5e6c-110">抑制包括减少攻击影响的步骤，同时确保从网络中删除攻击者活动的所有跟踪。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-110">Containment includes steps to reduce the impact of the attack while eradication ensures all traces of attacker activity are removed from the network.</span></span>  <span data-ttu-id="c5e6c-111">Microsoft 365 Defender 提供了几个修正操作，可配置为[](m365d-autoir.md)根据操作系统和攻击类型进行自动修正。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-111">Microsoft 365 Defender offers several remediation actions which can be configured to [auto-remediate](m365d-autoir.md) depending on your operating system and the attack type.</span></span>

<span data-ttu-id="c5e6c-112">Microsoft 365 Defender 提供了一些分析员可以手动启动的修正操作。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-112">Microsoft 365 Defender offers several remediation actions that analysts can manually initiate.</span></span> <span data-ttu-id="c5e6c-113">操作分为两类：设备上操作和文件操作。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-113">Actions are separated into two categories, Actions on devices and Actions on files.</span></span> <span data-ttu-id="c5e6c-114">某些操作可用于立即停止威胁，而其他操作有助于进一步取证分析。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-114">Some actions can be used to immediately stop the threat while other actions assist in further forensic analysis.</span></span>

## <a name="actions-on-devices"></a><span data-ttu-id="c5e6c-115">对设备的操作</span><span class="sxs-lookup"><span data-stu-id="c5e6c-115">Actions on devices</span></span>

- <span data-ttu-id="c5e6c-116">隔离设备 **-** 此活动将立即阻止 internet 和 (内部) 的所有网络流量，以最大限度地减少恶意软件的分布，并允许分析员继续分析，而无需恶意参与者继续攻击。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-116">**Isolate the device** - This activity immediately blocks all network traffic (internet and internal) to minimize the spread of malware and allow analysts to continue analysis without a malicious actor being able to continue an attack.</span></span> <span data-ttu-id="c5e6c-117">唯一允许的连接是 Microsoft Defender for Identity 服务云，因此 Microsoft Defender for Identity 可以继续监视设备。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-117">The only connection allowed is to the Microsoft Defender for Identity service cloud so Microsoft Defender for Identity can continue to monitor the device.</span></span> 
- <span data-ttu-id="c5e6c-118">**限制应用执行** - 若要限制应用程序运行，应用代码完整性策略，该策略只允许文件在由 Microsoft 颁发的证书签名时运行。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-118">**Restrict app execution** - To restrict an application from running, a code integrity policy is applied that only allows files to run if they are signed by a Microsoft-issued certificate.</span></span> <span data-ttu-id="c5e6c-119">这种限制方法有助于防止攻击者控制受到威胁的设备，并执行进一步恶意活动。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-119">This method of restriction can help prevent an attacker from controlling compromised devices and performing further malicious activities.</span></span>
- <span data-ttu-id="c5e6c-120">**运行防病毒扫描** - 无论 Defender 防病毒是否是活动的防病毒解决方案，Microsoft Defender 防病毒扫描都可以与其他防病毒解决方案一起运行。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-120">**Run Antivirus scan** - A Microsoft Defender Antivirus scan can run alongside other antivirus solutions, whether Defender Antivirus is the active antivirus solution or not.</span></span> <span data-ttu-id="c5e6c-121">如果另一个防病毒供应商产品是主要终结点保护解决方案，可以在被动模式下运行 Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-121">If another antivirus vendor product is the primary endpoint protection solution, you can run Defender Antivirus in Passive mode.</span></span>
- <span data-ttu-id="c5e6c-122">**启动自动调查** - 可以在设备上启动新的通用自动调查。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-122">**Initiate automated investigation** - You can start a new general purpose automated investigation on the device.</span></span> <span data-ttu-id="c5e6c-123">当调查正在运行时，从设备生成的其他任何警报都将添加到正在进行的自动调查，直到完成该调查。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-123">While an investigation is running, any other alert generated from the device will be added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="c5e6c-124">此外，如果在其他设备上看到相同的威胁，则这些设备将添加到调查。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-124">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>
- <span data-ttu-id="c5e6c-125">**启动实时响应** - 实时响应是一项功能，可让你使用远程 shell 连接即时访问设备。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-125">**Initiate live response** - Live response is a capability that gives you instantaneous access to a device by using a remote shell connection.</span></span> <span data-ttu-id="c5e6c-126">这让你能够执行深入调查工作，并立即采取响应操作，以实时迅速包含识别的威胁。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-126">This gives you the ability to do in-depth investigative work and take immediate response actions to promptly contain identified threats in real time.</span></span> <span data-ttu-id="c5e6c-127">实时响应旨在通过让你能够收集取证数据、运行脚本、发送可疑实体进行分析、修正威胁和主动搜寻新出现的威胁来增强调查。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-127">Live response is designed to enhance investigations by enabling you to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span>
- <span data-ttu-id="c5e6c-128">**收集调查** 包 - 作为调查或响应过程的一部分，你可以从设备收集调查包。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-128">**Collect investigation package** - As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="c5e6c-129">通过收集调查包，你可以确定设备的当前状态，并进一步理解攻击者使用的工具和技术。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-129">By collecting the investigation package, you can identify the current state of the device and further understand the tools and techniques used by the attacker.</span></span> 
- <span data-ttu-id="c5e6c-130">咨询 **威胁** 专家 (和文件上的操作) - 你可以咨询 Microsoft 威胁专家，了解有关可能受到威胁的设备或已受到威胁的设备的更多见解。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-130">**Consult a threat expert** (available in both Actions on devices and files) - You can consult a Microsoft threat expert for more insights regarding potentially compromised devices or devices that are already compromised.</span></span> <span data-ttu-id="c5e6c-131">Microsoft 威胁专家可以直接在 Microsoft Defender 安全中心内参与，以及时准确地做出响应。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-131">Microsoft threat experts can be engaged directly from within the Microsoft Defender Security Center for a timely and accurate response.</span></span> 

## <a name="actions-on-files"></a><span data-ttu-id="c5e6c-132">对文件的操作</span><span class="sxs-lookup"><span data-stu-id="c5e6c-132">Actions on files</span></span>

- <span data-ttu-id="c5e6c-133">**停止和隔离文件** - 此操作包括停止正在运行的进程、隔离文件和删除永久数据（如任何注册表项）。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-133">**Stop and quarantine file** - This action includes stopping running processes, quarantining files, and deleting persistent data, such as any registry keys.</span></span> <span data-ttu-id="c5e6c-134">此操作在 Windows 10 版本 1703 或更高版本（过去 30 天内观测到该文件）的设备上生效。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-134">This action takes effect on devices with Windows 10, version 1703 or later, where the file was observed in the last 30 days.</span></span> 
- <span data-ttu-id="c5e6c-135">**添加指示器以阻止或允许文件** - 通过禁止潜在恶意文件或可疑恶意软件，阻止攻击在组织中进一步传播。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-135">**Add indicators to block or allow file** - Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="c5e6c-136">此操作将阻止在组织的设备上读取、写入或执行文件。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-136">This operation will prevent the file from being read, written, or executed on devices in your organization.</span></span>
- <span data-ttu-id="c5e6c-137">**下载或收集文件** – 通过此操作，分析员可以下载受密码保护的文件.zip存档文件中，供组织进一步分析。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-137">**Download or collect file** – This action allows analysts to download a file in a password protected .zip archive file for further analysis by the organization.</span></span>
- <span data-ttu-id="c5e6c-138">**深度分析** – 此操作在安全、完全检测的云环境中执行文件。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-138">**Deep analysis** – This action executes a file in a secure, fully instrumented cloud environment.</span></span> <span data-ttu-id="c5e6c-139">深度分析结果显示文件的活动、观察到的行为以及关联的项目，例如丢弃的文件、注册表修改以及与 IP 地址的通信。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-139">Deep analysis results show the file's activities, observed behaviors, and associated artifacts, such as dropped files, registry modifications, and communication with IP addresses.</span></span> 

<span data-ttu-id="c5e6c-140">继续检测、 [会审](first-incident-analyze.md#analyze-your-first-incident)和分析事件中的示例，分析员可以使用以下操作修正此事件：</span><span class="sxs-lookup"><span data-stu-id="c5e6c-140">Continuing the example in [Detect, triage, and analyze incidents](first-incident-analyze.md#analyze-your-first-incident), an analyst can remediate this incident with these actions:</span></span>

1. <span data-ttu-id="c5e6c-141">立即重置用户帐户密码</span><span class="sxs-lookup"><span data-stu-id="c5e6c-141">Immediately reset the user account password</span></span>
2. <span data-ttu-id="c5e6c-142">在深入分析完成之前，在 Microsoft 365 Defender 中隔离设备</span><span class="sxs-lookup"><span data-stu-id="c5e6c-142">Isolate the device in Microsoft 365 Defender until deep analysis is complete</span></span>
3. <span data-ttu-id="c5e6c-143">确保从 SharePoint 隔离恶意文件</span><span class="sxs-lookup"><span data-stu-id="c5e6c-143">Ensure the malicious file was quarantined from SharePoint</span></span>
4. <span data-ttu-id="c5e6c-144">检查哪些终结点受恶意软件影响</span><span class="sxs-lookup"><span data-stu-id="c5e6c-144">Check which endpoints were affected by malware</span></span>
5. <span data-ttu-id="c5e6c-145">重新生成系统</span><span class="sxs-lookup"><span data-stu-id="c5e6c-145">Rebuild systems</span></span>
6. <span data-ttu-id="c5e6c-146">检查其他用户的类似 Microsoft Cloud App Security 警报</span><span class="sxs-lookup"><span data-stu-id="c5e6c-146">Check for similar Microsoft Cloud App Security alerts for other users</span></span>
7. <span data-ttu-id="c5e6c-147">在 Microsoft Defender for Endpoint 中创建自定义指示器以阻止 Tor IP 地址</span><span class="sxs-lookup"><span data-stu-id="c5e6c-147">Create a custom indicator in Microsoft Defender for Endpoint to block a Tor IP address</span></span>
8. <span data-ttu-id="c5e6c-148">在 Microsoft Cloud App Security 中为此类型的警报创建管理操作，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="c5e6c-148">Create a governance action in Microsoft Cloud App Security for this type of alert such as those shown in the following image:</span></span>

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="Microsoft Cloud App Security 门户中的管理操作示例"::: 
 
<span data-ttu-id="c5e6c-150">大多数修正操作都可以在 Microsoft 365 Defender 中应用和跟踪。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-150">Most of the remediation actions can be applied and tracked in Microsoft 365 Defender.</span></span> 

## <a name="using-playbooks"></a><span data-ttu-id="c5e6c-151">使用 Playbook</span><span class="sxs-lookup"><span data-stu-id="c5e6c-151">Using Playbooks</span></span>

<span data-ttu-id="c5e6c-152">此外，可以使用 Playbook 创建自动修正。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-152">In addition, automated remediation can be created using playbooks.</span></span> <span data-ttu-id="c5e6c-153">目前，Microsoft 在 GitHub 上具有 [Playbook](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) 模板，这些模板提供适用于以下方案的 Playbook：</span><span class="sxs-lookup"><span data-stu-id="c5e6c-153">Currently, Microsoft has [Playbook templates on GitHub](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) that provide playbooks for the following scenarios:</span></span>

- <span data-ttu-id="c5e6c-154">请求用户验证后删除敏感文件共享</span><span class="sxs-lookup"><span data-stu-id="c5e6c-154">Remove sensitive file sharing after requesting user validation</span></span>
- <span data-ttu-id="c5e6c-155">不经常使用的国家/地区警报自动分类</span><span class="sxs-lookup"><span data-stu-id="c5e6c-155">Auto-triage infrequent country alerts</span></span>
- <span data-ttu-id="c5e6c-156">禁用帐户之前请求管理员操作</span><span class="sxs-lookup"><span data-stu-id="c5e6c-156">Request for manager action before disabling an account</span></span>
- <span data-ttu-id="c5e6c-157">禁用恶意收件箱规则</span><span class="sxs-lookup"><span data-stu-id="c5e6c-157">Disable malicious inbox rules</span></span>

<span data-ttu-id="c5e6c-158">Playbook 使用 Power Automate 创建自定义的自动化流程，以在触发特定条件后自动执行某些活动。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-158">Playbooks use Power Automate to create custom robotic process automation flows to automate certain activities once specific criteria have been triggered.</span></span> <span data-ttu-id="c5e6c-159">组织可以从现有模板或从头开始创建游戏手册。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-159">Organizations can create playbooks either from existing templates or from scratch.</span></span> 

<span data-ttu-id="c5e6c-160">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-160">Here's an example.</span></span>
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="Power Automate 自定义自动化过程自动化流的示例"::: 
 
<span data-ttu-id="c5e6c-162">还可以在事后评审期间创建操作手册[](first-incident-post.md)，以从事件创建修正操作，以加快补救操作速度。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-162">Playbooks can also be created during [post-incident review](first-incident-post.md) to create remediation actions from incidents for faster remediation actions.</span></span> 

## <a name="next-step"></a><span data-ttu-id="c5e6c-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c5e6c-163">Next step</span></span>

<span data-ttu-id="c5e6c-164">[![步骤 3：了解如何对事件执行事后评审](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="c5e6c-164">[![Step 3: Learn how to perform a post-incident review of an incident](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)</span></span>

<span data-ttu-id="c5e6c-165">了解如何 [对事件执行事后评审](first-incident-post.md)。</span><span class="sxs-lookup"><span data-stu-id="c5e6c-165">Learn how to [perform a post-incident review of an incident](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c5e6c-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5e6c-166">See also</span></span>

- [<span data-ttu-id="c5e6c-167">事件概述</span><span class="sxs-lookup"><span data-stu-id="c5e6c-167">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c5e6c-168">调查事件</span><span class="sxs-lookup"><span data-stu-id="c5e6c-168">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="c5e6c-169">管理事件</span><span class="sxs-lookup"><span data-stu-id="c5e6c-169">Manage incidents</span></span>](manage-incidents.md)
