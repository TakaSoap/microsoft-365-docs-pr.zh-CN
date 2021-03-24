---
title: 高级搜寻架构中的 DeviceTvmSoftwareVulnerabilities 表
description: 了解设备上发现的软件漏洞，以及解决高级搜寻架构的 DeviceTvmSoftwareVulnerabilities 表中每个漏洞的可用安全更新列表。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， 威胁 & 漏洞管理， TVM， 设备管理， 软件， 清单， 漏洞， CVE ID， OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056392"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="fed25-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="fed25-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fed25-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="fed25-105">**Applies to:**</span></span>
- [<span data-ttu-id="fed25-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fed25-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="fed25-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="fed25-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fed25-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="fed25-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="fed25-109">高级 `DeviceTvmSoftwareVulnerabilities` 搜寻架构中的表包含已安装 [软件&](next-gen-threat-and-vuln-mgt.md) 漏洞的威胁和漏洞管理列表。</span><span class="sxs-lookup"><span data-stu-id="fed25-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="fed25-110">此表还包括操作系统信息、CVE ID 和漏洞严重性信息。</span><span class="sxs-lookup"><span data-stu-id="fed25-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="fed25-111">例如，您可以使用此表来搜寻涉及其软件中具有严重漏洞的设备的事件。</span><span class="sxs-lookup"><span data-stu-id="fed25-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="fed25-112">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="fed25-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="fed25-113">和 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 表已替换 `DeviceTvmSoftwareInventoryVulnerabilities` 表。</span><span class="sxs-lookup"><span data-stu-id="fed25-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="fed25-114">前两个表一起包含可用于帮助通知漏洞管理活动的更多列。</span><span class="sxs-lookup"><span data-stu-id="fed25-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="fed25-115">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。</span><span class="sxs-lookup"><span data-stu-id="fed25-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="fed25-116">列名称</span><span class="sxs-lookup"><span data-stu-id="fed25-116">Column name</span></span> | <span data-ttu-id="fed25-117">数据类型</span><span class="sxs-lookup"><span data-stu-id="fed25-117">Data type</span></span> | <span data-ttu-id="fed25-118">说明</span><span class="sxs-lookup"><span data-stu-id="fed25-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="fed25-119">string</span><span class="sxs-lookup"><span data-stu-id="fed25-119">string</span></span> | <span data-ttu-id="fed25-120">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="fed25-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="fed25-121">string</span><span class="sxs-lookup"><span data-stu-id="fed25-121">string</span></span> | <span data-ttu-id="fed25-122">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="fed25-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="fed25-123">string</span><span class="sxs-lookup"><span data-stu-id="fed25-123">string</span></span> | <span data-ttu-id="fed25-124">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="fed25-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="fed25-125">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="fed25-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="fed25-126">string</span><span class="sxs-lookup"><span data-stu-id="fed25-126">string</span></span> | <span data-ttu-id="fed25-127">在设备上运行的操作系统的版本</span><span class="sxs-lookup"><span data-stu-id="fed25-127">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="fed25-128">string</span><span class="sxs-lookup"><span data-stu-id="fed25-128">string</span></span> | <span data-ttu-id="fed25-129">在设备上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="fed25-129">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="fed25-130">string</span><span class="sxs-lookup"><span data-stu-id="fed25-130">string</span></span> | <span data-ttu-id="fed25-131">软件供应商的名称</span><span class="sxs-lookup"><span data-stu-id="fed25-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="fed25-132">string</span><span class="sxs-lookup"><span data-stu-id="fed25-132">string</span></span> | <span data-ttu-id="fed25-133">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="fed25-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="fed25-134">string</span><span class="sxs-lookup"><span data-stu-id="fed25-134">string</span></span> | <span data-ttu-id="fed25-135">软件产品版本号</span><span class="sxs-lookup"><span data-stu-id="fed25-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="fed25-136">string</span><span class="sxs-lookup"><span data-stu-id="fed25-136">string</span></span> | <span data-ttu-id="fed25-137">通用漏洞披露 (CVE) 系统下分配给安全漏洞的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="fed25-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="fed25-138">string</span><span class="sxs-lookup"><span data-stu-id="fed25-138">string</span></span> | <span data-ttu-id="fed25-139">基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别</span><span class="sxs-lookup"><span data-stu-id="fed25-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="fed25-140">string</span><span class="sxs-lookup"><span data-stu-id="fed25-140">string</span></span> | <span data-ttu-id="fed25-141">软件供应商提供的用于解决漏洞的安全更新的名称或说明</span><span class="sxs-lookup"><span data-stu-id="fed25-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="fed25-142">string</span><span class="sxs-lookup"><span data-stu-id="fed25-142">string</span></span> | <span data-ttu-id="fed25-143">相应指南或知识库的适用安全更新或标识符的标识符 (KB) 文章</span><span class="sxs-lookup"><span data-stu-id="fed25-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="fed25-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="fed25-144">Related topics</span></span>

- [<span data-ttu-id="fed25-145">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="fed25-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fed25-146">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="fed25-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fed25-147">了解架构</span><span class="sxs-lookup"><span data-stu-id="fed25-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="fed25-148">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="fed25-148">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
