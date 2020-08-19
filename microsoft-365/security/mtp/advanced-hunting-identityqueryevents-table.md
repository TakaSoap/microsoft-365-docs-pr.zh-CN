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
ms.openlocfilehash: b5238ca32cdf9050391ef69bae3be0914b93f452
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797800"
---
# <a name="identityqueryevents"></a><span data-ttu-id="9f42d-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="9f42d-104">IdentityQueryEvents</span></span>

<span data-ttu-id="9f42d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9f42d-105">**Applies to:**</span></span>
- <span data-ttu-id="9f42d-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="9f42d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="9f42d-107">`IdentityQueryEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含针对 Active Directory 对象（如用户、组、设备和域）执行的查询的相关信息。</span><span class="sxs-lookup"><span data-stu-id="9f42d-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="9f42d-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="9f42d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9f42d-109">若要详细了解表支持的事件类型 (`ActionType` 值) ，请使用 "安全中心" 中提供的 [内置架构引用](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。</span><span class="sxs-lookup"><span data-stu-id="9f42d-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="9f42d-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="9f42d-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9f42d-111">列名称</span><span class="sxs-lookup"><span data-stu-id="9f42d-111">Column name</span></span> | <span data-ttu-id="9f42d-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="9f42d-112">Data type</span></span> | <span data-ttu-id="9f42d-113">说明</span><span class="sxs-lookup"><span data-stu-id="9f42d-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9f42d-114">datetime</span><span class="sxs-lookup"><span data-stu-id="9f42d-114">datetime</span></span> | <span data-ttu-id="9f42d-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="9f42d-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="9f42d-116">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-116">string</span></span> | <span data-ttu-id="9f42d-117">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="9f42d-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="9f42d-118">有关详细信息，请参阅[在门户架构参考中](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="9f42d-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="9f42d-119">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-119">string</span></span> | <span data-ttu-id="9f42d-120">执行录制操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="9f42d-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="9f42d-121">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-121">string</span></span> | <span data-ttu-id="9f42d-122">查询类型，如 QueryGroup、QueryUser 或 EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="9f42d-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="9f42d-123">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-123">string</span></span> | <span data-ttu-id="9f42d-124">要查询的用户、组、设备、域或任何其他实体类型的名称</span><span class="sxs-lookup"><span data-stu-id="9f42d-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="9f42d-125">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-125">string</span></span> | <span data-ttu-id="9f42d-126">用于运行查询的字符串</span><span class="sxs-lookup"><span data-stu-id="9f42d-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="9f42d-127">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-127">string</span></span> | <span data-ttu-id="9f42d-128">通信过程中使用的协议</span><span class="sxs-lookup"><span data-stu-id="9f42d-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="9f42d-129">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-129">string</span></span> | <span data-ttu-id="9f42d-130">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="9f42d-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9f42d-131">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-131">string</span></span> | <span data-ttu-id="9f42d-132">帐户的域</span><span class="sxs-lookup"><span data-stu-id="9f42d-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="9f42d-133">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-133">string</span></span> | <span data-ttu-id="9f42d-134">帐户的用户主体名称 (UPN) </span><span class="sxs-lookup"><span data-stu-id="9f42d-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="9f42d-135">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-135">string</span></span> | <span data-ttu-id="9f42d-136">帐户的安全标识符 (SID) </span><span class="sxs-lookup"><span data-stu-id="9f42d-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9f42d-137">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-137">string</span></span> | <span data-ttu-id="9f42d-138">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="9f42d-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9f42d-139">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-139">string</span></span> | <span data-ttu-id="9f42d-140">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="9f42d-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9f42d-141">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="9f42d-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="9f42d-142">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-142">string</span></span> | <span data-ttu-id="9f42d-143">终结点 (FQDN) 的完全限定的域名称</span><span class="sxs-lookup"><span data-stu-id="9f42d-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="9f42d-144">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-144">string</span></span> | <span data-ttu-id="9f42d-145">分配给终结点的 IP 地址，并在相关的网络通信过程中使用</span><span class="sxs-lookup"><span data-stu-id="9f42d-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="9f42d-146">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-146">string</span></span> | <span data-ttu-id="9f42d-147">运行处理录制操作的服务器应用程序的设备的名称</span><span class="sxs-lookup"><span data-stu-id="9f42d-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="9f42d-148">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-148">string</span></span> | <span data-ttu-id="9f42d-149">运行用于处理录制操作的服务器应用程序的设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="9f42d-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="9f42d-150">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-150">string</span></span> | <span data-ttu-id="9f42d-151">应用录制的操作的设备的完全限定的域名 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="9f42d-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="9f42d-152">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-152">string</span></span> | <span data-ttu-id="9f42d-153">应用了录制的操作的帐户 (UPN) 的用户主体名称</span><span class="sxs-lookup"><span data-stu-id="9f42d-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="9f42d-154">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-154">string</span></span> | <span data-ttu-id="9f42d-155">将录制的操作应用于的帐户的显示名称</span><span class="sxs-lookup"><span data-stu-id="9f42d-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="9f42d-156">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-156">string</span></span> | <span data-ttu-id="9f42d-157">与事件关联的城市、国家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="9f42d-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="9f42d-158">long</span><span class="sxs-lookup"><span data-stu-id="9f42d-158">long</span></span> | <span data-ttu-id="9f42d-159">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="9f42d-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="9f42d-160">string</span><span class="sxs-lookup"><span data-stu-id="9f42d-160">string</span></span> | <span data-ttu-id="9f42d-161">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="9f42d-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9f42d-162">相关主题</span><span class="sxs-lookup"><span data-stu-id="9f42d-162">Related topics</span></span>
- [<span data-ttu-id="9f42d-163">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="9f42d-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9f42d-164">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="9f42d-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9f42d-165">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="9f42d-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9f42d-166">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="9f42d-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9f42d-167">了解架构</span><span class="sxs-lookup"><span data-stu-id="9f42d-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9f42d-168">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="9f42d-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
