---
title: 高级搜寻架构中的 IdentityInfo 表
description: 了解高级搜寻架构的 IdentityInfo 表中的用户帐户信息
keywords: 高级搜索、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、AccountInfo、IdentityInfo、帐户
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
ms.openlocfilehash: 6922f50906013cfbfa3bd63c69fff3e89ed46cd5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196817"
---
# <a name="identityinfo"></a><span data-ttu-id="9546f-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="9546f-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9546f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9546f-105">**Applies to:**</span></span>
- <span data-ttu-id="9546f-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="9546f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="9546f-107">`IdentityInfo`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关从各种服务（包括 Azure Active Directory）获取的用户帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="9546f-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="9546f-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="9546f-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="9546f-109">此表已重命名 `AccountInfo` 。</span><span class="sxs-lookup"><span data-stu-id="9546f-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="9546f-110">在重命名过程中，保存在门户中的所有查询都将自动更新。</span><span class="sxs-lookup"><span data-stu-id="9546f-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="9546f-111">检查已保存在其他位置的查询。</span><span class="sxs-lookup"><span data-stu-id="9546f-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="9546f-112">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="9546f-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9546f-113">列名称</span><span class="sxs-lookup"><span data-stu-id="9546f-113">Column name</span></span> | <span data-ttu-id="9546f-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="9546f-114">Data type</span></span> | <span data-ttu-id="9546f-115">说明</span><span class="sxs-lookup"><span data-stu-id="9546f-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="9546f-116">string</span><span class="sxs-lookup"><span data-stu-id="9546f-116">string</span></span> | <span data-ttu-id="9546f-117">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="9546f-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="9546f-118">string</span><span class="sxs-lookup"><span data-stu-id="9546f-118">string</span></span> | <span data-ttu-id="9546f-119">帐户的用户主体名称 (UPN) </span><span class="sxs-lookup"><span data-stu-id="9546f-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="9546f-120">string</span><span class="sxs-lookup"><span data-stu-id="9546f-120">string</span></span> | <span data-ttu-id="9546f-121">帐户的本地安全标识符 (SID) </span><span class="sxs-lookup"><span data-stu-id="9546f-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="9546f-122">string</span><span class="sxs-lookup"><span data-stu-id="9546f-122">string</span></span> | <span data-ttu-id="9546f-123">帐户的云安全标识符</span><span class="sxs-lookup"><span data-stu-id="9546f-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="9546f-124">string</span><span class="sxs-lookup"><span data-stu-id="9546f-124">string</span></span> | <span data-ttu-id="9546f-125">帐户用户的指定名称或名字</span><span class="sxs-lookup"><span data-stu-id="9546f-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="9546f-126">string</span><span class="sxs-lookup"><span data-stu-id="9546f-126">string</span></span> | <span data-ttu-id="9546f-127">帐户用户的姓氏、系列名称或姓氏</span><span class="sxs-lookup"><span data-stu-id="9546f-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9546f-128">string</span><span class="sxs-lookup"><span data-stu-id="9546f-128">string</span></span> | <span data-ttu-id="9546f-129">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="9546f-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9546f-130">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="9546f-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="9546f-131">string</span><span class="sxs-lookup"><span data-stu-id="9546f-131">string</span></span> | <span data-ttu-id="9546f-132">帐户用户所属部门的名称</span><span class="sxs-lookup"><span data-stu-id="9546f-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="9546f-133">string</span><span class="sxs-lookup"><span data-stu-id="9546f-133">string</span></span> | <span data-ttu-id="9546f-134">帐户用户的职务</span><span class="sxs-lookup"><span data-stu-id="9546f-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="9546f-135">string</span><span class="sxs-lookup"><span data-stu-id="9546f-135">string</span></span> | <span data-ttu-id="9546f-136">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="9546f-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9546f-137">string</span><span class="sxs-lookup"><span data-stu-id="9546f-137">string</span></span> | <span data-ttu-id="9546f-138">帐户的域</span><span class="sxs-lookup"><span data-stu-id="9546f-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="9546f-139">string</span><span class="sxs-lookup"><span data-stu-id="9546f-139">string</span></span> | <span data-ttu-id="9546f-140">帐户的 SMTP 地址</span><span class="sxs-lookup"><span data-stu-id="9546f-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="9546f-141">string</span><span class="sxs-lookup"><span data-stu-id="9546f-141">string</span></span> | <span data-ttu-id="9546f-142">帐户的 IP 语音 (VOIP) 会话初始协议 (SIP) 地址</span><span class="sxs-lookup"><span data-stu-id="9546f-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="9546f-143">string</span><span class="sxs-lookup"><span data-stu-id="9546f-143">string</span></span> | <span data-ttu-id="9546f-144">帐户用户所在的城市</span><span class="sxs-lookup"><span data-stu-id="9546f-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="9546f-145">string</span><span class="sxs-lookup"><span data-stu-id="9546f-145">string</span></span> | <span data-ttu-id="9546f-146">帐户用户所在的国家/地区</span><span class="sxs-lookup"><span data-stu-id="9546f-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="9546f-147">boolean</span><span class="sxs-lookup"><span data-stu-id="9546f-147">boolean</span></span> | <span data-ttu-id="9546f-148">指示帐户是否已启用</span><span class="sxs-lookup"><span data-stu-id="9546f-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9546f-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="9546f-149">Related topics</span></span>
- [<span data-ttu-id="9546f-150">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="9546f-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9546f-151">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="9546f-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9546f-152">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="9546f-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9546f-153">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="9546f-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9546f-154">了解架构</span><span class="sxs-lookup"><span data-stu-id="9546f-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9546f-155">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="9546f-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
