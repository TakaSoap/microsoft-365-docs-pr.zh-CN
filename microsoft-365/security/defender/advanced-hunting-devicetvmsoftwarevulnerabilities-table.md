---
title: 高级搜寻架构中的 DeviceTvmSoftwareVulnerabilities 表
description: 了解设备上发现的软件漏洞，以及可解决高级搜寻架构的 DeviceTvmSoftwareVulnerabilities 表中每个漏洞的可用安全更新列表。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 描述， 威胁 & 漏洞管理， TVM， 设备管理， 软件， 清单， 漏洞， CVE ID， OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 17faffc45cfd1f472dec3f423681aaa3f64944a3
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023805"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="6be56-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="6be56-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6be56-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6be56-105">**Applies to:**</span></span>
- <span data-ttu-id="6be56-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6be56-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="6be56-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6be56-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="6be56-108">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="6be56-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6be56-109">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="6be56-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6be56-110">高级 `DeviceTvmSoftwareVulnerabilities` 搜寻架构中的表包含已安装 [软件&](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 漏洞的威胁和漏洞管理列表。</span><span class="sxs-lookup"><span data-stu-id="6be56-110">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="6be56-111">此表还包括操作系统信息、CVE ID 和漏洞严重性信息。</span><span class="sxs-lookup"><span data-stu-id="6be56-111">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="6be56-112">例如，您可以使用此表来搜寻涉及其软件中具有严重漏洞的设备的事件。</span><span class="sxs-lookup"><span data-stu-id="6be56-112">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="6be56-113">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="6be56-113">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="6be56-114">和 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 表已替换 `DeviceTvmSoftwareInventoryVulnerabilities` 表。</span><span class="sxs-lookup"><span data-stu-id="6be56-114">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="6be56-115">前两个表一起包含更多列，可用于帮助通知 vulnerablity 管理活动或搜寻易受攻击的设备。</span><span class="sxs-lookup"><span data-stu-id="6be56-115">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="6be56-116">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="6be56-116">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6be56-117">列名称</span><span class="sxs-lookup"><span data-stu-id="6be56-117">Column name</span></span> | <span data-ttu-id="6be56-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="6be56-118">Data type</span></span> | <span data-ttu-id="6be56-119">说明</span><span class="sxs-lookup"><span data-stu-id="6be56-119">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="6be56-120">string</span><span class="sxs-lookup"><span data-stu-id="6be56-120">string</span></span> | <span data-ttu-id="6be56-121">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="6be56-121">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6be56-122">string</span><span class="sxs-lookup"><span data-stu-id="6be56-122">string</span></span> | <span data-ttu-id="6be56-123">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="6be56-123">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="6be56-124">string</span><span class="sxs-lookup"><span data-stu-id="6be56-124">string</span></span> | <span data-ttu-id="6be56-125">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="6be56-125">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="6be56-126">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="6be56-126">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="6be56-127">string</span><span class="sxs-lookup"><span data-stu-id="6be56-127">string</span></span> | <span data-ttu-id="6be56-128">计算机上运行的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="6be56-128">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="6be56-129">string</span><span class="sxs-lookup"><span data-stu-id="6be56-129">string</span></span> | <span data-ttu-id="6be56-130">计算机上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="6be56-130">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="6be56-131">string</span><span class="sxs-lookup"><span data-stu-id="6be56-131">string</span></span> | <span data-ttu-id="6be56-132">软件供应商的名称</span><span class="sxs-lookup"><span data-stu-id="6be56-132">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="6be56-133">string</span><span class="sxs-lookup"><span data-stu-id="6be56-133">string</span></span> | <span data-ttu-id="6be56-134">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="6be56-134">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="6be56-135">string</span><span class="sxs-lookup"><span data-stu-id="6be56-135">string</span></span> | <span data-ttu-id="6be56-136">软件产品版本号</span><span class="sxs-lookup"><span data-stu-id="6be56-136">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="6be56-137">string</span><span class="sxs-lookup"><span data-stu-id="6be56-137">string</span></span> | <span data-ttu-id="6be56-138">通用漏洞披露 (CVE) 系统下分配给安全漏洞的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="6be56-138">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="6be56-139">string</span><span class="sxs-lookup"><span data-stu-id="6be56-139">string</span></span> | <span data-ttu-id="6be56-140">基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别</span><span class="sxs-lookup"><span data-stu-id="6be56-140">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="6be56-141">string</span><span class="sxs-lookup"><span data-stu-id="6be56-141">string</span></span> | <span data-ttu-id="6be56-142">软件供应商提供的用于解决漏洞的安全更新的名称或说明</span><span class="sxs-lookup"><span data-stu-id="6be56-142">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="6be56-143">string</span><span class="sxs-lookup"><span data-stu-id="6be56-143">string</span></span> | <span data-ttu-id="6be56-144">相应指南或知识库的适用安全更新或标识符的标识符 (KB) 文章</span><span class="sxs-lookup"><span data-stu-id="6be56-144">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="6be56-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="6be56-145">Related topics</span></span>

- [<span data-ttu-id="6be56-146">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="6be56-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6be56-147">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="6be56-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6be56-148">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="6be56-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6be56-149">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="6be56-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6be56-150">了解架构</span><span class="sxs-lookup"><span data-stu-id="6be56-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6be56-151">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="6be56-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6be56-152">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="6be56-152">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)