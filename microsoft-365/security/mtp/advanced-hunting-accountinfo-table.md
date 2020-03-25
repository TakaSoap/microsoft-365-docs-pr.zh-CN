---
title: 高级搜寻架构中的 AccountInfo 表
description: 了解高级搜寻架构的 AccountInfo 表中的用户帐户信息
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、AlertInfo、警报、实体、证据、文件、IP 地址设备、计算机、用户、帐户
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929524"
---
# <a name="accountinfo"></a><span data-ttu-id="a4720-104">AccountInfo</span><span class="sxs-lookup"><span data-stu-id="a4720-104">AccountInfo</span></span>

<span data-ttu-id="a4720-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a4720-105">**Applies to:**</span></span>
- <span data-ttu-id="a4720-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="a4720-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a4720-107">`AccountInfo` [高级搜寻](advanced-hunting-overview.md)架构中的表包含有关从各种服务（包括 Azure Active Directory）获取的用户帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="a4720-107">The `AccountInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="a4720-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="a4720-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a4720-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="a4720-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a4720-110">列名称</span><span class="sxs-lookup"><span data-stu-id="a4720-110">Column name</span></span> | <span data-ttu-id="a4720-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="a4720-111">Data type</span></span> | <span data-ttu-id="a4720-112">说明</span><span class="sxs-lookup"><span data-stu-id="a4720-112">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="a4720-113">string</span><span class="sxs-lookup"><span data-stu-id="a4720-113">string</span></span> | <span data-ttu-id="a4720-114">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="a4720-114">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="a4720-115">string</span><span class="sxs-lookup"><span data-stu-id="a4720-115">string</span></span> | <span data-ttu-id="a4720-116">帐户的用户主体名称（UPN）</span><span class="sxs-lookup"><span data-stu-id="a4720-116">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="a4720-117">string</span><span class="sxs-lookup"><span data-stu-id="a4720-117">string</span></span> | <span data-ttu-id="a4720-118">帐户的本地安全标识符（SID）</span><span class="sxs-lookup"><span data-stu-id="a4720-118">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="a4720-119">string</span><span class="sxs-lookup"><span data-stu-id="a4720-119">string</span></span> | <span data-ttu-id="a4720-120">帐户的云安全标识符</span><span class="sxs-lookup"><span data-stu-id="a4720-120">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="a4720-121">string</span><span class="sxs-lookup"><span data-stu-id="a4720-121">string</span></span> | <span data-ttu-id="a4720-122">帐户用户的指定名称或名字</span><span class="sxs-lookup"><span data-stu-id="a4720-122">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="a4720-123">string</span><span class="sxs-lookup"><span data-stu-id="a4720-123">string</span></span> | <span data-ttu-id="a4720-124">帐户用户的姓氏、系列名称或姓氏</span><span class="sxs-lookup"><span data-stu-id="a4720-124">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="a4720-125">string</span><span class="sxs-lookup"><span data-stu-id="a4720-125">string</span></span> | <span data-ttu-id="a4720-126">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="a4720-126">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="a4720-127">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="a4720-127">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="a4720-128">string</span><span class="sxs-lookup"><span data-stu-id="a4720-128">string</span></span> | <span data-ttu-id="a4720-129">帐户用户所属部门的名称</span><span class="sxs-lookup"><span data-stu-id="a4720-129">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="a4720-130">string</span><span class="sxs-lookup"><span data-stu-id="a4720-130">string</span></span> | <span data-ttu-id="a4720-131">帐户用户的职务</span><span class="sxs-lookup"><span data-stu-id="a4720-131">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="a4720-132">string</span><span class="sxs-lookup"><span data-stu-id="a4720-132">string</span></span> | <span data-ttu-id="a4720-133">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="a4720-133">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="a4720-134">string</span><span class="sxs-lookup"><span data-stu-id="a4720-134">string</span></span> | <span data-ttu-id="a4720-135">帐户的域</span><span class="sxs-lookup"><span data-stu-id="a4720-135">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="a4720-136">string</span><span class="sxs-lookup"><span data-stu-id="a4720-136">string</span></span> | <span data-ttu-id="a4720-137">帐户的 SMTP 地址</span><span class="sxs-lookup"><span data-stu-id="a4720-137">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="a4720-138">string</span><span class="sxs-lookup"><span data-stu-id="a4720-138">string</span></span> | <span data-ttu-id="a4720-139">帐户的 IP 语音（VOIP）会话初始协议（SIP）地址</span><span class="sxs-lookup"><span data-stu-id="a4720-139">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="a4720-140">string</span><span class="sxs-lookup"><span data-stu-id="a4720-140">string</span></span> | <span data-ttu-id="a4720-141">帐户用户所在的城市</span><span class="sxs-lookup"><span data-stu-id="a4720-141">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="a4720-142">string</span><span class="sxs-lookup"><span data-stu-id="a4720-142">string</span></span> | <span data-ttu-id="a4720-143">帐户用户所在的国家/地区</span><span class="sxs-lookup"><span data-stu-id="a4720-143">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="a4720-144">boolean</span><span class="sxs-lookup"><span data-stu-id="a4720-144">boolean</span></span> | <span data-ttu-id="a4720-145">指示帐户是否已启用</span><span class="sxs-lookup"><span data-stu-id="a4720-145">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a4720-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="a4720-146">Related topics</span></span>
- [<span data-ttu-id="a4720-147">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="a4720-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a4720-148">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="a4720-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a4720-149">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="a4720-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a4720-150">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="a4720-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a4720-151">了解架构</span><span class="sxs-lookup"><span data-stu-id="a4720-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a4720-152">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="a4720-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
