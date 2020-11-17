---
title: 高级搜寻架构中的 CloudAppEvents 表
description: 了解高级搜寻架构的 CloudAppEvents 表中的云应用和服务中的事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、CloudAppEvents、云应用安全性、MCAS
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087760"
---
# <a name="cloudappevents"></a><span data-ttu-id="6d7cd-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="6d7cd-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6d7cd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6d7cd-105">**Applies to:**</span></span>
- <span data-ttu-id="6d7cd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d7cd-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="6d7cd-107">当前在预览中， `CloudAppEvents` [高级搜寻](advanced-hunting-overview.md) 架构中的表格包含有关各种云应用和服务（尤其是 Microsoft 团队和 Exchange Online）中的活动的信息。</span><span class="sxs-lookup"><span data-stu-id="6d7cd-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="6d7cd-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="6d7cd-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6d7cd-109">此表将展开以包含 Microsoft 云应用安全监视的更多活动。</span><span class="sxs-lookup"><span data-stu-id="6d7cd-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="6d7cd-110">最终，此表将包含当前存储在 [AppFileEvents](advanced-hunting-appfileevents-table.md) 表中的文件活动。</span><span class="sxs-lookup"><span data-stu-id="6d7cd-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="6d7cd-111">当更多数据移动到此表中时，Microsoft 将提供其他指导。</span><span class="sxs-lookup"><span data-stu-id="6d7cd-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="6d7cd-112">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="6d7cd-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6d7cd-113">列名称</span><span class="sxs-lookup"><span data-stu-id="6d7cd-113">Column name</span></span> | <span data-ttu-id="6d7cd-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="6d7cd-114">Data type</span></span> | <span data-ttu-id="6d7cd-115">说明</span><span class="sxs-lookup"><span data-stu-id="6d7cd-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6d7cd-116">datetime</span><span class="sxs-lookup"><span data-stu-id="6d7cd-116">datetime</span></span> | <span data-ttu-id="6d7cd-117">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="6d7cd-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="6d7cd-118">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-118">string</span></span> | <span data-ttu-id="6d7cd-119">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="6d7cd-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="6d7cd-120">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-120">string</span></span> | <span data-ttu-id="6d7cd-121">执行录制操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="6d7cd-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="6d7cd-122">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-122">string</span></span> | <span data-ttu-id="6d7cd-123">应用程序的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="6d7cd-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="6d7cd-124">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-124">string</span></span> | <span data-ttu-id="6d7cd-125">Azure Active Directory 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="6d7cd-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="6d7cd-126">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-126">string</span></span> | <span data-ttu-id="6d7cd-127">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="6d7cd-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="6d7cd-128">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="6d7cd-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="6d7cd-129">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-129">string</span></span> | <span data-ttu-id="6d7cd-130">指示活动是否由管理员执行</span><span class="sxs-lookup"><span data-stu-id="6d7cd-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="6d7cd-131">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-131">string</span></span> | <span data-ttu-id="6d7cd-132">基于用途和功能的设备类型，如 "网络设备"、"工作站"、"服务器"、"移动"、"游戏控制台" 或 "打印机"</span><span class="sxs-lookup"><span data-stu-id="6d7cd-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="6d7cd-133">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-133">string</span></span> | <span data-ttu-id="6d7cd-134">设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="6d7cd-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6d7cd-135">此列指示特定操作系统，包括同一系列内的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="6d7cd-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="6d7cd-136">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-136">string</span></span> | <span data-ttu-id="6d7cd-137">分配给终结点的 IP 地址，并在相关的网络通信过程中使用</span><span class="sxs-lookup"><span data-stu-id="6d7cd-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="6d7cd-138">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-138">string</span></span> | <span data-ttu-id="6d7cd-139">指示 IP 地址是否属于已知的匿名代理</span><span class="sxs-lookup"><span data-stu-id="6d7cd-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="6d7cd-140">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-140">string</span></span> | <span data-ttu-id="6d7cd-141">指示客户端 IP 地址所在国家/地区的两个字母的代码 geolocated</span><span class="sxs-lookup"><span data-stu-id="6d7cd-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="6d7cd-142">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-142">string</span></span> | <span data-ttu-id="6d7cd-143">客户端 IP 地址为 "geolocated" 的城市</span><span class="sxs-lookup"><span data-stu-id="6d7cd-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="6d7cd-144">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-144">string</span></span> | <span data-ttu-id="6d7cd-145">Internet 服务提供商 (与 IP 地址关联的 ISP) </span><span class="sxs-lookup"><span data-stu-id="6d7cd-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="6d7cd-146">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-146">string</span></span> | <span data-ttu-id="6d7cd-147">来自 web 浏览器或其他客户端应用程序的用户代理信息</span><span class="sxs-lookup"><span data-stu-id="6d7cd-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="6d7cd-148">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-148">string</span></span> | <span data-ttu-id="6d7cd-149">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="6d7cd-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="6d7cd-150">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-150">string</span></span> | <span data-ttu-id="6d7cd-151">录制的活动中涉及的对象（如文件或文件夹）的列表</span><span class="sxs-lookup"><span data-stu-id="6d7cd-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="6d7cd-152">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-152">string</span></span> | <span data-ttu-id="6d7cd-153">将录制的操作应用于的对象的名称</span><span class="sxs-lookup"><span data-stu-id="6d7cd-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="6d7cd-154">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-154">string</span></span> | <span data-ttu-id="6d7cd-155">将录制的操作应用于的对象的类型（如文件或文件夹）</span><span class="sxs-lookup"><span data-stu-id="6d7cd-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="6d7cd-156">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-156">string</span></span> | <span data-ttu-id="6d7cd-157">应用录制的操作的对象的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="6d7cd-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="6d7cd-158">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-158">string</span></span> | <span data-ttu-id="6d7cd-159">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="6d7cd-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="6d7cd-160">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-160">string</span></span> | <span data-ttu-id="6d7cd-161">来自 JSON 格式的源应用程序或服务的原始事件信息</span><span class="sxs-lookup"><span data-stu-id="6d7cd-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="6d7cd-162">string</span><span class="sxs-lookup"><span data-stu-id="6d7cd-162">string</span></span> | <span data-ttu-id="6d7cd-163">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="6d7cd-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6d7cd-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="6d7cd-164">Related topics</span></span>
- [<span data-ttu-id="6d7cd-165">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="6d7cd-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6d7cd-166">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="6d7cd-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6d7cd-167">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="6d7cd-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6d7cd-168">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="6d7cd-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6d7cd-169">了解架构</span><span class="sxs-lookup"><span data-stu-id="6d7cd-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6d7cd-170">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="6d7cd-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
