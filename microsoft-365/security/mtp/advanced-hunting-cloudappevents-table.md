---
title: 高级搜寻架构中的 CloudAppEvents 表
description: 了解高级搜寻架构的 CloudAppEvents 表中的云应用和服务事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， CloudAppEvents， Cloud App Security， MCAS
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
ms.openlocfilehash: a8ba1f94bc704a5fe99d54b77aa6570c5e43d3f7
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712482"
---
# <a name="cloudappevents"></a><span data-ttu-id="d4b0b-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="d4b0b-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d4b0b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d4b0b-105">**Applies to:**</span></span>
- <span data-ttu-id="d4b0b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4b0b-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="d4b0b-107">高级搜寻架构中的表包含有关 Microsoft Cloud App Security 涵盖的各种云应用和服务中的活动的信息，特别是 `CloudAppEvents` Dropbox、Exchange [](advanced-hunting-overview.md) Online、OneDrive、Microsoft Teams 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="d4b0b-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security, specifically Dropbox, Exchange Online, OneDrive, Microsoft Teams, and SharePoint.</span></span> <span data-ttu-id="d4b0b-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="d4b0b-108">Use this reference to construct queries that return information from this table.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d4b0b-109">此表包含以前在表中可用的 `AppFileEvents` 信息。</span><span class="sxs-lookup"><span data-stu-id="d4b0b-109">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="d4b0b-110">从 2021 年 3 月 7 开始，在此日期及之后，在云服务中搜寻与文件相关的活动的用户应改为使用 `CloudAppEvents` 该表。</span><span class="sxs-lookup"><span data-stu-id="d4b0b-110">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="d4b0b-111">请确保搜索仍在使用该表的查询和自定义检测规则， `AppFileEvents` 并编辑它们以使用 `CloudAppEvents` 该表。</span><span class="sxs-lookup"><span data-stu-id="d4b0b-111">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="d4b0b-112">有关转换受影响的查询的更多指南，可在 [使用 Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)高级搜寻的云应用活动中找到 Hunt。</span><span class="sxs-lookup"><span data-stu-id="d4b0b-112">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="d4b0b-113">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="d4b0b-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d4b0b-114">列名称</span><span class="sxs-lookup"><span data-stu-id="d4b0b-114">Column name</span></span> | <span data-ttu-id="d4b0b-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="d4b0b-115">Data type</span></span> | <span data-ttu-id="d4b0b-116">说明</span><span class="sxs-lookup"><span data-stu-id="d4b0b-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d4b0b-117">datetime</span><span class="sxs-lookup"><span data-stu-id="d4b0b-117">datetime</span></span> | <span data-ttu-id="d4b0b-118">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="d4b0b-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="d4b0b-119">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-119">string</span></span> | <span data-ttu-id="d4b0b-120">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="d4b0b-120">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="d4b0b-121">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-121">string</span></span> | <span data-ttu-id="d4b0b-122">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="d4b0b-122">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="d4b0b-123">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-123">string</span></span> | <span data-ttu-id="d4b0b-124">应用程序的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="d4b0b-124">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="d4b0b-125">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-125">string</span></span> | <span data-ttu-id="d4b0b-126">Azure Active Directory 中帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="d4b0b-126">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="d4b0b-127">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-127">string</span></span> | <span data-ttu-id="d4b0b-128">通讯簿中显示的帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="d4b0b-128">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="d4b0b-129">通常，给定或名字、中间初始和姓氏或姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="d4b0b-129">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="d4b0b-130">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-130">string</span></span> | <span data-ttu-id="d4b0b-131">指示活动是否由管理员执行</span><span class="sxs-lookup"><span data-stu-id="d4b0b-131">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="d4b0b-132">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-132">string</span></span> | <span data-ttu-id="d4b0b-133">基于用途和功能的设备类型，例如"网络设备"、"工作站"、"服务器"、"移动"、"游戏控制台"或"打印机"</span><span class="sxs-lookup"><span data-stu-id="d4b0b-133">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="d4b0b-134">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-134">string</span></span> | <span data-ttu-id="d4b0b-135">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="d4b0b-135">Platform of the operating system running on the device.</span></span> <span data-ttu-id="d4b0b-136">此列指示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="d4b0b-136">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="d4b0b-137">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-137">string</span></span> | <span data-ttu-id="d4b0b-138">分配给终结点的 IP 地址，在相关网络通信期间使用</span><span class="sxs-lookup"><span data-stu-id="d4b0b-138">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="d4b0b-139">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-139">string</span></span> | <span data-ttu-id="d4b0b-140">指示 IP 地址是否属于已知匿名代理</span><span class="sxs-lookup"><span data-stu-id="d4b0b-140">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="d4b0b-141">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-141">string</span></span> | <span data-ttu-id="d4b0b-142">两个字母的代码，指示客户端 IP 地址被异地分配的国家/地区</span><span class="sxs-lookup"><span data-stu-id="d4b0b-142">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="d4b0b-143">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-143">string</span></span> | <span data-ttu-id="d4b0b-144">客户端 IP 地址被异地分配的城市</span><span class="sxs-lookup"><span data-stu-id="d4b0b-144">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="d4b0b-145">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-145">string</span></span> | <span data-ttu-id="d4b0b-146">与 IP 地址 (ISP) 服务提供商</span><span class="sxs-lookup"><span data-stu-id="d4b0b-146">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="d4b0b-147">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-147">string</span></span> | <span data-ttu-id="d4b0b-148">来自 Web 浏览器或其他客户端应用程序的用户代理信息</span><span class="sxs-lookup"><span data-stu-id="d4b0b-148">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="d4b0b-149">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-149">string</span></span> | <span data-ttu-id="d4b0b-150">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="d4b0b-150">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="d4b0b-151">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-151">string</span></span> | <span data-ttu-id="d4b0b-152">记录的活动所涉及的对象列表，如文件或文件夹</span><span class="sxs-lookup"><span data-stu-id="d4b0b-152">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="d4b0b-153">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-153">string</span></span> | <span data-ttu-id="d4b0b-154">记录的操作应用于的对象的名称</span><span class="sxs-lookup"><span data-stu-id="d4b0b-154">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="d4b0b-155">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-155">string</span></span> | <span data-ttu-id="d4b0b-156">已记录操作应用于的对象类型，如文件或文件夹</span><span class="sxs-lookup"><span data-stu-id="d4b0b-156">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="d4b0b-157">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-157">string</span></span> | <span data-ttu-id="d4b0b-158">记录的操作应用于的对象的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="d4b0b-158">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="d4b0b-159">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-159">string</span></span> | <span data-ttu-id="d4b0b-160">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="d4b0b-160">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="d4b0b-161">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-161">string</span></span> | <span data-ttu-id="d4b0b-162">来自源应用程序或服务的原始事件信息，格式为 JSON</span><span class="sxs-lookup"><span data-stu-id="d4b0b-162">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="d4b0b-163">string</span><span class="sxs-lookup"><span data-stu-id="d4b0b-163">string</span></span> | <span data-ttu-id="d4b0b-164">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="d4b0b-164">Additional information about the entity or event</span></span> |


## <a name="related-topics"></a><span data-ttu-id="d4b0b-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="d4b0b-165">Related topics</span></span>
- [<span data-ttu-id="d4b0b-166">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="d4b0b-166">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d4b0b-167">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="d4b0b-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d4b0b-168">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="d4b0b-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d4b0b-169">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="d4b0b-169">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d4b0b-170">了解架构</span><span class="sxs-lookup"><span data-stu-id="d4b0b-170">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d4b0b-171">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="d4b0b-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
