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
ms.openlocfilehash: 7016127a75bca48103f5325ce169faa3d7c31c85
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929810"
---
# <a name="identityqueryevents"></a><span data-ttu-id="a0cec-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="a0cec-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a0cec-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a0cec-105">**Applies to:**</span></span>
- <span data-ttu-id="a0cec-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0cec-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a0cec-107">高级 `IdentityQueryEvents` 搜寻架构 [中的](advanced-hunting-overview.md) 表包含有关对 Active Directory 对象（如用户、组、设备和域）执行的查询的信息。</span><span class="sxs-lookup"><span data-stu-id="a0cec-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="a0cec-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="a0cec-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="a0cec-109">有关事件类型的详细信息 (表) 支持的值，请使用安全中心中提供的内置 `ActionType` 架构参考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="a0cec-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="a0cec-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="a0cec-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a0cec-111">列名称</span><span class="sxs-lookup"><span data-stu-id="a0cec-111">Column name</span></span> | <span data-ttu-id="a0cec-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="a0cec-112">Data type</span></span> | <span data-ttu-id="a0cec-113">说明</span><span class="sxs-lookup"><span data-stu-id="a0cec-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a0cec-114">datetime</span><span class="sxs-lookup"><span data-stu-id="a0cec-114">datetime</span></span> | <span data-ttu-id="a0cec-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="a0cec-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="a0cec-116">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-116">string</span></span> | <span data-ttu-id="a0cec-117">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="a0cec-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="a0cec-118">有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考</span><span class="sxs-lookup"><span data-stu-id="a0cec-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="a0cec-119">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-119">string</span></span> | <span data-ttu-id="a0cec-120">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="a0cec-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="a0cec-121">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-121">string</span></span> | <span data-ttu-id="a0cec-122">查询类型，如 QueryGroup、QueryUser 或 EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="a0cec-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="a0cec-123">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-123">string</span></span> | <span data-ttu-id="a0cec-124">要查询的用户、组、设备、域或其他任何实体类型的名称</span><span class="sxs-lookup"><span data-stu-id="a0cec-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="a0cec-125">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-125">string</span></span> | <span data-ttu-id="a0cec-126">用于运行查询的字符串</span><span class="sxs-lookup"><span data-stu-id="a0cec-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="a0cec-127">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-127">string</span></span> | <span data-ttu-id="a0cec-128">通信期间使用的协议</span><span class="sxs-lookup"><span data-stu-id="a0cec-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="a0cec-129">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-129">string</span></span> | <span data-ttu-id="a0cec-130">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="a0cec-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="a0cec-131">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-131">string</span></span> | <span data-ttu-id="a0cec-132">帐户的域</span><span class="sxs-lookup"><span data-stu-id="a0cec-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="a0cec-133">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-133">string</span></span> | <span data-ttu-id="a0cec-134">帐户的用户主体 (UPN) </span><span class="sxs-lookup"><span data-stu-id="a0cec-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="a0cec-135">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-135">string</span></span> | <span data-ttu-id="a0cec-136">帐户 (SID) 安全标识符</span><span class="sxs-lookup"><span data-stu-id="a0cec-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="a0cec-137">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-137">string</span></span> | <span data-ttu-id="a0cec-138">Azure AD 中帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="a0cec-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="a0cec-139">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-139">string</span></span> | <span data-ttu-id="a0cec-140">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="a0cec-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="a0cec-141">通常是给定或名字、中间初始和姓氏或姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="a0cec-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="a0cec-142">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-142">string</span></span> | <span data-ttu-id="a0cec-143">终结点的 FQDN (完全) 域名</span><span class="sxs-lookup"><span data-stu-id="a0cec-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="a0cec-144">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-144">string</span></span> | <span data-ttu-id="a0cec-145">分配给终结点的 IP 地址，在相关的网络通信期间使用</span><span class="sxs-lookup"><span data-stu-id="a0cec-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="a0cec-146">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-146">string</span></span> | <span data-ttu-id="a0cec-147">运行处理所记录操作的服务器应用程序的设备的名称</span><span class="sxs-lookup"><span data-stu-id="a0cec-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="a0cec-148">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-148">string</span></span> | <span data-ttu-id="a0cec-149">运行处理所记录操作的服务器应用程序的设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="a0cec-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="a0cec-150">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-150">string</span></span> | <span data-ttu-id="a0cec-151">已记录 (的) 的设备的 FQDN 的完全限定域名</span><span class="sxs-lookup"><span data-stu-id="a0cec-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="a0cec-152">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-152">string</span></span> | <span data-ttu-id="a0cec-153">用户主体 (UPN) 记录操作应用于的帐户的名称</span><span class="sxs-lookup"><span data-stu-id="a0cec-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="a0cec-154">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-154">string</span></span> | <span data-ttu-id="a0cec-155">记录的操作应用于的帐户的显示名称</span><span class="sxs-lookup"><span data-stu-id="a0cec-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="a0cec-156">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-156">string</span></span> | <span data-ttu-id="a0cec-157">与事件关联的城市、国家/地区或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="a0cec-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="a0cec-158">long</span><span class="sxs-lookup"><span data-stu-id="a0cec-158">long</span></span> | <span data-ttu-id="a0cec-159">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="a0cec-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="a0cec-160">string</span><span class="sxs-lookup"><span data-stu-id="a0cec-160">string</span></span> | <span data-ttu-id="a0cec-161">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="a0cec-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a0cec-162">相关主题</span><span class="sxs-lookup"><span data-stu-id="a0cec-162">Related topics</span></span>
- [<span data-ttu-id="a0cec-163">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="a0cec-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a0cec-164">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="a0cec-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a0cec-165">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="a0cec-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a0cec-166">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="a0cec-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a0cec-167">了解架构</span><span class="sxs-lookup"><span data-stu-id="a0cec-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a0cec-168">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="a0cec-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
