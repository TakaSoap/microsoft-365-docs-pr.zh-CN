---
title: 高级搜寻架构中的 DeviceTvmSoftwareInventory 表
description: 在高级搜寻架构的 DeviceTvmSoftwareInventory 表中了解设备中的软件清单。
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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408619"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="5d3c4-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="5d3c4-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5d3c4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5d3c4-105">**Applies to:**</span></span>
- [<span data-ttu-id="5d3c4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5d3c4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="5d3c4-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="5d3c4-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5d3c4-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="5d3c4-109">高级 `DeviceTvmSoftwareInventory` 搜寻架构中的表包含 [网络中](next-gen-threat-and-vuln-mgt.md) 设备上当前安装的软件的威胁和漏洞管理清单，包括停止提供支持信息。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="5d3c4-110">例如，可以搜寻涉及使用当前易受攻击的软件版本安装的设备的事件。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="5d3c4-111">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="5d3c4-112">DeviceTVMSoftwareInventory 包含威胁和漏洞管理能够与常见平台枚举 (CPE) 匹配的所有软件 – 它是否易受攻击。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-112">DeviceTVMSoftwareInventory contains all the software which threat and vulnerability management was able to match to a Common Platform Enumeration (CPE) – whether it is vulnerable or not.</span></span>

>[!NOTE]
><span data-ttu-id="5d3c4-113">和 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 表已替换 `DeviceTvmSoftwareInventoryVulnerabilities` 表。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="5d3c4-114">前两个表一起包含可用于帮助通知漏洞管理活动的更多列。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="5d3c4-115">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="5d3c4-116">列名称</span><span class="sxs-lookup"><span data-stu-id="5d3c4-116">Column name</span></span> | <span data-ttu-id="5d3c4-117">数据类型</span><span class="sxs-lookup"><span data-stu-id="5d3c4-117">Data type</span></span> | <span data-ttu-id="5d3c4-118">说明</span><span class="sxs-lookup"><span data-stu-id="5d3c4-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="5d3c4-119">string</span><span class="sxs-lookup"><span data-stu-id="5d3c4-119">string</span></span> | <span data-ttu-id="5d3c4-120">服务中设备的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-120">Unique identifier for the device in the service.</span></span> |
| `DeviceName` | <span data-ttu-id="5d3c4-121">string</span><span class="sxs-lookup"><span data-stu-id="5d3c4-121">string</span></span> | <span data-ttu-id="5d3c4-122">设备的完全限定 (FQDN) FQDN。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-122">Fully qualified domain name (FQDN) of the device.</span></span> |
| `OSPlatform` | <span data-ttu-id="5d3c4-123">string</span><span class="sxs-lookup"><span data-stu-id="5d3c4-123">string</span></span> | <span data-ttu-id="5d3c4-124">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="5d3c4-125">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="5d3c4-126">string</span><span class="sxs-lookup"><span data-stu-id="5d3c4-126">string</span></span> | <span data-ttu-id="5d3c4-127">在设备上运行的操作系统的版本。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-127">Version of the operating system running on the device.</span></span> |
| `OSArchitecture` | <span data-ttu-id="5d3c4-128">string</span><span class="sxs-lookup"><span data-stu-id="5d3c4-128">string</span></span> | <span data-ttu-id="5d3c4-129">在设备上运行的操作系统的体系结构。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-129">Architecture of the operating system running on the device.</span></span> |
| `SoftwareVendor` | <span data-ttu-id="5d3c4-130">string</span><span class="sxs-lookup"><span data-stu-id="5d3c4-130">string</span></span> | <span data-ttu-id="5d3c4-131">软件供应商的名称。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-131">Name of the software vendor.</span></span> |
| `SoftwareName` | <span data-ttu-id="5d3c4-132">string</span><span class="sxs-lookup"><span data-stu-id="5d3c4-132">string</span></span> | <span data-ttu-id="5d3c4-133">软件产品的名称。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-133">Name of the software product.</span></span> |
| `SoftwareVersion` | <span data-ttu-id="5d3c4-134">string</span><span class="sxs-lookup"><span data-stu-id="5d3c4-134">string</span></span> | <span data-ttu-id="5d3c4-135">软件产品的版本号。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-135">Version number of the software product.</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="5d3c4-136">string</span><span class="sxs-lookup"><span data-stu-id="5d3c4-136">string</span></span> | <span data-ttu-id="5d3c4-137">指示软件产品的生命周期阶段（相对于其指定的停止支持终止 (EOS) 或生命周期 (EOL) 日期。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date.</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="5d3c4-138">string</span><span class="sxs-lookup"><span data-stu-id="5d3c4-138">string</span></span> | <span data-ttu-id="5d3c4-139">在软件产品 (EOS) 或生命周期 (，) 终止支持。</span><span class="sxs-lookup"><span data-stu-id="5d3c4-139">End-of-support (EOS) or end-of-life (EOL) date of the software product.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5d3c4-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="5d3c4-140">Related topics</span></span>

- [<span data-ttu-id="5d3c4-141">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="5d3c4-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5d3c4-142">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="5d3c4-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5d3c4-143">了解架构</span><span class="sxs-lookup"><span data-stu-id="5d3c4-143">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="5d3c4-144">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="5d3c4-144">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
