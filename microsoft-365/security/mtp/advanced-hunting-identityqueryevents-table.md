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
ms.openlocfilehash: bec7f13d49e2ccf4e3a9121d5e5a2fecd1b10aa2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899109"
---
# <a name="identityqueryevents"></a><span data-ttu-id="63f7f-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="63f7f-104">IdentityQueryEvents</span></span>

<span data-ttu-id="63f7f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="63f7f-105">**Applies to:**</span></span>
- <span data-ttu-id="63f7f-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="63f7f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="63f7f-107">`IdentityQueryEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含针对 Active Directory 对象（如用户、组、设备和域）执行的查询的相关信息。</span><span class="sxs-lookup"><span data-stu-id="63f7f-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="63f7f-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="63f7f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="63f7f-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="63f7f-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="63f7f-110">列名称</span><span class="sxs-lookup"><span data-stu-id="63f7f-110">Column name</span></span> | <span data-ttu-id="63f7f-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="63f7f-111">Data type</span></span> | <span data-ttu-id="63f7f-112">说明</span><span class="sxs-lookup"><span data-stu-id="63f7f-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="63f7f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="63f7f-113">datetime</span></span> | <span data-ttu-id="63f7f-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="63f7f-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="63f7f-115">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-115">string</span></span> | <span data-ttu-id="63f7f-116">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="63f7f-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="63f7f-117">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-117">string</span></span> | <span data-ttu-id="63f7f-118">执行录制操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="63f7f-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="63f7f-119">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-119">string</span></span> | <span data-ttu-id="63f7f-120">查询类型： QueryGroup、QueryUser 或 EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="63f7f-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="63f7f-121">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-121">string</span></span> | <span data-ttu-id="63f7f-122">要查询的用户、组、设备、域或任何其他实体类型的名称</span><span class="sxs-lookup"><span data-stu-id="63f7f-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="63f7f-123">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-123">string</span></span> | <span data-ttu-id="63f7f-124">通信过程中使用的协议</span><span class="sxs-lookup"><span data-stu-id="63f7f-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="63f7f-125">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-125">string</span></span> | <span data-ttu-id="63f7f-126">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="63f7f-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="63f7f-127">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-127">string</span></span> | <span data-ttu-id="63f7f-128">帐户的域</span><span class="sxs-lookup"><span data-stu-id="63f7f-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="63f7f-129">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-129">string</span></span> | <span data-ttu-id="63f7f-130">帐户的用户主体名称（UPN）</span><span class="sxs-lookup"><span data-stu-id="63f7f-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="63f7f-131">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-131">string</span></span> | <span data-ttu-id="63f7f-132">帐户的安全标识符（SID）</span><span class="sxs-lookup"><span data-stu-id="63f7f-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="63f7f-133">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-133">string</span></span> | <span data-ttu-id="63f7f-134">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="63f7f-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="63f7f-135">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-135">string</span></span> | <span data-ttu-id="63f7f-136">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="63f7f-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="63f7f-137">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="63f7f-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="63f7f-138">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-138">string</span></span> | <span data-ttu-id="63f7f-139">终结点的完全限定的域名（FQDN）</span><span class="sxs-lookup"><span data-stu-id="63f7f-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="63f7f-140">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-140">string</span></span> | <span data-ttu-id="63f7f-141">分配给终结点的 IP 地址，并在相关的网络通信过程中使用</span><span class="sxs-lookup"><span data-stu-id="63f7f-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="63f7f-142">string</span><span class="sxs-lookup"><span data-stu-id="63f7f-142">string</span></span> | <span data-ttu-id="63f7f-143">与事件关联的城市、国家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="63f7f-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="63f7f-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="63f7f-144">Related topics</span></span>
- [<span data-ttu-id="63f7f-145">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="63f7f-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="63f7f-146">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="63f7f-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="63f7f-147">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="63f7f-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="63f7f-148">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="63f7f-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="63f7f-149">了解架构</span><span class="sxs-lookup"><span data-stu-id="63f7f-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="63f7f-150">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="63f7f-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
