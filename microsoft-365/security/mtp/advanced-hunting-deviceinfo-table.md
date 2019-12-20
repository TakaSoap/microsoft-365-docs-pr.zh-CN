---
title: 高级搜寻架构中的 DeviceInfo 表
description: 了解高级搜寻架构的 DeviceInfo 表中的操作系统、计算机名称和其他计算机信息
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、machineinfo、DeviceInfo、设备、计算机、OS、平台、用户
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1141447de9b7ac714fb200dab56c4c2e8d75a05d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809245"
---
# <a name="deviceinfo"></a><span data-ttu-id="5fb1d-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="5fb1d-104">DeviceInfo</span></span>

<span data-ttu-id="5fb1d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5fb1d-105">**Applies to:**</span></span>
- <span data-ttu-id="5fb1d-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="5fb1d-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="5fb1d-107">`DeviceInfo` [高级搜寻](advanced-hunting-overview.md)架构中的表包含有关组织中的计算机的信息，包括 OS 版本、活动用户和计算机名称。</span><span class="sxs-lookup"><span data-stu-id="5fb1d-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="5fb1d-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="5fb1d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="5fb1d-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5fb1d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5fb1d-110">列名称</span><span class="sxs-lookup"><span data-stu-id="5fb1d-110">Column name</span></span> | <span data-ttu-id="5fb1d-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="5fb1d-111">Data type</span></span> | <span data-ttu-id="5fb1d-112">说明</span><span class="sxs-lookup"><span data-stu-id="5fb1d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5fb1d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5fb1d-113">datetime</span></span> | <span data-ttu-id="5fb1d-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="5fb1d-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="5fb1d-115">string</span><span class="sxs-lookup"><span data-stu-id="5fb1d-115">string</span></span> | <span data-ttu-id="5fb1d-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="5fb1d-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5fb1d-117">string</span><span class="sxs-lookup"><span data-stu-id="5fb1d-117">string</span></span> | <span data-ttu-id="5fb1d-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="5fb1d-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="5fb1d-119">string</span><span class="sxs-lookup"><span data-stu-id="5fb1d-119">string</span></span> | <span data-ttu-id="5fb1d-120">在计算机上运行的终结点代理或传感器的版本</span><span class="sxs-lookup"><span data-stu-id="5fb1d-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="5fb1d-121">string</span><span class="sxs-lookup"><span data-stu-id="5fb1d-121">string</span></span> | <span data-ttu-id="5fb1d-122">载入计算机用于连接到 Microsoft Defender ATP 服务的公用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5fb1d-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="5fb1d-123">这可以是计算机本身、NAT 设备或代理的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="5fb1d-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="5fb1d-124">string</span><span class="sxs-lookup"><span data-stu-id="5fb1d-124">string</span></span> | <span data-ttu-id="5fb1d-125">计算机上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="5fb1d-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="5fb1d-126">string</span><span class="sxs-lookup"><span data-stu-id="5fb1d-126">string</span></span> | <span data-ttu-id="5fb1d-127">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="5fb1d-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="5fb1d-128">这表示特定操作系统，包括同一系列内的变体，如 Windows 10 和 Windows 7</span><span class="sxs-lookup"><span data-stu-id="5fb1d-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="5fb1d-129">string</span><span class="sxs-lookup"><span data-stu-id="5fb1d-129">string</span></span> | <span data-ttu-id="5fb1d-130">计算机上运行的操作系统的内部版本版本</span><span class="sxs-lookup"><span data-stu-id="5fb1d-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="5fb1d-131">boolean</span><span class="sxs-lookup"><span data-stu-id="5fb1d-131">boolean</span></span> | <span data-ttu-id="5fb1d-132">指示是否已将计算机加入 Azure Active Directory 的布尔指示符</span><span class="sxs-lookup"><span data-stu-id="5fb1d-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="5fb1d-133">string</span><span class="sxs-lookup"><span data-stu-id="5fb1d-133">string</span></span> | <span data-ttu-id="5fb1d-134">在事件采用 JSON 数组格式时，在计算机上登录的所有用户的列表</span><span class="sxs-lookup"><span data-stu-id="5fb1d-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="5fb1d-135">string</span><span class="sxs-lookup"><span data-stu-id="5fb1d-135">string</span></span> | <span data-ttu-id="5fb1d-136">通过注册表添加的计算机标记</span><span class="sxs-lookup"><span data-stu-id="5fb1d-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="5fb1d-137">long</span><span class="sxs-lookup"><span data-stu-id="5fb1d-137">long</span></span> | <span data-ttu-id="5fb1d-138">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="5fb1d-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="5fb1d-139">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="5fb1d-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="5fb1d-140">string</span><span class="sxs-lookup"><span data-stu-id="5fb1d-140">string</span></span> | <span data-ttu-id="5fb1d-141">计算机上运行的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="5fb1d-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="5fb1d-142">string</span><span class="sxs-lookup"><span data-stu-id="5fb1d-142">string</span></span> | <span data-ttu-id="5fb1d-143">计算机的计算机组。</span><span class="sxs-lookup"><span data-stu-id="5fb1d-143">Machine group of the machine.</span></span> <span data-ttu-id="5fb1d-144">此组由基于角色的访问控制用于确定对计算机的访问权限</span><span class="sxs-lookup"><span data-stu-id="5fb1d-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5fb1d-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="5fb1d-145">Related topics</span></span>
- [<span data-ttu-id="5fb1d-146">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="5fb1d-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5fb1d-147">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="5fb1d-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5fb1d-148">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="5fb1d-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5fb1d-149">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="5fb1d-149">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5fb1d-150">了解架构</span><span class="sxs-lookup"><span data-stu-id="5fb1d-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5fb1d-151">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="5fb1d-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)