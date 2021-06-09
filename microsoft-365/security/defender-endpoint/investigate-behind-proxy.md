---
title: 调查正向代理背后发生的连接事件
description: 了解如何通过 Microsoft Defender for Endpoint 中的网络保护使用高级 HTTP 级别监视，从而显示真实目标，而不是代理。
keywords: 代理， 网络保护， 转发代理， 网络事件， 审核， 阻止， 域名， 域
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 55c001781ff016d7a23dc5db286d454b39fac5de
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841050"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a><span data-ttu-id="8701d-104">调查正向代理背后发生的连接事件</span><span class="sxs-lookup"><span data-stu-id="8701d-104">Investigate connection events that occur behind forward proxies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8701d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8701d-105">**Applies to:**</span></span>
- [<span data-ttu-id="8701d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8701d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8701d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8701d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8701d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="8701d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8701d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8701d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="8701d-110">Defender for Endpoint 支持来自不同级别的网络堆栈的网络连接监视。</span><span class="sxs-lookup"><span data-stu-id="8701d-110">Defender for Endpoint supports network connection monitoring from different levels of the network stack.</span></span> <span data-ttu-id="8701d-111">一个难题是，当网络使用转发代理作为 Internet 网关时。</span><span class="sxs-lookup"><span data-stu-id="8701d-111">A challenging case is when the network uses a forward proxy as a gateway to the Internet.</span></span>

<span data-ttu-id="8701d-112">代理的作用就像它是目标终结点一样。</span><span class="sxs-lookup"><span data-stu-id="8701d-112">The proxy acts as if it was the target endpoint.</span></span>  <span data-ttu-id="8701d-113">在这些情况下，简单的网络连接监视器将审核与代理的连接，该代理是正确的，但调查值较低。</span><span class="sxs-lookup"><span data-stu-id="8701d-113">In these cases, simple network connection monitors will audit the connections with the proxy which is correct but has lower investigation value.</span></span> 

<span data-ttu-id="8701d-114">Defender for Endpoint 通过网络保护支持高级 HTTP 级别监视。</span><span class="sxs-lookup"><span data-stu-id="8701d-114">Defender for Endpoint supports advanced HTTP level monitoring through network protection.</span></span> <span data-ttu-id="8701d-115">打开后，将显示新的事件类型，以公开真实目标域名。</span><span class="sxs-lookup"><span data-stu-id="8701d-115">When turned on, a new type of event is surfaced which exposes the real target domain names.</span></span>

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a><span data-ttu-id="8701d-116">使用网络保护监视防火墙后的网络连接</span><span class="sxs-lookup"><span data-stu-id="8701d-116">Use network protection to monitor network connection behind a firewall</span></span>
<span data-ttu-id="8701d-117">由于源自网络保护的其他网络事件，可以监视转发代理后面的网络连接。</span><span class="sxs-lookup"><span data-stu-id="8701d-117">Monitoring network connection behind a forward proxy is possible due to additional network events that originate from network protection.</span></span> <span data-ttu-id="8701d-118">若要在设备时间线上查看它们，请至少 (在审核模式下打开网络) 。</span><span class="sxs-lookup"><span data-stu-id="8701d-118">To see them on a device timeline, turn network protection on (at the minimum in audit mode).</span></span> 

<span data-ttu-id="8701d-119">可以使用以下模式控制网络保护：</span><span class="sxs-lookup"><span data-stu-id="8701d-119">Network protection can be controlled using the following modes:</span></span>

- <span data-ttu-id="8701d-120">**阻止**</span><span class="sxs-lookup"><span data-stu-id="8701d-120">**Block**</span></span> <br> <span data-ttu-id="8701d-121">将阻止用户或应用连接到危险域。</span><span class="sxs-lookup"><span data-stu-id="8701d-121">Users or apps will be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="8701d-122">你将能够在活动中心内看到此Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="8701d-122">You will be able to see this activity in Microsoft Defender Security Center.</span></span>
- <span data-ttu-id="8701d-123">**审核**</span><span class="sxs-lookup"><span data-stu-id="8701d-123">**Audit**</span></span> <br> <span data-ttu-id="8701d-124">不会阻止用户或应用连接到危险域。</span><span class="sxs-lookup"><span data-stu-id="8701d-124">Users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="8701d-125">但是，你仍将看到此活动Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="8701d-125">However, you will still see this activity in Microsoft Defender Security Center.</span></span>


<span data-ttu-id="8701d-126">如果关闭网络保护，将不会阻止用户或应用连接到危险域。</span><span class="sxs-lookup"><span data-stu-id="8701d-126">If you turn network protection off, users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="8701d-127">你将不会在 Microsoft Defender 安全中心 中看到任何网络Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="8701d-127">You will not see any network activity in Microsoft Defender Security Center.</span></span>

<span data-ttu-id="8701d-128">如果未配置它，则默认情况下将关闭网络阻止。</span><span class="sxs-lookup"><span data-stu-id="8701d-128">If you do not configure it, network blocking will be turned off by default.</span></span>

<span data-ttu-id="8701d-129">有关详细信息，请参阅启用 [网络保护](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8701d-129">For more information, see [Enable network protection](enable-network-protection.md).</span></span>

## <a name="investigation-impact"></a><span data-ttu-id="8701d-130">调查影响</span><span class="sxs-lookup"><span data-stu-id="8701d-130">Investigation impact</span></span>
<span data-ttu-id="8701d-131">当网络保护打开时，你将看到，在设备的时间线上，IP 地址将一直表示代理，而真实目标地址将显示。</span><span class="sxs-lookup"><span data-stu-id="8701d-131">When network protection is turned on, you'll see that on a device's timeline the IP address will keep representing the proxy, while the real target address shows up.</span></span>

![设备时间线上的网络事件的图像](images/atp-proxy-investigation.png)

<span data-ttu-id="8701d-133">网络保护层触发的其他事件现在甚至可以在代理后面显示真实域名。</span><span class="sxs-lookup"><span data-stu-id="8701d-133">Additional events triggered by the network protection layer are now available to surface the real domain names even behind a proxy.</span></span>

<span data-ttu-id="8701d-134">事件的信息：</span><span class="sxs-lookup"><span data-stu-id="8701d-134">Event's information:</span></span>

![单个网络事件的图像](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a><span data-ttu-id="8701d-136">使用高级搜寻搜寻连接事件</span><span class="sxs-lookup"><span data-stu-id="8701d-136">Hunt for connection events using advanced hunting</span></span> 
<span data-ttu-id="8701d-137">所有新的连接事件都可供你通过高级搜寻进行搜寻。</span><span class="sxs-lookup"><span data-stu-id="8701d-137">All new connection events are available for you to hunt on through advanced hunting as well.</span></span> <span data-ttu-id="8701d-138">由于这些事件是连接事件，因此可以在操作类型下的 DeviceNetworkEvents 表 `ConnecionSuccess` 下找到它们。</span><span class="sxs-lookup"><span data-stu-id="8701d-138">Since these events are connection events, you can find them under the DeviceNetworkEvents table under the `ConnecionSuccess` action type.</span></span>

<span data-ttu-id="8701d-139">使用此简单查询将显示所有相关事件：</span><span class="sxs-lookup"><span data-stu-id="8701d-139">Using this simple query will show you all the relevant events:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![高级搜寻查询的图像](images/atp-proxy-investigation-ah.png)

<span data-ttu-id="8701d-141">还可以筛选掉与与代理本身连接相关的事件。</span><span class="sxs-lookup"><span data-stu-id="8701d-141">You can also filter out  events that are related to connection to the proxy itself.</span></span> 

<span data-ttu-id="8701d-142">使用以下查询筛选出与代理的连接：</span><span class="sxs-lookup"><span data-stu-id="8701d-142">Use the following query to filter out the connections to the proxy:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a><span data-ttu-id="8701d-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="8701d-143">Related topics</span></span>
- [<span data-ttu-id="8701d-144">通过 GP 应用网络保护 - 策略 CSP</span><span class="sxs-lookup"><span data-stu-id="8701d-144">Applying network protection with GP - policy CSP</span></span>](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
