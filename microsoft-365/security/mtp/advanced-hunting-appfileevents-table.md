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
ms.openlocfilehash: 9eb2f195959409ad25b9a401a44425cc4af7f97e
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712494"
---
# <a name="appfileevents"></a><span data-ttu-id="7607c-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="7607c-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7607c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7607c-105">**Applies to:**</span></span>
- <span data-ttu-id="7607c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7607c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7607c-107">高级 `AppFileEvents` 搜寻架构 [中的](advanced-hunting-overview.md) 表包含有关 Microsoft Cloud App Security 监视的云应用和服务中的文件相关活动的信息。</span><span class="sxs-lookup"><span data-stu-id="7607c-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="7607c-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="7607c-108">Use this reference to construct queries that return information from this table.</span></span>

>[!WARNING]
><span data-ttu-id="7607c-109">此表将很快停用。</span><span class="sxs-lookup"><span data-stu-id="7607c-109">This table will be retired soon.</span></span> <span data-ttu-id="7607c-110">自 2021 年 3 月 7 日起， `AppFileEvents` 该表不再记录记录。</span><span class="sxs-lookup"><span data-stu-id="7607c-110">As of March 7, 2021, the `AppFileEvents` table is no longer logging records.</span></span> <span data-ttu-id="7607c-111">用户应改为使用 [CloudAppEvents](advanced-hunting-cloudappevents-table.md) 表，以在超过该日期的云服务中搜寻与文件相关的活动。</span><span class="sxs-lookup"><span data-stu-id="7607c-111">Users hunting through file-related activities in cloud services on and beyond the said date should use the [CloudAppEvents](advanced-hunting-cloudappevents-table.md) table instead.</span></span> <br><br><span data-ttu-id="7607c-112">请确保搜索仍在使用该表的查询和自定义检测规则， `AppFileEvents` 并编辑它们以使用 `CloudAppEvents` 该表。</span><span class="sxs-lookup"><span data-stu-id="7607c-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="7607c-113">有关转换受影响的查询的更多指南，可在 [使用 Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)高级搜寻的云应用活动中找到 Hunt。</span><span class="sxs-lookup"><span data-stu-id="7607c-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="7607c-114">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="7607c-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7607c-115">列名称</span><span class="sxs-lookup"><span data-stu-id="7607c-115">Column name</span></span> | <span data-ttu-id="7607c-116">数据类型</span><span class="sxs-lookup"><span data-stu-id="7607c-116">Data type</span></span> | <span data-ttu-id="7607c-117">说明</span><span class="sxs-lookup"><span data-stu-id="7607c-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7607c-118">datetime</span><span class="sxs-lookup"><span data-stu-id="7607c-118">datetime</span></span> | <span data-ttu-id="7607c-119">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="7607c-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="7607c-120">string</span><span class="sxs-lookup"><span data-stu-id="7607c-120">string</span></span> | <span data-ttu-id="7607c-121">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="7607c-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="7607c-122">有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考</span><span class="sxs-lookup"><span data-stu-id="7607c-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="7607c-123">string</span><span class="sxs-lookup"><span data-stu-id="7607c-123">string</span></span> | <span data-ttu-id="7607c-124">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="7607c-124">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="7607c-125">string</span><span class="sxs-lookup"><span data-stu-id="7607c-125">string</span></span> | <span data-ttu-id="7607c-126">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="7607c-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="7607c-127">string</span><span class="sxs-lookup"><span data-stu-id="7607c-127">string</span></span> | <span data-ttu-id="7607c-128">包含已记录操作所应用到的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="7607c-128">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="7607c-129">string</span><span class="sxs-lookup"><span data-stu-id="7607c-129">string</span></span> | <span data-ttu-id="7607c-130">由于操作而重命名的文件的原始名称</span><span class="sxs-lookup"><span data-stu-id="7607c-130">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="7607c-131">string</span><span class="sxs-lookup"><span data-stu-id="7607c-131">string</span></span> | <span data-ttu-id="7607c-132">应用录制的操作之前包含文件的原始文件夹</span><span class="sxs-lookup"><span data-stu-id="7607c-132">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="7607c-133">string</span><span class="sxs-lookup"><span data-stu-id="7607c-133">string</span></span> | <span data-ttu-id="7607c-134">使用的网络协议</span><span class="sxs-lookup"><span data-stu-id="7607c-134">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="7607c-135">string</span><span class="sxs-lookup"><span data-stu-id="7607c-135">string</span></span> | <span data-ttu-id="7607c-136">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="7607c-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="7607c-137">string</span><span class="sxs-lookup"><span data-stu-id="7607c-137">string</span></span> | <span data-ttu-id="7607c-138">帐户的域</span><span class="sxs-lookup"><span data-stu-id="7607c-138">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="7607c-139">string</span><span class="sxs-lookup"><span data-stu-id="7607c-139">string</span></span> | <span data-ttu-id="7607c-140">帐户 (SID) 安全标识符</span><span class="sxs-lookup"><span data-stu-id="7607c-140">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="7607c-141">string</span><span class="sxs-lookup"><span data-stu-id="7607c-141">string</span></span> | <span data-ttu-id="7607c-142">帐户 (UPN) 用户主体名称</span><span class="sxs-lookup"><span data-stu-id="7607c-142">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="7607c-143">string</span><span class="sxs-lookup"><span data-stu-id="7607c-143">string</span></span> | <span data-ttu-id="7607c-144">Azure AD 中帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="7607c-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="7607c-145">string</span><span class="sxs-lookup"><span data-stu-id="7607c-145">string</span></span> | <span data-ttu-id="7607c-146">通讯簿中显示的帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="7607c-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="7607c-147">通常，给定或名字、中间初始和姓氏或姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="7607c-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="7607c-148">string</span><span class="sxs-lookup"><span data-stu-id="7607c-148">string</span></span> | <span data-ttu-id="7607c-149">设备的 FQDN (完全) 域名</span><span class="sxs-lookup"><span data-stu-id="7607c-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="7607c-150">string</span><span class="sxs-lookup"><span data-stu-id="7607c-150">string</span></span> | <span data-ttu-id="7607c-151">设备类型</span><span class="sxs-lookup"><span data-stu-id="7607c-151">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="7607c-152">string</span><span class="sxs-lookup"><span data-stu-id="7607c-152">string</span></span> | <span data-ttu-id="7607c-153">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="7607c-153">Platform of the operating system running on the device.</span></span> <span data-ttu-id="7607c-154">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="7607c-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="7607c-155">string</span><span class="sxs-lookup"><span data-stu-id="7607c-155">string</span></span> | <span data-ttu-id="7607c-156">分配给终结点的 IP 地址，在相关网络通信期间使用</span><span class="sxs-lookup"><span data-stu-id="7607c-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="7607c-157">string</span><span class="sxs-lookup"><span data-stu-id="7607c-157">string</span></span> | <span data-ttu-id="7607c-158">通信期间使用的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="7607c-158">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="7607c-159">string</span><span class="sxs-lookup"><span data-stu-id="7607c-159">string</span></span> | <span data-ttu-id="7607c-160">运行处理所记录操作的服务器应用程序的设备的名称</span><span class="sxs-lookup"><span data-stu-id="7607c-160">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="7607c-161">string</span><span class="sxs-lookup"><span data-stu-id="7607c-161">string</span></span> | <span data-ttu-id="7607c-162">运行处理所记录操作的服务器应用程序的设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="7607c-162">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="7607c-163">string</span><span class="sxs-lookup"><span data-stu-id="7607c-163">string</span></span> | <span data-ttu-id="7607c-164">相关网络通信的目标端口</span><span class="sxs-lookup"><span data-stu-id="7607c-164">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="7607c-165">string</span><span class="sxs-lookup"><span data-stu-id="7607c-165">string</span></span> | <span data-ttu-id="7607c-166">与事件关联的城市、国家/地区或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="7607c-166">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="7607c-167">string</span><span class="sxs-lookup"><span data-stu-id="7607c-167">string</span></span> | <span data-ttu-id="7607c-168">Internet 服务提供商 (ISP) 与终结点 IP 地址关联</span><span class="sxs-lookup"><span data-stu-id="7607c-168">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="7607c-169">long</span><span class="sxs-lookup"><span data-stu-id="7607c-169">long</span></span> | <span data-ttu-id="7607c-170">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="7607c-170">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="7607c-171">string</span><span class="sxs-lookup"><span data-stu-id="7607c-171">string</span></span> | <span data-ttu-id="7607c-172">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="7607c-172">Additional information about the entity or event</span></span> |

>[!TIP]
> <span data-ttu-id="7607c-173">有关事件类型的详细信息 (表) 支持的值，请使用安全中心中提供的内置 `ActionType` 架构引用。</span><span class="sxs-lookup"><span data-stu-id="7607c-173">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>


## <a name="related-topics"></a><span data-ttu-id="7607c-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="7607c-174">Related topics</span></span>
- [<span data-ttu-id="7607c-175">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="7607c-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7607c-176">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="7607c-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7607c-177">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="7607c-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7607c-178">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="7607c-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7607c-179">了解架构</span><span class="sxs-lookup"><span data-stu-id="7607c-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7607c-180">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="7607c-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
