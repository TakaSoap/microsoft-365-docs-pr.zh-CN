---
title: Microsoft 365 Defender 高级搜寻中的 DeviceFromIP ( ) 函数
description: 了解如何使用 DeviceFromIP () 函数获取已分配有特定 IP 地址的设备
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 设备， devicefromIP， 函数， 扩充
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931298"
---
# <a name="devicefromip"></a><span data-ttu-id="7279b-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="7279b-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7279b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7279b-105">**Applies to:**</span></span>
- <span data-ttu-id="7279b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7279b-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="7279b-107">使用高级搜寻查询中的函数可快速获取给定时间点已分配给特定 IP 地址 `DeviceFromIP()` 的设备列表。 [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7279b-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="7279b-108">此函数返回具有以下列的表：</span><span class="sxs-lookup"><span data-stu-id="7279b-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="7279b-109">列</span><span class="sxs-lookup"><span data-stu-id="7279b-109">Column</span></span> | <span data-ttu-id="7279b-110">数据类型</span><span class="sxs-lookup"><span data-stu-id="7279b-110">Data type</span></span> | <span data-ttu-id="7279b-111">说明</span><span class="sxs-lookup"><span data-stu-id="7279b-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="7279b-112">string</span><span class="sxs-lookup"><span data-stu-id="7279b-112">string</span></span> | <span data-ttu-id="7279b-113">IP 地址</span><span class="sxs-lookup"><span data-stu-id="7279b-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="7279b-114">string</span><span class="sxs-lookup"><span data-stu-id="7279b-114">string</span></span> | <span data-ttu-id="7279b-115">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="7279b-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="7279b-116">语法</span><span class="sxs-lookup"><span data-stu-id="7279b-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="7279b-117">参数</span><span class="sxs-lookup"><span data-stu-id="7279b-117">Arguments</span></span>

<span data-ttu-id="7279b-118">此函数作为查询的一部分调用。</span><span class="sxs-lookup"><span data-stu-id="7279b-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="7279b-119">**x**— 第一个参数通常是查询中的列。</span><span class="sxs-lookup"><span data-stu-id="7279b-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="7279b-120">在这种情况下，它是名为"IP 地址"的列，您希望查看已分配给它的设备 `IP` 列表。</span><span class="sxs-lookup"><span data-stu-id="7279b-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="7279b-121">它应该是本地 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7279b-121">It should be a local IP address.</span></span> <span data-ttu-id="7279b-122">不支持外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7279b-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="7279b-123">**y**—第二个可选参数是 ，指示函数从特定时间获取最新 `Timestamp` 分配的设备。</span><span class="sxs-lookup"><span data-stu-id="7279b-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="7279b-124">如果未指定，函数将返回最新可用记录。</span><span class="sxs-lookup"><span data-stu-id="7279b-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="7279b-125">示例</span><span class="sxs-lookup"><span data-stu-id="7279b-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="7279b-126">获取已分配特定 IP 地址的最新设备</span><span class="sxs-lookup"><span data-stu-id="7279b-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="7279b-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="7279b-127">Related topics</span></span>
- [<span data-ttu-id="7279b-128">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="7279b-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7279b-129">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="7279b-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7279b-130">了解架构</span><span class="sxs-lookup"><span data-stu-id="7279b-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
