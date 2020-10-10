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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7f0b479051c46fe35ec9aea84b23ca0c4937fbfe
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412318"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="58b9b-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="58b9b-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="58b9b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="58b9b-105">**Applies to:**</span></span>
- <span data-ttu-id="58b9b-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="58b9b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="58b9b-107">使用 `AssignedIPAddresses()` [高级搜寻](advanced-hunting-overview.md) 查询中的功能快速获取已分配给设备的最新 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="58b9b-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="58b9b-108">如果指定时间戳参数，此函数将获取指定时间的最新 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="58b9b-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="58b9b-109">此函数返回具有以下列的表：</span><span class="sxs-lookup"><span data-stu-id="58b9b-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="58b9b-110">列</span><span class="sxs-lookup"><span data-stu-id="58b9b-110">Column</span></span> | <span data-ttu-id="58b9b-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="58b9b-111">Data type</span></span> | <span data-ttu-id="58b9b-112">说明</span><span class="sxs-lookup"><span data-stu-id="58b9b-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="58b9b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="58b9b-113">datetime</span></span> | <span data-ttu-id="58b9b-114">使用 IP 地址观察到设备的最晚时间</span><span class="sxs-lookup"><span data-stu-id="58b9b-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="58b9b-115">string</span><span class="sxs-lookup"><span data-stu-id="58b9b-115">string</span></span> | <span data-ttu-id="58b9b-116">设备使用的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="58b9b-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="58b9b-117">string</span><span class="sxs-lookup"><span data-stu-id="58b9b-117">string</span></span> | <span data-ttu-id="58b9b-118">指示 IP 地址是否为公用地址或专用地址</span><span class="sxs-lookup"><span data-stu-id="58b9b-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="58b9b-119">int</span><span class="sxs-lookup"><span data-stu-id="58b9b-119">int</span></span> | <span data-ttu-id="58b9b-120">已为其分配 IP 地址的设备使用的网络适配器类型。</span><span class="sxs-lookup"><span data-stu-id="58b9b-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="58b9b-121">有关可能的值，请参阅 [this 枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="58b9b-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="58b9b-122">int</span><span class="sxs-lookup"><span data-stu-id="58b9b-122">int</span></span> | <span data-ttu-id="58b9b-123">与分配的 IP 地址的适配器连接的网络。</span><span class="sxs-lookup"><span data-stu-id="58b9b-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="58b9b-124">每个 JSON 数组包含网络名称、类别 (公用、专用或域) 、说明以及指示是否已将其公开连接到 internet 的标志</span><span class="sxs-lookup"><span data-stu-id="58b9b-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="58b9b-125">语法</span><span class="sxs-lookup"><span data-stu-id="58b9b-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="58b9b-126">参数</span><span class="sxs-lookup"><span data-stu-id="58b9b-126">Arguments</span></span>

- <span data-ttu-id="58b9b-127">**x**— `DeviceId` 或 `DeviceName` 标识设备的值</span><span class="sxs-lookup"><span data-stu-id="58b9b-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="58b9b-128">**y**— `Timestamp` (datetime) 值指示函数获取特定时间的最近分配的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="58b9b-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="58b9b-129">如果未指定，则该函数将返回最新的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="58b9b-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="58b9b-130">示例</span><span class="sxs-lookup"><span data-stu-id="58b9b-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="58b9b-131">获取设备24小时前使用的 IP 地址的列表</span><span class="sxs-lookup"><span data-stu-id="58b9b-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="58b9b-132">获取设备使用的 IP 地址并查找与之通信的设备</span><span class="sxs-lookup"><span data-stu-id="58b9b-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="58b9b-133">此查询使用 `AssignedIPAddresses()` 函数来获取设备 (`example-device-name`) 在特定日期 () 之前或之前的已分配 IP 地址 `example-date` 。</span><span class="sxs-lookup"><span data-stu-id="58b9b-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="58b9b-134">然后，它使用 IP 地址查找与其他设备启动的设备的连接。</span><span class="sxs-lookup"><span data-stu-id="58b9b-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="58b9b-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="58b9b-135">Related topics</span></span>
- [<span data-ttu-id="58b9b-136">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="58b9b-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="58b9b-137">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="58b9b-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="58b9b-138">了解架构</span><span class="sxs-lookup"><span data-stu-id="58b9b-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
