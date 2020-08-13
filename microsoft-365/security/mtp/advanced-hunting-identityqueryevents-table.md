---
title: 高级搜寻架构中的 IdentityQueryEvents 表
description: 了解高级搜寻架构的 IdentityQueryEvents 表中的 Active Directory 查询事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、IdentityQueryEvents、Azure AD、Active Directory、Azure ATP、标识、LDAP 查询
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
ms.openlocfilehash: cf2038a15242139817eb073ec2a6408905824123
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649315"
---
# <a name="identityqueryevents"></a><span data-ttu-id="f50c6-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="f50c6-104">IdentityQueryEvents</span></span>

<span data-ttu-id="f50c6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f50c6-105">**Applies to:**</span></span>
- <span data-ttu-id="f50c6-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="f50c6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f50c6-107">`IdentityQueryEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含针对 Active Directory 对象（如用户、组、设备和域）执行的查询的相关信息。</span><span class="sxs-lookup"><span data-stu-id="f50c6-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="f50c6-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="f50c6-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f50c6-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="f50c6-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f50c6-110">列名称</span><span class="sxs-lookup"><span data-stu-id="f50c6-110">Column name</span></span> | <span data-ttu-id="f50c6-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="f50c6-111">Data type</span></span> | <span data-ttu-id="f50c6-112">说明</span><span class="sxs-lookup"><span data-stu-id="f50c6-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f50c6-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f50c6-113">datetime</span></span> | <span data-ttu-id="f50c6-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="f50c6-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="f50c6-115">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-115">string</span></span> | <span data-ttu-id="f50c6-116">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="f50c6-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="f50c6-117">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-117">string</span></span> | <span data-ttu-id="f50c6-118">执行录制操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="f50c6-118">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="f50c6-119">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-119">string</span></span> | <span data-ttu-id="f50c6-120">查询类型，如 QueryGroup、QueryUser 或 EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="f50c6-120">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="f50c6-121">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-121">string</span></span> | <span data-ttu-id="f50c6-122">要查询的用户、组、设备、域或任何其他实体类型的名称</span><span class="sxs-lookup"><span data-stu-id="f50c6-122">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="f50c6-123">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-123">string</span></span> | <span data-ttu-id="f50c6-124">用于运行查询的字符串</span><span class="sxs-lookup"><span data-stu-id="f50c6-124">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="f50c6-125">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-125">string</span></span> | <span data-ttu-id="f50c6-126">通信过程中使用的协议</span><span class="sxs-lookup"><span data-stu-id="f50c6-126">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="f50c6-127">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-127">string</span></span> | <span data-ttu-id="f50c6-128">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="f50c6-128">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f50c6-129">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-129">string</span></span> | <span data-ttu-id="f50c6-130">帐户的域</span><span class="sxs-lookup"><span data-stu-id="f50c6-130">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="f50c6-131">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-131">string</span></span> | <span data-ttu-id="f50c6-132">帐户的用户主体名称 (UPN) </span><span class="sxs-lookup"><span data-stu-id="f50c6-132">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="f50c6-133">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-133">string</span></span> | <span data-ttu-id="f50c6-134">帐户的安全标识符 (SID) </span><span class="sxs-lookup"><span data-stu-id="f50c6-134">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="f50c6-135">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-135">string</span></span> | <span data-ttu-id="f50c6-136">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="f50c6-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f50c6-137">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-137">string</span></span> | <span data-ttu-id="f50c6-138">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="f50c6-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f50c6-139">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="f50c6-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="f50c6-140">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-140">string</span></span> | <span data-ttu-id="f50c6-141">终结点 (FQDN) 的完全限定的域名称</span><span class="sxs-lookup"><span data-stu-id="f50c6-141">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="f50c6-142">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-142">string</span></span> | <span data-ttu-id="f50c6-143">分配给终结点的 IP 地址，并在相关的网络通信过程中使用</span><span class="sxs-lookup"><span data-stu-id="f50c6-143">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="f50c6-144">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-144">string</span></span> | <span data-ttu-id="f50c6-145">运行处理录制操作的服务器应用程序的设备的名称</span><span class="sxs-lookup"><span data-stu-id="f50c6-145">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="f50c6-146">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-146">string</span></span> | <span data-ttu-id="f50c6-147">运行用于处理录制操作的服务器应用程序的设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="f50c6-147">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="f50c6-148">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-148">string</span></span> | <span data-ttu-id="f50c6-149">应用录制的操作的设备的完全限定的域名 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="f50c6-149">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="f50c6-150">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-150">string</span></span> | <span data-ttu-id="f50c6-151">应用了录制的操作的帐户 (UPN) 的用户主体名称</span><span class="sxs-lookup"><span data-stu-id="f50c6-151">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="f50c6-152">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-152">string</span></span> | <span data-ttu-id="f50c6-153">将录制的操作应用于的帐户的显示名称</span><span class="sxs-lookup"><span data-stu-id="f50c6-153">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="f50c6-154">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-154">string</span></span> | <span data-ttu-id="f50c6-155">与事件关联的城市、国家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="f50c6-155">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="f50c6-156">long</span><span class="sxs-lookup"><span data-stu-id="f50c6-156">long</span></span> | <span data-ttu-id="f50c6-157">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="f50c6-157">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="f50c6-158">string</span><span class="sxs-lookup"><span data-stu-id="f50c6-158">string</span></span> | <span data-ttu-id="f50c6-159">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="f50c6-159">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f50c6-160">相关主题</span><span class="sxs-lookup"><span data-stu-id="f50c6-160">Related topics</span></span>
- [<span data-ttu-id="f50c6-161">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="f50c6-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f50c6-162">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="f50c6-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f50c6-163">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="f50c6-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f50c6-164">跨设备、电子邮件、应用和标识的智能寻线</span><span class="sxs-lookup"><span data-stu-id="f50c6-164">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f50c6-165">了解架构</span><span class="sxs-lookup"><span data-stu-id="f50c6-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f50c6-166">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="f50c6-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
