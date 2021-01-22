---
title: 高级搜寻架构中的 IdentityInfo 表
description: 了解高级搜寻架构的 IdentityInfo 表中的用户帐户信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， AccountInfo， IdentityInfo， 帐户
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929906"
---
# <a name="identityinfo"></a><span data-ttu-id="be54e-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="be54e-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="be54e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="be54e-105">**Applies to:**</span></span>
- <span data-ttu-id="be54e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be54e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="be54e-107">高级 `IdentityInfo` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关从各种服务（包括 Azure Active Directory）获取的用户帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="be54e-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="be54e-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="be54e-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="be54e-109">该表被重命名为 `AccountInfo` 。</span><span class="sxs-lookup"><span data-stu-id="be54e-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="be54e-110">在重命名期间，门户中保存的所有查询都会自动更新。</span><span class="sxs-lookup"><span data-stu-id="be54e-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="be54e-111">检查已保存在其他位置的查询。</span><span class="sxs-lookup"><span data-stu-id="be54e-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="be54e-112">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="be54e-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="be54e-113">列名称</span><span class="sxs-lookup"><span data-stu-id="be54e-113">Column name</span></span> | <span data-ttu-id="be54e-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="be54e-114">Data type</span></span> | <span data-ttu-id="be54e-115">说明</span><span class="sxs-lookup"><span data-stu-id="be54e-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="be54e-116">string</span><span class="sxs-lookup"><span data-stu-id="be54e-116">string</span></span> | <span data-ttu-id="be54e-117">Azure AD 中帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="be54e-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="be54e-118">string</span><span class="sxs-lookup"><span data-stu-id="be54e-118">string</span></span> | <span data-ttu-id="be54e-119">帐户的用户主体 (UPN) </span><span class="sxs-lookup"><span data-stu-id="be54e-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="be54e-120">string</span><span class="sxs-lookup"><span data-stu-id="be54e-120">string</span></span> | <span data-ttu-id="be54e-121">帐户 (SID) 本地安全标识符</span><span class="sxs-lookup"><span data-stu-id="be54e-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="be54e-122">string</span><span class="sxs-lookup"><span data-stu-id="be54e-122">string</span></span> | <span data-ttu-id="be54e-123">帐户的云安全标识符</span><span class="sxs-lookup"><span data-stu-id="be54e-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="be54e-124">string</span><span class="sxs-lookup"><span data-stu-id="be54e-124">string</span></span> | <span data-ttu-id="be54e-125">帐户用户的给定名称或名字</span><span class="sxs-lookup"><span data-stu-id="be54e-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="be54e-126">string</span><span class="sxs-lookup"><span data-stu-id="be54e-126">string</span></span> | <span data-ttu-id="be54e-127">帐户用户的姓、姓或名</span><span class="sxs-lookup"><span data-stu-id="be54e-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="be54e-128">string</span><span class="sxs-lookup"><span data-stu-id="be54e-128">string</span></span> | <span data-ttu-id="be54e-129">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="be54e-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="be54e-130">通常是给定或名字、中间初始和姓氏或姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="be54e-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="be54e-131">string</span><span class="sxs-lookup"><span data-stu-id="be54e-131">string</span></span> | <span data-ttu-id="be54e-132">帐户用户所属的部门的名称</span><span class="sxs-lookup"><span data-stu-id="be54e-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="be54e-133">string</span><span class="sxs-lookup"><span data-stu-id="be54e-133">string</span></span> | <span data-ttu-id="be54e-134">帐户用户职务</span><span class="sxs-lookup"><span data-stu-id="be54e-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="be54e-135">string</span><span class="sxs-lookup"><span data-stu-id="be54e-135">string</span></span> | <span data-ttu-id="be54e-136">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="be54e-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="be54e-137">string</span><span class="sxs-lookup"><span data-stu-id="be54e-137">string</span></span> | <span data-ttu-id="be54e-138">帐户的域</span><span class="sxs-lookup"><span data-stu-id="be54e-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="be54e-139">string</span><span class="sxs-lookup"><span data-stu-id="be54e-139">string</span></span> | <span data-ttu-id="be54e-140">帐户的 SMTP 地址</span><span class="sxs-lookup"><span data-stu-id="be54e-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="be54e-141">string</span><span class="sxs-lookup"><span data-stu-id="be54e-141">string</span></span> | <span data-ttu-id="be54e-142">IP 语音 (VOIP) 会话初始 (SIP) 地址</span><span class="sxs-lookup"><span data-stu-id="be54e-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="be54e-143">string</span><span class="sxs-lookup"><span data-stu-id="be54e-143">string</span></span> | <span data-ttu-id="be54e-144">帐户用户所在的城市</span><span class="sxs-lookup"><span data-stu-id="be54e-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="be54e-145">string</span><span class="sxs-lookup"><span data-stu-id="be54e-145">string</span></span> | <span data-ttu-id="be54e-146">帐户用户所在的国家/地区</span><span class="sxs-lookup"><span data-stu-id="be54e-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="be54e-147">boolean</span><span class="sxs-lookup"><span data-stu-id="be54e-147">boolean</span></span> | <span data-ttu-id="be54e-148">指示帐户是否已启用</span><span class="sxs-lookup"><span data-stu-id="be54e-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="be54e-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="be54e-149">Related topics</span></span>
- [<span data-ttu-id="be54e-150">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="be54e-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="be54e-151">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="be54e-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="be54e-152">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="be54e-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="be54e-153">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="be54e-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="be54e-154">了解架构</span><span class="sxs-lookup"><span data-stu-id="be54e-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="be54e-155">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="be54e-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
