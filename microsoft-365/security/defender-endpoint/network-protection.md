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
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: be98bf810d00b6e39ba9d2674604a9fd2128a8cc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198645"
---
# <a name="protect-your-network"></a><span data-ttu-id="93610-104">保护网络</span><span class="sxs-lookup"><span data-stu-id="93610-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="93610-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="93610-105">**Applies to:**</span></span>
- [<span data-ttu-id="93610-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="93610-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="93610-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93610-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="93610-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="93610-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="93610-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="93610-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="93610-110">网络保护有助于减少基于 Internet 的事件对设备的攻击面。</span><span class="sxs-lookup"><span data-stu-id="93610-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="93610-111">它防止员工使用任何应用程序访问可能承载网络钓鱼欺诈、攻击和 Internet 上的其他恶意内容危险域。</span><span class="sxs-lookup"><span data-stu-id="93610-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="93610-112">网络保护扩展了 Microsoft [Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 的范围，以阻止所有基于域或主机名 (尝试连接到低信誉源 (的出站 HTTP) ) 。</span><span class="sxs-lookup"><span data-stu-id="93610-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="93610-113">从 Windows 10 版本 1709 开始，Windows 支持网络保护。</span><span class="sxs-lookup"><span data-stu-id="93610-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> 

<span data-ttu-id="93610-114">若要详细了解如何启用网络保护，请参阅 [启用网络保护](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="93610-114">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="93610-115">使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。</span><span class="sxs-lookup"><span data-stu-id="93610-115">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="93610-116">有关网络保护的工作原理 [，demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Microsoft Defender ATP 测试站点。</span><span class="sxs-lookup"><span data-stu-id="93610-116">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="93610-117">网络保护最适合 [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)，它为你提供有关 Exploit Protection 事件的详细报告，并作为警报调查方案的一部分 [进行阻止](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)。</span><span class="sxs-lookup"><span data-stu-id="93610-117">Network protection works best with [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="93610-118">当网络保护阻止连接时，将显示来自操作中心的通知。</span><span class="sxs-lookup"><span data-stu-id="93610-118">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="93610-119">安全运营团队 [可以使用](customize-attack-surface-reduction.md#customize-the-notification) 组织的详细信息和联系信息自定义通知。</span><span class="sxs-lookup"><span data-stu-id="93610-119">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="93610-120">此外，可以启用和自定义各个攻击面减少规则，以适合要监视的某些技术。</span><span class="sxs-lookup"><span data-stu-id="93610-120">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="93610-121">您还可以使用 [审核模式评估](audit-windows-defender.md) 网络保护在启用后对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="93610-121">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="93610-122">要求</span><span class="sxs-lookup"><span data-stu-id="93610-122">Requirements</span></span>

<span data-ttu-id="93610-123">网络保护需要 Windows 10 专业版或企业版以及 Microsoft Defender 防病毒实时保护。</span><span class="sxs-lookup"><span data-stu-id="93610-123">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="93610-124">Windows 版本</span><span class="sxs-lookup"><span data-stu-id="93610-124">Windows version</span></span> | <span data-ttu-id="93610-125">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="93610-125">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="93610-126">Windows 10 版本 1709 或更高版本</span><span class="sxs-lookup"><span data-stu-id="93610-126">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="93610-127">Windows Server 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="93610-127">Windows Server 1803 or later</span></span> | <span data-ttu-id="93610-128">[必须启用 Microsoft Defender 防病毒实时](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md)[保护和云保护](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="93610-128">[Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="93610-129">启用服务后，可能需要配置网络或防火墙，以允许服务和设备之间的连接 (也称为终结点) 。</span><span class="sxs-lookup"><span data-stu-id="93610-129">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- <span data-ttu-id="93610-130">.smartscreen.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="93610-130">.smartscreen.microsoft.com</span></span>
- <span data-ttu-id="93610-131">.smartscreen-prod.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="93610-131">.smartscreen-prod.microsoft.com</span></span>

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="93610-132">查看 Microsoft Defender 终结点安全中心中的网络保护事件</span><span class="sxs-lookup"><span data-stu-id="93610-132">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="93610-133">Microsoft Defender for Endpoint 提供事件的详细报告和阻止，作为警报调查方案的 [一部分](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)。</span><span class="sxs-lookup"><span data-stu-id="93610-133">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="93610-134">可以使用高级搜寻查询 Microsoft Defender 的终结点 [数据](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="93610-134">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="93610-135">如果你使用的是审核 [模式](audit-windows-defender.md)，可以使用高级搜寻来查看网络保护设置在启用后将如何影响你的环境。</span><span class="sxs-lookup"><span data-stu-id="93610-135">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="93610-136">下面是一个示例查询</span><span class="sxs-lookup"><span data-stu-id="93610-136">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="93610-137">在 Windows 事件查看器中查看网络保护事件</span><span class="sxs-lookup"><span data-stu-id="93610-137">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="93610-138">你可以查看 Windows 事件日志以查看网络保护阻止访问恶意 IP 或域 (或审核) IP 或域时创建的事件：</span><span class="sxs-lookup"><span data-stu-id="93610-138">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="93610-139">[直接复制 XML。](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="93610-139">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="93610-140">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="93610-140">Select **OK**.</span></span>

<span data-ttu-id="93610-141">此过程将创建一个自定义视图，该视图筛选为只显示与网络保护相关的以下事件：</span><span class="sxs-lookup"><span data-stu-id="93610-141">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="93610-142">事件 ID</span><span class="sxs-lookup"><span data-stu-id="93610-142">Event ID</span></span> | <span data-ttu-id="93610-143">说明</span><span class="sxs-lookup"><span data-stu-id="93610-143">Description</span></span> |
|:---|:---|
| <span data-ttu-id="93610-144">5007</span><span class="sxs-lookup"><span data-stu-id="93610-144">5007</span></span> | <span data-ttu-id="93610-145">更改设置时的事件</span><span class="sxs-lookup"><span data-stu-id="93610-145">Event when settings are changed</span></span> |
| <span data-ttu-id="93610-146">1125</span><span class="sxs-lookup"><span data-stu-id="93610-146">1125</span></span> | <span data-ttu-id="93610-147">在审核模式下触发网络保护时的事件</span><span class="sxs-lookup"><span data-stu-id="93610-147">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="93610-148">1126</span><span class="sxs-lookup"><span data-stu-id="93610-148">1126</span></span> | <span data-ttu-id="93610-149">在阻止模式下触发网络保护时的事件</span><span class="sxs-lookup"><span data-stu-id="93610-149">Event when network protection fires in block mode</span></span> |

## <a name="related-articles"></a><span data-ttu-id="93610-150">相关文章</span><span class="sxs-lookup"><span data-stu-id="93610-150">Related articles</span></span>

- <span data-ttu-id="93610-151">[评估网络保护](evaluate-network-protection.md) |执行一个快速方案，演示功能的工作方式以及通常会创建哪些事件。</span><span class="sxs-lookup"><span data-stu-id="93610-151">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="93610-152">[启用网络保护](enable-network-protection.md) |使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。</span><span class="sxs-lookup"><span data-stu-id="93610-152">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
