---
title: 高级搜寻架构中的 DeviceNetworkInfo 表
description: 了解高级搜寻架构的 DeviceNetworkInfo 表中的网络配置信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， devicenetworkinfo， 设备， 设备， mac， ip， 适配器， dns， dhcp， 网关， 隧道， DeviceNetworkInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e63af4153804a09424c36fb03ac715da5f6d9485
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499140"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="d88eb-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="d88eb-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d88eb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d88eb-105">**Applies to:**</span></span>
- [<span data-ttu-id="d88eb-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d88eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="d88eb-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="d88eb-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d88eb-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="d88eb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="d88eb-109">高级 `DeviceNetworkInfo` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关设备网络配置的信息，包括网络适配器、IP 和 MAC 地址以及连接的网络或域。</span><span class="sxs-lookup"><span data-stu-id="d88eb-109">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of devices, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="d88eb-110">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="d88eb-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d88eb-111">有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="d88eb-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="d88eb-112">列名称</span><span class="sxs-lookup"><span data-stu-id="d88eb-112">Column name</span></span> | <span data-ttu-id="d88eb-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="d88eb-113">Data type</span></span> | <span data-ttu-id="d88eb-114">说明</span><span class="sxs-lookup"><span data-stu-id="d88eb-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d88eb-115">datetime</span><span class="sxs-lookup"><span data-stu-id="d88eb-115">datetime</span></span> | <span data-ttu-id="d88eb-116">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="d88eb-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d88eb-117">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-117">string</span></span> | <span data-ttu-id="d88eb-118">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="d88eb-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d88eb-119">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-119">string</span></span> | <span data-ttu-id="d88eb-120">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="d88eb-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ReportId` | <span data-ttu-id="d88eb-121">long</span><span class="sxs-lookup"><span data-stu-id="d88eb-121">long</span></span> | <span data-ttu-id="d88eb-122">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="d88eb-122">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d88eb-123">若要标识唯一事件，此列必须与 和 `DeviceName` `Timestamp` 列一起使用</span><span class="sxs-lookup"><span data-stu-id="d88eb-123">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="d88eb-124">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-124">string</span></span> | <span data-ttu-id="d88eb-125">网络适配器的名称</span><span class="sxs-lookup"><span data-stu-id="d88eb-125">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="d88eb-126">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-126">string</span></span> | <span data-ttu-id="d88eb-127">网络适配器的 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="d88eb-127">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="d88eb-128">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-128">string</span></span> | <span data-ttu-id="d88eb-129">网络适配器类型。</span><span class="sxs-lookup"><span data-stu-id="d88eb-129">Network adapter type.</span></span> <span data-ttu-id="d88eb-130">有关可能的值，请参阅 [此枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="d88eb-130">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="d88eb-131">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-131">string</span></span> | <span data-ttu-id="d88eb-132">网络适配器的运行状态。</span><span class="sxs-lookup"><span data-stu-id="d88eb-132">Operational status of the network adapter.</span></span> <span data-ttu-id="d88eb-133">有关可能的值，请参阅 [此枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="d88eb-133">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `TunnelType` | <span data-ttu-id="d88eb-134">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-134">string</span></span> | <span data-ttu-id="d88eb-135">隧道协议（如果接口用于此目的，例如 6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH）</span><span class="sxs-lookup"><span data-stu-id="d88eb-135">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="d88eb-136">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-136">string</span></span> | <span data-ttu-id="d88eb-137">适配器连接到的网络。</span><span class="sxs-lookup"><span data-stu-id="d88eb-137">Networks that the adapter is connected to.</span></span> <span data-ttu-id="d88eb-138">每个 JSON 数组都包含网络名称、类别 (公共、专用或域) 、说明以及指示其是否公开连接到 Internet 的标志</span><span class="sxs-lookup"><span data-stu-id="d88eb-138">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="d88eb-139">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-139">string</span></span> | <span data-ttu-id="d88eb-140">JSON 数组格式的 DNS 服务器地址</span><span class="sxs-lookup"><span data-stu-id="d88eb-140">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="d88eb-141">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-141">string</span></span> | <span data-ttu-id="d88eb-142">DHCP 服务器的 IPv4 地址</span><span class="sxs-lookup"><span data-stu-id="d88eb-142">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="d88eb-143">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-143">string</span></span> | <span data-ttu-id="d88eb-144">DHCP 服务器的 IPv6 地址</span><span class="sxs-lookup"><span data-stu-id="d88eb-144">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="d88eb-145">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-145">string</span></span> | <span data-ttu-id="d88eb-146">JSON 数组格式的默认网关地址</span><span class="sxs-lookup"><span data-stu-id="d88eb-146">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="d88eb-147">string</span><span class="sxs-lookup"><span data-stu-id="d88eb-147">string</span></span> | <span data-ttu-id="d88eb-148">包含分配给适配器的所有 IP 地址及其各自的子网前缀和 IP 地址空间（如公共、专用或链接本地）的 JSON 数组</span><span class="sxs-lookup"><span data-stu-id="d88eb-148">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d88eb-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="d88eb-149">Related topics</span></span>
- [<span data-ttu-id="d88eb-150">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="d88eb-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d88eb-151">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="d88eb-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d88eb-152">了解架构</span><span class="sxs-lookup"><span data-stu-id="d88eb-152">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
