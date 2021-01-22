---
title: 高级搜寻架构中的 DeviceNetworkInfo 表
description: 了解高级搜寻架构的 DeviceNetworkInfo 表中的网络配置信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， machinenetworkinfo， DeviceNetworkInfo， 设备， 计算机， mac， ip， 适配器， dns， dhcp， 网关， 隧道
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931202"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="10e57-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="10e57-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="10e57-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="10e57-105">**Applies to:**</span></span>
- <span data-ttu-id="10e57-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10e57-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="10e57-107">高级搜寻架构中的表包含有关计算机网络配置的信息，包括网络适配器、IP 和 MAC 地址以及连接的 `DeviceNetworkInfo` 网络或域。 [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="10e57-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="10e57-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="10e57-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="10e57-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="10e57-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="10e57-110">列名称</span><span class="sxs-lookup"><span data-stu-id="10e57-110">Column name</span></span> | <span data-ttu-id="10e57-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="10e57-111">Data type</span></span> | <span data-ttu-id="10e57-112">说明</span><span class="sxs-lookup"><span data-stu-id="10e57-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="10e57-113">datetime</span><span class="sxs-lookup"><span data-stu-id="10e57-113">datetime</span></span> | <span data-ttu-id="10e57-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="10e57-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="10e57-115">string</span><span class="sxs-lookup"><span data-stu-id="10e57-115">string</span></span> | <span data-ttu-id="10e57-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="10e57-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="10e57-117">string</span><span class="sxs-lookup"><span data-stu-id="10e57-117">string</span></span> | <span data-ttu-id="10e57-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="10e57-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="10e57-119">long</span><span class="sxs-lookup"><span data-stu-id="10e57-119">long</span></span> | <span data-ttu-id="10e57-120">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="10e57-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="10e57-121">若要标识唯一事件，此列必须与 DeviceName 和时间戳列一起使用</span><span class="sxs-lookup"><span data-stu-id="10e57-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="10e57-122">string</span><span class="sxs-lookup"><span data-stu-id="10e57-122">string</span></span> | <span data-ttu-id="10e57-123">网络适配器的名称</span><span class="sxs-lookup"><span data-stu-id="10e57-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="10e57-124">string</span><span class="sxs-lookup"><span data-stu-id="10e57-124">string</span></span> | <span data-ttu-id="10e57-125">网络适配器的 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="10e57-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="10e57-126">string</span><span class="sxs-lookup"><span data-stu-id="10e57-126">string</span></span> | <span data-ttu-id="10e57-127">网络适配器类型。</span><span class="sxs-lookup"><span data-stu-id="10e57-127">Network adapter type.</span></span> <span data-ttu-id="10e57-128">有关可能的值，请参阅 [此枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="10e57-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="10e57-129">string</span><span class="sxs-lookup"><span data-stu-id="10e57-129">string</span></span> | <span data-ttu-id="10e57-130">网络适配器的运行状态。</span><span class="sxs-lookup"><span data-stu-id="10e57-130">Operational status of the network adapter.</span></span> <span data-ttu-id="10e57-131">有关可能的值，请参阅 [此枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="10e57-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="10e57-132">string</span><span class="sxs-lookup"><span data-stu-id="10e57-132">string</span></span> | <span data-ttu-id="10e57-133">隧道协议（如果接口用于此目的，例如 6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH）</span><span class="sxs-lookup"><span data-stu-id="10e57-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="10e57-134">string</span><span class="sxs-lookup"><span data-stu-id="10e57-134">string</span></span> | <span data-ttu-id="10e57-135">适配器连接到的网络。</span><span class="sxs-lookup"><span data-stu-id="10e57-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="10e57-136">每个 JSON 数组都包含网络名称、 (公共、专用或域) 、说明和指示其是否公开连接到 Internet 的标志</span><span class="sxs-lookup"><span data-stu-id="10e57-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="10e57-137">string</span><span class="sxs-lookup"><span data-stu-id="10e57-137">string</span></span> | <span data-ttu-id="10e57-138">JSON 数组格式的 DNS 服务器地址</span><span class="sxs-lookup"><span data-stu-id="10e57-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="10e57-139">string</span><span class="sxs-lookup"><span data-stu-id="10e57-139">string</span></span> | <span data-ttu-id="10e57-140">DHCP 服务器的 IPv4 地址</span><span class="sxs-lookup"><span data-stu-id="10e57-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="10e57-141">string</span><span class="sxs-lookup"><span data-stu-id="10e57-141">string</span></span> | <span data-ttu-id="10e57-142">DHCP 服务器的 IPv6 地址</span><span class="sxs-lookup"><span data-stu-id="10e57-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="10e57-143">string</span><span class="sxs-lookup"><span data-stu-id="10e57-143">string</span></span> | <span data-ttu-id="10e57-144">JSON 数组格式的默认网关地址</span><span class="sxs-lookup"><span data-stu-id="10e57-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="10e57-145">string</span><span class="sxs-lookup"><span data-stu-id="10e57-145">string</span></span> | <span data-ttu-id="10e57-146">包含分配给适配器的所有 IP 地址及其各自的子网前缀和 IP 地址空间（如公共、专用或链接本地）的 JSON 数组</span><span class="sxs-lookup"><span data-stu-id="10e57-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="10e57-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="10e57-147">Related topics</span></span>
- [<span data-ttu-id="10e57-148">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="10e57-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="10e57-149">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="10e57-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="10e57-150">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="10e57-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="10e57-151">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="10e57-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="10e57-152">了解架构</span><span class="sxs-lookup"><span data-stu-id="10e57-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="10e57-153">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="10e57-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
