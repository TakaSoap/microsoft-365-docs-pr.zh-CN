---
title: 高级搜寻架构中的 AlertEvidence 表
description: 了解与高级搜寻架构的 AlertEvidence 表中生成的警报相关联的文件、网络地址、用户或设备信息
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、AlertInfo、设备、实体、证据、文件、IP 地址、设备、计算机、用户、帐户
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
ms.openlocfilehash: da6e84725aa391e4cb6056fadd327fdba2436214
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617082"
---
# <a name="alertevidence"></a><span data-ttu-id="a286b-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="a286b-104">AlertEvidence</span></span>

<span data-ttu-id="a286b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a286b-105">**Applies to:**</span></span>
- <span data-ttu-id="a286b-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="a286b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a286b-107">`AlertEvidence`[高级搜寻](advanced-hunting-overview.md)架构中的表格包含有关各种实体（文件、IP 地址、url、用户或设备）的信息，这些信息与 Microsoft Defender ATP、Office 365 ATP、Microsoft 云应用安全性和 Azure atp 中的警报相关联。</span><span class="sxs-lookup"><span data-stu-id="a286b-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="a286b-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="a286b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a286b-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="a286b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a286b-110">列名称</span><span class="sxs-lookup"><span data-stu-id="a286b-110">Column name</span></span> | <span data-ttu-id="a286b-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="a286b-111">Data type</span></span> | <span data-ttu-id="a286b-112">说明</span><span class="sxs-lookup"><span data-stu-id="a286b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a286b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="a286b-113">datetime</span></span> | <span data-ttu-id="a286b-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="a286b-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="a286b-115">string</span><span class="sxs-lookup"><span data-stu-id="a286b-115">string</span></span> | <span data-ttu-id="a286b-116">警报的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="a286b-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="a286b-117">string</span><span class="sxs-lookup"><span data-stu-id="a286b-117">string</span></span> | <span data-ttu-id="a286b-118">对象的类型，如文件、进程、设备或用户</span><span class="sxs-lookup"><span data-stu-id="a286b-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="a286b-119">string</span><span class="sxs-lookup"><span data-stu-id="a286b-119">string</span></span> | <span data-ttu-id="a286b-120">如何将实体包含在警报中，以指示它是受影响的还是只是相关的</span><span class="sxs-lookup"><span data-stu-id="a286b-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="a286b-121">string</span><span class="sxs-lookup"><span data-stu-id="a286b-121">string</span></span> | <span data-ttu-id="a286b-122">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="a286b-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="a286b-123">string</span><span class="sxs-lookup"><span data-stu-id="a286b-123">string</span></span> | <span data-ttu-id="a286b-124">录制操作所应用到的文件的 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="a286b-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="a286b-125">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="a286b-125">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="a286b-126">string</span><span class="sxs-lookup"><span data-stu-id="a286b-126">string</span></span> | <span data-ttu-id="a286b-127">连接到的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="a286b-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="a286b-128">string</span><span class="sxs-lookup"><span data-stu-id="a286b-128">string</span></span> | <span data-ttu-id="a286b-129">连接到的 URL 或完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="a286b-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="a286b-130">string</span><span class="sxs-lookup"><span data-stu-id="a286b-130">string</span></span> | <span data-ttu-id="a286b-131">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="a286b-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="a286b-132">string</span><span class="sxs-lookup"><span data-stu-id="a286b-132">string</span></span> | <span data-ttu-id="a286b-133">帐户的域</span><span class="sxs-lookup"><span data-stu-id="a286b-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="a286b-134">string</span><span class="sxs-lookup"><span data-stu-id="a286b-134">string</span></span> | <span data-ttu-id="a286b-135">帐户的安全标识符（SID）</span><span class="sxs-lookup"><span data-stu-id="a286b-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="a286b-136">string</span><span class="sxs-lookup"><span data-stu-id="a286b-136">string</span></span> | <span data-ttu-id="a286b-137">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="a286b-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="a286b-138">string</span><span class="sxs-lookup"><span data-stu-id="a286b-138">string</span></span> | <span data-ttu-id="a286b-139">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="a286b-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="a286b-140">string</span><span class="sxs-lookup"><span data-stu-id="a286b-140">string</span></span> | <span data-ttu-id="a286b-141">已在其下对可疑或恶意文件或流程进行了分类的恶意软件系列</span><span class="sxs-lookup"><span data-stu-id="a286b-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="a286b-142">string</span><span class="sxs-lookup"><span data-stu-id="a286b-142">string</span></span> | <span data-ttu-id="a286b-143">指示实体是否为网络连接的源或目标</span><span class="sxs-lookup"><span data-stu-id="a286b-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="a286b-144">string</span><span class="sxs-lookup"><span data-stu-id="a286b-144">string</span></span> | <span data-ttu-id="a286b-145">有关 JSON 数组格式事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="a286b-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a286b-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="a286b-146">Related topics</span></span>
- [<span data-ttu-id="a286b-147">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="a286b-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a286b-148">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="a286b-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a286b-149">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="a286b-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a286b-150">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="a286b-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a286b-151">了解架构</span><span class="sxs-lookup"><span data-stu-id="a286b-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a286b-152">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="a286b-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
