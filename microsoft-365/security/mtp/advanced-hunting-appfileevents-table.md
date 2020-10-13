---
title: 高级搜寻架构中的 AppFileEvents 表
description: 了解与高级搜寻架构的 AppFileEvents 表中的云应用和服务关联的与文件相关的事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、AppFileEvents、云应用安全性、MCAS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 5cab6e3fe7a3b4b74989dde360c03d58e0bad46f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430147"
---
# <a name="appfileevents"></a><span data-ttu-id="8ba6a-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="8ba6a-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8ba6a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8ba6a-105">**Applies to:**</span></span>
- <span data-ttu-id="8ba6a-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="8ba6a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8ba6a-107">`AppFileEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关 Microsoft 云应用安全监视的云应用和服务中与文件相关的活动的信息。</span><span class="sxs-lookup"><span data-stu-id="8ba6a-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="8ba6a-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="8ba6a-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="8ba6a-109">若要详细了解表支持的事件类型 (`ActionType` 值) ，请使用 "安全中心" 中提供的 [内置架构引用](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。</span><span class="sxs-lookup"><span data-stu-id="8ba6a-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="8ba6a-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba6a-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8ba6a-111">列名称</span><span class="sxs-lookup"><span data-stu-id="8ba6a-111">Column name</span></span> | <span data-ttu-id="8ba6a-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="8ba6a-112">Data type</span></span> | <span data-ttu-id="8ba6a-113">说明</span><span class="sxs-lookup"><span data-stu-id="8ba6a-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8ba6a-114">datetime</span><span class="sxs-lookup"><span data-stu-id="8ba6a-114">datetime</span></span> | <span data-ttu-id="8ba6a-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="8ba6a-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="8ba6a-116">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-116">string</span></span> | <span data-ttu-id="8ba6a-117">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="8ba6a-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="8ba6a-118">有关详细信息，请参阅[在门户架构参考中](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="8ba6a-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="8ba6a-119">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-119">string</span></span> | <span data-ttu-id="8ba6a-120">执行录制操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="8ba6a-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="8ba6a-121">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-121">string</span></span> | <span data-ttu-id="8ba6a-122">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="8ba6a-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="8ba6a-123">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-123">string</span></span> | <span data-ttu-id="8ba6a-124">包含录制的操作所应用于的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="8ba6a-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="8ba6a-125">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-125">string</span></span> | <span data-ttu-id="8ba6a-126">作为操作的结果重命名的文件的原始名称</span><span class="sxs-lookup"><span data-stu-id="8ba6a-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="8ba6a-127">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-127">string</span></span> | <span data-ttu-id="8ba6a-128">在应用录制的操作之前包含文件的原始文件夹</span><span class="sxs-lookup"><span data-stu-id="8ba6a-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="8ba6a-129">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-129">string</span></span> | <span data-ttu-id="8ba6a-130">使用的网络协议</span><span class="sxs-lookup"><span data-stu-id="8ba6a-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="8ba6a-131">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-131">string</span></span> | <span data-ttu-id="8ba6a-132">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="8ba6a-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="8ba6a-133">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-133">string</span></span> | <span data-ttu-id="8ba6a-134">帐户的域</span><span class="sxs-lookup"><span data-stu-id="8ba6a-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="8ba6a-135">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-135">string</span></span> | <span data-ttu-id="8ba6a-136">帐户的用户主体名称 (UPN) </span><span class="sxs-lookup"><span data-stu-id="8ba6a-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="8ba6a-137">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-137">string</span></span> | <span data-ttu-id="8ba6a-138">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="8ba6a-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="8ba6a-139">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-139">string</span></span> | <span data-ttu-id="8ba6a-140">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="8ba6a-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="8ba6a-141">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="8ba6a-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="8ba6a-142">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-142">string</span></span> | <span data-ttu-id="8ba6a-143">设备 (FQDN) 的完全限定的域名称</span><span class="sxs-lookup"><span data-stu-id="8ba6a-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="8ba6a-144">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-144">string</span></span> | <span data-ttu-id="8ba6a-145">设备类型</span><span class="sxs-lookup"><span data-stu-id="8ba6a-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="8ba6a-146">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-146">string</span></span> | <span data-ttu-id="8ba6a-147">设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="8ba6a-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="8ba6a-148">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="8ba6a-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="8ba6a-149">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-149">string</span></span> | <span data-ttu-id="8ba6a-150">分配给终结点的 IP 地址，并在相关的网络通信过程中使用</span><span class="sxs-lookup"><span data-stu-id="8ba6a-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="8ba6a-151">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-151">string</span></span> | <span data-ttu-id="8ba6a-152">运行处理录制操作的服务器应用程序的设备的名称</span><span class="sxs-lookup"><span data-stu-id="8ba6a-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="8ba6a-153">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-153">string</span></span> | <span data-ttu-id="8ba6a-154">运行用于处理录制操作的服务器应用程序的设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8ba6a-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="8ba6a-155">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-155">string</span></span> | <span data-ttu-id="8ba6a-156">与事件关联的城市、国家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="8ba6a-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="8ba6a-157">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-157">string</span></span> | <span data-ttu-id="8ba6a-158">Internet 服务提供商 (与终结点 IP 地址关联的 ISP) </span><span class="sxs-lookup"><span data-stu-id="8ba6a-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="8ba6a-159">long</span><span class="sxs-lookup"><span data-stu-id="8ba6a-159">long</span></span> | <span data-ttu-id="8ba6a-160">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="8ba6a-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="8ba6a-161">string</span><span class="sxs-lookup"><span data-stu-id="8ba6a-161">string</span></span> | <span data-ttu-id="8ba6a-162">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="8ba6a-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8ba6a-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="8ba6a-163">Related topics</span></span>
- [<span data-ttu-id="8ba6a-164">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="8ba6a-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8ba6a-165">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="8ba6a-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8ba6a-166">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="8ba6a-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8ba6a-167">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="8ba6a-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8ba6a-168">了解架构</span><span class="sxs-lookup"><span data-stu-id="8ba6a-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8ba6a-169">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="8ba6a-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
