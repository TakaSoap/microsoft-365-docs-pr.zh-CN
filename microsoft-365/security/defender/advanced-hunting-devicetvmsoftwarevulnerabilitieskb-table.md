---
title: 高级搜寻架构中的 DeviceTvmSoftwareVulnerabilitiesKB 表
description: 在高级搜寻架构的 DeviceTvmSoftwareVulnerabilitiesKB 表中，了解由威胁和漏洞管理跟踪的软件漏洞。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构， 参考， kusto， 表格， 列， 数据类型， 说明， 威胁 & 漏洞管理， TVM， 设备管理， 软件， 清单， 漏洞， CVE ID， CVSS， DeviceTvmSoftwareVulnerabilitiesKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023793"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="8d664-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="8d664-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8d664-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8d664-105">**Applies to:**</span></span>
- <span data-ttu-id="8d664-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d664-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="8d664-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8d664-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="8d664-108">高级搜寻架构中的 `DeviceTvmSoftwareVulnerabilitiesKB` 表包含漏洞列表，[威胁和漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)会针对这些漏洞对设备进行评估。</span><span class="sxs-lookup"><span data-stu-id="8d664-108">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="8d664-109">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="8d664-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="8d664-110">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="8d664-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8d664-111">列名称</span><span class="sxs-lookup"><span data-stu-id="8d664-111">Column name</span></span> | <span data-ttu-id="8d664-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="8d664-112">Data type</span></span> | <span data-ttu-id="8d664-113">说明</span><span class="sxs-lookup"><span data-stu-id="8d664-113">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="8d664-114">string</span><span class="sxs-lookup"><span data-stu-id="8d664-114">string</span></span> | <span data-ttu-id="8d664-115">通用漏洞披露 (CVE) 系统下分配给安全漏洞的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="8d664-115">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="8d664-116">string</span><span class="sxs-lookup"><span data-stu-id="8d664-116">string</span></span> | <span data-ttu-id="8d664-117">通用漏洞评分系统 (CVSS) 下分配给安全漏洞的严重性评分</span><span class="sxs-lookup"><span data-stu-id="8d664-117">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="8d664-118">boolean</span><span class="sxs-lookup"><span data-stu-id="8d664-118">boolean</span></span> | <span data-ttu-id="8d664-119">指示该漏洞的攻击代码是否公开可用</span><span class="sxs-lookup"><span data-stu-id="8d664-119">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="8d664-120">string</span><span class="sxs-lookup"><span data-stu-id="8d664-120">string</span></span> | <span data-ttu-id="8d664-121">基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别</span><span class="sxs-lookup"><span data-stu-id="8d664-121">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="8d664-122">datetime</span><span class="sxs-lookup"><span data-stu-id="8d664-122">datetime</span></span> | <span data-ttu-id="8d664-123">上次修改项或相关元数据的日期和时间</span><span class="sxs-lookup"><span data-stu-id="8d664-123">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="8d664-124">datetime</span><span class="sxs-lookup"><span data-stu-id="8d664-124">datetime</span></span> | <span data-ttu-id="8d664-125">向公众公开漏洞的日期</span><span class="sxs-lookup"><span data-stu-id="8d664-125">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="8d664-126">string</span><span class="sxs-lookup"><span data-stu-id="8d664-126">string</span></span> | <span data-ttu-id="8d664-127">漏洞和相关风险的描述</span><span class="sxs-lookup"><span data-stu-id="8d664-127">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="8d664-128">string</span><span class="sxs-lookup"><span data-stu-id="8d664-128">string</span></span> | <span data-ttu-id="8d664-129">受漏洞影响的所有软件产品列表</span><span class="sxs-lookup"><span data-stu-id="8d664-129">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8d664-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="8d664-130">Related topics</span></span>

- [<span data-ttu-id="8d664-131">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="8d664-131">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8d664-132">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="8d664-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8d664-133">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="8d664-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8d664-134">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="8d664-134">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8d664-135">了解架构</span><span class="sxs-lookup"><span data-stu-id="8d664-135">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8d664-136">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="8d664-136">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="8d664-137">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="8d664-137">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)