---
title: 高级搜寻架构中的 DeviceNetworkInfo 表
description: 了解高级搜寻架构的 DeviceNetworkInfo 表中的网络配置信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， machinenetworkinfo， DeviceNetworkInfo， 设备， 计算机， mac， ip， 适配器， dns， dhcp， 网关， 隧道
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 11a6fd00524e3dd7ad456f68da6f493d74deee69
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023185"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="2cbc8-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="2cbc8-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2cbc8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2cbc8-105">**Applies to:**</span></span>
- <span data-ttu-id="2cbc8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2cbc8-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="2cbc8-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2cbc8-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="2cbc8-108">高级 `DeviceNetworkInfo` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关计算机网络配置的信息，包括网络适配器、IP 和 MAC 地址以及连接的网络或域。</span><span class="sxs-lookup"><span data-stu-id="2cbc8-108">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="2cbc8-109">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="2cbc8-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="2cbc8-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="2cbc8-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2cbc8-111">列名称</span><span class="sxs-lookup"><span data-stu-id="2cbc8-111">Column name</span></span> | <span data-ttu-id="2cbc8-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="2cbc8-112">Data type</span></span> | <span data-ttu-id="2cbc8-113">说明</span><span class="sxs-lookup"><span data-stu-id="2cbc8-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2cbc8-114">datetime</span><span class="sxs-lookup"><span data-stu-id="2cbc8-114">datetime</span></span> | <span data-ttu-id="2cbc8-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="2cbc8-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="2cbc8-116">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-116">string</span></span> | <span data-ttu-id="2cbc8-117">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="2cbc8-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2cbc8-118">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-118">string</span></span> | <span data-ttu-id="2cbc8-119">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="2cbc8-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="2cbc8-120">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-120">string</span></span> | <span data-ttu-id="2cbc8-121">网络适配器的名称</span><span class="sxs-lookup"><span data-stu-id="2cbc8-121">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="2cbc8-122">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-122">string</span></span> | <span data-ttu-id="2cbc8-123">网络适配器的 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="2cbc8-123">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="2cbc8-124">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-124">string</span></span> | <span data-ttu-id="2cbc8-125">网络适配器类型。</span><span class="sxs-lookup"><span data-stu-id="2cbc8-125">Network adapter type.</span></span> <span data-ttu-id="2cbc8-126">有关可能的值，请参阅 [此枚举](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="2cbc8-126">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="2cbc8-127">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-127">string</span></span> | <span data-ttu-id="2cbc8-128">网络适配器的运行状态。</span><span class="sxs-lookup"><span data-stu-id="2cbc8-128">Operational status of the network adapter.</span></span> <span data-ttu-id="2cbc8-129">有关可能的值，请参阅 [此枚举](/dotnet/api/system.net.networkinformation.operationalstatus)</span><span class="sxs-lookup"><span data-stu-id="2cbc8-129">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus)</span></span> |
| `TunnelType` | <span data-ttu-id="2cbc8-130">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-130">string</span></span> | <span data-ttu-id="2cbc8-131">隧道协议（如果接口用于此目的，例如 6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH）</span><span class="sxs-lookup"><span data-stu-id="2cbc8-131">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="2cbc8-132">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-132">string</span></span> | <span data-ttu-id="2cbc8-133">适配器连接到的网络。</span><span class="sxs-lookup"><span data-stu-id="2cbc8-133">Networks that the adapter is connected to.</span></span> <span data-ttu-id="2cbc8-134">每个 JSON 数组都包含网络名称、类别 (公共、专用或域) 、说明以及指示其是否公开连接到 Internet 的标志</span><span class="sxs-lookup"><span data-stu-id="2cbc8-134">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="2cbc8-135">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-135">string</span></span> | <span data-ttu-id="2cbc8-136">JSON 数组格式的 DNS 服务器地址</span><span class="sxs-lookup"><span data-stu-id="2cbc8-136">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="2cbc8-137">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-137">string</span></span> | <span data-ttu-id="2cbc8-138">DHCP 服务器的 IPv4 地址</span><span class="sxs-lookup"><span data-stu-id="2cbc8-138">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="2cbc8-139">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-139">string</span></span> | <span data-ttu-id="2cbc8-140">DHCP 服务器的 IPv6 地址</span><span class="sxs-lookup"><span data-stu-id="2cbc8-140">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="2cbc8-141">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-141">string</span></span> | <span data-ttu-id="2cbc8-142">JSON 数组格式的默认网关地址</span><span class="sxs-lookup"><span data-stu-id="2cbc8-142">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="2cbc8-143">string</span><span class="sxs-lookup"><span data-stu-id="2cbc8-143">string</span></span> | <span data-ttu-id="2cbc8-144">包含分配给适配器的所有 IP 地址及其各自的子网前缀和 IP 地址空间（如公共、专用或链接本地）的 JSON 数组</span><span class="sxs-lookup"><span data-stu-id="2cbc8-144">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="2cbc8-145">long</span><span class="sxs-lookup"><span data-stu-id="2cbc8-145">long</span></span> | <span data-ttu-id="2cbc8-146">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="2cbc8-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="2cbc8-147">若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用</span><span class="sxs-lookup"><span data-stu-id="2cbc8-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2cbc8-148">相关主题</span><span class="sxs-lookup"><span data-stu-id="2cbc8-148">Related topics</span></span>
- [<span data-ttu-id="2cbc8-149">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="2cbc8-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2cbc8-150">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="2cbc8-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2cbc8-151">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="2cbc8-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2cbc8-152">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="2cbc8-152">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2cbc8-153">了解架构</span><span class="sxs-lookup"><span data-stu-id="2cbc8-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2cbc8-154">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="2cbc8-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)