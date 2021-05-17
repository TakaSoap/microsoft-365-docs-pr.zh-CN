---
title: 高级搜寻架构中的 CloudAppEvents 表
description: 了解高级搜寻架构的 CloudAppEvents 表中的云应用和服务中的事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， CloudAppEvents， 云应用安全， MCAS
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
ms.openlocfilehash: 17f424d368c0df2f07cda41917f005e4163e5750
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935865"
---
# <a name="cloudappevents"></a><span data-ttu-id="07b58-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="07b58-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="07b58-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="07b58-105">**Applies to:**</span></span>
- <span data-ttu-id="07b58-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07b58-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="07b58-107">高级 `CloudAppEvents` 搜寻[架构中的](advanced-hunting-overview.md)表包含有关云应用和服务中活动的信息，Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="07b58-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="07b58-108">有关完整列表，跳转到 [涵盖的应用和服务](#apps-and-services-covered)。</span><span class="sxs-lookup"><span data-stu-id="07b58-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="07b58-109">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="07b58-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="07b58-110">此表包含以前在表中可用的 `AppFileEvents` 信息。</span><span class="sxs-lookup"><span data-stu-id="07b58-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="07b58-111">从 2021 年 3 月 7 开始，在此日期及之后，在云服务中搜寻与文件相关的活动的用户应改为使用 `CloudAppEvents` 表。</span><span class="sxs-lookup"><span data-stu-id="07b58-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="07b58-112">请确保搜索仍使用表的查询和自定义检测规则，并 `AppFileEvents` 编辑它们以使用 `CloudAppEvents` 该表。</span><span class="sxs-lookup"><span data-stu-id="07b58-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="07b58-113">有关转换受影响查询的更多指南，可在使用 Defender 高级搜寻的跨云应用[Microsoft 365中找到](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)。</span><span class="sxs-lookup"><span data-stu-id="07b58-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="07b58-114">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="07b58-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="07b58-115">列名称</span><span class="sxs-lookup"><span data-stu-id="07b58-115">Column name</span></span> | <span data-ttu-id="07b58-116">数据类型</span><span class="sxs-lookup"><span data-stu-id="07b58-116">Data type</span></span> | <span data-ttu-id="07b58-117">说明</span><span class="sxs-lookup"><span data-stu-id="07b58-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="07b58-118">datetime</span><span class="sxs-lookup"><span data-stu-id="07b58-118">datetime</span></span> | <span data-ttu-id="07b58-119">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="07b58-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="07b58-120">string</span><span class="sxs-lookup"><span data-stu-id="07b58-120">string</span></span> | <span data-ttu-id="07b58-121">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="07b58-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="07b58-122">string</span><span class="sxs-lookup"><span data-stu-id="07b58-122">string</span></span> | <span data-ttu-id="07b58-123">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="07b58-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="07b58-124">string</span><span class="sxs-lookup"><span data-stu-id="07b58-124">string</span></span> | <span data-ttu-id="07b58-125">应用程序的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="07b58-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="07b58-126">string</span><span class="sxs-lookup"><span data-stu-id="07b58-126">string</span></span> | <span data-ttu-id="07b58-127">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="07b58-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="07b58-128">string</span><span class="sxs-lookup"><span data-stu-id="07b58-128">string</span></span> | <span data-ttu-id="07b58-129">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="07b58-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="07b58-130">通常是给定或名字、中间启动和姓氏或姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="07b58-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="07b58-131">string</span><span class="sxs-lookup"><span data-stu-id="07b58-131">string</span></span> | <span data-ttu-id="07b58-132">指示活动是否由管理员执行</span><span class="sxs-lookup"><span data-stu-id="07b58-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="07b58-133">string</span><span class="sxs-lookup"><span data-stu-id="07b58-133">string</span></span> | <span data-ttu-id="07b58-134">基于用途和功能的设备类型，例如"网络设备"、"工作站"、"服务器"、"移动"、"游戏控制台"或"打印机"</span><span class="sxs-lookup"><span data-stu-id="07b58-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="07b58-135">string</span><span class="sxs-lookup"><span data-stu-id="07b58-135">string</span></span> | <span data-ttu-id="07b58-136">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="07b58-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="07b58-137">此列指示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="07b58-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="07b58-138">string</span><span class="sxs-lookup"><span data-stu-id="07b58-138">string</span></span> | <span data-ttu-id="07b58-139">分配给终结点的 IP 地址，在相关的网络通信期间使用</span><span class="sxs-lookup"><span data-stu-id="07b58-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="07b58-140">string</span><span class="sxs-lookup"><span data-stu-id="07b58-140">string</span></span> | <span data-ttu-id="07b58-141">指示 IP 地址是否属于已知匿名代理</span><span class="sxs-lookup"><span data-stu-id="07b58-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="07b58-142">string</span><span class="sxs-lookup"><span data-stu-id="07b58-142">string</span></span> | <span data-ttu-id="07b58-143">指示客户端 IP 地址已异地分配的国家/地区两个字母的代码</span><span class="sxs-lookup"><span data-stu-id="07b58-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="07b58-144">string</span><span class="sxs-lookup"><span data-stu-id="07b58-144">string</span></span> | <span data-ttu-id="07b58-145">已异地分配客户端 IP 地址的城市</span><span class="sxs-lookup"><span data-stu-id="07b58-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="07b58-146">string</span><span class="sxs-lookup"><span data-stu-id="07b58-146">string</span></span> | <span data-ttu-id="07b58-147">Internet 服务提供商 (ISP) IP 地址相关联</span><span class="sxs-lookup"><span data-stu-id="07b58-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="07b58-148">string</span><span class="sxs-lookup"><span data-stu-id="07b58-148">string</span></span> | <span data-ttu-id="07b58-149">来自 Web 浏览器或其他客户端应用程序的用户代理信息</span><span class="sxs-lookup"><span data-stu-id="07b58-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="07b58-150">string</span><span class="sxs-lookup"><span data-stu-id="07b58-150">string</span></span> | <span data-ttu-id="07b58-151">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="07b58-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="07b58-152">string</span><span class="sxs-lookup"><span data-stu-id="07b58-152">string</span></span> | <span data-ttu-id="07b58-153">记录的活动所涉及的对象列表，如文件或文件夹</span><span class="sxs-lookup"><span data-stu-id="07b58-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="07b58-154">string</span><span class="sxs-lookup"><span data-stu-id="07b58-154">string</span></span> | <span data-ttu-id="07b58-155">已记录操作应用于的对象的名称</span><span class="sxs-lookup"><span data-stu-id="07b58-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="07b58-156">string</span><span class="sxs-lookup"><span data-stu-id="07b58-156">string</span></span> | <span data-ttu-id="07b58-157">记录的操作应用于的对象类型，例如文件或文件夹</span><span class="sxs-lookup"><span data-stu-id="07b58-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="07b58-158">string</span><span class="sxs-lookup"><span data-stu-id="07b58-158">string</span></span> | <span data-ttu-id="07b58-159">记录的操作应用于的对象的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="07b58-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="07b58-160">string</span><span class="sxs-lookup"><span data-stu-id="07b58-160">string</span></span> | <span data-ttu-id="07b58-161">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="07b58-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="07b58-162">string</span><span class="sxs-lookup"><span data-stu-id="07b58-162">string</span></span> | <span data-ttu-id="07b58-163">来自 JSON 格式的源应用程序或服务的原始事件信息</span><span class="sxs-lookup"><span data-stu-id="07b58-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="07b58-164">string</span><span class="sxs-lookup"><span data-stu-id="07b58-164">string</span></span> | <span data-ttu-id="07b58-165">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="07b58-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="07b58-166">涵盖的应用和服务</span><span class="sxs-lookup"><span data-stu-id="07b58-166">Apps and services covered</span></span>

- <span data-ttu-id="07b58-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="07b58-167">Dropbox</span></span>
- <span data-ttu-id="07b58-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="07b58-168">Dynamics 365</span></span>
- <span data-ttu-id="07b58-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="07b58-169">Exchange Online</span></span>
- <span data-ttu-id="07b58-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07b58-170">Microsoft Teams</span></span>
- <span data-ttu-id="07b58-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="07b58-171">OneDrive for Business</span></span>
- <span data-ttu-id="07b58-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="07b58-172">Power Automate</span></span>
- <span data-ttu-id="07b58-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="07b58-173">Power BI</span></span>
- <span data-ttu-id="07b58-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="07b58-174">SharePoint Online</span></span>
- <span data-ttu-id="07b58-175">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="07b58-175">Skype for Business</span></span>
- <span data-ttu-id="07b58-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="07b58-176">Office 365</span></span>
- <span data-ttu-id="07b58-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="07b58-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="07b58-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="07b58-178">Related topics</span></span>
- [<span data-ttu-id="07b58-179">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="07b58-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="07b58-180">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="07b58-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="07b58-181">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="07b58-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="07b58-182">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="07b58-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="07b58-183">了解架构</span><span class="sxs-lookup"><span data-stu-id="07b58-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="07b58-184">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="07b58-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
