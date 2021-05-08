---
title: 设备发现概述
description: 了解如何在 Microsoft 365 Defender 中利用终结点发现查找网络中非托管设备
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
ms.openlocfilehash: 2dee1193e9f852e66df324927bf38d37d736d251
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245944"
---
# <a name="device-discovery-overview"></a><span data-ttu-id="912f6-104">设备发现概述</span><span class="sxs-lookup"><span data-stu-id="912f6-104">Device discovery overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="912f6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="912f6-105">**Applies to:**</span></span>
- [<span data-ttu-id="912f6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="912f6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="912f6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="912f6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="912f6-108">保护环境需要清点网络中设备。</span><span class="sxs-lookup"><span data-stu-id="912f6-108">Protecting your environment requires taking inventory of the devices that are in your network.</span></span> <span data-ttu-id="912f6-109">但是，网络中映射设备的成本通常很高、具有挑战性且耗时。</span><span class="sxs-lookup"><span data-stu-id="912f6-109">However, mapping devices in a network can often be expensive, challenging, and time-consuming.</span></span> 

<span data-ttu-id="912f6-110">Microsoft Defender for Endpoint 提供设备发现功能，可帮助你查找连接到公司网络的非托管设备，而无需额外的设备或繁琐的过程更改。</span><span class="sxs-lookup"><span data-stu-id="912f6-110">Microsoft Defender for Endpoint provides a device discovery capability that helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span>


<span data-ttu-id="912f6-111">设备发现功能允许你：</span><span class="sxs-lookup"><span data-stu-id="912f6-111">The device discovery capability allows you to:</span></span>

- <span data-ttu-id="912f6-112">**发现连接到企业网络的企业终结点**</span><span class="sxs-lookup"><span data-stu-id="912f6-112">**Discover enterprise endpoints connected to your corporate network**</span></span> <br>
<span data-ttu-id="912f6-113">使用基本或标准发现选项，你可以发现尚未载入到 Microsoft Defender for Endpoint 的工作站、服务器和移动终结点。</span><span class="sxs-lookup"><span data-stu-id="912f6-113">Using either basic or standard discovery options, you can discover workstations, servers, and mobile endpoints that are not yet onboarded to Microsoft Defender for Endpoint.</span></span>  

- <span data-ttu-id="912f6-114">**载入发现的终结点**</span><span class="sxs-lookup"><span data-stu-id="912f6-114">**Onboard discovered endpoints**</span></span><br>
<span data-ttu-id="912f6-115">网络中非托管终结点会为网络带来漏洞和风险。</span><span class="sxs-lookup"><span data-stu-id="912f6-115">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="912f6-116">将它们载入服务可提升对它们的安全可见性。</span><span class="sxs-lookup"><span data-stu-id="912f6-116">Onboarding them to the service can increase the security visibility on them.</span></span> 

<span data-ttu-id="912f6-117">结合此功能，将设备载入 Microsoft Defender for Endpoint 的新安全建议将作为现有威胁和漏洞管理体验的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="912f6-117">In conjunction with this capability, a new security recommendation to onboard devices to Microsoft Defender for Endpoint will be available as part of the existing Threat and Vulnerability Management experience.</span></span>



## <a name="discovery-methods"></a><span data-ttu-id="912f6-118">发现方法</span><span class="sxs-lookup"><span data-stu-id="912f6-118">Discovery methods</span></span>
<span data-ttu-id="912f6-119">有两种发现模式：</span><span class="sxs-lookup"><span data-stu-id="912f6-119">There are two modes of discovery:</span></span> 

-   <span data-ttu-id="912f6-120">基本发现</span><span class="sxs-lookup"><span data-stu-id="912f6-120">Basic discovery</span></span> 
-   <span data-ttu-id="912f6-121">标准发现 (推荐) </span><span class="sxs-lookup"><span data-stu-id="912f6-121">Standard discovery (recommended)</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="912f6-122">发现设置为基本模式。</span><span class="sxs-lookup"><span data-stu-id="912f6-122">Discovery is set to basic mode.</span></span> <span data-ttu-id="912f6-123">你可以选择通过设置页保留此配置。</span><span class="sxs-lookup"><span data-stu-id="912f6-123">You can choose to retain this configuration through the settings page.</span></span> <span data-ttu-id="912f6-124">标准发现将是从 2021 年 5 月 10 日开始的所有预览客户的默认模式 - 除非在此日期之前通过设置页面进行了修改。</span><span class="sxs-lookup"><span data-stu-id="912f6-124">Standard discovery will be the default mode for all preview customers starting May 10, 2021 - unless modified through the settings page before this date.</span></span>

### <a name="basic-discovery"></a><span data-ttu-id="912f6-125">基本发现</span><span class="sxs-lookup"><span data-stu-id="912f6-125">Basic discovery</span></span> 

<span data-ttu-id="912f6-126">在此模式中，终结点将被动收集网络中事件并从中提取设备信息。</span><span class="sxs-lookup"><span data-stu-id="912f6-126">In this mode, endpoints will passively collect events in your network and extract device information from them.</span></span> <span data-ttu-id="912f6-127">基本发现使用SenseNDR.exe二进制进行被动网络数据收集，并且不会启动任何网络流量。</span><span class="sxs-lookup"><span data-stu-id="912f6-127">Basic discovery uses the SenseNDR.exe binary for passive network data collection and no network traffic will be initiated.</span></span> <span data-ttu-id="912f6-128">终结点只需从载入的设备看到的每一个网络流量中提取数据。</span><span class="sxs-lookup"><span data-stu-id="912f6-128">Endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> 

### <a name="standard-discovery"></a><span data-ttu-id="912f6-129">标准发现</span><span class="sxs-lookup"><span data-stu-id="912f6-129">Standard discovery</span></span> 

<span data-ttu-id="912f6-130">此模式允许终结点主动探测网络中观测到的设备，以丰富收集的数据 -帮助你构建可靠且一致的设备清单。</span><span class="sxs-lookup"><span data-stu-id="912f6-130">This mode allows endpoints to actively probe observed devices in the network to enrich collected data - helping you build a reliable and coherent device inventory.</span></span> <span data-ttu-id="912f6-131">标准模式使用智能、主动探测来发现有关观测到的设备详细信息，以丰富现有设备信息。</span><span class="sxs-lookup"><span data-stu-id="912f6-131">Standard mode uses smart, active probing to discover even more information about observed devices to enrich existing device information.</span></span>  

<span data-ttu-id="912f6-132">启用标准模式后，组织中网络监视工具可能会观察到由发现传感器生成的最少且可以忽略不计的网络活动。</span><span class="sxs-lookup"><span data-stu-id="912f6-132">When Standard mode is enabled, minimal and negligible network activity generated by the discovery sensor might be observed by network monitoring tools in your organization.</span></span>  

 <span data-ttu-id="912f6-133">如果选择不启用此模式，将仅获取网络中非托管终结点的有限可见性。</span><span class="sxs-lookup"><span data-stu-id="912f6-133">If you choose not to enable this mode, you will only gain limited visibility of unmanaged endpoints in your network.</span></span>

<span data-ttu-id="912f6-134">标准发现使用各种 PowerShell 脚本主动探测网络中设备。</span><span class="sxs-lookup"><span data-stu-id="912f6-134">Standard discovery uses various PowerShell scripts to actively probe devices in the network.</span></span> <span data-ttu-id="912f6-135">这些 PowerShell 脚本由 Microsoft 签名，从以下位置执行 `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` ：。</span><span class="sxs-lookup"><span data-stu-id="912f6-135">Those PowerShell scripts are Microsoft signed and are executed from the following location: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`.</span></span> <span data-ttu-id="912f6-136">例如，`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`。</span><span class="sxs-lookup"><span data-stu-id="912f6-136">For example, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span></span>

<span data-ttu-id="912f6-137">你可以更改和自定义发现设置，有关详细信息，请参阅配置 [设备发现](configure-device-discovery.md)。</span><span class="sxs-lookup"><span data-stu-id="912f6-137">You can change and customize your discovery settings, for more information see [Configure device discovery](configure-device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="912f6-138">发现引擎区分在企业网络中接收的网络事件与企业网络外部的网络事件。</span><span class="sxs-lookup"><span data-stu-id="912f6-138">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="912f6-139">未连接到公司网络的设备不会在设备清单中发现或列出。</span><span class="sxs-lookup"><span data-stu-id="912f6-139">Devices that are not connected to corporate networks will not be discovered or listed in the device inventory.</span></span> 



## <a name="device-inventory"></a><span data-ttu-id="912f6-140">设备清点</span><span class="sxs-lookup"><span data-stu-id="912f6-140">Device Inventory</span></span> 
<span data-ttu-id="912f6-141">已发现但尚未由 Microsoft Defender for Endpoint 载入并保护的设备将在"终结点"选项卡内的"设备清单"中列出。你现在可以在设备清单列表中使用名为载入状态的新筛选器，该筛选器可以具有以下任何值：</span><span class="sxs-lookup"><span data-stu-id="912f6-141">Devices that have been discovered but have not yet been onboarded and secured by Microsoft Defender for Endpoint will be listed in Device Inventory within the Endpoints tab. You can now use a new filter in the device inventory list called Onboarding status which can have any of the following values:</span></span>

- <span data-ttu-id="912f6-142">已载入 – 终结点已载入到 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="912f6-142">Onboarded – The endpoint is onboarded to Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="912f6-143">可以载入 – 终结点已发现在网络中，操作系统被标识为 Microsoft Defender for Endpoint 支持的操作系统，但当前尚未载入。</span><span class="sxs-lookup"><span data-stu-id="912f6-143">Can be onboarded – The endpoint was discovered in the network and the Operating System was identified as one that is supported by Microsoft Defender for Endpoint, but it is not currently onboarded.</span></span> <span data-ttu-id="912f6-144">我们强烈建议载入这些设备。</span><span class="sxs-lookup"><span data-stu-id="912f6-144">We highly recommend onboarding these devices.</span></span>
- <span data-ttu-id="912f6-145">不受支持 – 终结点已发现在网络中，但不受 Microsoft Defender for Endpoint 支持。</span><span class="sxs-lookup"><span data-stu-id="912f6-145">Unsupported – The endpoint was discovered in the network but is not supported by Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="912f6-146">信息不足 – 系统无法确定设备的可支持性。</span><span class="sxs-lookup"><span data-stu-id="912f6-146">Insufficient info – The system could not determine the supportability of the device.</span></span> <span data-ttu-id="912f6-147">在网络中更多设备上启用标准发现可以丰富发现的属性。</span><span class="sxs-lookup"><span data-stu-id="912f6-147">Enabling standard discovery on more devices in the network can enrich the discovered attributes.</span></span> 
 

![设备清单仪表板的图像](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> <span data-ttu-id="912f6-149">你始终可以应用筛选器以从设备清单列表中排除非托管设备。</span><span class="sxs-lookup"><span data-stu-id="912f6-149">You can always apply filters to exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="912f6-150">您还可以使用 API 查询上的载入状态列筛选出非托管设备。</span><span class="sxs-lookup"><span data-stu-id="912f6-150">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 

## <a name="vulnerability-assessment-on-discovered-devices"></a><span data-ttu-id="912f6-151">已发现设备的漏洞评估</span><span class="sxs-lookup"><span data-stu-id="912f6-151">Vulnerability assessment on discovered devices</span></span>
<span data-ttu-id="912f6-152">设备上以及网络中发现的其他非托管设备的漏洞和风险是"安全 推荐"下当前 TVM 流的一部分，在门户的实体页面中表示。</span><span class="sxs-lookup"><span data-stu-id="912f6-152">Vulnerabilities and risks on your devices as well as other discovered unmanaged devices in the network are part of the current TVM flows under "Security Recommendations" and represented in entity pages across the portal.</span></span> <span data-ttu-id="912f6-153">搜索与"SSH"相关的安全建议，以查找与非托管和托管设备相关的 SSH 漏洞。</span><span class="sxs-lookup"><span data-stu-id="912f6-153">Search for "SSH" related security recommendations to find SSH vulnerabilities that are related for unmanaged and managed devices.</span></span> 

![安全建议仪表板的图像](images/1156c82ffadd356ce329d1cf551e806c.png)  

## <a name="use-advanced-hunting-on-discovered-devices"></a><span data-ttu-id="912f6-155">在发现的设备上使用高级搜寻</span><span class="sxs-lookup"><span data-stu-id="912f6-155">Use Advanced Hunting on discovered devices</span></span>
<span data-ttu-id="912f6-156">可以使用高级搜寻查询了解发现的设备的可见性。</span><span class="sxs-lookup"><span data-stu-id="912f6-156">You can use Advanced Hunting queries to gain visibility on discovered devices.</span></span>
<span data-ttu-id="912f6-157">在 DeviceInfo 表中查找有关发现的终结点的详细信息，或在 DeviceNetworkInfo 表中查找有关这些设备的网络相关信息。</span><span class="sxs-lookup"><span data-stu-id="912f6-157">Find details about discovered Endpoints in the DeviceInfo table, or network-related information about those devices in the DeviceNetworkInfo table.</span></span>
  

![高级搜寻使用的图像](images/f48ba1779eddee9872f167453c24e5c9.png)


<span data-ttu-id="912f6-159">设备发现将适用于终结点载入设备的 Microsoft Defender 用作网络数据源，将活动属性化为未载入的设备。</span><span class="sxs-lookup"><span data-stu-id="912f6-159">Device discovery leverages Microsoft Defender for Endpoint onboarded devices as a network data source to attribute activities to non-onboarded devices.</span></span> <span data-ttu-id="912f6-160">这意味着，如果 Microsoft Defender for Endpoint 已载入设备与非载入设备通信，则未载入的设备上的活动可以在时间线上和通过高级搜寻 DeviceNetworkEvents 表查看。</span><span class="sxs-lookup"><span data-stu-id="912f6-160">This means that if a Microsoft Defender for Endpoint onboarded device communicated with a non-onboarded device, activities on the non-onboarded device can be seen on the timeline and through the Advanced hunting DeviceNetworkEvents table.</span></span> 



<span data-ttu-id="912f6-161">新事件是基于连接的传输控制 (TCP) ，并且适合当前的 DeviceNetworkEvents 方案。</span><span class="sxs-lookup"><span data-stu-id="912f6-161">New events are Transmission Control Protocol (TCP) connections-based and will fit to the current DeviceNetworkEvents scheme.</span></span> <span data-ttu-id="912f6-162">从启用了非 Microsoft Defender for Endpoint 的设备进入启用终结点的 Microsoft Defender 设备的 TCP。</span><span class="sxs-lookup"><span data-stu-id="912f6-162">TCP ingress to the Microsoft Defender for Endpoint enabled device from a non-Microsoft Defender for Endpoint enabled.</span></span>  

<span data-ttu-id="912f6-163">还添加了以下操作类型：</span><span class="sxs-lookup"><span data-stu-id="912f6-163">The following action types have also been added:</span></span>  

- <span data-ttu-id="912f6-164">ConnectionAttempt - 尝试建立 TCP 连接 (同步) </span><span class="sxs-lookup"><span data-stu-id="912f6-164">ConnectionAttempt - An attempt to establish a TCP connection (syn)</span></span>  
- <span data-ttu-id="912f6-165">ConnectionAcknowledged - 确认已接受 syn\ack (TCP) </span><span class="sxs-lookup"><span data-stu-id="912f6-165">ConnectionAcknowledged - An acknowledgment that a TCP connection was accepted (syn\ack)</span></span>  

<span data-ttu-id="912f6-166">您可以尝试此示例查询：</span><span class="sxs-lookup"><span data-stu-id="912f6-166">You can try this example query:</span></span>  

```
DeviceNetworkEvents  
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"  
| take 10  
```


## <a name="changed-behavior"></a><span data-ttu-id="912f6-167">已更改行为</span><span class="sxs-lookup"><span data-stu-id="912f6-167">Changed behavior</span></span>
<span data-ttu-id="912f6-168">以下部分列出了启用此功能后，你将在 Microsoft Defender for Endpoint 和/Microsoft 365安全中心中观察到的更改。</span><span class="sxs-lookup"><span data-stu-id="912f6-168">The following section lists the changes you'll observe in Microsoft Defender for Endpoint and/or Microsoft 365 Security Center when this capability is enabled.</span></span> 
 
1.  <span data-ttu-id="912f6-169">未载入到 Microsoft Defender 到终结点的设备应显示在设备清单、高级搜寻和 API 查询中。</span><span class="sxs-lookup"><span data-stu-id="912f6-169">Devices that are not onboarded to Microsoft Defender to Endpoint are expected to appear in the device inventory, advanced hunting, and API queries.</span></span> <span data-ttu-id="912f6-170">这可能会显著增加查询结果的大小。</span><span class="sxs-lookup"><span data-stu-id="912f6-170">This may significantly increase the size of query results.</span></span> 
    1. <span data-ttu-id="912f6-171">高级搜寻中的"DeviceInfo"和"DeviceNetworkInfo"表现在将保留发现的设备。</span><span class="sxs-lookup"><span data-stu-id="912f6-171">"DeviceInfo" and "DeviceNetworkInfo" tables in Advanced Hunting will now hold discovered device.</span></span> <span data-ttu-id="912f6-172">可以使用"OnboardingStatus"属性筛选出这些设备。</span><span class="sxs-lookup"><span data-stu-id="912f6-172">You can filter out those devices by using “OnboardingStatus” attribute.</span></span>

    2. <span data-ttu-id="912f6-173">发现的设备应显示在流式 API 查询结果中。</span><span class="sxs-lookup"><span data-stu-id="912f6-173">Discovered devices are expected to appear in Streaming API query results.</span></span> <span data-ttu-id="912f6-174">可以使用查询中的筛选器筛选出 `OnboardingStatus` 这些设备。</span><span class="sxs-lookup"><span data-stu-id="912f6-174">You can filter out those devices by using the `OnboardingStatus` filter in your query.</span></span> 

2.  <span data-ttu-id="912f6-175">非托管设备将基于定义的条件分配到现有设备组。</span><span class="sxs-lookup"><span data-stu-id="912f6-175">Unmanaged devices will be assigned to existing device groups based on the defined criteria.</span></span> 
3.  <span data-ttu-id="912f6-176">在极少数情况下，标准发现可能会触发网络监视器或安全工具上的警报。</span><span class="sxs-lookup"><span data-stu-id="912f6-176">In rare cases, Standard discovery might trigger alerts on network monitors or security tools.</span></span> <span data-ttu-id="912f6-177">如果遇到此类事件，请提供反馈以帮助防止这些问题定期发生。</span><span class="sxs-lookup"><span data-stu-id="912f6-177">Please provide feedback, if you experience such events, to help prevent these issues from recurring.</span></span> <span data-ttu-id="912f6-178">你可以明确排除特定目标或整个子网，不由标准发现主动探测。</span><span class="sxs-lookup"><span data-stu-id="912f6-178">You can explicitly exclude specific targets or entire subnets from being actively probed by Standard discovery.</span></span> 



## <a name="next-steps"></a><span data-ttu-id="912f6-179">后续步骤</span><span class="sxs-lookup"><span data-stu-id="912f6-179">Next steps</span></span>
- [<span data-ttu-id="912f6-180">配置设备发现</span><span class="sxs-lookup"><span data-stu-id="912f6-180">Configure device discovery</span></span>](configure-device-discovery.md)
- [<span data-ttu-id="912f6-181">设备发现常见问题解答</span><span class="sxs-lookup"><span data-stu-id="912f6-181">Device discovery FAQs</span></span>](device-discovery-faq.md)
