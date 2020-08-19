---
title: 'Microsoft 威胁防护中的 AssignedIPAddresses ( # A1 函数在高级搜寻中'
description: '了解如何使用 AssignedIPAddresses ( # A1 函数来获取分配给设备的最新 IP 地址'
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、FileProfile、文件配置文件、函数、扩充
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794227"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="66ac3-104">AssignedIPAddresses ( # A1</span><span class="sxs-lookup"><span data-stu-id="66ac3-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="66ac3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="66ac3-105">**Applies to:**</span></span>
- <span data-ttu-id="66ac3-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="66ac3-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="66ac3-107">使用该 `AssignedIPAddresses()` 函数可以快速获取从指定时间点分配给设备或最近的 ip 地址的最新 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="66ac3-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span> <span data-ttu-id="66ac3-108">此函数返回具有以下列的表：</span><span class="sxs-lookup"><span data-stu-id="66ac3-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="66ac3-109">列</span><span class="sxs-lookup"><span data-stu-id="66ac3-109">Column</span></span> | <span data-ttu-id="66ac3-110">数据类型</span><span class="sxs-lookup"><span data-stu-id="66ac3-110">Data type</span></span> | <span data-ttu-id="66ac3-111">说明</span><span class="sxs-lookup"><span data-stu-id="66ac3-111">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="66ac3-112">Timestamp</span><span class="sxs-lookup"><span data-stu-id="66ac3-112">Timestamp</span></span> | <span data-ttu-id="66ac3-113">datetime</span><span class="sxs-lookup"><span data-stu-id="66ac3-113">datetime</span></span> | <span data-ttu-id="66ac3-114">使用 IP 地址观察到设备的最晚时间</span><span class="sxs-lookup"><span data-stu-id="66ac3-114">Latest time when the device was observed using the IP address</span></span> |
| <span data-ttu-id="66ac3-115">IPAddress</span><span class="sxs-lookup"><span data-stu-id="66ac3-115">IPAddress</span></span> | <span data-ttu-id="66ac3-116">string</span><span class="sxs-lookup"><span data-stu-id="66ac3-116">string</span></span> | <span data-ttu-id="66ac3-117">设备使用的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66ac3-117">IP address used by the device</span></span> |
| <span data-ttu-id="66ac3-118">IPType</span><span class="sxs-lookup"><span data-stu-id="66ac3-118">IPType</span></span> | <span data-ttu-id="66ac3-119">string</span><span class="sxs-lookup"><span data-stu-id="66ac3-119">string</span></span> | <span data-ttu-id="66ac3-120">指示 IP 地址是否为公用地址或专用地址</span><span class="sxs-lookup"><span data-stu-id="66ac3-120">Indicates whether the IP address is a public or private address</span></span> |
| <span data-ttu-id="66ac3-121">NetworkAdapterType</span><span class="sxs-lookup"><span data-stu-id="66ac3-121">NetworkAdapterType</span></span> | <span data-ttu-id="66ac3-122">int</span><span class="sxs-lookup"><span data-stu-id="66ac3-122">int</span></span> | <span data-ttu-id="66ac3-123">已为其分配 IP 地址的设备使用的网络适配器类型。</span><span class="sxs-lookup"><span data-stu-id="66ac3-123">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="66ac3-124">有关可能的值，请参阅 [this 枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="66ac3-124">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span>  |
| <span data-ttu-id="66ac3-125">ConnectedNetworks</span><span class="sxs-lookup"><span data-stu-id="66ac3-125">ConnectedNetworks</span></span> | <span data-ttu-id="66ac3-126">int</span><span class="sxs-lookup"><span data-stu-id="66ac3-126">int</span></span> | <span data-ttu-id="66ac3-127">与分配的 IP 地址的适配器连接的网络。</span><span class="sxs-lookup"><span data-stu-id="66ac3-127">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="66ac3-128">每个 JSON 数组包含网络名称、类别 (public、private 或 domain) 、说明以及指示是否已将其公开连接到 internet 的标志</span><span class="sxs-lookup"><span data-stu-id="66ac3-128">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |


## <a name="syntax"></a><span data-ttu-id="66ac3-129">语法</span><span class="sxs-lookup"><span data-stu-id="66ac3-129">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="66ac3-130">参数</span><span class="sxs-lookup"><span data-stu-id="66ac3-130">Arguments</span></span>

- <span data-ttu-id="66ac3-131">**x** — `DeviceId` 或 `DeviceName` 标识设备的值</span><span class="sxs-lookup"><span data-stu-id="66ac3-131">**x** — `DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="66ac3-132">**y** — `Timestamp` (datetime) 值，该值指示获取最新 IP 地址的特定时间点。</span><span class="sxs-lookup"><span data-stu-id="66ac3-132">**y** — `Timestamp` (datetime) value indicating the specific point in time where to get the most recent IP addresses.</span></span> <span data-ttu-id="66ac3-133">如果未指定，则该函数将返回最新的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="66ac3-133">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="66ac3-134">示例</span><span class="sxs-lookup"><span data-stu-id="66ac3-134">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a><span data-ttu-id="66ac3-135">获取设备在24小时前使用的 IP 地址列表</span><span class="sxs-lookup"><span data-stu-id="66ac3-135">Get the list of IP addresses used by a device as of 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="66ac3-136">获取设备使用的 IP 地址并查找与之通信的设备</span><span class="sxs-lookup"><span data-stu-id="66ac3-136">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="66ac3-137">此查询使用 `AssignedIPAddresses()` 函数来获取设备 (`example-device-name`) 在特定日期 () 之前或之前的已分配 IP 地址 `example-date` 。</span><span class="sxs-lookup"><span data-stu-id="66ac3-137">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="66ac3-138">然后，它使用 IP 地址查找与其他设备启动的设备的连接。</span><span class="sxs-lookup"><span data-stu-id="66ac3-138">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="66ac3-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="66ac3-139">Related topics</span></span>
- [<span data-ttu-id="66ac3-140">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="66ac3-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="66ac3-141">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="66ac3-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="66ac3-142">了解架构</span><span class="sxs-lookup"><span data-stu-id="66ac3-142">Understand the schema</span></span>](advanced-hunting-schema-tables.md)