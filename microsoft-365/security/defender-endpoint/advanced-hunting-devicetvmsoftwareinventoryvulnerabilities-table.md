---
title: 高级搜寻架构中的 DeviceTvmSoftwareInventoryVulnerabilities 表
description: 在高级搜寻架构的 DeviceTvmSoftwareInventoryVulnerabilities 表中，了解设备的软件清单及其漏洞。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， 威胁 & 漏洞管理， TVM， 设备管理， 软件， 清单， 漏洞， CVE ID， OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163455"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="571e3-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="571e3-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="571e3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="571e3-105">**Applies to:**</span></span>

- [<span data-ttu-id="571e3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="571e3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="571e3-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="571e3-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="571e3-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="571e3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="571e3-109">高级搜寻架构中的 `DeviceTvmSoftwareInventoryVulnerabilities` 表包含设备上软件的[威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)清单以及这些软件产品中的任何已知漏洞。</span><span class="sxs-lookup"><span data-stu-id="571e3-109">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="571e3-110">此表还包括操作系统信息、CVE ID 和漏洞严重性信息。</span><span class="sxs-lookup"><span data-stu-id="571e3-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="571e3-111">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="571e3-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="571e3-112">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。</span><span class="sxs-lookup"><span data-stu-id="571e3-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="571e3-113">列名称</span><span class="sxs-lookup"><span data-stu-id="571e3-113">Column name</span></span> | <span data-ttu-id="571e3-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="571e3-114">Data type</span></span> | <span data-ttu-id="571e3-115">说明</span><span class="sxs-lookup"><span data-stu-id="571e3-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="571e3-116">string</span><span class="sxs-lookup"><span data-stu-id="571e3-116">string</span></span> | <span data-ttu-id="571e3-117">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="571e3-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="571e3-118">string</span><span class="sxs-lookup"><span data-stu-id="571e3-118">string</span></span> | <span data-ttu-id="571e3-119">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="571e3-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="571e3-120">string</span><span class="sxs-lookup"><span data-stu-id="571e3-120">string</span></span> | <span data-ttu-id="571e3-121">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="571e3-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="571e3-122">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="571e3-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="571e3-123">string</span><span class="sxs-lookup"><span data-stu-id="571e3-123">string</span></span> | <span data-ttu-id="571e3-124">在设备上运行的操作系统的版本</span><span class="sxs-lookup"><span data-stu-id="571e3-124">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="571e3-125">string</span><span class="sxs-lookup"><span data-stu-id="571e3-125">string</span></span> | <span data-ttu-id="571e3-126">在设备上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="571e3-126">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="571e3-127">string</span><span class="sxs-lookup"><span data-stu-id="571e3-127">string</span></span> | <span data-ttu-id="571e3-128">软件供应商的名称</span><span class="sxs-lookup"><span data-stu-id="571e3-128">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="571e3-129">string</span><span class="sxs-lookup"><span data-stu-id="571e3-129">string</span></span> | <span data-ttu-id="571e3-130">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="571e3-130">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="571e3-131">string</span><span class="sxs-lookup"><span data-stu-id="571e3-131">string</span></span> | <span data-ttu-id="571e3-132">软件产品版本号</span><span class="sxs-lookup"><span data-stu-id="571e3-132">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="571e3-133">string</span><span class="sxs-lookup"><span data-stu-id="571e3-133">string</span></span> | <span data-ttu-id="571e3-134">通用漏洞披露 (CVE) 系统下分配给安全漏洞的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="571e3-134">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="571e3-135">string</span><span class="sxs-lookup"><span data-stu-id="571e3-135">string</span></span> | <span data-ttu-id="571e3-136">基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别</span><span class="sxs-lookup"><span data-stu-id="571e3-136">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="571e3-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="571e3-137">Related topics</span></span>

- [<span data-ttu-id="571e3-138">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="571e3-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="571e3-139">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="571e3-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="571e3-140">了解架构</span><span class="sxs-lookup"><span data-stu-id="571e3-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="571e3-141">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="571e3-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
