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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4221af6b0378e67e12852dbef0bbc0a11ff56511
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649471"
---
# <a name="appfileevents"></a><span data-ttu-id="00f70-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="00f70-104">AppFileEvents</span></span>

<span data-ttu-id="00f70-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="00f70-105">**Applies to:**</span></span>
- <span data-ttu-id="00f70-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="00f70-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="00f70-107">`AppFileEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关 Microsoft 云应用安全监视的云应用和服务中与文件相关的活动的信息。</span><span class="sxs-lookup"><span data-stu-id="00f70-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="00f70-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="00f70-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="00f70-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="00f70-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="00f70-110">列名称</span><span class="sxs-lookup"><span data-stu-id="00f70-110">Column name</span></span> | <span data-ttu-id="00f70-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="00f70-111">Data type</span></span> | <span data-ttu-id="00f70-112">说明</span><span class="sxs-lookup"><span data-stu-id="00f70-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="00f70-113">datetime</span><span class="sxs-lookup"><span data-stu-id="00f70-113">datetime</span></span> | <span data-ttu-id="00f70-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="00f70-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="00f70-115">string</span><span class="sxs-lookup"><span data-stu-id="00f70-115">string</span></span> | <span data-ttu-id="00f70-116">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="00f70-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="00f70-117">string</span><span class="sxs-lookup"><span data-stu-id="00f70-117">string</span></span> | <span data-ttu-id="00f70-118">执行录制操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="00f70-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="00f70-119">string</span><span class="sxs-lookup"><span data-stu-id="00f70-119">string</span></span> | <span data-ttu-id="00f70-120">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="00f70-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="00f70-121">string</span><span class="sxs-lookup"><span data-stu-id="00f70-121">string</span></span> | <span data-ttu-id="00f70-122">包含录制的操作所应用于的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="00f70-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="00f70-123">string</span><span class="sxs-lookup"><span data-stu-id="00f70-123">string</span></span> | <span data-ttu-id="00f70-124">作为操作的结果重命名的文件的原始名称</span><span class="sxs-lookup"><span data-stu-id="00f70-124">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="00f70-125">string</span><span class="sxs-lookup"><span data-stu-id="00f70-125">string</span></span> | <span data-ttu-id="00f70-126">在应用录制的操作之前包含文件的原始文件夹</span><span class="sxs-lookup"><span data-stu-id="00f70-126">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="00f70-127">string</span><span class="sxs-lookup"><span data-stu-id="00f70-127">string</span></span> | <span data-ttu-id="00f70-128">使用的网络协议</span><span class="sxs-lookup"><span data-stu-id="00f70-128">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="00f70-129">string</span><span class="sxs-lookup"><span data-stu-id="00f70-129">string</span></span> | <span data-ttu-id="00f70-130">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="00f70-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="00f70-131">string</span><span class="sxs-lookup"><span data-stu-id="00f70-131">string</span></span> | <span data-ttu-id="00f70-132">帐户的域</span><span class="sxs-lookup"><span data-stu-id="00f70-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="00f70-133">string</span><span class="sxs-lookup"><span data-stu-id="00f70-133">string</span></span> | <span data-ttu-id="00f70-134">帐户的用户主体名称 (UPN) </span><span class="sxs-lookup"><span data-stu-id="00f70-134">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="00f70-135">string</span><span class="sxs-lookup"><span data-stu-id="00f70-135">string</span></span> | <span data-ttu-id="00f70-136">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="00f70-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="00f70-137">string</span><span class="sxs-lookup"><span data-stu-id="00f70-137">string</span></span> | <span data-ttu-id="00f70-138">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="00f70-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="00f70-139">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="00f70-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="00f70-140">string</span><span class="sxs-lookup"><span data-stu-id="00f70-140">string</span></span> | <span data-ttu-id="00f70-141">设备 (FQDN) 的完全限定的域名称</span><span class="sxs-lookup"><span data-stu-id="00f70-141">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="00f70-142">string</span><span class="sxs-lookup"><span data-stu-id="00f70-142">string</span></span> | <span data-ttu-id="00f70-143">设备类型</span><span class="sxs-lookup"><span data-stu-id="00f70-143">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="00f70-144">string</span><span class="sxs-lookup"><span data-stu-id="00f70-144">string</span></span> | <span data-ttu-id="00f70-145">设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="00f70-145">Platform of the operating system running on the device.</span></span> <span data-ttu-id="00f70-146">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="00f70-146">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="00f70-147">string</span><span class="sxs-lookup"><span data-stu-id="00f70-147">string</span></span> | <span data-ttu-id="00f70-148">分配给终结点的 IP 地址，并在相关的网络通信过程中使用</span><span class="sxs-lookup"><span data-stu-id="00f70-148">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="00f70-149">string</span><span class="sxs-lookup"><span data-stu-id="00f70-149">string</span></span> | <span data-ttu-id="00f70-150">运行处理录制操作的服务器应用程序的设备的名称</span><span class="sxs-lookup"><span data-stu-id="00f70-150">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="00f70-151">string</span><span class="sxs-lookup"><span data-stu-id="00f70-151">string</span></span> | <span data-ttu-id="00f70-152">运行用于处理录制操作的服务器应用程序的设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="00f70-152">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="00f70-153">string</span><span class="sxs-lookup"><span data-stu-id="00f70-153">string</span></span> | <span data-ttu-id="00f70-154">与事件关联的城市、国家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="00f70-154">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="00f70-155">string</span><span class="sxs-lookup"><span data-stu-id="00f70-155">string</span></span> | <span data-ttu-id="00f70-156">Internet 服务提供商 (与终结点 IP 地址关联的 ISP) </span><span class="sxs-lookup"><span data-stu-id="00f70-156">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="00f70-157">long</span><span class="sxs-lookup"><span data-stu-id="00f70-157">long</span></span> | <span data-ttu-id="00f70-158">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="00f70-158">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="00f70-159">string</span><span class="sxs-lookup"><span data-stu-id="00f70-159">string</span></span> | <span data-ttu-id="00f70-160">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="00f70-160">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="00f70-161">相关主题</span><span class="sxs-lookup"><span data-stu-id="00f70-161">Related topics</span></span>
- [<span data-ttu-id="00f70-162">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="00f70-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="00f70-163">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="00f70-163">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="00f70-164">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="00f70-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="00f70-165">跨设备、电子邮件、应用和标识的智能寻线</span><span class="sxs-lookup"><span data-stu-id="00f70-165">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="00f70-166">了解架构</span><span class="sxs-lookup"><span data-stu-id="00f70-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="00f70-167">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="00f70-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
