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
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500834"
---
# <a name="deviceinfo"></a><span data-ttu-id="37f3e-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="37f3e-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37f3e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="37f3e-105">**Applies to:**</span></span>
- [<span data-ttu-id="37f3e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="37f3e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="37f3e-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="37f3e-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="37f3e-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="37f3e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="37f3e-109">高级 `DeviceInfo` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关组织中设备的信息，包括其操作系统版本、活动用户和计算机名称。</span><span class="sxs-lookup"><span data-stu-id="37f3e-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="37f3e-110">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="37f3e-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="37f3e-111">有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="37f3e-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="37f3e-112">列名称</span><span class="sxs-lookup"><span data-stu-id="37f3e-112">Column name</span></span> | <span data-ttu-id="37f3e-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="37f3e-113">Data type</span></span> | <span data-ttu-id="37f3e-114">说明</span><span class="sxs-lookup"><span data-stu-id="37f3e-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="37f3e-115">datetime</span><span class="sxs-lookup"><span data-stu-id="37f3e-115">datetime</span></span> | <span data-ttu-id="37f3e-116">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="37f3e-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="37f3e-117">string</span><span class="sxs-lookup"><span data-stu-id="37f3e-117">string</span></span> | <span data-ttu-id="37f3e-118">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="37f3e-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="37f3e-119">string</span><span class="sxs-lookup"><span data-stu-id="37f3e-119">string</span></span> | <span data-ttu-id="37f3e-120">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="37f3e-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="37f3e-121">string</span><span class="sxs-lookup"><span data-stu-id="37f3e-121">string</span></span> | <span data-ttu-id="37f3e-122">在设备上运行的终结点代理或传感器的版本</span><span class="sxs-lookup"><span data-stu-id="37f3e-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="37f3e-123">string</span><span class="sxs-lookup"><span data-stu-id="37f3e-123">string</span></span> | <span data-ttu-id="37f3e-124">已载入设备用于连接到 Defender for Endpoint 服务的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="37f3e-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="37f3e-125">这可能是设备本身、NAT 设备或代理的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="37f3e-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="37f3e-126">string</span><span class="sxs-lookup"><span data-stu-id="37f3e-126">string</span></span> | <span data-ttu-id="37f3e-127">在设备上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="37f3e-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="37f3e-128">string</span><span class="sxs-lookup"><span data-stu-id="37f3e-128">string</span></span> | <span data-ttu-id="37f3e-129">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="37f3e-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="37f3e-130">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7</span><span class="sxs-lookup"><span data-stu-id="37f3e-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="37f3e-131">string</span><span class="sxs-lookup"><span data-stu-id="37f3e-131">string</span></span> | <span data-ttu-id="37f3e-132">在设备上运行的操作系统的生成版本</span><span class="sxs-lookup"><span data-stu-id="37f3e-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="37f3e-133">boolean</span><span class="sxs-lookup"><span data-stu-id="37f3e-133">boolean</span></span> | <span data-ttu-id="37f3e-134">指示设备是否已加入 Azure Active Directory 的布尔值指示器</span><span class="sxs-lookup"><span data-stu-id="37f3e-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="37f3e-135">string</span><span class="sxs-lookup"><span data-stu-id="37f3e-135">string</span></span> | <span data-ttu-id="37f3e-136">事件时以 JSON 数组格式登录设备的所有用户列表</span><span class="sxs-lookup"><span data-stu-id="37f3e-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="37f3e-137">string</span><span class="sxs-lookup"><span data-stu-id="37f3e-137">string</span></span> | <span data-ttu-id="37f3e-138">通过注册表添加的设备标记</span><span class="sxs-lookup"><span data-stu-id="37f3e-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="37f3e-139">long</span><span class="sxs-lookup"><span data-stu-id="37f3e-139">long</span></span> | <span data-ttu-id="37f3e-140">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="37f3e-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="37f3e-141">若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用</span><span class="sxs-lookup"><span data-stu-id="37f3e-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="37f3e-142">string</span><span class="sxs-lookup"><span data-stu-id="37f3e-142">string</span></span> | <span data-ttu-id="37f3e-143">在设备上运行的操作系统的版本</span><span class="sxs-lookup"><span data-stu-id="37f3e-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="37f3e-144">string</span><span class="sxs-lookup"><span data-stu-id="37f3e-144">string</span></span> | <span data-ttu-id="37f3e-145">计算机的机器组。</span><span class="sxs-lookup"><span data-stu-id="37f3e-145">Machine group of the machine.</span></span> <span data-ttu-id="37f3e-146">基于角色的访问控制使用该组来确定对计算机的访问权限</span><span class="sxs-lookup"><span data-stu-id="37f3e-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="37f3e-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="37f3e-147">Related topics</span></span>
- [<span data-ttu-id="37f3e-148">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="37f3e-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="37f3e-149">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="37f3e-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="37f3e-150">了解架构</span><span class="sxs-lookup"><span data-stu-id="37f3e-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
