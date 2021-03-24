---
title: 'Windows 10 (威胁防护) '
description: Microsoft Defender for Endpoint 是一个统一的平台，可用于预防性保护、入侵后检测、自动调查和响应。
keywords: 威胁防护， Microsoft Defender 高级威胁防护， 攻击面减少， 下一代保护， 终结点检测和响应， 自动调查和响应， Microsoft 威胁专家， Microsoft 设备安全分数， 高级搜寻， 网络威胁搜寻， Web 威胁防护
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 4206519d62feb82bbc297659e01b0cc3902b83dc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054684"
---
# <a name="threat-protection"></a><span data-ttu-id="2ed02-104">威胁防护</span><span class="sxs-lookup"><span data-stu-id="2ed02-104">Threat Protection</span></span>
<span data-ttu-id="2ed02-105">[Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) 是一个统一的平台，可用于预防性保护、入侵后检测、自动调查和响应。</span><span class="sxs-lookup"><span data-stu-id="2ed02-105">[Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="2ed02-106">Defender for Endpoint 可保护终结点免受网络威胁，检测高级攻击和数据泄露，自动执行安全事件，并改进安全状况。</span><span class="sxs-lookup"><span data-stu-id="2ed02-106">Defender for Endpoint protects endpoints from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span>

> [!TIP]
> <span data-ttu-id="2ed02-107">使用户可以轻松访问云服务和本地应用程序，并启用所有设备的新式管理功能。</span><span class="sxs-lookup"><span data-stu-id="2ed02-107">Enable your users to access cloud services and on-premises applications with ease and enable modern management capabilities for all devices.</span></span> <span data-ttu-id="2ed02-108">有关详细信息，请参阅保护 [远程工作人员](https://docs.microsoft.com/enterprise-mobility-security/remote-work/)。</span><span class="sxs-lookup"><span data-stu-id="2ed02-108">For more information, see [Secure your remote workforce](https://docs.microsoft.com/enterprise-mobility-security/remote-work/).</span></span> 

<center><h2><span data-ttu-id="2ed02-109">Microsoft Defender for Endpoint</center></span><span class="sxs-lookup"><span data-stu-id="2ed02-109">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><span data-ttu-id="2ed02-110"><b>威胁&漏洞管理</b></center></a></span><span class="sxs-lookup"><span data-stu-id="2ed02-110"><b>Threat & vulnerability management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><span data-ttu-id="2ed02-111"><b>攻击面减少</b></center></a></span><span class="sxs-lookup"><span data-stu-id="2ed02-111"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <span data-ttu-id="2ed02-112"><b>下一代保护</b></a></center></span><span class="sxs-lookup"><span data-stu-id="2ed02-112"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <span data-ttu-id="2ed02-113"><b>终结点检测和响应</b></a></center></span><span class="sxs-lookup"><span data-stu-id="2ed02-113"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <span data-ttu-id="2ed02-114"><b>自动调查和修正</b></a></center></span><span class="sxs-lookup"><span data-stu-id="2ed02-114"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <span data-ttu-id="2ed02-115"><b>Microsoft 威胁专家</b></a></center></span><span class="sxs-lookup"><span data-stu-id="2ed02-115"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="2ed02-116">
<a href="#apis"><center><b>集中配置和管理、API</a></span><span class="sxs-lookup"><span data-stu-id="2ed02-116">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="2ed02-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span><span class="sxs-lookup"><span data-stu-id="2ed02-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

<span data-ttu-id="2ed02-118">**[威胁&漏洞管理](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="2ed02-118">**[Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="2ed02-119">此内置功能使用基于游戏变化风险的方法发现、确定终结点漏洞和错误配置的优先顺序并修正。</span><span class="sxs-lookup"><span data-stu-id="2ed02-119">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span>

- [<span data-ttu-id="2ed02-120">威胁&漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="2ed02-120">Threat & vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="2ed02-121">入门</span><span class="sxs-lookup"><span data-stu-id="2ed02-121">Get started</span></span>](tvm-prerequisites.md)
- [<span data-ttu-id="2ed02-122">访问安全状态</span><span class="sxs-lookup"><span data-stu-id="2ed02-122">Access your security posture</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="2ed02-123">改善安全状况并降低风险</span><span class="sxs-lookup"><span data-stu-id="2ed02-123">Improve your security posture and reduce risk</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="2ed02-124">了解设备上漏洞</span><span class="sxs-lookup"><span data-stu-id="2ed02-124">Understand vulnerabilities on your devices</span></span>](tvm-software-inventory.md)

<a name="asr"></a>

<span data-ttu-id="2ed02-125">**[攻击面减少](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="2ed02-125">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="2ed02-126">攻击面减少功能集在堆栈中提供第一道防线。</span><span class="sxs-lookup"><span data-stu-id="2ed02-126">The attack surface reduction set of capabilities provide the first line of defense in the stack.</span></span> <span data-ttu-id="2ed02-127">通过确保正确设置配置设置并应用攻击缓解技术，这些功能集可抵御攻击和利用。</span><span class="sxs-lookup"><span data-stu-id="2ed02-127">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

- [<span data-ttu-id="2ed02-128">基于硬件的隔离</span><span class="sxs-lookup"><span data-stu-id="2ed02-128">Hardware based isolation</span></span>](overview-hardware-based-isolation.md)
- [<span data-ttu-id="2ed02-129">应用程序控制</span><span class="sxs-lookup"><span data-stu-id="2ed02-129">Application control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [<span data-ttu-id="2ed02-130">设备控件</span><span class="sxs-lookup"><span data-stu-id="2ed02-130">Device control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [<span data-ttu-id="2ed02-131">Exploit Protection</span><span class="sxs-lookup"><span data-stu-id="2ed02-131">Exploit protection</span></span>](exploit-protection.md)
- <span data-ttu-id="2ed02-132">[网络保护](network-protection.md)[、Web 保护](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2ed02-132">[Network protection](network-protection.md), [web protection](web-protection-overview.md)</span></span>
- [<span data-ttu-id="2ed02-133">受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="2ed02-133">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="2ed02-134">网络防火墙</span><span class="sxs-lookup"><span data-stu-id="2ed02-134">Network firewall</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [<span data-ttu-id="2ed02-135">攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="2ed02-135">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

<a name="ngp"></a>

<span data-ttu-id="2ed02-136">**[下一代保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="2ed02-136">**[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="2ed02-137">为了进一步强化网络的安全外围，Microsoft Defender for Endpoint 使用旨在捕获所有类型的新兴威胁的下一代保护。</span><span class="sxs-lookup"><span data-stu-id="2ed02-137">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

- [<span data-ttu-id="2ed02-138">行为监视</span><span class="sxs-lookup"><span data-stu-id="2ed02-138">Behavior monitoring</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="2ed02-139">基于云的保护</span><span class="sxs-lookup"><span data-stu-id="2ed02-139">Cloud-based protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [<span data-ttu-id="2ed02-140">机器学习</span><span class="sxs-lookup"><span data-stu-id="2ed02-140">Machine learning</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="2ed02-141">URL 保护</span><span class="sxs-lookup"><span data-stu-id="2ed02-141">URL Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [<span data-ttu-id="2ed02-142">自动沙盒服务</span><span class="sxs-lookup"><span data-stu-id="2ed02-142">Automated sandbox service</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

<span data-ttu-id="2ed02-143">**[终结点检测和响应](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="2ed02-143">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="2ed02-144">终结点检测和响应功能已到位，以检测、调查和响应入侵尝试和主动泄露。</span><span class="sxs-lookup"><span data-stu-id="2ed02-144">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span> <span data-ttu-id="2ed02-145">借助高级搜寻，你拥有基于查询的威胁搜寻工具，可让你主动发现漏洞并创建自定义检测。</span><span class="sxs-lookup"><span data-stu-id="2ed02-145">With Advanced hunting, you have a query-based threat-hunting tool that lets your proactively find breaches and create custom detections.</span></span>

- [<span data-ttu-id="2ed02-146">警告</span><span class="sxs-lookup"><span data-stu-id="2ed02-146">Alerts</span></span>](alerts-queue.md)
- [<span data-ttu-id="2ed02-147">历史终结点数据</span><span class="sxs-lookup"><span data-stu-id="2ed02-147">Historical endpoint data</span></span>](investigate-machines.md#timeline)
- [<span data-ttu-id="2ed02-148">响应业务流程</span><span class="sxs-lookup"><span data-stu-id="2ed02-148">Response orchestration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [<span data-ttu-id="2ed02-149">取证集合</span><span class="sxs-lookup"><span data-stu-id="2ed02-149">Forensic collection</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [<span data-ttu-id="2ed02-150">威胁智能</span><span class="sxs-lookup"><span data-stu-id="2ed02-150">Threat intelligence</span></span>](threat-indicator-concepts.md)
- [<span data-ttu-id="2ed02-151">高级爆炸和分析服务</span><span class="sxs-lookup"><span data-stu-id="2ed02-151">Advanced detonation and analysis service</span></span>](respond-file-alerts.md#deep-analysis)
- [<span data-ttu-id="2ed02-152">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="2ed02-152">Advanced hunting</span></span>](advanced-hunting-overview.md)
    - [<span data-ttu-id="2ed02-153">自定义检测</span><span class="sxs-lookup"><span data-stu-id="2ed02-153">Custom detections</span></span>](overview-custom-detections.md)

<a name="ai"></a>

<span data-ttu-id="2ed02-154">**[自动调查和修复](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="2ed02-154">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="2ed02-155">除了快速响应高级攻击外，Microsoft Defender for Endpoint 还提供自动调查和修正功能，可帮助以分钟数为比例减少警报量。</span><span class="sxs-lookup"><span data-stu-id="2ed02-155">In addition to quickly responding to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span>

- [<span data-ttu-id="2ed02-156">自动调查和修复</span><span class="sxs-lookup"><span data-stu-id="2ed02-156">Automated investigation and remediation</span></span>](automated-investigations.md)
- [<span data-ttu-id="2ed02-157">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="2ed02-157">View details and results of automated investigations</span></span>](auto-investigation-action-center.md)
- [<span data-ttu-id="2ed02-158">查看和批准修正操作</span><span class="sxs-lookup"><span data-stu-id="2ed02-158">View and approve remediation actions</span></span>](manage-auto-investigation.md)

<a name="mte"></a>

<span data-ttu-id="2ed02-159">**[Microsoft 威胁专家](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="2ed02-159">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="2ed02-160">Microsoft Defender for Endpoint 的新托管威胁搜寻服务提供主动搜寻、优先顺序和其他上下文和见解。</span><span class="sxs-lookup"><span data-stu-id="2ed02-160">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights.</span></span> <span data-ttu-id="2ed02-161">Microsoft 威胁专家进一步授权安全操作 (SOC) 快速准确地识别和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="2ed02-161">Microsoft Threat Experts further empowers Security Operation Centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

- [<span data-ttu-id="2ed02-162">目标攻击通知</span><span class="sxs-lookup"><span data-stu-id="2ed02-162">Targeted attack notification</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="2ed02-163">专家按需</span><span class="sxs-lookup"><span data-stu-id="2ed02-163">Experts-on-demand</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="2ed02-164">配置 Microsoft 365 Defender 托管搜寻服务</span><span class="sxs-lookup"><span data-stu-id="2ed02-164">Configure your Microsoft 365 Defender managed hunting service</span></span>](configure-microsoft-threat-experts.md)

<a name="apis"></a>

<span data-ttu-id="2ed02-165">**[集中配置和管理、API](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="2ed02-165">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="2ed02-166">将 Microsoft Defender for Endpoint 集成到现有工作流中。</span><span class="sxs-lookup"><span data-stu-id="2ed02-166">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>
- [<span data-ttu-id="2ed02-167">载入</span><span class="sxs-lookup"><span data-stu-id="2ed02-167">Onboarding</span></span>](onboard-configure.md)
- [<span data-ttu-id="2ed02-168">API 和 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="2ed02-168">API and SIEM integration</span></span>](configure-siem.md)
- [<span data-ttu-id="2ed02-169">公开的 API</span><span class="sxs-lookup"><span data-stu-id="2ed02-169">Exposed APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="2ed02-170">基于角色的访问控制 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="2ed02-170">Role-based access control (RBAC)</span></span>](rbac.md)
- [<span data-ttu-id="2ed02-171">报告和趋势</span><span class="sxs-lookup"><span data-stu-id="2ed02-171">Reporting and trends</span></span>](threat-protection-reports.md)

<a name="integration"></a>
<span data-ttu-id="2ed02-172">**[与 Microsoft 解决方案集成](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="2ed02-172">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
 <span data-ttu-id="2ed02-173">Microsoft Defender for Endpoint 直接与各种 Microsoft 解决方案集成，包括：</span><span class="sxs-lookup"><span data-stu-id="2ed02-173">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="2ed02-174">Intune</span><span class="sxs-lookup"><span data-stu-id="2ed02-174">Intune</span></span>
- <span data-ttu-id="2ed02-175">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="2ed02-175">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="2ed02-176">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2ed02-176">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="2ed02-177">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="2ed02-177">Azure Defender</span></span>
- <span data-ttu-id="2ed02-178">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2ed02-178">Skype for Business</span></span>
- <span data-ttu-id="2ed02-179">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2ed02-179">Microsoft Cloud App Security</span></span>

<a name="mtp"></a>
<span data-ttu-id="2ed02-180">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="2ed02-180">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
 <span data-ttu-id="2ed02-181">借助 Microsoft 365 Defender，Microsoft Defender for Endpoint 和各种 Microsoft 安全解决方案形成统一的攻破前和入侵后企业防御套件，可跨终结点、标识、电子邮件和应用程序进行本机集成，以检测、阻止、调查和自动响应复杂的攻击。</span><span class="sxs-lookup"><span data-stu-id="2ed02-181">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>
