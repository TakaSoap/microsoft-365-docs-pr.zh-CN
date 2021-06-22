---
title: 设备发现常见问题
description: 查找有关设备发现的常见问题 (常见问题) 常见问题解答
keywords: 设备发现， 发现， 被动， 主动， 网络， 可见性， 服务器， 工作站， 载入， 非托管设备
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b2c0b986ef6dbb54cd34e9b4413711cd3e5f9c6d
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053151"
---
# <a name="device-discovery-frequently-asked-questions"></a><span data-ttu-id="5fc6f-104">设备发现常见问题</span><span class="sxs-lookup"><span data-stu-id="5fc6f-104">Device discovery frequently asked questions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5fc6f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5fc6f-105">**Applies to:**</span></span>
- [<span data-ttu-id="5fc6f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5fc6f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="5fc6f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fc6f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="5fc6f-108">查找有关设备发现的常见问题 (常见问题) 常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-108">Find answers to frequently asked questions (FAQs) about device discovery.</span></span>

## <a name="what-is-basic-discovery-mode"></a><span data-ttu-id="5fc6f-109">什么是基本发现模式？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-109">What is Basic discovery mode?</span></span>
<span data-ttu-id="5fc6f-110">此模式允许每个 Microsoft Defender for Endpoint 载入设备收集网络数据并发现相邻设备。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-110">This mode allows every Microsoft Defender for Endpoint onboarded device to collect network data and discover neighboring devices.</span></span> <span data-ttu-id="5fc6f-111">已载入的终结点被动收集网络中事件并从中提取设备信息。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-111">Onboarded endpoints passively collect events in the network and extract device information from them.</span></span> <span data-ttu-id="5fc6f-112">不会启动任何网络流量。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-112">No network traffic will be initiated.</span></span> <span data-ttu-id="5fc6f-113">载入的终结点只需从已载入设备看到的每一个网络流量中提取数据。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-113">Onboarded endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> <span data-ttu-id="5fc6f-114">此数据用于列出网络中非托管设备。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-114">This data used to list unmanaged devices in your network.</span></span>

## <a name="can-i-disable-basic-discovery"></a><span data-ttu-id="5fc6f-115">能否禁用基本发现？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-115">Can I disable Basic discovery?</span></span>
<span data-ttu-id="5fc6f-116">可以选择通过"高级功能"页关闭 [设备](advanced-features.md) 发现。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-116">You have the option to turn off device discovery through the [Advanced features](advanced-features.md) page.</span></span> <span data-ttu-id="5fc6f-117">但是，你将丢失网络中非托管设备的可见性。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-117">However, you will lose visibility on unmanaged devices in your network.</span></span> 

## <a name="what-is-standard-discovery-mode"></a><span data-ttu-id="5fc6f-118">什么是标准发现模式？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-118">What is Standard discovery mode?</span></span>
 <span data-ttu-id="5fc6f-119">在此模式下，载入到 Microsoft Defender for Endpoint 的终结点可以主动探测网络中观察到的设备，以丰富收集的数据 (网络流量可以忽略不计) 。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-119">In this mode endpoints onboarded to Microsoft Defender for Endpoint can actively probe observed devices in the network to enrich collected data (with negligible amount of network traffic).</span></span> <span data-ttu-id="5fc6f-120">强烈建议使用此模式生成可靠且一致的设备清单。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-120">This mode is highly recommended for building a reliable and coherent device inventory.</span></span> <span data-ttu-id="5fc6f-121">如果选择禁用此模式，并选择"基本发现模式"，可能只会获得网络中非托管终结点的有限可见性。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-121">If you choose to disable this mode, and select Basic discovery mode, you will likely only gain limited visibility of unmanaged endpoints in your network.</span></span>

## <a name="can-i-control-which-devices-perform-standard-discovery"></a><span data-ttu-id="5fc6f-122">我能否控制哪些设备执行标准发现？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-122">Can I control which devices perform Standard discovery?</span></span>
 <span data-ttu-id="5fc6f-123">你可以自定义用于执行标准发现的设备列表。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-123">You can customize the list of devices that are used to perform Standard discovery.</span></span> <span data-ttu-id="5fc6f-124">你可以在所有也支持此功能的已载入设备上启用标准发现 (当前仅 Windows 10 设备) 或者通过指定设备的设备标记选择一部分或部分设备。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-124">You can either enable Standard discovery on all the onboarded devices that also support this capability (currently Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span> <span data-ttu-id="5fc6f-125">在这种情况下，所有其他设备将配置为仅运行基本发现。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-125">In this case, all other devices will be configured to run Basic discovery only.</span></span> <span data-ttu-id="5fc6f-126">配置在设备发现设置页中提供。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-126">The configuration is available in the device discovery settings page.</span></span>

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a><span data-ttu-id="5fc6f-127">能否从设备清单列表中排除非托管设备？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-127">Can I exclude unmanaged devices from the device inventory list?</span></span>
<span data-ttu-id="5fc6f-128">是，你可以应用筛选器，从设备清单列表中排除非托管设备。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-128">Yes, you can apply filters exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="5fc6f-129">您还可以使用 API 查询上的载入状态列筛选出非托管设备。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-129">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 


## <a name="which-onboarded-devices-can-perform-discovery"></a><span data-ttu-id="5fc6f-130">哪些载入的设备可以执行发现？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-130">Which onboarded devices can perform discovery?</span></span>
 <span data-ttu-id="5fc6f-131">在版本 1809 或Windows 10上运行的已载入设备可以执行发现。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-131">Onboarded devices running on Windows 10 version 1809 or later can perform discovery.</span></span>

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a><span data-ttu-id="5fc6f-132">如果我的已载入设备连接到我的家庭网络或公共访问点，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-132">What happens if my onboarded devices is connected to my home network, or to public access point?</span></span>
 <span data-ttu-id="5fc6f-133">发现引擎区分在企业网络中接收的网络事件与企业网络外部的网络事件。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-133">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="5fc6f-134">通过在所有租户的客户端之间关联网络标识符，可以区分从专用网络和企业网络接收的事件。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-134">By correlating network identifiers across all tenant's clients, events are differentiated between ones that were received from private networks and corporate networks.</span></span> <span data-ttu-id="5fc6f-135">例如，如果网络中的大多数设备报告它们连接到了相同的网络名称，并且具有相同的默认网关和 DHCP 服务器地址，则假定此网络可能是企业网络。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-135">For example, if the majority of the devices in the network report that they are connected to the same network name, with the same default gateway and DHCP server address, it can be assumed that this network is likely a corporate network.</span></span> <span data-ttu-id="5fc6f-136">专用网络设备不会在清单中列出，并且不会主动探测器。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-136">Private network devices will not be listed in the inventory and will not be actively probed.</span></span>

## <a name="what-protocols-are-you-capturing-and-analyzing"></a><span data-ttu-id="5fc6f-137">要捕获和分析哪些协议？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-137">What protocols are you capturing and analyzing?</span></span>
 <span data-ttu-id="5fc6f-138">默认情况下， 在 Windows 10 版本 1809 或更高版本上运行的所有已载入设备正在捕获和分析以下协议：ARP、CDP、DHCP、DHCPv6、IP (标头) 、LLDP、LLMNR、mDNS、MNDP、NBNS、SSDP、TCP (标头) 、UDP (标头) 、WSD</span><span class="sxs-lookup"><span data-stu-id="5fc6f-138">By default, all onboarded devices running on Windows 10 version 1809 or later are capturing and analyzing the following protocols: ARP, CDP, DHCP, DHCPv6, IP (headers), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (headers), UDP (headers), WSD</span></span>

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a><span data-ttu-id="5fc6f-139">在标准发现中，使用哪些协议进行主动探测？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-139">Which protocols do you use for active probing in Standard discovery?</span></span>
 <span data-ttu-id="5fc6f-140">当设备配置为运行标准发现时，会使用下列协议对公开的服务进行探测：ARP、FTP、HTTP、HTTPS、ICMP、LLMNR、NBNS、RDP、SIP、SMTP、SNMP、SSH、Telnet、UPNP、WSD、SMB、NBSS、IPP、PJL、RPC、mDNS、DHCP、AFP、CrestonCIP、IphoneSync</span><span class="sxs-lookup"><span data-stu-id="5fc6f-140">When a device is configured to run Standard discovery, exposed services are being probed by using the following protocols: ARP, FTP, HTTP, HTTPS, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL, RPC, mDNS, DHCP, AFP, CrestonCIP, IphoneSync</span></span>

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a><span data-ttu-id="5fc6f-141">如何排除使用标准发现对目标进行探测？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-141">How can I exclude targets from being probed with Standard discovery?</span></span>
 <span data-ttu-id="5fc6f-142">如果网络上有些设备不应主动探测器，则还可以定义排除项列表以防止它们被扫描。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-142">If there are devices on your network which should not be actively probed, you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="5fc6f-143">配置在设备发现设置页中提供。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-143">The configuration is available in the device discovery settings page.</span></span>

## <a name="can-i-exclude-devices-from-being-discovered"></a><span data-ttu-id="5fc6f-144">能否排除发现的设备？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-144">Can I exclude devices from being discovered?</span></span>
 <span data-ttu-id="5fc6f-145">由于设备发现使用被动方法发现网络中设备，因此可以发现与企业网络中已载入设备通信的任何设备，并列在清单中。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-145">As device discovery uses passive methods to discover devices in the network, any device that communicates with your onboarded devices in the corporate network can be discovered and listed in the inventory.</span></span> <span data-ttu-id="5fc6f-146">只能将设备排除在活动探测中。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-146">You can exclude devices from active probing only.</span></span>

## <a name="how-frequent-is-the-active-probing"></a><span data-ttu-id="5fc6f-147">活动探测频率如何？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-147">How frequent is the active probing?</span></span>
 <span data-ttu-id="5fc6f-148">当每 1 到 3 周 (观察设备特征更改时) 将主动探测设备，以确保现有信息是最新的。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-148">Devices will actively be probed when changes in device characteristics are observed (every 1 to 3 weeks) to make sure the existing information is up-to-date.</span></span>

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a><span data-ttu-id="5fc6f-149">我的安全工具引发了UnicastScanner.ps1启动的扫描活动或端口扫描活动的警报，我应该做什么？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-149">My security tool raised alert on UnicastScanner.ps1 or port scanning activity initiated by it, what should I do?</span></span>
 <span data-ttu-id="5fc6f-150">活动的探测脚本由 Microsoft 签名，并且是安全的。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-150">The active probing scripts are signed by Microsoft and are safe.</span></span> <span data-ttu-id="5fc6f-151">你可以将以下路径添加到排除列表： `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`</span><span class="sxs-lookup"><span data-stu-id="5fc6f-151">You can add the following path to your exclusion list: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`</span></span>


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a><span data-ttu-id="5fc6f-152">标准发现活动探测器生成的流量量是什么？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-152">What is the amount of traffic being generated by the Standard discovery active probe?</span></span>
 <span data-ttu-id="5fc6f-153">每次探测尝试，活动探测在已载入设备和探测器设备之间可生成多达 5K 的流量</span><span class="sxs-lookup"><span data-stu-id="5fc6f-153">Active probing can generate up to 5K of traffic between the onboarded device and the probed device, every probing attempt</span></span>

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a><span data-ttu-id="5fc6f-154">为什么设备清单中的"可载入"设备与仪表板磁贴中的"可载入"设备数存在差异？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-154">Why is there a discrepancy between "can be onboarded" devices in the device inventory, and the number of "devices to onboard" in the dashboard tile?</span></span>
<span data-ttu-id="5fc6f-155">你可能会注意到，在设备清单、"载入到 Microsoft Defender for Endpoint"安全建议和"载入设备"仪表板小组件中"可以载入"下列出的设备数量之间存在差异。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-155">You may notice differences between the number of listed devices under "can be onboarded" in the device inventory, "onboard to Microsoft Defender for Endpoint" security recommendation, and "devices to onboard" dashboard widget.</span></span>

 <span data-ttu-id="5fc6f-156">安全建议和仪表板小部件适用于网络中稳定的设备;不包括临时设备、来宾设备和其他。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-156">The security recommendation and the dashboard widget are for devices that are stable in the network; excluding ephemeral devices, guest devices and others.</span></span> <span data-ttu-id="5fc6f-157">该想法是在持久性设备上推荐，这也意味着组织的总体安全分数。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-157">The idea is to recommend on persistent devices, that also imply on the overall security score of the organization.</span></span>

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a><span data-ttu-id="5fc6f-158">我能否载入找到的非托管设备？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-158">Can I onboard unmanaged devices that were found?</span></span>
 <span data-ttu-id="5fc6f-159">是。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-159">Yes.</span></span> <span data-ttu-id="5fc6f-160">网络中非托管终结点会为网络带来漏洞和风险。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-160">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="5fc6f-161">将它们载入服务可提升对它们的安全可见性。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-161">Onboarding them to the service can increase the security visibility on them.</span></span> 

## <a name="ive-noticed-that-unmanaged-device-health-state-is-always-active-why-is-that"></a><span data-ttu-id="5fc6f-162">我已注意到非托管设备运行状况状态始终为"活动"，为什么？</span><span class="sxs-lookup"><span data-stu-id="5fc6f-162">I've noticed that unmanaged device health state is always "Active", why is that?</span></span>
<span data-ttu-id="5fc6f-163">在设备清单的标准保留期内，非托管设备运行状况临时为"活动"状态，无论其实际状态如何。</span><span class="sxs-lookup"><span data-stu-id="5fc6f-163">Temporarily, unmanaged device health state will be "Active" during the standard retention period of the device inventory, regardless of their actual state.</span></span>
