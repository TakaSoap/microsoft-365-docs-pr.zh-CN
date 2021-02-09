---
title: 高级搜寻架构中的 AppFileEvents 表
description: 在高级搜寻架构的 AppFileEvents 表中了解与云应用和服务关联的文件相关事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， AppFileEvents， Cloud App Security， MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8406d1f9e3d56555b1699d191933c6f9735c9574
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145483"
---
# <a name="appfileevents"></a><span data-ttu-id="89426-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="89426-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="89426-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="89426-105">**Applies to:**</span></span>
- <span data-ttu-id="89426-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89426-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="89426-107">高级 `AppFileEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关 Microsoft Cloud App Security 监视的云应用和服务中的文件相关活动的信息。</span><span class="sxs-lookup"><span data-stu-id="89426-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="89426-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="89426-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="89426-109">有关事件类型的详细信息 (表) 支持的值，请使用安全中心中提供的内置 `ActionType` 架构参考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="89426-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="89426-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="89426-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="89426-111">列名称</span><span class="sxs-lookup"><span data-stu-id="89426-111">Column name</span></span> | <span data-ttu-id="89426-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="89426-112">Data type</span></span> | <span data-ttu-id="89426-113">说明</span><span class="sxs-lookup"><span data-stu-id="89426-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="89426-114">datetime</span><span class="sxs-lookup"><span data-stu-id="89426-114">datetime</span></span> | <span data-ttu-id="89426-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="89426-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="89426-116">string</span><span class="sxs-lookup"><span data-stu-id="89426-116">string</span></span> | <span data-ttu-id="89426-117">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="89426-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="89426-118">有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考</span><span class="sxs-lookup"><span data-stu-id="89426-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="89426-119">string</span><span class="sxs-lookup"><span data-stu-id="89426-119">string</span></span> | <span data-ttu-id="89426-120">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="89426-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="89426-121">string</span><span class="sxs-lookup"><span data-stu-id="89426-121">string</span></span> | <span data-ttu-id="89426-122">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="89426-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="89426-123">string</span><span class="sxs-lookup"><span data-stu-id="89426-123">string</span></span> | <span data-ttu-id="89426-124">包含已记录操作所应用到的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="89426-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="89426-125">string</span><span class="sxs-lookup"><span data-stu-id="89426-125">string</span></span> | <span data-ttu-id="89426-126">由于操作而重命名的文件的原始名称</span><span class="sxs-lookup"><span data-stu-id="89426-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="89426-127">string</span><span class="sxs-lookup"><span data-stu-id="89426-127">string</span></span> | <span data-ttu-id="89426-128">应用录制的操作之前包含文件的原始文件夹</span><span class="sxs-lookup"><span data-stu-id="89426-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="89426-129">string</span><span class="sxs-lookup"><span data-stu-id="89426-129">string</span></span> | <span data-ttu-id="89426-130">使用的网络协议</span><span class="sxs-lookup"><span data-stu-id="89426-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="89426-131">string</span><span class="sxs-lookup"><span data-stu-id="89426-131">string</span></span> | <span data-ttu-id="89426-132">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="89426-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="89426-133">string</span><span class="sxs-lookup"><span data-stu-id="89426-133">string</span></span> | <span data-ttu-id="89426-134">帐户的域</span><span class="sxs-lookup"><span data-stu-id="89426-134">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="89426-135">string</span><span class="sxs-lookup"><span data-stu-id="89426-135">string</span></span> | <span data-ttu-id="89426-136">帐户 (SID) 安全标识符</span><span class="sxs-lookup"><span data-stu-id="89426-136">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="89426-137">string</span><span class="sxs-lookup"><span data-stu-id="89426-137">string</span></span> | <span data-ttu-id="89426-138">帐户的用户主体 (UPN) </span><span class="sxs-lookup"><span data-stu-id="89426-138">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="89426-139">string</span><span class="sxs-lookup"><span data-stu-id="89426-139">string</span></span> | <span data-ttu-id="89426-140">Azure AD 中帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="89426-140">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="89426-141">string</span><span class="sxs-lookup"><span data-stu-id="89426-141">string</span></span> | <span data-ttu-id="89426-142">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="89426-142">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="89426-143">通常是给定或名字、中间初始和姓氏或姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="89426-143">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="89426-144">string</span><span class="sxs-lookup"><span data-stu-id="89426-144">string</span></span> | <span data-ttu-id="89426-145">设备的 FQDN (完全) 域名</span><span class="sxs-lookup"><span data-stu-id="89426-145">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="89426-146">string</span><span class="sxs-lookup"><span data-stu-id="89426-146">string</span></span> | <span data-ttu-id="89426-147">设备类型</span><span class="sxs-lookup"><span data-stu-id="89426-147">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="89426-148">string</span><span class="sxs-lookup"><span data-stu-id="89426-148">string</span></span> | <span data-ttu-id="89426-149">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="89426-149">Platform of the operating system running on the device.</span></span> <span data-ttu-id="89426-150">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="89426-150">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="89426-151">string</span><span class="sxs-lookup"><span data-stu-id="89426-151">string</span></span> | <span data-ttu-id="89426-152">分配给终结点的 IP 地址，在相关的网络通信期间使用</span><span class="sxs-lookup"><span data-stu-id="89426-152">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="89426-153">string</span><span class="sxs-lookup"><span data-stu-id="89426-153">string</span></span> | <span data-ttu-id="89426-154">通信期间使用的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="89426-154">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="89426-155">string</span><span class="sxs-lookup"><span data-stu-id="89426-155">string</span></span> | <span data-ttu-id="89426-156">运行处理所记录操作的服务器应用程序的设备的名称</span><span class="sxs-lookup"><span data-stu-id="89426-156">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="89426-157">string</span><span class="sxs-lookup"><span data-stu-id="89426-157">string</span></span> | <span data-ttu-id="89426-158">运行处理所记录操作的服务器应用程序的设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="89426-158">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="89426-159">string</span><span class="sxs-lookup"><span data-stu-id="89426-159">string</span></span> | <span data-ttu-id="89426-160">相关网络通信的目标端口</span><span class="sxs-lookup"><span data-stu-id="89426-160">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="89426-161">string</span><span class="sxs-lookup"><span data-stu-id="89426-161">string</span></span> | <span data-ttu-id="89426-162">与事件关联的城市、国家/地区或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="89426-162">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="89426-163">string</span><span class="sxs-lookup"><span data-stu-id="89426-163">string</span></span> | <span data-ttu-id="89426-164">Internet 服务提供商 (ISP) 与终结点 IP 地址关联</span><span class="sxs-lookup"><span data-stu-id="89426-164">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="89426-165">long</span><span class="sxs-lookup"><span data-stu-id="89426-165">long</span></span> | <span data-ttu-id="89426-166">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="89426-166">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="89426-167">string</span><span class="sxs-lookup"><span data-stu-id="89426-167">string</span></span> | <span data-ttu-id="89426-168">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="89426-168">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="89426-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="89426-169">Related topics</span></span>
- [<span data-ttu-id="89426-170">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="89426-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="89426-171">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="89426-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="89426-172">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="89426-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="89426-173">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="89426-173">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="89426-174">了解架构</span><span class="sxs-lookup"><span data-stu-id="89426-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="89426-175">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="89426-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
