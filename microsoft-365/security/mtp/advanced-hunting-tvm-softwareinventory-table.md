---
title: 高级搜寻架构中的 DeviceTvmSoftwareInventoryVulnerabilities 表
description: 在高级搜寻架构的 DeviceTvmSoftwareInventoryVulnerabilities 表中，了解设备的软件清单及其漏洞。
keywords: 高级搜寻, 威胁搜寻, 网络威胁搜寻, 搜索, 查询, 遥测, 架构参考, kusto, 表格, 列, 数据类型, 说明, 威胁和漏洞管理, TVM, 设备管理, 软件, 清单, 漏洞, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f7c7ab393a956aa894a0ca8704ea0e99a82addc9
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910785"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="ed999-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="ed999-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="ed999-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ed999-105">**Applies to:**</span></span>
- <span data-ttu-id="ed999-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="ed999-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="ed999-107">高级搜寻架构中的 `DeviceTvmSoftwareInventoryVulnerabilities` 表包含设备上软件的[威胁和漏洞管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)清单以及这些软件产品中的任何已知漏洞。</span><span class="sxs-lookup"><span data-stu-id="ed999-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="ed999-108">此表还包括操作系统信息、CVE ID 和漏洞严重性信息。</span><span class="sxs-lookup"><span data-stu-id="ed999-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="ed999-109">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="ed999-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="ed999-110">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="ed999-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ed999-111">列名称</span><span class="sxs-lookup"><span data-stu-id="ed999-111">Column name</span></span> | <span data-ttu-id="ed999-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="ed999-112">Data type</span></span> | <span data-ttu-id="ed999-113">说明</span><span class="sxs-lookup"><span data-stu-id="ed999-113">Description</span></span> |
|-------------|-----------|-------------|
| `MachineId` | <span data-ttu-id="ed999-114">string</span><span class="sxs-lookup"><span data-stu-id="ed999-114">string</span></span> | <span data-ttu-id="ed999-115">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="ed999-115">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="ed999-116">string</span><span class="sxs-lookup"><span data-stu-id="ed999-116">string</span></span> | <span data-ttu-id="ed999-117">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ed999-117">Fully qualified domain name (FQDN) of the pool</span></span> |
| `OSPlatform` | <span data-ttu-id="ed999-118">string</span><span class="sxs-lookup"><span data-stu-id="ed999-118">string</span></span> | <span data-ttu-id="ed999-119">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="ed999-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="ed999-120">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="ed999-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="ed999-121">string</span><span class="sxs-lookup"><span data-stu-id="ed999-121">string</span></span> | <span data-ttu-id="ed999-122">计算机上运行的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="ed999-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="ed999-123">string</span><span class="sxs-lookup"><span data-stu-id="ed999-123">string</span></span> | <span data-ttu-id="ed999-124">计算机上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="ed999-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="ed999-125">string</span><span class="sxs-lookup"><span data-stu-id="ed999-125">string</span></span> | <span data-ttu-id="ed999-126">基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别</span><span class="sxs-lookup"><span data-stu-id="ed999-126">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `SoftwareName` | <span data-ttu-id="ed999-127">string</span><span class="sxs-lookup"><span data-stu-id="ed999-127">string</span></span> | <span data-ttu-id="ed999-128">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="ed999-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="ed999-129">string</span><span class="sxs-lookup"><span data-stu-id="ed999-129">string</span></span> | <span data-ttu-id="ed999-130">软件产品版本号</span><span class="sxs-lookup"><span data-stu-id="ed999-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="ed999-131">string</span><span class="sxs-lookup"><span data-stu-id="ed999-131">string</span></span> | <span data-ttu-id="ed999-132">通用漏洞披露 (CVE) 系统下分配给安全漏洞的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="ed999-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="ed999-133">string</span><span class="sxs-lookup"><span data-stu-id="ed999-133">string</span></span> | <span data-ttu-id="ed999-134">基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别</span><span class="sxs-lookup"><span data-stu-id="ed999-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="ed999-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="ed999-135">Related topics</span></span>

- [<span data-ttu-id="ed999-136">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="ed999-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ed999-137">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="ed999-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ed999-138">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="ed999-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ed999-139">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="ed999-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ed999-140">了解架构</span><span class="sxs-lookup"><span data-stu-id="ed999-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ed999-141">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="ed999-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ed999-142">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="ed999-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
