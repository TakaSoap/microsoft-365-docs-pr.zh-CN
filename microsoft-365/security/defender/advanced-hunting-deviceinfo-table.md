---
title: 高级搜寻架构中的 DeviceInfo 表
description: 了解高级搜寻架构的 DeviceInfo 表中的操作系统、计算机名称和其他计算机信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， machineinfo， DeviceInfo， 设备， 计算机， 操作系统， 平台， 用户
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
ms.openlocfilehash: b5baf4adf9c9abaf746c1d6c3ea1c29c3b471b0b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498603"
---
# <a name="deviceinfo"></a><span data-ttu-id="e0e3f-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="e0e3f-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e0e3f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e0e3f-105">**Applies to:**</span></span>
- <span data-ttu-id="e0e3f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0e3f-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="e0e3f-107">高级 `DeviceInfo` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关组织中设备的信息，包括操作系统版本、活动用户和计算机名称。</span><span class="sxs-lookup"><span data-stu-id="e0e3f-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="e0e3f-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="e0e3f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="e0e3f-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="e0e3f-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e0e3f-110">列名称</span><span class="sxs-lookup"><span data-stu-id="e0e3f-110">Column name</span></span> | <span data-ttu-id="e0e3f-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="e0e3f-111">Data type</span></span> | <span data-ttu-id="e0e3f-112">说明</span><span class="sxs-lookup"><span data-stu-id="e0e3f-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e0e3f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="e0e3f-113">datetime</span></span> | <span data-ttu-id="e0e3f-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="e0e3f-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="e0e3f-115">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-115">string</span></span> | <span data-ttu-id="e0e3f-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="e0e3f-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e0e3f-117">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-117">string</span></span> | <span data-ttu-id="e0e3f-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e0e3f-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="e0e3f-119">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-119">string</span></span> | <span data-ttu-id="e0e3f-120">计算机上运行的终结点代理或传感器的版本</span><span class="sxs-lookup"><span data-stu-id="e0e3f-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="e0e3f-121">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-121">string</span></span> | <span data-ttu-id="e0e3f-122">已载入计算机用于连接到 Microsoft Defender for Endpoint 服务的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e0e3f-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="e0e3f-123">这可能是计算机本身、NAT 设备或代理的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="e0e3f-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="e0e3f-124">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-124">string</span></span> | <span data-ttu-id="e0e3f-125">计算机上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="e0e3f-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="e0e3f-126">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-126">string</span></span> | <span data-ttu-id="e0e3f-127">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="e0e3f-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="e0e3f-128">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7</span><span class="sxs-lookup"><span data-stu-id="e0e3f-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="e0e3f-129">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-129">string</span></span> | <span data-ttu-id="e0e3f-130">计算机上运行的操作系统的生成版本</span><span class="sxs-lookup"><span data-stu-id="e0e3f-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="e0e3f-131">boolean</span><span class="sxs-lookup"><span data-stu-id="e0e3f-131">boolean</span></span> | <span data-ttu-id="e0e3f-132">指示计算机是否已加入 Azure Active Directory 的布尔值指示器</span><span class="sxs-lookup"><span data-stu-id="e0e3f-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="e0e3f-133">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-133">string</span></span> | <span data-ttu-id="e0e3f-134">Azure AD 中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="e0e3f-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="e0e3f-135">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-135">string</span></span> | <span data-ttu-id="e0e3f-136">事件时以 JSON 数组格式登录的所有用户的列表</span><span class="sxs-lookup"><span data-stu-id="e0e3f-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="e0e3f-137">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-137">string</span></span> | <span data-ttu-id="e0e3f-138">通过注册表添加的机器标记</span><span class="sxs-lookup"><span data-stu-id="e0e3f-138">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="e0e3f-139">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-139">string</span></span> | <span data-ttu-id="e0e3f-140">计算机上运行的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="e0e3f-140">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="e0e3f-141">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-141">string</span></span> | <span data-ttu-id="e0e3f-142">计算机的机器组。</span><span class="sxs-lookup"><span data-stu-id="e0e3f-142">Machine group of the machine.</span></span> <span data-ttu-id="e0e3f-143">基于角色的访问控制使用该组来确定对计算机的访问权限</span><span class="sxs-lookup"><span data-stu-id="e0e3f-143">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="e0e3f-144">long</span><span class="sxs-lookup"><span data-stu-id="e0e3f-144">long</span></span> | <span data-ttu-id="e0e3f-145">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="e0e3f-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e0e3f-146">若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用</span><span class="sxs-lookup"><span data-stu-id="e0e3f-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="e0e3f-147">string</span><span class="sxs-lookup"><span data-stu-id="e0e3f-147">string</span></span> | <span data-ttu-id="e0e3f-148">有关 JSON 数组格式的事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="e0e3f-148">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="e0e3f-149">`DeviceInfo`该表提供基于检测信号的设备信息，检测信号是定期报告或来自设备的信号。</span><span class="sxs-lookup"><span data-stu-id="e0e3f-149">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="e0e3f-150">每隔十五分钟，设备发送包含经常更改的属性（如 ）的部分检测信号 `LoggedOnUsers` 。</span><span class="sxs-lookup"><span data-stu-id="e0e3f-150">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="e0e3f-151">每天发送一次包含设备属性的完整检测信号。</span><span class="sxs-lookup"><span data-stu-id="e0e3f-151">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="e0e3f-152">可以使用以下示例查询获取设备的最新状态：</span><span class="sxs-lookup"><span data-stu-id="e0e3f-152">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="e0e3f-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="e0e3f-153">Related topics</span></span>
- [<span data-ttu-id="e0e3f-154">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="e0e3f-154">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e0e3f-155">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="e0e3f-155">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e0e3f-156">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="e0e3f-156">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e0e3f-157">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="e0e3f-157">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e0e3f-158">了解架构</span><span class="sxs-lookup"><span data-stu-id="e0e3f-158">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e0e3f-159">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="e0e3f-159">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
