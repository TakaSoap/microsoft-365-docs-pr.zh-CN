---
title: 配置设备发现
description: 了解如何使用基本或标准发现Microsoft 365 Defender设备发现
keywords: 基本， 标准， 配置终结点发现， 设备发现
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
ms.openlocfilehash: e1efeff77657e04223b21d639a0a09287f3707cc
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177581"
---
# <a name="configure-device-discovery"></a><span data-ttu-id="f0144-104">配置设备发现</span><span class="sxs-lookup"><span data-stu-id="f0144-104">Configure device discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f0144-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f0144-105">**Applies to:**</span></span>
- [<span data-ttu-id="f0144-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f0144-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f0144-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0144-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f0144-108">发现可以配置为标准模式或基本模式。</span><span class="sxs-lookup"><span data-stu-id="f0144-108">Discovery can be configured to be on standard or basic mode.</span></span> <span data-ttu-id="f0144-109">使用标准选项主动查找网络中设备，这将更好地保证终结点的发现并提供更丰富的设备分类。</span><span class="sxs-lookup"><span data-stu-id="f0144-109">Use the standard option to actively find devices in your network, which will better guarantee the discovery of endpoints and provide richer device classification.</span></span> 

<span data-ttu-id="f0144-110">你可以自定义用于执行标准发现的设备列表。</span><span class="sxs-lookup"><span data-stu-id="f0144-110">You can customize the list of devices that are used to perform standard discovery.</span></span> <span data-ttu-id="f0144-111">你可以在所有也支持此功能的已载入设备上启用标准发现 (当前 - Windows 10 设备仅) 或者通过指定设备的设备标记来选择设备的子集。</span><span class="sxs-lookup"><span data-stu-id="f0144-111">You can either enable standard discovery on all the onboarded devices that also support this capability (currently - Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="f0144-112">对于预览版，你首先需要在预览版中启用预览Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="f0144-112">For preview, you'll first need to turn on the Preview features in Microsoft Defender Security Center.</span></span>
> <span data-ttu-id="f0144-113">然后，你可以访问安全中心中的Microsoft 365配置。</span><span class="sxs-lookup"><span data-stu-id="f0144-113">You can then access the device discovery configuration in Microsoft 365 security center.</span></span> <span data-ttu-id="f0144-114">非托管设备和安全建议列表将在 Microsoft Defender 安全中心 和 Microsoft 365 安全中心提供，而仪表板磁贴将仅在安全中心Microsoft 365提供。</span><span class="sxs-lookup"><span data-stu-id="f0144-114">The list of unmanaged devices and security recommendations will be available in both Microsoft Defender Security Center and Microsoft 365 security center, while the dashboard tiles will only be available in Microsoft 365 security center.</span></span>


<span data-ttu-id="f0144-115">在安全中心执行Microsoft 365步骤：</span><span class="sxs-lookup"><span data-stu-id="f0144-115">Take the following configuration steps in Microsoft 365 security center:</span></span>

1.  <span data-ttu-id="f0144-116">导航到 **设置 >设备发现 "**。</span><span class="sxs-lookup"><span data-stu-id="f0144-116">Navigate to **Settings > Device discovery**.</span></span>
2.  <span data-ttu-id="f0144-117">选择要在载入的设备上使用的发现模式。</span><span class="sxs-lookup"><span data-stu-id="f0144-117">Select the discovery mode to use on your onboarded devices.</span></span> 
3.  <span data-ttu-id="f0144-118">如果你已选择使用标准发现，请通过指定设备标记来选择用于活动探测的设备：所有设备或子集。</span><span class="sxs-lookup"><span data-stu-id="f0144-118">If you've selected to use standard discovery, select which devices to use for active probing: all devices or on a subset by specifying their device tags.</span></span>
4. <span data-ttu-id="f0144-119">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f0144-119">Click **Save**.</span></span>


## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a><span data-ttu-id="f0144-120">在标准发现中排除设备的活动探测器</span><span class="sxs-lookup"><span data-stu-id="f0144-120">Exclude devices from being actively probed in standard discovery</span></span>
<span data-ttu-id="f0144-121">如果网络上有些设备不应主动扫描 (例如，用作另一个安全工具) 的热点的设备，则还可以定义排除项列表以防止它们被扫描。</span><span class="sxs-lookup"><span data-stu-id="f0144-121">If there are devices on your network which should not be actively scanned (for example, devices used as honeypots for another security tool), you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="f0144-122">请注意，仍可使用基本发现模式发现设备。</span><span class="sxs-lookup"><span data-stu-id="f0144-122">Note that devices can still be discovered using Basic discovery mode.</span></span> <span data-ttu-id="f0144-123">将被动发现这些设备，但不主动探测器。</span><span class="sxs-lookup"><span data-stu-id="f0144-123">Those devices will be passively discovered but won't be actively probed.</span></span> 

## <a name="select-networks-to-monitor"></a><span data-ttu-id="f0144-124">选择要监视的网络</span><span class="sxs-lookup"><span data-stu-id="f0144-124">Select networks to monitor</span></span>
 <span data-ttu-id="f0144-125">Microsoft Defender for Endpoint 分析网络，并确定它是需要监视的公司网络还是可忽略的非公司网络。</span><span class="sxs-lookup"><span data-stu-id="f0144-125">Microsoft Defender for Endpoint analyzes a network and determines if it is a corporate network that needs to be monitored or a non-corporate network that can be ignored.</span></span> <span data-ttu-id="f0144-126">通常选择监视公司网络。</span><span class="sxs-lookup"><span data-stu-id="f0144-126">Corporate networks are typically chosen to be monitored.</span></span> <span data-ttu-id="f0144-127">但是，可以通过选择监视找到已载入设备的非公司网络来替代此决定。</span><span class="sxs-lookup"><span data-stu-id="f0144-127">However, you can override this decision by choosing to monitor non-corporate networks where onboarded devices are found.</span></span> 

<span data-ttu-id="f0144-128">可以通过指定要监视的网络来配置设备发现执行位置。</span><span class="sxs-lookup"><span data-stu-id="f0144-128">You can configure where device discovery can be performed by specifying which networks to monitor.</span></span> <span data-ttu-id="f0144-129">当网络受到监视时，可以在它上执行设备发现。</span><span class="sxs-lookup"><span data-stu-id="f0144-129">When a network is monitored, device discovery can be performed on it.</span></span> 

<span data-ttu-id="f0144-130">可在其中执行设备发现的网络列表显示在"受监视网络 **"** 页中。</span><span class="sxs-lookup"><span data-stu-id="f0144-130">A list of networks where device discovery can be performed is shown in the **Monitored networks** page.</span></span> 


>[!NOTE]
> <span data-ttu-id="f0144-131">只有前 50 (根据网络列表中的关联设备) 数量可用。</span><span class="sxs-lookup"><span data-stu-id="f0144-131">Only top 50 networks (according to the number of associated devices) will be available in the network list.</span></span> 


<span data-ttu-id="f0144-132">受监视网络的列表根据最近 7 天内网络上看到的设备总数进行排序。</span><span class="sxs-lookup"><span data-stu-id="f0144-132">The list of monitored networks is sorted based upon the total number of devices seen on the network in the last 7 days.</span></span>


<span data-ttu-id="f0144-133">可以应用筛选器以查看以下任一网络发现状态：</span><span class="sxs-lookup"><span data-stu-id="f0144-133">You can apply a filter to view any of the following network discovery states:</span></span>

- <span data-ttu-id="f0144-134">**受监视的网络** - 执行设备发现的网络。</span><span class="sxs-lookup"><span data-stu-id="f0144-134">**Monitored networks** - Networks where device discovery is performed.</span></span>
- <span data-ttu-id="f0144-135">**忽略的网络** - 此网络将被忽略，并且不会对它执行设备发现。</span><span class="sxs-lookup"><span data-stu-id="f0144-135">**Ignored networks** - This network will be ignored and device discovery will not be performed on it.</span></span>
- <span data-ttu-id="f0144-136">**All** - 将显示受监视和忽略的网络。</span><span class="sxs-lookup"><span data-stu-id="f0144-136">**All** - Both monitored and ignored networks will be displayed.</span></span> 


### <a name="configure-the-network-monitor-state"></a><span data-ttu-id="f0144-137">配置网络监视器状态</span><span class="sxs-lookup"><span data-stu-id="f0144-137">Configure the network monitor state</span></span>
<span data-ttu-id="f0144-138">控制设备发现发生的位置。</span><span class="sxs-lookup"><span data-stu-id="f0144-138">You control where device discovery takes place.</span></span> <span data-ttu-id="f0144-139">受监视的网络是执行设备发现的地方，通常是公司网络。</span><span class="sxs-lookup"><span data-stu-id="f0144-139">Monitored networks is where device discovery will be performed and are typically corporate networks.</span></span> <span data-ttu-id="f0144-140">还可以选择忽略网络或在修改状态后选择初始发现分类。</span><span class="sxs-lookup"><span data-stu-id="f0144-140">You can also choose to ignore networks or select the initial discovery classification after modifying a state.</span></span> 

<span data-ttu-id="f0144-141">选择初始发现分类意味着应用默认的系统创建网络监视器状态。</span><span class="sxs-lookup"><span data-stu-id="f0144-141">Choosing the initial discovery classification means applying the default system-made network monitor state.</span></span> <span data-ttu-id="f0144-142">选择系统创建的默认网络监视器状态意味着，将监视标识为公司的网络，并自动忽略标识为非公司网络的网络。</span><span class="sxs-lookup"><span data-stu-id="f0144-142">Selecting the default system-made network monitor state means that networks that were identified to be corporate, will be monitored, and ones identified as non-corporate, will be ignored automatically.</span></span>
 
1. <span data-ttu-id="f0144-143">选择 **设置 >设备发现"。**</span><span class="sxs-lookup"><span data-stu-id="f0144-143">Select **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="f0144-144">选择 **"受监视的网络"。**</span><span class="sxs-lookup"><span data-stu-id="f0144-144">Select **Monitored networks**.</span></span> 
3. <span data-ttu-id="f0144-145">查看网络列表。</span><span class="sxs-lookup"><span data-stu-id="f0144-145">View the list of networks.</span></span> 
4. <span data-ttu-id="f0144-146">选择网络名称旁边的三个点。</span><span class="sxs-lookup"><span data-stu-id="f0144-146">Select the three dots next to the network name.</span></span> 
5. <span data-ttu-id="f0144-147">选择是监视、忽略还是使用初始发现分类。</span><span class="sxs-lookup"><span data-stu-id="f0144-147">Choose whether you want to monitor, ignore, or use the initial discovery classification.</span></span> 
    
    > [!WARNING]
    >- <span data-ttu-id="f0144-148">选择监视未由 Microsoft Defender for Endpoint 标识为企业网络的网络可能会导致设备在企业网络外部发现，因此可能会检测家庭或其他非公司设备。</span><span class="sxs-lookup"><span data-stu-id="f0144-148">Choosing to monitor a network that was not identified by Microsoft Defender for Endpoint as a corporate network can cause device discovery outside of your corporate network, and may therefore detect home or other non-corporate devices.</span></span> 
    > - <span data-ttu-id="f0144-149">选择忽略网络将停止监控和发现该网络中的设备。</span><span class="sxs-lookup"><span data-stu-id="f0144-149">Choosing to ignore a network will stop monitoring and discovering devices in that network.</span></span> <span data-ttu-id="f0144-150">已发现的设备不会从清单中删除，但将不再更新，详细信息将一直保留到 Defender for Endpoint 的数据保留期到期。</span><span class="sxs-lookup"><span data-stu-id="f0144-150">Devices that were already discovered will not be removed from the inventory, but will no longer be updated, and details will be retained until the data retention period of the Defender for Endpoint expires.</span></span>
    > - <span data-ttu-id="f0144-151">在选择监视非公司网络之前，必须确保你有权这样做。</span><span class="sxs-lookup"><span data-stu-id="f0144-151">Before choosing to monitor non-corporate networks, you must ensure you have permission to do so.</span></span> <br>


6. <span data-ttu-id="f0144-152">确认要更改。</span><span class="sxs-lookup"><span data-stu-id="f0144-152">Confirm that you want to make the change.</span></span> 


## <a name="explore-devices-in-the-network"></a><span data-ttu-id="f0144-153">浏览网络中设备</span><span class="sxs-lookup"><span data-stu-id="f0144-153">Explore devices in the network</span></span>

<span data-ttu-id="f0144-154">可以使用以下高级搜寻查询获取有关网络列表中描述的每个网络名称的更多上下文。</span><span class="sxs-lookup"><span data-stu-id="f0144-154">You can use the following advanced hunting query to get more context about each network name described in the networks list.</span></span> <span data-ttu-id="f0144-155">该查询列出了最近 7 天内连接到特定网络的所有已载入设备。</span><span class="sxs-lookup"><span data-stu-id="f0144-155">The query lists all the onboarded devices that were connected to a certain network within the last 7 days.</span></span>



```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"


```

## <a name="see-also"></a><span data-ttu-id="f0144-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0144-156">See also</span></span>
- [<span data-ttu-id="f0144-157">设备发现概述</span><span class="sxs-lookup"><span data-stu-id="f0144-157">Device discovery overview</span></span>](device-discovery.md)
- [<span data-ttu-id="f0144-158">设备发现常见问题解答</span><span class="sxs-lookup"><span data-stu-id="f0144-158">Device discovery FAQs</span></span>](device-discovery-faq.md)