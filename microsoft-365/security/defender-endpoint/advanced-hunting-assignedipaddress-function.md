---
title: AssignedIPAddresses () Microsoft Defender for Endpoint 高级搜寻中的函数
description: 了解如何使用 AssignedIPAddresses () 函数获取分配给设备的最新 IP 地址
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， Microsoft Defender ATP， Microsoft Defender for Endpoint， Windows Defender， Windows Defender ATP， Windows Defender 高级威胁防护， 搜索， 查询， 遥测， 架构参考， kusto， FileProfile， 文件配置文件， 函数， 扩充
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 08ab7ff5bac917a027e4380a46ab1cb2cf0a1312
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055492"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="46f47-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="46f47-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

><span data-ttu-id="46f47-105">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="46f47-105">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="46f47-106">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="46f47-106">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="46f47-107">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="46f47-107">**Applies to:**</span></span>
- [<span data-ttu-id="46f47-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="46f47-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="46f47-109">使用高级搜寻查询中的 函数可快速获取已分配给设备的最新 `AssignedIPAddresses()` IP 地址。</span><span class="sxs-lookup"><span data-stu-id="46f47-109">Use the `AssignedIPAddresses()` function in your advanced hunting queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="46f47-110">如果指定时间戳参数，此函数将获取指定时间的最新 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="46f47-110">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span>

<span data-ttu-id="46f47-111">此函数返回具有以下列的表：</span><span class="sxs-lookup"><span data-stu-id="46f47-111">This function returns a table with the following columns:</span></span>

<span data-ttu-id="46f47-112">Column</span><span class="sxs-lookup"><span data-stu-id="46f47-112">Column</span></span> | <span data-ttu-id="46f47-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="46f47-113">Data type</span></span> | <span data-ttu-id="46f47-114">说明</span><span class="sxs-lookup"><span data-stu-id="46f47-114">Description</span></span>
-|-|-
`Timestamp` | <span data-ttu-id="46f47-115">datetime</span><span class="sxs-lookup"><span data-stu-id="46f47-115">datetime</span></span> | <span data-ttu-id="46f47-116">使用 IP 地址观测到设备的最新时间</span><span class="sxs-lookup"><span data-stu-id="46f47-116">Latest time when the device was observed using the IP address</span></span>
`IPAddress` | <span data-ttu-id="46f47-117">string</span><span class="sxs-lookup"><span data-stu-id="46f47-117">string</span></span> | <span data-ttu-id="46f47-118">设备使用的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46f47-118">IP address used by the device</span></span>
`IPType` | <span data-ttu-id="46f47-119">string</span><span class="sxs-lookup"><span data-stu-id="46f47-119">string</span></span> | <span data-ttu-id="46f47-120">指示 IP 地址是公用地址还是专用地址</span><span class="sxs-lookup"><span data-stu-id="46f47-120">Indicates whether the IP address is a public or private address</span></span>
`NetworkAdapterType` | <span data-ttu-id="46f47-121">int</span><span class="sxs-lookup"><span data-stu-id="46f47-121">int</span></span> | <span data-ttu-id="46f47-122">已分配 IP 地址的设备使用的网络适配器类型。</span><span class="sxs-lookup"><span data-stu-id="46f47-122">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="46f47-123">有关可能的值，请参阅 [此枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="46f47-123">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span>
`ConnectedNetworks` | <span data-ttu-id="46f47-124">int</span><span class="sxs-lookup"><span data-stu-id="46f47-124">int</span></span> | <span data-ttu-id="46f47-125">具有分配 IP 地址的适配器所连接至的网络。</span><span class="sxs-lookup"><span data-stu-id="46f47-125">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="46f47-126">每个 JSON 数组都包含网络名称、类别 (公共、专用或域) 、说明以及指示其是否公开连接到 Internet 的标志</span><span class="sxs-lookup"><span data-stu-id="46f47-126">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span>

## <a name="syntax"></a><span data-ttu-id="46f47-127">语法</span><span class="sxs-lookup"><span data-stu-id="46f47-127">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="46f47-128">参数</span><span class="sxs-lookup"><span data-stu-id="46f47-128">Arguments</span></span>

- <span data-ttu-id="46f47-129">**x** `DeviceId` — `DeviceName` 或用于标识设备的值</span><span class="sxs-lookup"><span data-stu-id="46f47-129">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="46f47-130">**y**— (datetime) 指示函数从特定时间获取最新分配的 `Timestamp` IP 地址的值。</span><span class="sxs-lookup"><span data-stu-id="46f47-130">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="46f47-131">如果未指定，函数将返回最新的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="46f47-131">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="46f47-132">示例</span><span class="sxs-lookup"><span data-stu-id="46f47-132">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="46f47-133">获取设备 24 小时之前使用的 IP 地址列表</span><span class="sxs-lookup"><span data-stu-id="46f47-133">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="46f47-134">获取设备使用的 IP 地址并查找与设备通信的设备</span><span class="sxs-lookup"><span data-stu-id="46f47-134">Get IP addresses used by a device and find devices communicating with it</span></span>

<span data-ttu-id="46f47-135">此查询使用 函数获取特定日期或 () 或之前为设备分配的 `AssignedIPAddresses()` IP `example-device-name` `example-date` () 。</span><span class="sxs-lookup"><span data-stu-id="46f47-135">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="46f47-136">然后，它使用 IP 地址查找与其他设备启动的设备的连接。</span><span class="sxs-lookup"><span data-stu-id="46f47-136">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a><span data-ttu-id="46f47-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="46f47-137">Related topics</span></span>

- [<span data-ttu-id="46f47-138">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="46f47-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="46f47-139">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="46f47-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="46f47-140">了解架构</span><span class="sxs-lookup"><span data-stu-id="46f47-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
