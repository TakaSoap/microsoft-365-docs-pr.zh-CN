---
title: 高级搜寻架构中的 IdentityQueryEvents 表
description: 了解高级搜寻架构的 IdentityQueryEvents 表中的 Active Directory 查询事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， IdentityQueryEvents， Azure AD， Active Directory， Azure ATP， 标识， LDAP 查询
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
ms.openlocfilehash: eb1f408b61444771f5d450b46dbc9c2b4a009e4c
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712326"
---
# <a name="identityqueryevents"></a><span data-ttu-id="9baca-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="9baca-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9baca-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9baca-105">**Applies to:**</span></span>
- <span data-ttu-id="9baca-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9baca-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9baca-107">高级 `IdentityQueryEvents` 搜寻架构 [中的](advanced-hunting-overview.md) 表包含有关对 Active Directory 对象（如用户、组、设备和域）执行的查询的信息。</span><span class="sxs-lookup"><span data-stu-id="9baca-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="9baca-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="9baca-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9baca-109">有关事件类型的详细信息 (表) 支持的值，请使用安全中心中提供的内置 `ActionType` 架构引用。</span><span class="sxs-lookup"><span data-stu-id="9baca-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="9baca-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="9baca-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9baca-111">列名称</span><span class="sxs-lookup"><span data-stu-id="9baca-111">Column name</span></span> | <span data-ttu-id="9baca-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="9baca-112">Data type</span></span> | <span data-ttu-id="9baca-113">说明</span><span class="sxs-lookup"><span data-stu-id="9baca-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9baca-114">datetime</span><span class="sxs-lookup"><span data-stu-id="9baca-114">datetime</span></span> | <span data-ttu-id="9baca-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="9baca-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="9baca-116">string</span><span class="sxs-lookup"><span data-stu-id="9baca-116">string</span></span> | <span data-ttu-id="9baca-117">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="9baca-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="9baca-118">有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考</span><span class="sxs-lookup"><span data-stu-id="9baca-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="9baca-119">string</span><span class="sxs-lookup"><span data-stu-id="9baca-119">string</span></span> | <span data-ttu-id="9baca-120">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="9baca-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="9baca-121">string</span><span class="sxs-lookup"><span data-stu-id="9baca-121">string</span></span> | <span data-ttu-id="9baca-122">查询类型，如 QueryGroup、QueryUser 或 EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="9baca-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="9baca-123">string</span><span class="sxs-lookup"><span data-stu-id="9baca-123">string</span></span> | <span data-ttu-id="9baca-124">要查询的用户、组、设备、域或任何其他实体类型的名称</span><span class="sxs-lookup"><span data-stu-id="9baca-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="9baca-125">string</span><span class="sxs-lookup"><span data-stu-id="9baca-125">string</span></span> | <span data-ttu-id="9baca-126">用于运行查询的字符串</span><span class="sxs-lookup"><span data-stu-id="9baca-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="9baca-127">string</span><span class="sxs-lookup"><span data-stu-id="9baca-127">string</span></span> | <span data-ttu-id="9baca-128">通信期间使用的协议</span><span class="sxs-lookup"><span data-stu-id="9baca-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="9baca-129">string</span><span class="sxs-lookup"><span data-stu-id="9baca-129">string</span></span> | <span data-ttu-id="9baca-130">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="9baca-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9baca-131">string</span><span class="sxs-lookup"><span data-stu-id="9baca-131">string</span></span> | <span data-ttu-id="9baca-132">帐户的域</span><span class="sxs-lookup"><span data-stu-id="9baca-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="9baca-133">string</span><span class="sxs-lookup"><span data-stu-id="9baca-133">string</span></span> | <span data-ttu-id="9baca-134">帐户 (UPN) 用户主体名称</span><span class="sxs-lookup"><span data-stu-id="9baca-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="9baca-135">string</span><span class="sxs-lookup"><span data-stu-id="9baca-135">string</span></span> | <span data-ttu-id="9baca-136">帐户 (SID) 安全标识符</span><span class="sxs-lookup"><span data-stu-id="9baca-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9baca-137">string</span><span class="sxs-lookup"><span data-stu-id="9baca-137">string</span></span> | <span data-ttu-id="9baca-138">Azure AD 中帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="9baca-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9baca-139">string</span><span class="sxs-lookup"><span data-stu-id="9baca-139">string</span></span> | <span data-ttu-id="9baca-140">通讯簿中显示的帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="9baca-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9baca-141">通常，给定或名字、中间初始和姓氏或姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="9baca-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="9baca-142">string</span><span class="sxs-lookup"><span data-stu-id="9baca-142">string</span></span> | <span data-ttu-id="9baca-143">终结点的 FQDN (完全) 域名</span><span class="sxs-lookup"><span data-stu-id="9baca-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="9baca-144">string</span><span class="sxs-lookup"><span data-stu-id="9baca-144">string</span></span> | <span data-ttu-id="9baca-145">分配给终结点的 IP 地址，在相关网络通信期间使用</span><span class="sxs-lookup"><span data-stu-id="9baca-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="9baca-146">string</span><span class="sxs-lookup"><span data-stu-id="9baca-146">string</span></span> | <span data-ttu-id="9baca-147">通信期间使用的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="9baca-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="9baca-148">string</span><span class="sxs-lookup"><span data-stu-id="9baca-148">string</span></span> | <span data-ttu-id="9baca-149">运行处理所记录操作的服务器应用程序的设备的名称</span><span class="sxs-lookup"><span data-stu-id="9baca-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="9baca-150">string</span><span class="sxs-lookup"><span data-stu-id="9baca-150">string</span></span> | <span data-ttu-id="9baca-151">运行处理所记录操作的服务器应用程序的设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="9baca-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="9baca-152">string</span><span class="sxs-lookup"><span data-stu-id="9baca-152">string</span></span> | <span data-ttu-id="9baca-153">相关网络通信的目标端口</span><span class="sxs-lookup"><span data-stu-id="9baca-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="9baca-154">string</span><span class="sxs-lookup"><span data-stu-id="9baca-154">string</span></span> | <span data-ttu-id="9baca-155">已记录 (设备的 FQDN) 的完全限定域名</span><span class="sxs-lookup"><span data-stu-id="9baca-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="9baca-156">string</span><span class="sxs-lookup"><span data-stu-id="9baca-156">string</span></span> | <span data-ttu-id="9baca-157">用户主体 (UPN) 记录操作应用到的帐户的 UPN 名称</span><span class="sxs-lookup"><span data-stu-id="9baca-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="9baca-158">string</span><span class="sxs-lookup"><span data-stu-id="9baca-158">string</span></span> | <span data-ttu-id="9baca-159">记录的操作应用于的帐户的显示名称</span><span class="sxs-lookup"><span data-stu-id="9baca-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="9baca-160">string</span><span class="sxs-lookup"><span data-stu-id="9baca-160">string</span></span> | <span data-ttu-id="9baca-161">与事件关联的城市、国家/地区或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="9baca-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="9baca-162">long</span><span class="sxs-lookup"><span data-stu-id="9baca-162">long</span></span> | <span data-ttu-id="9baca-163">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="9baca-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="9baca-164">string</span><span class="sxs-lookup"><span data-stu-id="9baca-164">string</span></span> | <span data-ttu-id="9baca-165">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="9baca-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9baca-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="9baca-166">Related topics</span></span>
- [<span data-ttu-id="9baca-167">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="9baca-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9baca-168">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="9baca-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9baca-169">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="9baca-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9baca-170">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="9baca-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9baca-171">了解架构</span><span class="sxs-lookup"><span data-stu-id="9baca-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9baca-172">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="9baca-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
