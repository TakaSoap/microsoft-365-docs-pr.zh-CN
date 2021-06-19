---
title: 行为阻止和控制
description: 了解 Microsoft Defender for Endpoint 中的行为阻止和包含功能
keywords: Microsoft Defender for Endpoint，EDR阻止模式，被动模式阻止
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: c480bb83465e6057cd1cf29f1f5077f2a0e165e8
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028819"
---
# <a name="behavioral-blocking-and-containment"></a><span data-ttu-id="53e46-104">行为阻止和控制</span><span class="sxs-lookup"><span data-stu-id="53e46-104">Behavioral blocking and containment</span></span>

<span data-ttu-id="53e46-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="53e46-105">**Applies to:**</span></span>
- [<span data-ttu-id="53e46-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="53e46-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="53e46-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53e46-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="53e46-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="53e46-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="53e46-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="53e46-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="53e46-110">概述</span><span class="sxs-lookup"><span data-stu-id="53e46-110">Overview</span></span>

<span data-ttu-id="53e46-111">如今的威胁形势被无文件恶意软件所溢出[](/windows/security/threat-protection/intelligence/fileless-threats)，并位于陆地外，其变化速度比传统解决方案快的高度多态威胁，以及适应攻击者在遭到入侵的设备上发现的攻击。</span><span class="sxs-lookup"><span data-stu-id="53e46-111">Today’s threat landscape is overrun by [fileless malware](/windows/security/threat-protection/intelligence/fileless-threats) and that lives off the land, highly polymorphic threats that mutate faster than traditional solutions can keep up with, and human-operated attacks that adapt to what adversaries find on compromised devices.</span></span> <span data-ttu-id="53e46-112">传统安全解决方案不足以阻止此类攻击;你需要人工智能 (AI) 和设备学习 (ML) 支持的功能，如行为阻止和抑制，包含在[Defender for Endpoint 中](/windows/security)。</span><span class="sxs-lookup"><span data-stu-id="53e46-112">Traditional security solutions are not sufficient to stop such attacks; you need artificial intelligence (AI) and device learning (ML) backed capabilities, such as behavioral blocking and containment, included in [Defender for Endpoint](/windows/security).</span></span> 

<span data-ttu-id="53e46-113">行为阻止和抑制功能可帮助根据威胁的行为和进程树识别和停止威胁，即使威胁已开始执行。</span><span class="sxs-lookup"><span data-stu-id="53e46-113">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> <span data-ttu-id="53e46-114">下一代保护、EDR和适用于终结点的 Defender 组件和功能在行为阻止和抑制功能中协同工作。</span><span class="sxs-lookup"><span data-stu-id="53e46-114">Next-generation protection, EDR, and Defender for Endpoint components and features work together in behavioral blocking and containment capabilities.</span></span> 

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="行为阻止和控制":::

<span data-ttu-id="53e46-116">行为阻止和包含功能适用于 Defender for Endpoint 的多个组件和功能，可立即停止攻击并阻止攻击的进行。</span><span class="sxs-lookup"><span data-stu-id="53e46-116">Behavioral blocking and containment capabilities work with multiple components and features of Defender for Endpoint to stop attacks immediately and prevent attacks from progressing.</span></span>

- <span data-ttu-id="53e46-117">[下一代](microsoft-defender-antivirus-in-windows-10.md) (防护功能Microsoft Defender 防病毒) 分析行为来检测威胁，并停止已开始运行的威胁。</span><span class="sxs-lookup"><span data-stu-id="53e46-117">[Next-generation protection](microsoft-defender-antivirus-in-windows-10.md) (which includes Microsoft Defender Antivirus) can detect threats by analyzing behaviors, and stop threats that have started running.</span></span>

- <span data-ttu-id="53e46-118">[终结点检测和响应 (EDR) ](overview-endpoint-detection-response.md)网络、设备和内核行为接收安全信号。</span><span class="sxs-lookup"><span data-stu-id="53e46-118">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR) receives security signals across your network, devices, and kernel behavior.</span></span> <span data-ttu-id="53e46-119">检测到威胁时，将创建警报。</span><span class="sxs-lookup"><span data-stu-id="53e46-119">As threats are detected, alerts are created.</span></span> <span data-ttu-id="53e46-120">同一类型的多个警报将聚合到事件中，这便于安全运营团队调查和响应。</span><span class="sxs-lookup"><span data-stu-id="53e46-120">Multiple alerts of the same type are aggregated into incidents, which makes it easier for your security operations team to investigate and respond.</span></span>

- <span data-ttu-id="53e46-121">[Defender for Endpoint](overview-endpoint-detection-response.md)具有广泛的光学系统，包括标识、电子邮件、数据和应用，以及通过 EDR 接收的网络、终结点和内核行为信号。</span><span class="sxs-lookup"><span data-stu-id="53e46-121">[Defender for Endpoint](overview-endpoint-detection-response.md) has a wide range of optics across identities, email, data, and apps, in addition to the network, endpoint, and kernel behavior signals received through EDR.</span></span> <span data-ttu-id="53e46-122">事件[、Microsoft 365 Defender](../defender/microsoft-365-defender.md)Defender 处理和关联这些信号、引发检测警报以及连接事件中的相关警报的组件。</span><span class="sxs-lookup"><span data-stu-id="53e46-122">A component of [Microsoft 365 Defender](../defender/microsoft-365-defender.md), Defender for Endpoint processes and correlates these signals, raises detection alerts, and connects related alerts in incidents.</span></span>

<span data-ttu-id="53e46-123">借助这些功能，可以阻止或阻止更多威胁，即使它们开始运行。</span><span class="sxs-lookup"><span data-stu-id="53e46-123">With these capabilities, more threats can be prevented or blocked, even if they start running.</span></span> <span data-ttu-id="53e46-124">只要检测到可疑行为，就会包含威胁，创建警报，并停止威胁。</span><span class="sxs-lookup"><span data-stu-id="53e46-124">Whenever suspicious behavior is detected, the threat is contained, alerts are created, and threats are stopped in their tracks.</span></span> 

<span data-ttu-id="53e46-125">下图显示了由行为阻止和抑制功能触发的警报示例：</span><span class="sxs-lookup"><span data-stu-id="53e46-125">The following image shows an example of an alert that was triggered by behavioral blocking and containment capabilities:</span></span>

:::image type="content" source="images/blocked-behav-alert.png" alt-text="通过行为阻止和包含的警报示例":::

## <a name="components-of-behavioral-blocking-and-containment"></a><span data-ttu-id="53e46-127">行为阻止和包含的组件</span><span class="sxs-lookup"><span data-stu-id="53e46-127">Components of behavioral blocking and containment</span></span>

- <span data-ttu-id="53e46-128">**客户端上策略驱动的 [攻击面减少规则](attack-surface-reduction.md)** 根据攻击面减少规则，防止执行预定义的常见攻击行为。</span><span class="sxs-lookup"><span data-stu-id="53e46-128">**On-client, policy-driven [attack surface reduction rules](attack-surface-reduction.md)** Predefined common attack behaviors are prevented from executing, according to your attack surface reduction rules.</span></span> <span data-ttu-id="53e46-129">当此类行为尝试执行时，可以在事件Microsoft 365 Defender () [https://security.microsoft.com](https://security.microsoft.com) 信息警报。</span><span class="sxs-lookup"><span data-stu-id="53e46-129">When such behaviors attempt to execute, they can be seen in Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) as informational alerts.</span></span> <span data-ttu-id="53e46-130">默认情况下不会启用攻击面减少规则;在策略中[配置Microsoft 365 Defender。](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="53e46-130">Attack surface reduction rules are not enabled by default; you configure your policies in the [Microsoft 365 Defender](microsoft-defender-security-center.md).</span></span>

- <span data-ttu-id="53e46-131">**[客户端行为阻止](client-behavioral-blocking.md)** 终结点上的威胁通过机器学习进行检测，然后自动阻止和修正。</span><span class="sxs-lookup"><span data-stu-id="53e46-131">**[Client behavioral blocking](client-behavioral-blocking.md)** Threats on endpoints are detected through machine learning, and then are blocked and remediated automatically.</span></span> <span data-ttu-id="53e46-132"> (启用客户端行为阻止。) </span><span class="sxs-lookup"><span data-stu-id="53e46-132">(Client behavioral blocking is enabled by default.)</span></span> 

- <span data-ttu-id="53e46-133">**[反馈循环阻止 (](feedback-loop-blocking.md)** 也称为快速保护) 行为智能观察到威胁检测。</span><span class="sxs-lookup"><span data-stu-id="53e46-133">**[Feedback-loop blocking](feedback-loop-blocking.md)** (also referred to as rapid protection) Threat detections are observed through behavioral intelligence.</span></span> <span data-ttu-id="53e46-134">威胁将停止并阻止在其他终结点上运行。</span><span class="sxs-lookup"><span data-stu-id="53e46-134">Threats are stopped and prevented from running on other endpoints.</span></span> <span data-ttu-id="53e46-135"> (启用反馈循环阻止。) </span><span class="sxs-lookup"><span data-stu-id="53e46-135">(Feedback-loop blocking is enabled by default.)</span></span> 

- <span data-ttu-id="53e46-136">**[终结点检测和响应 (EDR) 阻止模式](edr-in-block-mode.md)** 通过泄露后保护观察到的恶意项目或行为将被阻止和包含。</span><span class="sxs-lookup"><span data-stu-id="53e46-136">**[Endpoint detection and response (EDR) in block mode](edr-in-block-mode.md)** Malicious artifacts or behaviors that are observed through post-breach protection are blocked and contained.</span></span> <span data-ttu-id="53e46-137">EDR阻止模式运行，即使Microsoft Defender 防病毒不是主要的防病毒解决方案。</span><span class="sxs-lookup"><span data-stu-id="53e46-137">EDR in block mode works even if Microsoft Defender Antivirus is not the primary antivirus solution.</span></span> <span data-ttu-id="53e46-138"> (EDR在阻止模式下未启用;在 Microsoft 365 Defender.) </span><span class="sxs-lookup"><span data-stu-id="53e46-138">(EDR in block mode is not enabled by default; you turn it on in Microsoft 365 Defender.)</span></span> 

<span data-ttu-id="53e46-139">随着 Microsoft 继续改进威胁防护特性和功能，预期行为阻止和抑制领域会有更多的变化。</span><span class="sxs-lookup"><span data-stu-id="53e46-139">Expect more to come in the area of behavioral blocking and containment, as Microsoft continues to improve threat protection features and capabilities.</span></span> <span data-ttu-id="53e46-140">若要了解现在的计划和推出，请访问 Microsoft 365[路线图](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="53e46-140">To see what's planned and rolling out now, visit the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a><span data-ttu-id="53e46-141">操作中的行为阻止和包含的示例</span><span class="sxs-lookup"><span data-stu-id="53e46-141">Examples of behavioral blocking and containment in action</span></span>

<span data-ttu-id="53e46-142">行为阻止和抑制功能阻止了攻击者技术，如下所示：</span><span class="sxs-lookup"><span data-stu-id="53e46-142">Behavioral blocking and containment capabilities have blocked attacker techniques such as the following:</span></span>

- <span data-ttu-id="53e46-143">从 LSASS 进行凭据转储</span><span class="sxs-lookup"><span data-stu-id="53e46-143">Credential dumping from LSASS</span></span>
- <span data-ttu-id="53e46-144">跨进程注入</span><span class="sxs-lookup"><span data-stu-id="53e46-144">Cross-process injection</span></span>
- <span data-ttu-id="53e46-145">进程空心</span><span class="sxs-lookup"><span data-stu-id="53e46-145">Process hollowing</span></span>
- <span data-ttu-id="53e46-146">用户帐户控制绕过</span><span class="sxs-lookup"><span data-stu-id="53e46-146">User Account Control bypass</span></span>
- <span data-ttu-id="53e46-147">篡改防病毒程序 (例如禁用它或添加恶意软件作为排除) </span><span class="sxs-lookup"><span data-stu-id="53e46-147">Tampering with antivirus (such as disabling it or adding the malware as exclusion)</span></span>
- <span data-ttu-id="53e46-148">联系 Command and Control (C&C) 以下载有效负载</span><span class="sxs-lookup"><span data-stu-id="53e46-148">Contacting Command and Control (C&C) to download payloads</span></span>
- <span data-ttu-id="53e46-149">硬币挖掘</span><span class="sxs-lookup"><span data-stu-id="53e46-149">Coin mining</span></span>
- <span data-ttu-id="53e46-150">启动记录修改</span><span class="sxs-lookup"><span data-stu-id="53e46-150">Boot record modification</span></span>
- <span data-ttu-id="53e46-151">哈希传递攻击</span><span class="sxs-lookup"><span data-stu-id="53e46-151">Pass-the-hash attacks</span></span>
- <span data-ttu-id="53e46-152">根证书的安装</span><span class="sxs-lookup"><span data-stu-id="53e46-152">Installation of root certificate</span></span>
- <span data-ttu-id="53e46-153">利用各种漏洞的尝试</span><span class="sxs-lookup"><span data-stu-id="53e46-153">Exploitation attempt for various vulnerabilities</span></span>

<span data-ttu-id="53e46-154">下面是操作中的行为阻止和包含的两个实际示例。</span><span class="sxs-lookup"><span data-stu-id="53e46-154">Below are two real-life examples of behavioral blocking and containment in action.</span></span>

### <a name="example-1-credential-theft-attack-against-100-organizations"></a><span data-ttu-id="53e46-155">示例 1：针对 100 个组织的凭据盗窃攻击</span><span class="sxs-lookup"><span data-stu-id="53e46-155">Example 1: Credential theft attack against 100 organizations</span></span>

<span data-ttu-id="53e46-156">如在热门威胁中所述： [基于 AI](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)驱动行为的阻止会停止其跟踪中的攻击，针对全球 100 个组织的凭据盗窃攻击已由行为阻止和封闭功能停止。</span><span class="sxs-lookup"><span data-stu-id="53e46-156">As described in [In hot pursuit of elusive threats: AI-driven behavior-based blocking stops attacks in their tracks](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks), a credential theft attack against 100 organizations around the world was stopped by behavioral blocking and containment capabilities.</span></span> <span data-ttu-id="53e46-157">包含恶意文档的 Spear-phishing 电子邮件已发送到目标组织。</span><span class="sxs-lookup"><span data-stu-id="53e46-157">Spear-phishing email messages that contained a lure document were sent to the targeted organizations.</span></span> <span data-ttu-id="53e46-158">如果收件人打开了附件，相关远程文档可以在用户设备上执行代码并加载 Lokibot 恶意软件（该恶意软件会生成凭据、被盗数据被窃取，并等待命令和控制服务器提供进一步的说明）。</span><span class="sxs-lookup"><span data-stu-id="53e46-158">If a recipient opened the attachment, a related remote document was able to execute code on the user’s device and load Lokibot malware, which stole credentials, exfiltrated stolen data, and waited for further instructions from a command-and-control server.</span></span> 

<span data-ttu-id="53e46-159">Defender for Endpoint 中基于行为的设备学习模型在攻击链中的两个点捕获并停止了攻击者的技术：</span><span class="sxs-lookup"><span data-stu-id="53e46-159">Behavior-based device learning models in Defender for Endpoint caught and stopped the attacker’s techniques at two points in the attack chain:</span></span>

- <span data-ttu-id="53e46-160">第一个保护层检测到攻击行为。</span><span class="sxs-lookup"><span data-stu-id="53e46-160">The first protection layer detected the exploit behavior.</span></span> <span data-ttu-id="53e46-161">云中的设备学习分类器正确地将威胁标识为 并立即指示客户端设备阻止攻击。</span><span class="sxs-lookup"><span data-stu-id="53e46-161">Device learning classifiers in the cloud correctly identified the threat as and immediately instructed the client device to block the attack.</span></span>
- <span data-ttu-id="53e46-162">第二个保护层，帮助阻止攻击通过第一层、检测到进程正在停靠、停止该进程并删除了相应文件 (如 Lokibot) 。</span><span class="sxs-lookup"><span data-stu-id="53e46-162">The second protection layer, which helped stop cases where the attack got past the first layer, detected process hollowing, stopped that process, and removed the corresponding files (such as Lokibot).</span></span> 

<span data-ttu-id="53e46-163">在检测到并停止攻击时，警报（如"初始访问警报）"会触发并出现在 Microsoft 365 Defender[门户](microsoft-defender-security-center.md)中 (以前Microsoft Defender 安全中心) ：</span><span class="sxs-lookup"><span data-stu-id="53e46-163">While the attack was detected and stopped, alerts, such as an "initial access alert," were triggered and appeared in the [Microsoft 365 Defender portal](microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center):</span></span>

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Microsoft 365 Defender门户中的初始Microsoft 365 Defender警报":::

<span data-ttu-id="53e46-165">此示例演示云中基于行为的设备学习模型如何添加抵御攻击的新保护层，即使它们开始运行。</span><span class="sxs-lookup"><span data-stu-id="53e46-165">This example shows how behavior-based device learning models in the cloud add new layers of protection against attacks, even after they have started running.</span></span>

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a><span data-ttu-id="53e46-166">示例 2：NTLM 中继 - Juicy Malware 恶意软件变体</span><span class="sxs-lookup"><span data-stu-id="53e46-166">Example 2: NTLM relay - Juicy Potato malware variant</span></span>

<span data-ttu-id="53e46-167">如最近的博客文章行为阻止和抑制： [将](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)光学镜头转换为保护中所述，2020 年 1 月，Defender for Endpoint 检测到组织中设备上的权限提升活动。</span><span class="sxs-lookup"><span data-stu-id="53e46-167">As described in the recent blog post, [Behavioral blocking and containment: Transforming optics into protection](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection), in January 2020, Defender for Endpoint detected a privilege escalation activity on a device in an organization.</span></span> <span data-ttu-id="53e46-168">触发了名为"使用 NTLM 中继的可能特权升级"的警报。</span><span class="sxs-lookup"><span data-stu-id="53e46-168">An alert called “Possible privilege escalation using NTLM relay” was triggered.</span></span>

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="Juicy Malware 恶意软件的 NTLM 警报":::

<span data-ttu-id="53e46-170">威胁已变成恶意软件;它是名为 Juicy 为的黑客工具的一个之前未发现的新变体，攻击者使用该工具在设备上获取特权提升。</span><span class="sxs-lookup"><span data-stu-id="53e46-170">The threat turned out to be malware; it was a new, not-seen-before variant of a notorious hacking tool called Juicy Potato, which is used by attackers to get privilege escalation on a device.</span></span> 

<span data-ttu-id="53e46-171">警报触发后的几分钟内，将分析文件并确认为恶意文件。</span><span class="sxs-lookup"><span data-stu-id="53e46-171">Minutes after the alert was triggered, the file was analyzed, and confirmed to be malicious.</span></span> <span data-ttu-id="53e46-172">其进程已停止和阻止，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="53e46-172">Its process was stopped and blocked, as shown in the following image:</span></span>

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="项目被阻止":::

<span data-ttu-id="53e46-174">项目被阻止几分钟后，同一设备的多个同一文件实例被阻止，从而阻止其他攻击者或其他恶意软件在设备上部署。</span><span class="sxs-lookup"><span data-stu-id="53e46-174">A few minutes after the artifact was blocked, multiple instances of the same file were blocked on the same device, preventing additional attackers or other malware from deploying on the device.</span></span> 

<span data-ttu-id="53e46-175">此示例显示，使用行为阻止和抑制功能，可以自动检测、包含和阻止威胁。</span><span class="sxs-lookup"><span data-stu-id="53e46-175">This example shows that with behavioral blocking and containment capabilities, threats are detected, contained, and blocked automatically.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="53e46-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="53e46-176">Next steps</span></span>

- [<span data-ttu-id="53e46-177">详细了解适用于终结点的 Defender</span><span class="sxs-lookup"><span data-stu-id="53e46-177">Learn more about Defender for Endpoint</span></span>](overview-endpoint-detection-response.md)

- [<span data-ttu-id="53e46-178">配置攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="53e46-178">Configure your attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="53e46-179">启用EDR阻止模式</span><span class="sxs-lookup"><span data-stu-id="53e46-179">Enable EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="53e46-180">查看最近的全球威胁活动</span><span class="sxs-lookup"><span data-stu-id="53e46-180">See recent global threat activity</span></span>](https://www.microsoft.com/wdsi/threats)

- [<span data-ttu-id="53e46-181">大致了解Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53e46-181">Get an overview of Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)
