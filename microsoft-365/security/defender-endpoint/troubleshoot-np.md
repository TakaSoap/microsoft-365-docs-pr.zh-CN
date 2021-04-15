---
title: 网络保护问题疑难解答
description: 用于解决 Microsoft Defender for Endpoint 中的网络保护问题的资源和示例代码。
keywords: 疑难解答， 错误， 修复， windows defender eg， asr， 规则， hips， 疑难解答， 审核， 排除， 误报， 损坏， 阻止， microsoft defender 终结点， microsoft defender 高级威胁防护
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 9efc42441c2cb30f35abf658071088f7f7bbaf00
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760094"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="74b3e-104">网络保护疑难解答</span><span class="sxs-lookup"><span data-stu-id="74b3e-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74b3e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="74b3e-105">**Applies to:**</span></span>
- [<span data-ttu-id="74b3e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="74b3e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="74b3e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74b3e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="74b3e-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="74b3e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="74b3e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="74b3e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="74b3e-110">使用网络 [保护时](network-protection.md) ，可能会遇到问题，例如：</span><span class="sxs-lookup"><span data-stu-id="74b3e-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="74b3e-111">网络保护阻止安全网站 (误报) </span><span class="sxs-lookup"><span data-stu-id="74b3e-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="74b3e-112">网络保护无法阻止可疑或已知的恶意网站 (漏报) </span><span class="sxs-lookup"><span data-stu-id="74b3e-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="74b3e-113">解决这些问题有四个步骤：</span><span class="sxs-lookup"><span data-stu-id="74b3e-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="74b3e-114">确认先决条件</span><span class="sxs-lookup"><span data-stu-id="74b3e-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="74b3e-115">使用审核模式测试规则</span><span class="sxs-lookup"><span data-stu-id="74b3e-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="74b3e-116">为指定的误报规则 (排除项) </span><span class="sxs-lookup"><span data-stu-id="74b3e-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="74b3e-117">提交支持日志</span><span class="sxs-lookup"><span data-stu-id="74b3e-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="74b3e-118">确认先决条件</span><span class="sxs-lookup"><span data-stu-id="74b3e-118">Confirm prerequisites</span></span>

<span data-ttu-id="74b3e-119">网络保护仅适用于具有以下条件的设备：</span><span class="sxs-lookup"><span data-stu-id="74b3e-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="74b3e-120">终结点运行的是 Windows 10 专业版或企业版版本 1709 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="74b3e-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="74b3e-121">终结点使用 Microsoft Defender 防病毒作为唯一的防病毒保护应用。</span><span class="sxs-lookup"><span data-stu-id="74b3e-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="74b3e-122">[查看使用非 Microsoft 防病毒解决方案时会发生什么情况](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="74b3e-122">[See what happens when you are using a non-Microsoft antivirus solution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="74b3e-123">[实时保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) 已启用。</span><span class="sxs-lookup"><span data-stu-id="74b3e-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="74b3e-124">[云提供的保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 已启用。</span><span class="sxs-lookup"><span data-stu-id="74b3e-124">[Cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="74b3e-125">审核模式未启用。</span><span class="sxs-lookup"><span data-stu-id="74b3e-125">Audit mode is not enabled.</span></span> <span data-ttu-id="74b3e-126">使用 [组策略](enable-network-protection.md#group-policy)将规则设置为禁用 (值 **：0**) 。</span><span class="sxs-lookup"><span data-stu-id="74b3e-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="74b3e-127">使用审核模式</span><span class="sxs-lookup"><span data-stu-id="74b3e-127">Use audit mode</span></span>

<span data-ttu-id="74b3e-128">可以在审核模式下启用网络保护，然后访问我们创建的演示该功能的网站。</span><span class="sxs-lookup"><span data-stu-id="74b3e-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="74b3e-129">网络保护将允许所有网站连接，但会记录一个事件，以指示启用网络保护后可能阻止的任何连接。</span><span class="sxs-lookup"><span data-stu-id="74b3e-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="74b3e-130">将网络保护设置为 **审核模式**。</span><span class="sxs-lookup"><span data-stu-id="74b3e-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="74b3e-131">执行导致问题的连接活动 (例如，尝试访问站点，或者连接到您这样做或不希望阻止访问的 IP) 。</span><span class="sxs-lookup"><span data-stu-id="74b3e-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="74b3e-132">[查看网络保护事件](network-protection.md#review-network-protection-events-in-windows-event-viewer) 日志，以查看如果该功能已设置为"已启用"，该功能是否阻止 **了连接**。</span><span class="sxs-lookup"><span data-stu-id="74b3e-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="74b3e-133">如果网络保护未阻止预期应该阻止的连接，请启用该功能。</span><span class="sxs-lookup"><span data-stu-id="74b3e-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="74b3e-134">报告误报或漏报</span><span class="sxs-lookup"><span data-stu-id="74b3e-134">Report a false positive or false negative</span></span>

<span data-ttu-id="74b3e-135">如果已使用演示网站和审核模式测试了该功能，并且网络保护适用于预配置的方案，但无法按预期为特定连接工作，请使用 [基于 Windows Defender](https://www.microsoft.com/wdsi/filesubmission) 安全智能 Web 的提交表单报告网络保护的漏报或误报。</span><span class="sxs-lookup"><span data-stu-id="74b3e-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="74b3e-136">使用 E5 订阅，还可以 [提供指向任何关联警报的链接](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="74b3e-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="74b3e-137">请参阅在 Microsoft Defender for Endpoint 中解决 [误报/负数](defender-endpoint-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="74b3e-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="74b3e-138">从网络保护范围排除网站</span><span class="sxs-lookup"><span data-stu-id="74b3e-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="74b3e-139">若要允许被阻止的网站 (误报) ，请将其 URL 添加到 [受信任网站列表中](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)。</span><span class="sxs-lookup"><span data-stu-id="74b3e-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="74b3e-140">此列表中的 Web 资源绕过网络保护检查。</span><span class="sxs-lookup"><span data-stu-id="74b3e-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="74b3e-141">收集文件提交的诊断数据</span><span class="sxs-lookup"><span data-stu-id="74b3e-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="74b3e-142">当你报告网络保护问题时，会要求你收集和提交诊断数据，Microsoft 支持和工程团队可以使用这些数据来帮助解决问题。</span><span class="sxs-lookup"><span data-stu-id="74b3e-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="74b3e-143">打开提升的命令提示符并更改为Windows Defender目录：</span><span class="sxs-lookup"><span data-stu-id="74b3e-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="74b3e-144">运行此命令以生成诊断日志：</span><span class="sxs-lookup"><span data-stu-id="74b3e-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="74b3e-145">将文件附加到提交表单。</span><span class="sxs-lookup"><span data-stu-id="74b3e-145">Attach the file to the submission form.</span></span> <span data-ttu-id="74b3e-146">默认情况下，诊断日志保存在 中 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。</span><span class="sxs-lookup"><span data-stu-id="74b3e-146">By default, diagnostic logs are saved at `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a><span data-ttu-id="74b3e-147">解决 E5 客户 (网络保护服务的连接) </span><span class="sxs-lookup"><span data-stu-id="74b3e-147">Resolve connectivity issues with network protection (for E5 customers)</span></span>

<span data-ttu-id="74b3e-148">由于网络保护运行的环境，Microsoft 无法查看操作系统代理设置。</span><span class="sxs-lookup"><span data-stu-id="74b3e-148">Due to the environment where network protection runs, Microsoft is unable to see your operating system proxy settings.</span></span> <span data-ttu-id="74b3e-149">在某些情况下，网络保护客户端无法访问云服务。</span><span class="sxs-lookup"><span data-stu-id="74b3e-149">In some cases, network protection clients are unable to reach the cloud service.</span></span> <span data-ttu-id="74b3e-150">要解决网络保护的连接问题，请配置以下注册表项之一，以便网络保护能够识别代理配置：</span><span class="sxs-lookup"><span data-stu-id="74b3e-150">To resolve connectivity issues with network protection, configure one of the following registry keys so that network protection becomes aware of the proxy configuration:</span></span>

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

<span data-ttu-id="74b3e-151">---OR---</span><span class="sxs-lookup"><span data-stu-id="74b3e-151">---OR---</span></span>


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

<span data-ttu-id="74b3e-152">可以使用 PowerShell、Microsoft Endpoint Manager 或组策略配置注册表项。</span><span class="sxs-lookup"><span data-stu-id="74b3e-152">You can configure the registry key by using PowerShell, Microsoft Endpoint Manager, or Group Policy.</span></span> <span data-ttu-id="74b3e-153">以下是一些可帮助的资源：</span><span class="sxs-lookup"><span data-stu-id="74b3e-153">Here are some resources to help:</span></span>
- [<span data-ttu-id="74b3e-154">使用注册表项</span><span class="sxs-lookup"><span data-stu-id="74b3e-154">Working with Registry Keys</span></span>](/powershell/scripting/samples/working-with-registry-keys)
- [<span data-ttu-id="74b3e-155">配置 Endpoint Protection 的自定义客户端设置</span><span class="sxs-lookup"><span data-stu-id="74b3e-155">Configure custom client settings for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [<span data-ttu-id="74b3e-156">使用组策略设置管理 Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="74b3e-156">Use Group Policy settings to manage Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a><span data-ttu-id="74b3e-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74b3e-157">See also</span></span>

- [<span data-ttu-id="74b3e-158">网络保护</span><span class="sxs-lookup"><span data-stu-id="74b3e-158">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="74b3e-159">网络保护功能评估</span><span class="sxs-lookup"><span data-stu-id="74b3e-159">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="74b3e-160">启用网络保护</span><span class="sxs-lookup"><span data-stu-id="74b3e-160">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="74b3e-161">在 Defender for Endpoint 中解决误报/负数</span><span class="sxs-lookup"><span data-stu-id="74b3e-161">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
