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
ms.openlocfilehash: b384e76439ae706520725e7193fa64224b724be0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898953"
---
# <a name="identityinfo"></a><span data-ttu-id="6cdae-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="6cdae-104">IdentityInfo</span></span>

<span data-ttu-id="6cdae-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6cdae-105">**Applies to:**</span></span>
- <span data-ttu-id="6cdae-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="6cdae-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6cdae-107">`IdentityInfo`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关从各种服务（包括 Azure Active Directory）获取的用户帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="6cdae-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="6cdae-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="6cdae-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="6cdae-109">此表已重命名 `AccountInfo` 。</span><span class="sxs-lookup"><span data-stu-id="6cdae-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="6cdae-110">在重命名过程中，保存在门户中的所有查询都将自动更新。</span><span class="sxs-lookup"><span data-stu-id="6cdae-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="6cdae-111">检查已保存在其他位置的查询。</span><span class="sxs-lookup"><span data-stu-id="6cdae-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="6cdae-112">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="6cdae-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6cdae-113">列名称</span><span class="sxs-lookup"><span data-stu-id="6cdae-113">Column name</span></span> | <span data-ttu-id="6cdae-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="6cdae-114">Data type</span></span> | <span data-ttu-id="6cdae-115">说明</span><span class="sxs-lookup"><span data-stu-id="6cdae-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="6cdae-116">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-116">string</span></span> | <span data-ttu-id="6cdae-117">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="6cdae-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="6cdae-118">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-118">string</span></span> | <span data-ttu-id="6cdae-119">帐户的用户主体名称（UPN）</span><span class="sxs-lookup"><span data-stu-id="6cdae-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="6cdae-120">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-120">string</span></span> | <span data-ttu-id="6cdae-121">帐户的本地安全标识符（SID）</span><span class="sxs-lookup"><span data-stu-id="6cdae-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="6cdae-122">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-122">string</span></span> | <span data-ttu-id="6cdae-123">帐户的云安全标识符</span><span class="sxs-lookup"><span data-stu-id="6cdae-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="6cdae-124">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-124">string</span></span> | <span data-ttu-id="6cdae-125">帐户用户的指定名称或名字</span><span class="sxs-lookup"><span data-stu-id="6cdae-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="6cdae-126">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-126">string</span></span> | <span data-ttu-id="6cdae-127">帐户用户的姓氏、系列名称或姓氏</span><span class="sxs-lookup"><span data-stu-id="6cdae-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="6cdae-128">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-128">string</span></span> | <span data-ttu-id="6cdae-129">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="6cdae-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="6cdae-130">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="6cdae-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="6cdae-131">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-131">string</span></span> | <span data-ttu-id="6cdae-132">帐户用户所属部门的名称</span><span class="sxs-lookup"><span data-stu-id="6cdae-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="6cdae-133">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-133">string</span></span> | <span data-ttu-id="6cdae-134">帐户用户的职务</span><span class="sxs-lookup"><span data-stu-id="6cdae-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="6cdae-135">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-135">string</span></span> | <span data-ttu-id="6cdae-136">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="6cdae-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6cdae-137">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-137">string</span></span> | <span data-ttu-id="6cdae-138">帐户的域</span><span class="sxs-lookup"><span data-stu-id="6cdae-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="6cdae-139">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-139">string</span></span> | <span data-ttu-id="6cdae-140">帐户的 SMTP 地址</span><span class="sxs-lookup"><span data-stu-id="6cdae-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="6cdae-141">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-141">string</span></span> | <span data-ttu-id="6cdae-142">帐户的 IP 语音（VOIP）会话初始协议（SIP）地址</span><span class="sxs-lookup"><span data-stu-id="6cdae-142">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="6cdae-143">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-143">string</span></span> | <span data-ttu-id="6cdae-144">帐户用户所在的城市</span><span class="sxs-lookup"><span data-stu-id="6cdae-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="6cdae-145">string</span><span class="sxs-lookup"><span data-stu-id="6cdae-145">string</span></span> | <span data-ttu-id="6cdae-146">帐户用户所在的国家/地区</span><span class="sxs-lookup"><span data-stu-id="6cdae-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="6cdae-147">boolean</span><span class="sxs-lookup"><span data-stu-id="6cdae-147">boolean</span></span> | <span data-ttu-id="6cdae-148">指示帐户是否已启用</span><span class="sxs-lookup"><span data-stu-id="6cdae-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6cdae-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="6cdae-149">Related topics</span></span>
- [<span data-ttu-id="6cdae-150">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="6cdae-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6cdae-151">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="6cdae-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6cdae-152">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="6cdae-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6cdae-153">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="6cdae-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6cdae-154">了解架构</span><span class="sxs-lookup"><span data-stu-id="6cdae-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6cdae-155">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="6cdae-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
