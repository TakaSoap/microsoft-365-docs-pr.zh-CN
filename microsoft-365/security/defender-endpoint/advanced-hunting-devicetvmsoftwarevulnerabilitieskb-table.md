---
title: 高级搜寻架构中的 DeviceTvmSoftwareVulnerabilitiesKB 表
description: 在高级搜寻架构的 DeviceTvmSoftwareVulnerabilitiesKB 表中，了解由威胁和漏洞管理跟踪的软件漏洞。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， 威胁 & 漏洞管理， TVM， 设备管理， 软件， 清单， 漏洞， CVE ID， CVSS， DeviceTvmSoftwareVulnerabilitiesKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055114"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="4ab7b-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="4ab7b-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4ab7b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4ab7b-105">**Applies to:**</span></span>
- [<span data-ttu-id="4ab7b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4ab7b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="4ab7b-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="4ab7b-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4ab7b-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4ab7b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="4ab7b-109">高级搜寻架构中的 `DeviceTvmSoftwareVulnerabilitiesKB` 表包含漏洞列表，[威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)会针对这些漏洞对设备进行评估。</span><span class="sxs-lookup"><span data-stu-id="4ab7b-109">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) assesses devices for.</span></span> <span data-ttu-id="4ab7b-110">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="4ab7b-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="4ab7b-111">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="4ab7b-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="4ab7b-112">列名称</span><span class="sxs-lookup"><span data-stu-id="4ab7b-112">Column name</span></span> | <span data-ttu-id="4ab7b-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="4ab7b-113">Data type</span></span> | <span data-ttu-id="4ab7b-114">说明</span><span class="sxs-lookup"><span data-stu-id="4ab7b-114">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="4ab7b-115">string</span><span class="sxs-lookup"><span data-stu-id="4ab7b-115">string</span></span> | <span data-ttu-id="4ab7b-116">通用漏洞披露 (CVE) 系统下分配给安全漏洞的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="4ab7b-116">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="4ab7b-117">string</span><span class="sxs-lookup"><span data-stu-id="4ab7b-117">string</span></span> | <span data-ttu-id="4ab7b-118">通用漏洞评分系统 (CVSS) 下分配给安全漏洞的严重性评分</span><span class="sxs-lookup"><span data-stu-id="4ab7b-118">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="4ab7b-119">boolean</span><span class="sxs-lookup"><span data-stu-id="4ab7b-119">boolean</span></span> | <span data-ttu-id="4ab7b-120">指示该漏洞的攻击代码是否公开可用</span><span class="sxs-lookup"><span data-stu-id="4ab7b-120">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="4ab7b-121">string</span><span class="sxs-lookup"><span data-stu-id="4ab7b-121">string</span></span> | <span data-ttu-id="4ab7b-122">基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别</span><span class="sxs-lookup"><span data-stu-id="4ab7b-122">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="4ab7b-123">datetime</span><span class="sxs-lookup"><span data-stu-id="4ab7b-123">datetime</span></span> | <span data-ttu-id="4ab7b-124">上次修改项或相关元数据的日期和时间</span><span class="sxs-lookup"><span data-stu-id="4ab7b-124">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="4ab7b-125">datetime</span><span class="sxs-lookup"><span data-stu-id="4ab7b-125">datetime</span></span> | <span data-ttu-id="4ab7b-126">向公众公开漏洞的日期</span><span class="sxs-lookup"><span data-stu-id="4ab7b-126">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="4ab7b-127">string</span><span class="sxs-lookup"><span data-stu-id="4ab7b-127">string</span></span> | <span data-ttu-id="4ab7b-128">漏洞和相关风险的描述</span><span class="sxs-lookup"><span data-stu-id="4ab7b-128">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="4ab7b-129">string</span><span class="sxs-lookup"><span data-stu-id="4ab7b-129">string</span></span> | <span data-ttu-id="4ab7b-130">受漏洞影响的所有软件产品列表</span><span class="sxs-lookup"><span data-stu-id="4ab7b-130">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4ab7b-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="4ab7b-131">Related topics</span></span>

- [<span data-ttu-id="4ab7b-132">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="4ab7b-132">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4ab7b-133">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="4ab7b-133">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4ab7b-134">了解架构</span><span class="sxs-lookup"><span data-stu-id="4ab7b-134">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="4ab7b-135">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="4ab7b-135">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
