---
title: 高级搜寻架构中的 DeviceNetworkInfo 表
description: 了解高级搜寻架构的 DeviceNetworkInfo 表中的网络配置信息
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、machinenetworkinfo、DeviceNetworkInfo、设备、计算机、mac、ip、适配器、dns、dhcp、gateway、隧道
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
ms.openlocfilehash: b874ef77dcf6efacd7adeff18553c0c8e6752bda
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197069"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="f0bd3-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="f0bd3-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f0bd3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f0bd3-105">**Applies to:**</span></span>
- <span data-ttu-id="f0bd3-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="f0bd3-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="f0bd3-107">`DeviceNetworkInfo`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关计算机的网络配置的信息，包括网络适配器、IP 和 MAC 地址以及连接的网络或域。</span><span class="sxs-lookup"><span data-stu-id="f0bd3-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="f0bd3-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="f0bd3-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f0bd3-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="f0bd3-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f0bd3-110">列名称</span><span class="sxs-lookup"><span data-stu-id="f0bd3-110">Column name</span></span> | <span data-ttu-id="f0bd3-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="f0bd3-111">Data type</span></span> | <span data-ttu-id="f0bd3-112">说明</span><span class="sxs-lookup"><span data-stu-id="f0bd3-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f0bd3-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f0bd3-113">datetime</span></span> | <span data-ttu-id="f0bd3-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="f0bd3-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f0bd3-115">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-115">string</span></span> | <span data-ttu-id="f0bd3-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="f0bd3-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f0bd3-117">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-117">string</span></span> | <span data-ttu-id="f0bd3-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f0bd3-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="f0bd3-119">long</span><span class="sxs-lookup"><span data-stu-id="f0bd3-119">long</span></span> | <span data-ttu-id="f0bd3-120">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="f0bd3-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f0bd3-121">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="f0bd3-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="f0bd3-122">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-122">string</span></span> | <span data-ttu-id="f0bd3-123">网络适配器的名称</span><span class="sxs-lookup"><span data-stu-id="f0bd3-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="f0bd3-124">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-124">string</span></span> | <span data-ttu-id="f0bd3-125">网络适配器的 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="f0bd3-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="f0bd3-126">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-126">string</span></span> | <span data-ttu-id="f0bd3-127">网络适配器类型。</span><span class="sxs-lookup"><span data-stu-id="f0bd3-127">Network adapter type.</span></span> <span data-ttu-id="f0bd3-128">有关可能的值，请参阅 [this 枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="f0bd3-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="f0bd3-129">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-129">string</span></span> | <span data-ttu-id="f0bd3-130">网络适配器的操作状态。</span><span class="sxs-lookup"><span data-stu-id="f0bd3-130">Operational status of the network adapter.</span></span> <span data-ttu-id="f0bd3-131">有关可能的值，请参阅 [this 枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="f0bd3-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="f0bd3-132">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-132">string</span></span> | <span data-ttu-id="f0bd3-133">隧道协议，如果该接口用于实现此目的，例如6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH</span><span class="sxs-lookup"><span data-stu-id="f0bd3-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="f0bd3-134">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-134">string</span></span> | <span data-ttu-id="f0bd3-135">适配器连接到的网络。</span><span class="sxs-lookup"><span data-stu-id="f0bd3-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="f0bd3-136">每个 JSON 数组包含网络名称、类别 (public、private 或 domain) 、说明以及指示是否已将其公开连接到 internet 的标志</span><span class="sxs-lookup"><span data-stu-id="f0bd3-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="f0bd3-137">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-137">string</span></span> | <span data-ttu-id="f0bd3-138">JSON 数组格式的 DNS 服务器地址</span><span class="sxs-lookup"><span data-stu-id="f0bd3-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="f0bd3-139">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-139">string</span></span> | <span data-ttu-id="f0bd3-140">DHCP 服务器的 IPv4 地址</span><span class="sxs-lookup"><span data-stu-id="f0bd3-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="f0bd3-141">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-141">string</span></span> | <span data-ttu-id="f0bd3-142">DHCP 服务器的 IPv6 地址</span><span class="sxs-lookup"><span data-stu-id="f0bd3-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="f0bd3-143">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-143">string</span></span> | <span data-ttu-id="f0bd3-144">以 JSON 数组格式的默认网关地址</span><span class="sxs-lookup"><span data-stu-id="f0bd3-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="f0bd3-145">string</span><span class="sxs-lookup"><span data-stu-id="f0bd3-145">string</span></span> | <span data-ttu-id="f0bd3-146">包含分配给适配器的所有 IP 地址的 JSON 数组及其各自的子网前缀和 IP 地址空间，如 public、private 或 link 本地</span><span class="sxs-lookup"><span data-stu-id="f0bd3-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f0bd3-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="f0bd3-147">Related topics</span></span>
- [<span data-ttu-id="f0bd3-148">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="f0bd3-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f0bd3-149">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="f0bd3-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f0bd3-150">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="f0bd3-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f0bd3-151">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="f0bd3-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f0bd3-152">了解架构</span><span class="sxs-lookup"><span data-stu-id="f0bd3-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f0bd3-153">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="f0bd3-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
