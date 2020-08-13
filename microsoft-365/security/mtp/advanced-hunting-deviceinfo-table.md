---
title: 高级搜寻架构中的 DeviceInfo 表
description: 了解高级搜寻架构的 DeviceInfo 表中的操作系统、计算机名称和其他计算机信息
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、machineinfo、DeviceInfo、设备、计算机、OS、平台、用户
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
ms.openlocfilehash: 342e5747f2c59022ffef76f30e4845f26550c88a
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649081"
---
# <a name="deviceinfo"></a><span data-ttu-id="c454e-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="c454e-104">DeviceInfo</span></span>

<span data-ttu-id="c454e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c454e-105">**Applies to:**</span></span>
- <span data-ttu-id="c454e-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="c454e-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="c454e-107">`DeviceInfo`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关组织中的计算机的信息，包括 OS 版本、活动用户和计算机名称。</span><span class="sxs-lookup"><span data-stu-id="c454e-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="c454e-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="c454e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c454e-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="c454e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c454e-110">列名称</span><span class="sxs-lookup"><span data-stu-id="c454e-110">Column name</span></span> | <span data-ttu-id="c454e-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="c454e-111">Data type</span></span> | <span data-ttu-id="c454e-112">说明</span><span class="sxs-lookup"><span data-stu-id="c454e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c454e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c454e-113">datetime</span></span> | <span data-ttu-id="c454e-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="c454e-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c454e-115">string</span><span class="sxs-lookup"><span data-stu-id="c454e-115">string</span></span> | <span data-ttu-id="c454e-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="c454e-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c454e-117">string</span><span class="sxs-lookup"><span data-stu-id="c454e-117">string</span></span> | <span data-ttu-id="c454e-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="c454e-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="c454e-119">string</span><span class="sxs-lookup"><span data-stu-id="c454e-119">string</span></span> | <span data-ttu-id="c454e-120">在计算机上运行的终结点代理或传感器的版本</span><span class="sxs-lookup"><span data-stu-id="c454e-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="c454e-121">string</span><span class="sxs-lookup"><span data-stu-id="c454e-121">string</span></span> | <span data-ttu-id="c454e-122">载入计算机用于连接到 Microsoft Defender ATP 服务的公用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c454e-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="c454e-123">这可以是计算机本身、NAT 设备或代理的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c454e-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="c454e-124">string</span><span class="sxs-lookup"><span data-stu-id="c454e-124">string</span></span> | <span data-ttu-id="c454e-125">计算机上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="c454e-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c454e-126">string</span><span class="sxs-lookup"><span data-stu-id="c454e-126">string</span></span> | <span data-ttu-id="c454e-127">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="c454e-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c454e-128">这表示特定操作系统，包括同一系列内的变体，如 Windows 10 和 Windows 7</span><span class="sxs-lookup"><span data-stu-id="c454e-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="c454e-129">string</span><span class="sxs-lookup"><span data-stu-id="c454e-129">string</span></span> | <span data-ttu-id="c454e-130">计算机上运行的操作系统的内部版本版本</span><span class="sxs-lookup"><span data-stu-id="c454e-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="c454e-131">boolean</span><span class="sxs-lookup"><span data-stu-id="c454e-131">boolean</span></span> | <span data-ttu-id="c454e-132">指示是否已将计算机加入 Azure Active Directory 的布尔指示符</span><span class="sxs-lookup"><span data-stu-id="c454e-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="c454e-133">string</span><span class="sxs-lookup"><span data-stu-id="c454e-133">string</span></span> | <span data-ttu-id="c454e-134">在事件采用 JSON 数组格式时，在计算机上登录的所有用户的列表</span><span class="sxs-lookup"><span data-stu-id="c454e-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="c454e-135">string</span><span class="sxs-lookup"><span data-stu-id="c454e-135">string</span></span> | <span data-ttu-id="c454e-136">通过注册表添加的计算机标记</span><span class="sxs-lookup"><span data-stu-id="c454e-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="c454e-137">long</span><span class="sxs-lookup"><span data-stu-id="c454e-137">long</span></span> | <span data-ttu-id="c454e-138">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="c454e-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c454e-139">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="c454e-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="c454e-140">string</span><span class="sxs-lookup"><span data-stu-id="c454e-140">string</span></span> | <span data-ttu-id="c454e-141">计算机上运行的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="c454e-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="c454e-142">string</span><span class="sxs-lookup"><span data-stu-id="c454e-142">string</span></span> | <span data-ttu-id="c454e-143">计算机的计算机组。</span><span class="sxs-lookup"><span data-stu-id="c454e-143">Machine group of the machine.</span></span> <span data-ttu-id="c454e-144">此组由基于角色的访问控制用于确定对计算机的访问权限</span><span class="sxs-lookup"><span data-stu-id="c454e-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c454e-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="c454e-145">Related topics</span></span>
- [<span data-ttu-id="c454e-146">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="c454e-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c454e-147">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="c454e-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c454e-148">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="c454e-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c454e-149">跨设备、电子邮件、应用和标识的智能寻线</span><span class="sxs-lookup"><span data-stu-id="c454e-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c454e-150">了解架构</span><span class="sxs-lookup"><span data-stu-id="c454e-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c454e-151">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="c454e-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
