---
title: 高级搜寻架构中的 DeviceTvmSoftwareVulnerabilities 表
description: 了解设备上发现的软件漏洞，以及可解决高级搜寻架构的 DeviceTvmSoftwareVulnerabilities 表中每个漏洞的可用安全更新列表。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， 威胁 & 漏洞管理， TVM， 设备管理， 软件， 清单， 漏洞， CVE ID， OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: dfa0c74757a5403573a9300002b92e4b2b109ebb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907248"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="69009-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="69009-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="69009-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="69009-105">**Applies to:**</span></span>
- <span data-ttu-id="69009-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69009-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="69009-107">某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="69009-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="69009-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="69009-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="69009-109">高级 `DeviceTvmSoftwareVulnerabilities` 搜寻架构中的表包含已安装 [软件&](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 漏洞的威胁和漏洞管理列表。</span><span class="sxs-lookup"><span data-stu-id="69009-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="69009-110">此表还包括操作系统信息、CVE ID 和漏洞严重性信息。</span><span class="sxs-lookup"><span data-stu-id="69009-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="69009-111">例如，您可以使用此表来搜寻涉及其软件中具有严重漏洞的设备的事件。</span><span class="sxs-lookup"><span data-stu-id="69009-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="69009-112">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="69009-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="69009-113">和 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 表已替换 `DeviceTvmSoftwareInventoryVulnerabilities` 表。</span><span class="sxs-lookup"><span data-stu-id="69009-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="69009-114">前两个表一起包含更多列，可用于帮助通知 vulnerablity 管理活动或搜寻易受攻击的设备。</span><span class="sxs-lookup"><span data-stu-id="69009-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="69009-115">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="69009-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="69009-116">列名称</span><span class="sxs-lookup"><span data-stu-id="69009-116">Column name</span></span> | <span data-ttu-id="69009-117">数据类型</span><span class="sxs-lookup"><span data-stu-id="69009-117">Data type</span></span> | <span data-ttu-id="69009-118">说明</span><span class="sxs-lookup"><span data-stu-id="69009-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="69009-119">string</span><span class="sxs-lookup"><span data-stu-id="69009-119">string</span></span> | <span data-ttu-id="69009-120">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="69009-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="69009-121">string</span><span class="sxs-lookup"><span data-stu-id="69009-121">string</span></span> | <span data-ttu-id="69009-122">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="69009-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="69009-123">string</span><span class="sxs-lookup"><span data-stu-id="69009-123">string</span></span> | <span data-ttu-id="69009-124">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="69009-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="69009-125">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="69009-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="69009-126">string</span><span class="sxs-lookup"><span data-stu-id="69009-126">string</span></span> | <span data-ttu-id="69009-127">计算机上运行的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="69009-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="69009-128">string</span><span class="sxs-lookup"><span data-stu-id="69009-128">string</span></span> | <span data-ttu-id="69009-129">计算机上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="69009-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="69009-130">string</span><span class="sxs-lookup"><span data-stu-id="69009-130">string</span></span> | <span data-ttu-id="69009-131">软件供应商的名称</span><span class="sxs-lookup"><span data-stu-id="69009-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="69009-132">string</span><span class="sxs-lookup"><span data-stu-id="69009-132">string</span></span> | <span data-ttu-id="69009-133">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="69009-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="69009-134">string</span><span class="sxs-lookup"><span data-stu-id="69009-134">string</span></span> | <span data-ttu-id="69009-135">软件产品版本号</span><span class="sxs-lookup"><span data-stu-id="69009-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="69009-136">string</span><span class="sxs-lookup"><span data-stu-id="69009-136">string</span></span> | <span data-ttu-id="69009-137">通用漏洞披露 (CVE) 系统下分配给安全漏洞的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="69009-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="69009-138">string</span><span class="sxs-lookup"><span data-stu-id="69009-138">string</span></span> | <span data-ttu-id="69009-139">基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别</span><span class="sxs-lookup"><span data-stu-id="69009-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="69009-140">string</span><span class="sxs-lookup"><span data-stu-id="69009-140">string</span></span> | <span data-ttu-id="69009-141">软件供应商提供的用于解决漏洞的安全更新的名称或说明</span><span class="sxs-lookup"><span data-stu-id="69009-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="69009-142">string</span><span class="sxs-lookup"><span data-stu-id="69009-142">string</span></span> | <span data-ttu-id="69009-143">相应指南或知识库的适用安全更新或标识符的标识符 (KB) 文章</span><span class="sxs-lookup"><span data-stu-id="69009-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="69009-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="69009-144">Related topics</span></span>

- [<span data-ttu-id="69009-145">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="69009-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="69009-146">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="69009-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="69009-147">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="69009-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="69009-148">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="69009-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="69009-149">了解架构</span><span class="sxs-lookup"><span data-stu-id="69009-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="69009-150">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="69009-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="69009-151">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="69009-151">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)