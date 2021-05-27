---
title: 高级搜寻架构中的 DeviceInfo 表
description: 了解高级搜寻架构的 DeviceInfo 表中的操作系统、计算机名称和其他计算机信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， machineinfo， DeviceInfo， 设备， 计算机， 操作系统， 平台， 用户
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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689105"
---
# <a name="deviceinfo"></a><span data-ttu-id="c18ed-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="c18ed-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c18ed-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c18ed-105">**Applies to:**</span></span>
- <span data-ttu-id="c18ed-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c18ed-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="c18ed-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c18ed-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="c18ed-108">高级 `DeviceInfo` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关组织中设备的信息，包括操作系统版本、活动用户和计算机名称。</span><span class="sxs-lookup"><span data-stu-id="c18ed-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="c18ed-109">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="c18ed-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c18ed-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="c18ed-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c18ed-111">列名称</span><span class="sxs-lookup"><span data-stu-id="c18ed-111">Column name</span></span> | <span data-ttu-id="c18ed-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="c18ed-112">Data type</span></span> | <span data-ttu-id="c18ed-113">说明</span><span class="sxs-lookup"><span data-stu-id="c18ed-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c18ed-114">datetime</span><span class="sxs-lookup"><span data-stu-id="c18ed-114">datetime</span></span> | <span data-ttu-id="c18ed-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="c18ed-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c18ed-116">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-116">string</span></span> | <span data-ttu-id="c18ed-117">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="c18ed-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c18ed-118">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-118">string</span></span> | <span data-ttu-id="c18ed-119">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="c18ed-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="c18ed-120">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-120">string</span></span> | <span data-ttu-id="c18ed-121">计算机上运行的终结点代理或传感器的版本</span><span class="sxs-lookup"><span data-stu-id="c18ed-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="c18ed-122">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-122">string</span></span> | <span data-ttu-id="c18ed-123">已载入计算机用于连接到 Microsoft Defender for Endpoint 服务的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c18ed-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="c18ed-124">这可能是计算机本身、NAT 设备或代理的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c18ed-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="c18ed-125">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-125">string</span></span> | <span data-ttu-id="c18ed-126">计算机上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="c18ed-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c18ed-127">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-127">string</span></span> | <span data-ttu-id="c18ed-128">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="c18ed-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c18ed-129">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7</span><span class="sxs-lookup"><span data-stu-id="c18ed-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="c18ed-130">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-130">string</span></span> | <span data-ttu-id="c18ed-131">计算机上运行的操作系统的生成版本</span><span class="sxs-lookup"><span data-stu-id="c18ed-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="c18ed-132">boolean</span><span class="sxs-lookup"><span data-stu-id="c18ed-132">boolean</span></span> | <span data-ttu-id="c18ed-133">用于指示计算机是否已加入域的布尔Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c18ed-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="c18ed-134">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-134">string</span></span> | <span data-ttu-id="c18ed-135">Azure AD 中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="c18ed-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="c18ed-136">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-136">string</span></span> | <span data-ttu-id="c18ed-137">事件时以 JSON 数组格式登录的所有用户的列表</span><span class="sxs-lookup"><span data-stu-id="c18ed-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="c18ed-138">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-138">string</span></span> | <span data-ttu-id="c18ed-139">通过注册表添加的机器标记</span><span class="sxs-lookup"><span data-stu-id="c18ed-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="c18ed-140">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-140">string</span></span> | <span data-ttu-id="c18ed-141">计算机上运行的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="c18ed-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="c18ed-142">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-142">string</span></span> | <span data-ttu-id="c18ed-143">计算机的机器组。</span><span class="sxs-lookup"><span data-stu-id="c18ed-143">Machine group of the machine.</span></span> <span data-ttu-id="c18ed-144">基于角色的访问控制使用该组来确定对计算机的访问权限</span><span class="sxs-lookup"><span data-stu-id="c18ed-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="c18ed-145">long</span><span class="sxs-lookup"><span data-stu-id="c18ed-145">long</span></span> | <span data-ttu-id="c18ed-146">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="c18ed-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c18ed-147">若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用</span><span class="sxs-lookup"><span data-stu-id="c18ed-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OnboardingStatus` | <span data-ttu-id="c18ed-148">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-148">string</span></span> | <span data-ttu-id="c18ed-149">指示设备当前是否已载入 Microsoft Defender For Endpoint 或者设备是否不受支持</span><span class="sxs-lookup"><span data-stu-id="c18ed-149">Indicates whether the device is currently onboarded or not to Microsoft Defender For Endpoint or if the device is not supported</span></span> |
|`AdditionalFields` | <span data-ttu-id="c18ed-150">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-150">string</span></span> | <span data-ttu-id="c18ed-151">有关 JSON 数组格式的事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="c18ed-151">Additional information about the event in JSON array format</span></span> |
|`DeviceCategory` | <span data-ttu-id="c18ed-152">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-152">string</span></span> | <span data-ttu-id="c18ed-153">将特定设备类型分组到以下类别的更广泛的分类：终结点、网络设备、IoT、未知</span><span class="sxs-lookup"><span data-stu-id="c18ed-153">Broader classification that groups certain device types under the following categories: Endpoint, Network device, IoT, Unknown</span></span> |
|`DeviceType` | <span data-ttu-id="c18ed-154">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-154">string</span></span> | <span data-ttu-id="c18ed-155">基于目的和功能的设备类型，例如网络设备、工作站、服务器、移动设备、游戏控制台或打印机</span><span class="sxs-lookup"><span data-stu-id="c18ed-155">Type of device based on purpose and functionality, such as network device, workstation, server, mobile, gaming console, or printer</span></span> |
|`DeviceSubType` | <span data-ttu-id="c18ed-156">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-156">string</span></span> | <span data-ttu-id="c18ed-157">某些类型的设备的其他修饰符，例如，移动设备可以是平板电脑或智能手机</span><span class="sxs-lookup"><span data-stu-id="c18ed-157">Additional modifier for certain types of devices, for example, a mobile device can be a tablet or a smartphone</span></span> |
|`Model` | <span data-ttu-id="c18ed-158">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-158">string</span></span> | <span data-ttu-id="c18ed-159">供应商或制造商的产品型号或编号</span><span class="sxs-lookup"><span data-stu-id="c18ed-159">Model name or number of the product from the vendor or manufacturer</span></span> |
|`Vendor` | <span data-ttu-id="c18ed-160">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-160">string</span></span> | <span data-ttu-id="c18ed-161">产品供应商或制造商的名称</span><span class="sxs-lookup"><span data-stu-id="c18ed-161">Name of the product vendor or manufacturer</span></span> |
|`OSDistribution` | <span data-ttu-id="c18ed-162">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-162">string</span></span> | <span data-ttu-id="c18ed-163">操作系统平台的分发，如适用于 Linux 平台的 Ubuntu 或 RedHat</span><span class="sxs-lookup"><span data-stu-id="c18ed-163">Distribution of the OS platform, such as Ubuntu or RedHat for Linux platforms</span></span> |
|`OSVersionInfo` | <span data-ttu-id="c18ed-164">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-164">string</span></span> | <span data-ttu-id="c18ed-165">有关操作系统版本的其他信息，例如常用名称、代码名称或版本号</span><span class="sxs-lookup"><span data-stu-id="c18ed-165">Additional information about the OS version, such as the popular name, code name, or version number</span></span> |
|`MergedDeviceIds` | <span data-ttu-id="c18ed-166">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-166">string</span></span> | <span data-ttu-id="c18ed-167">已分配给同一设备的以前的设备 ID</span><span class="sxs-lookup"><span data-stu-id="c18ed-167">Previous device IDs that have been assigned to the same device</span></span> |
|`MergedToDeviceId` | <span data-ttu-id="c18ed-168">string</span><span class="sxs-lookup"><span data-stu-id="c18ed-168">string</span></span> | <span data-ttu-id="c18ed-169">分配给设备的最新设备 ID</span><span class="sxs-lookup"><span data-stu-id="c18ed-169">The most recent device ID assigned to a device</span></span> |

<span data-ttu-id="c18ed-170">`DeviceInfo`该表提供基于检测信号的设备信息，检测信号是定期报告或来自设备的信号。</span><span class="sxs-lookup"><span data-stu-id="c18ed-170">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="c18ed-171">每隔十五分钟，设备发送包含经常更改的属性（如 ）的部分检测信号 `LoggedOnUsers` 。</span><span class="sxs-lookup"><span data-stu-id="c18ed-171">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="c18ed-172">每天发送一次包含设备属性的完整检测信号。</span><span class="sxs-lookup"><span data-stu-id="c18ed-172">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="c18ed-173">可以使用以下示例查询获取设备的最新状态：</span><span class="sxs-lookup"><span data-stu-id="c18ed-173">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="c18ed-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="c18ed-174">Related topics</span></span>
- [<span data-ttu-id="c18ed-175">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="c18ed-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c18ed-176">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="c18ed-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c18ed-177">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="c18ed-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c18ed-178">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="c18ed-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c18ed-179">了解架构</span><span class="sxs-lookup"><span data-stu-id="c18ed-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c18ed-180">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="c18ed-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
