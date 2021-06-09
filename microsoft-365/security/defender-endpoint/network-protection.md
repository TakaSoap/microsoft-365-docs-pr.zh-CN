---
title: 使用网络保护来帮助防止连接到错误站点
description: 通过阻止用户访问已知的恶意和可疑网络地址来保护网络
keywords: 网络保护， 攻击， 恶意网站， ip， 域， 域
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b6b664d471e238e2feb1e1aedd100c1299fc5bbe
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844258"
---
# <a name="protect-your-network"></a><span data-ttu-id="81699-104">保护你的网络</span><span class="sxs-lookup"><span data-stu-id="81699-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="81699-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="81699-105">**Applies to:**</span></span>
- [<span data-ttu-id="81699-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="81699-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="81699-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81699-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="81699-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="81699-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="81699-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="81699-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="81699-110">网络保护有助于减少基于 Internet 的事件对设备的攻击面。</span><span class="sxs-lookup"><span data-stu-id="81699-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="81699-111">它防止员工使用任何应用程序访问可能承载网络钓鱼欺诈、攻击和 Internet 上的其他恶意内容危险域。</span><span class="sxs-lookup"><span data-stu-id="81699-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="81699-112">网络保护扩展[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)以阻止所有尝试基于域或主机名连接到低信誉源 (的出站 HTTP () ) 。</span><span class="sxs-lookup"><span data-stu-id="81699-112">Network protection expands the scope of [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="81699-113">网络保护在 Windows版本 1709 Windows 10起受支持。</span><span class="sxs-lookup"><span data-stu-id="81699-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="81699-114">网络保护在其他操作系统上尚不受支持，但 Web 保护支持使用基于 Microsoft Edge 的新Chromium。</span><span class="sxs-lookup"><span data-stu-id="81699-114">Network protection is not yet supported on other operating systems, but web protection is supported using the new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="81699-115">若要了解更多信息，请参阅 [Web 保护](web-protection-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="81699-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="81699-116">网络保护将 Web 保护 [中的保护扩展到](web-protection-overview.md) 操作系统级别。</span><span class="sxs-lookup"><span data-stu-id="81699-116">Network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="81699-117">它在 Edge 中为其他受支持的浏览器和非浏览器应用程序提供 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="81699-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="81699-118">此外，当与终结点检测和响应一 (ICS 时，网络保护) 和阻止泄露[指示器。](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="81699-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="81699-119">例如，网络保护适用于你的 [自定义指示器](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="81699-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="81699-120">若要详细了解如何启用网络保护，请参阅 [启用网络保护](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="81699-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="81699-121">使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。</span><span class="sxs-lookup"><span data-stu-id="81699-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="81699-122">有关网络保护的工作原理，demo.wd.microsoft.com Microsoft Defender [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) for Endpoint 测试站点。</span><span class="sxs-lookup"><span data-stu-id="81699-122">See the Microsoft Defender for Endpoint testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="81699-123">网络保护最适合 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)，它为你提供有关 Exploit Protection 事件的详细报告，并作为警报调查方案的一部分 [进行阻止](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="81699-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="81699-124">当网络保护阻止连接时，将显示来自操作中心的通知。</span><span class="sxs-lookup"><span data-stu-id="81699-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="81699-125">安全运营团队 [可以使用](customize-attack-surface-reduction.md#customize-the-notification) 组织的详细信息和联系信息自定义通知。</span><span class="sxs-lookup"><span data-stu-id="81699-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="81699-126">此外，可以启用和自定义各个攻击面减少规则，以适合要监视的某些技术。</span><span class="sxs-lookup"><span data-stu-id="81699-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="81699-127">您还可以使用 [审核模式评估](audit-windows-defender.md) 网络保护在启用后对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="81699-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="81699-128">要求</span><span class="sxs-lookup"><span data-stu-id="81699-128">Requirements</span></span>

<span data-ttu-id="81699-129">网络保护Windows 10 专业版或Enterprise，Microsoft Defender 防病毒实时保护。</span><span class="sxs-lookup"><span data-stu-id="81699-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="81699-130">Windows 版本</span><span class="sxs-lookup"><span data-stu-id="81699-130">Windows version</span></span> | <span data-ttu-id="81699-131">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="81699-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="81699-132">Windows 10版本 1709 或更高版本</span><span class="sxs-lookup"><span data-stu-id="81699-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="81699-133">Windows服务器 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="81699-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="81699-134">[Microsoft Defender 防病毒必须启用](configure-real-time-protection-microsoft-defender-antivirus.md)实时[保护和云保护](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="81699-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="81699-135">启用服务后，可能需要配置网络或防火墙，以允许服务和设备之间的连接 (也称为终结点) 。</span><span class="sxs-lookup"><span data-stu-id="81699-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="81699-136">查看 Microsoft Defender 终结点安全中心中的网络保护事件</span><span class="sxs-lookup"><span data-stu-id="81699-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="81699-137">Microsoft Defender for Endpoint 提供事件的详细报告和阻止，作为警报调查方案的 [一部分](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="81699-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="81699-138">可以使用高级搜寻查询 Microsoft Defender 的终结点 [数据](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="81699-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="81699-139">如果你使用的是审核 [模式](audit-windows-defender.md)，可以使用高级搜寻来查看网络保护设置在启用后将如何影响你的环境。</span><span class="sxs-lookup"><span data-stu-id="81699-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="81699-140">下面是一个示例查询</span><span class="sxs-lookup"><span data-stu-id="81699-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="81699-141">在事件查看器中查看Windows保护事件</span><span class="sxs-lookup"><span data-stu-id="81699-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="81699-142">你可以查看Windows事件日志，以查看网络保护阻止访问恶意 IP 或 (或审核) IP 或域时创建的事件：</span><span class="sxs-lookup"><span data-stu-id="81699-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="81699-143">[直接复制 XML。](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="81699-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="81699-144">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="81699-144">Select **OK**.</span></span>

<span data-ttu-id="81699-145">此过程将创建一个自定义视图，该视图筛选为只显示与网络保护相关的以下事件：</span><span class="sxs-lookup"><span data-stu-id="81699-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="81699-146">事件 ID</span><span class="sxs-lookup"><span data-stu-id="81699-146">Event ID</span></span> | <span data-ttu-id="81699-147">说明</span><span class="sxs-lookup"><span data-stu-id="81699-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="81699-148">5007</span><span class="sxs-lookup"><span data-stu-id="81699-148">5007</span></span> | <span data-ttu-id="81699-149">更改设置时的事件</span><span class="sxs-lookup"><span data-stu-id="81699-149">Event when settings are changed</span></span> |
| <span data-ttu-id="81699-150">1125</span><span class="sxs-lookup"><span data-stu-id="81699-150">1125</span></span> | <span data-ttu-id="81699-151">在审核模式下触发网络保护时的事件</span><span class="sxs-lookup"><span data-stu-id="81699-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="81699-152">1126</span><span class="sxs-lookup"><span data-stu-id="81699-152">1126</span></span> | <span data-ttu-id="81699-153">在阻止模式下触发网络保护时的事件</span><span class="sxs-lookup"><span data-stu-id="81699-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="81699-154">在多Windows中运行虚拟Windows 10 企业版的注意事项</span><span class="sxs-lookup"><span data-stu-id="81699-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="81699-155">由于应用程序具有多用户Windows 10 企业版，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="81699-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="81699-156">网络保护是设备范围内的一项功能，不能面向特定的用户会话。</span><span class="sxs-lookup"><span data-stu-id="81699-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="81699-157">Web 内容筛选策略也是设备范围的。</span><span class="sxs-lookup"><span data-stu-id="81699-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="81699-158">如果需要区分用户组，请考虑创建单独的虚拟Windows池和分配。</span><span class="sxs-lookup"><span data-stu-id="81699-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="81699-159">在审核模式下测试网络保护，以在推出之前评估其行为。</span><span class="sxs-lookup"><span data-stu-id="81699-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="81699-160">如果您具有大量用户或大量多用户会话，请考虑调整部署大小。</span><span class="sxs-lookup"><span data-stu-id="81699-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="81699-161">网络保护的备用选项</span><span class="sxs-lookup"><span data-stu-id="81699-161">Alternative option for network protection</span></span>

<span data-ttu-id="81699-162">对于Windows 10 企业版会话 1909 及之后（在 Azure 上的 Windows 虚拟桌面中使用）中，可以使用以下方法启用 Microsoft Edge 的网络保护：</span><span class="sxs-lookup"><span data-stu-id="81699-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="81699-163">使用 ["打开网络保护](enable-network-protection.md) "并按照说明应用策略。</span><span class="sxs-lookup"><span data-stu-id="81699-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="81699-164">执行以下 PowerShell 命令： `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="81699-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="81699-165">网络保护疑难解答</span><span class="sxs-lookup"><span data-stu-id="81699-165">Network protection troubleshooting</span></span>

<span data-ttu-id="81699-166">由于网络保护运行的环境，Microsoft 可能无法检测操作系统代理设置。</span><span class="sxs-lookup"><span data-stu-id="81699-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="81699-167">在某些情况下，网络保护客户端无法访问云服务。</span><span class="sxs-lookup"><span data-stu-id="81699-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="81699-168">若要解决连接问题，具有 E5 许可证的客户应配置以下 Defender 注册表项之一：</span><span class="sxs-lookup"><span data-stu-id="81699-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="81699-169">相关文章</span><span class="sxs-lookup"><span data-stu-id="81699-169">Related articles</span></span>

- <span data-ttu-id="81699-170">[评估网络保护](evaluate-network-protection.md) |执行一个快速方案，演示功能的工作方式以及通常会创建哪些事件。</span><span class="sxs-lookup"><span data-stu-id="81699-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="81699-171">[启用网络保护](enable-network-protection.md) |使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。</span><span class="sxs-lookup"><span data-stu-id="81699-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
