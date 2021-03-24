---
title: 高级搜寻架构中的 DeviceInfo 表
description: 了解高级搜寻架构的 DeviceInfo 表中的操作系统、计算机名称和其他设备信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， deviceinfo， 设备， 操作系统， 平台， 用户， DeviceInfo
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
ms.technology: mde
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056159"
---
# <a name="deviceinfo"></a><span data-ttu-id="2863d-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="2863d-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2863d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2863d-105">**Applies to:**</span></span>
- [<span data-ttu-id="2863d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2863d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="2863d-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="2863d-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2863d-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2863d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="2863d-109">高级 `DeviceInfo` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关组织中设备的信息，包括其操作系统版本、活动用户和计算机名称。</span><span class="sxs-lookup"><span data-stu-id="2863d-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="2863d-110">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="2863d-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="2863d-111">有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="2863d-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="2863d-112">列名称</span><span class="sxs-lookup"><span data-stu-id="2863d-112">Column name</span></span> | <span data-ttu-id="2863d-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="2863d-113">Data type</span></span> | <span data-ttu-id="2863d-114">说明</span><span class="sxs-lookup"><span data-stu-id="2863d-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2863d-115">datetime</span><span class="sxs-lookup"><span data-stu-id="2863d-115">datetime</span></span> | <span data-ttu-id="2863d-116">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="2863d-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="2863d-117">string</span><span class="sxs-lookup"><span data-stu-id="2863d-117">string</span></span> | <span data-ttu-id="2863d-118">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="2863d-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2863d-119">string</span><span class="sxs-lookup"><span data-stu-id="2863d-119">string</span></span> | <span data-ttu-id="2863d-120">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="2863d-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="2863d-121">string</span><span class="sxs-lookup"><span data-stu-id="2863d-121">string</span></span> | <span data-ttu-id="2863d-122">在设备上运行的终结点代理或传感器的版本</span><span class="sxs-lookup"><span data-stu-id="2863d-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="2863d-123">string</span><span class="sxs-lookup"><span data-stu-id="2863d-123">string</span></span> | <span data-ttu-id="2863d-124">已载入设备用于连接到 Defender for Endpoint 服务的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2863d-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="2863d-125">这可能是设备本身、NAT 设备或代理的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="2863d-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="2863d-126">string</span><span class="sxs-lookup"><span data-stu-id="2863d-126">string</span></span> | <span data-ttu-id="2863d-127">在设备上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="2863d-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="2863d-128">string</span><span class="sxs-lookup"><span data-stu-id="2863d-128">string</span></span> | <span data-ttu-id="2863d-129">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="2863d-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2863d-130">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7</span><span class="sxs-lookup"><span data-stu-id="2863d-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="2863d-131">string</span><span class="sxs-lookup"><span data-stu-id="2863d-131">string</span></span> | <span data-ttu-id="2863d-132">在设备上运行的操作系统的生成版本</span><span class="sxs-lookup"><span data-stu-id="2863d-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="2863d-133">boolean</span><span class="sxs-lookup"><span data-stu-id="2863d-133">boolean</span></span> | <span data-ttu-id="2863d-134">指示设备是否已加入 Azure Active Directory 的布尔值指示器</span><span class="sxs-lookup"><span data-stu-id="2863d-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="2863d-135">string</span><span class="sxs-lookup"><span data-stu-id="2863d-135">string</span></span> | <span data-ttu-id="2863d-136">事件时以 JSON 数组格式登录设备的所有用户列表</span><span class="sxs-lookup"><span data-stu-id="2863d-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="2863d-137">string</span><span class="sxs-lookup"><span data-stu-id="2863d-137">string</span></span> | <span data-ttu-id="2863d-138">通过注册表添加的设备标记</span><span class="sxs-lookup"><span data-stu-id="2863d-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="2863d-139">long</span><span class="sxs-lookup"><span data-stu-id="2863d-139">long</span></span> | <span data-ttu-id="2863d-140">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="2863d-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="2863d-141">若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用</span><span class="sxs-lookup"><span data-stu-id="2863d-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="2863d-142">string</span><span class="sxs-lookup"><span data-stu-id="2863d-142">string</span></span> | <span data-ttu-id="2863d-143">在设备上运行的操作系统的版本</span><span class="sxs-lookup"><span data-stu-id="2863d-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="2863d-144">string</span><span class="sxs-lookup"><span data-stu-id="2863d-144">string</span></span> | <span data-ttu-id="2863d-145">计算机的机器组。</span><span class="sxs-lookup"><span data-stu-id="2863d-145">Machine group of the machine.</span></span> <span data-ttu-id="2863d-146">基于角色的访问控制使用该组来确定对计算机的访问权限</span><span class="sxs-lookup"><span data-stu-id="2863d-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2863d-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="2863d-147">Related topics</span></span>
- [<span data-ttu-id="2863d-148">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="2863d-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2863d-149">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="2863d-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2863d-150">了解架构</span><span class="sxs-lookup"><span data-stu-id="2863d-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
