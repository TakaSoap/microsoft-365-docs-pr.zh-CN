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
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056269"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="5639b-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="5639b-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5639b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5639b-105">**Applies to:**</span></span>
- [<span data-ttu-id="5639b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5639b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="5639b-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="5639b-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5639b-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5639b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="5639b-109">高级 `DeviceTvmSoftwareInventory` 搜寻架构中的表包含&网络中设备上[](next-gen-threat-and-vuln-mgt.md)当前安装的软件的威胁和漏洞管理清单，包括停止提供支持信息。</span><span class="sxs-lookup"><span data-stu-id="5639b-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="5639b-110">例如，可以搜寻涉及使用当前易受攻击的软件版本安装的设备的事件。</span><span class="sxs-lookup"><span data-stu-id="5639b-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="5639b-111">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="5639b-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="5639b-112">和 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 表已替换 `DeviceTvmSoftwareInventoryVulnerabilities` 表。</span><span class="sxs-lookup"><span data-stu-id="5639b-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="5639b-113">前两个表一起包含可用于帮助通知漏洞管理活动的更多列。</span><span class="sxs-lookup"><span data-stu-id="5639b-113">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="5639b-114">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。</span><span class="sxs-lookup"><span data-stu-id="5639b-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="5639b-115">列名称</span><span class="sxs-lookup"><span data-stu-id="5639b-115">Column name</span></span> | <span data-ttu-id="5639b-116">数据类型</span><span class="sxs-lookup"><span data-stu-id="5639b-116">Data type</span></span> | <span data-ttu-id="5639b-117">说明</span><span class="sxs-lookup"><span data-stu-id="5639b-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="5639b-118">string</span><span class="sxs-lookup"><span data-stu-id="5639b-118">string</span></span> | <span data-ttu-id="5639b-119">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="5639b-119">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5639b-120">string</span><span class="sxs-lookup"><span data-stu-id="5639b-120">string</span></span> | <span data-ttu-id="5639b-121">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="5639b-121">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="5639b-122">string</span><span class="sxs-lookup"><span data-stu-id="5639b-122">string</span></span> | <span data-ttu-id="5639b-123">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="5639b-123">Platform of the operating system running on the device.</span></span> <span data-ttu-id="5639b-124">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="5639b-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="5639b-125">string</span><span class="sxs-lookup"><span data-stu-id="5639b-125">string</span></span> | <span data-ttu-id="5639b-126">在设备上运行的操作系统的版本</span><span class="sxs-lookup"><span data-stu-id="5639b-126">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="5639b-127">string</span><span class="sxs-lookup"><span data-stu-id="5639b-127">string</span></span> | <span data-ttu-id="5639b-128">在设备上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="5639b-128">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="5639b-129">string</span><span class="sxs-lookup"><span data-stu-id="5639b-129">string</span></span> | <span data-ttu-id="5639b-130">软件供应商的名称</span><span class="sxs-lookup"><span data-stu-id="5639b-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="5639b-131">string</span><span class="sxs-lookup"><span data-stu-id="5639b-131">string</span></span> | <span data-ttu-id="5639b-132">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="5639b-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="5639b-133">string</span><span class="sxs-lookup"><span data-stu-id="5639b-133">string</span></span> | <span data-ttu-id="5639b-134">软件产品版本号</span><span class="sxs-lookup"><span data-stu-id="5639b-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="5639b-135">string</span><span class="sxs-lookup"><span data-stu-id="5639b-135">string</span></span> | <span data-ttu-id="5639b-136">指示软件产品的生命周期阶段（相对于其指定的 EOS (停止) 或生命周期结束 (EOL) 日期</span><span class="sxs-lookup"><span data-stu-id="5639b-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="5639b-137">string</span><span class="sxs-lookup"><span data-stu-id="5639b-137">string</span></span> | <span data-ttu-id="5639b-138">在软件产品 (EOS) 或生命周期结束 (EOL) 终止支持</span><span class="sxs-lookup"><span data-stu-id="5639b-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="5639b-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="5639b-139">Related topics</span></span>

- [<span data-ttu-id="5639b-140">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="5639b-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5639b-141">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="5639b-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5639b-142">了解架构</span><span class="sxs-lookup"><span data-stu-id="5639b-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="5639b-143">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="5639b-143">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

