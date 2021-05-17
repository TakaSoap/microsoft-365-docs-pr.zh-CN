---
title: 高级搜寻架构中的 DeviceTvmSoftwareInventory 表
description: 在高级搜寻架构的 DeviceTvmSoftwareInventory 表中了解设备中的软件清单。
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
ms.openlocfilehash: 5f82684ebb10b72ff83a6789c010f5ec9fa099e7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024225"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="052ac-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="052ac-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="052ac-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="052ac-105">**Applies to:**</span></span>
- <span data-ttu-id="052ac-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="052ac-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="052ac-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="052ac-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="052ac-108">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="052ac-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="052ac-109">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="052ac-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="052ac-110">高级 `DeviceTvmSoftwareInventory` 搜寻架构中的表包含&网络中设备上[](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)当前安装的软件的威胁和漏洞管理清单，包括停止提供支持信息。</span><span class="sxs-lookup"><span data-stu-id="052ac-110">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="052ac-111">例如，可以搜寻涉及使用当前易受攻击的软件版本安装的设备的事件。</span><span class="sxs-lookup"><span data-stu-id="052ac-111">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="052ac-112">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="052ac-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="052ac-113">和 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 表已替换 `DeviceTvmSoftwareInventoryVulnerabilities` 表。</span><span class="sxs-lookup"><span data-stu-id="052ac-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="052ac-114">前两个表一起包含更多列，可用于帮助通知 vulnerablity 管理活动或搜寻易受攻击的设备。</span><span class="sxs-lookup"><span data-stu-id="052ac-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="052ac-115">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="052ac-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="052ac-116">列名称</span><span class="sxs-lookup"><span data-stu-id="052ac-116">Column name</span></span> | <span data-ttu-id="052ac-117">数据类型</span><span class="sxs-lookup"><span data-stu-id="052ac-117">Data type</span></span> | <span data-ttu-id="052ac-118">说明</span><span class="sxs-lookup"><span data-stu-id="052ac-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="052ac-119">string</span><span class="sxs-lookup"><span data-stu-id="052ac-119">string</span></span> | <span data-ttu-id="052ac-120">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="052ac-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="052ac-121">string</span><span class="sxs-lookup"><span data-stu-id="052ac-121">string</span></span> | <span data-ttu-id="052ac-122">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="052ac-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="052ac-123">string</span><span class="sxs-lookup"><span data-stu-id="052ac-123">string</span></span> | <span data-ttu-id="052ac-124">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="052ac-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="052ac-125">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="052ac-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="052ac-126">string</span><span class="sxs-lookup"><span data-stu-id="052ac-126">string</span></span> | <span data-ttu-id="052ac-127">计算机上运行的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="052ac-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="052ac-128">string</span><span class="sxs-lookup"><span data-stu-id="052ac-128">string</span></span> | <span data-ttu-id="052ac-129">计算机上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="052ac-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="052ac-130">string</span><span class="sxs-lookup"><span data-stu-id="052ac-130">string</span></span> | <span data-ttu-id="052ac-131">软件供应商的名称</span><span class="sxs-lookup"><span data-stu-id="052ac-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="052ac-132">string</span><span class="sxs-lookup"><span data-stu-id="052ac-132">string</span></span> | <span data-ttu-id="052ac-133">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="052ac-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="052ac-134">string</span><span class="sxs-lookup"><span data-stu-id="052ac-134">string</span></span> | <span data-ttu-id="052ac-135">软件产品版本号</span><span class="sxs-lookup"><span data-stu-id="052ac-135">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="052ac-136">string</span><span class="sxs-lookup"><span data-stu-id="052ac-136">string</span></span> | <span data-ttu-id="052ac-137">指示软件产品的生命周期阶段（相对于其指定的 EOS (停止) 或生命周期结束 (EOL) 日期</span><span class="sxs-lookup"><span data-stu-id="052ac-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="052ac-138">string</span><span class="sxs-lookup"><span data-stu-id="052ac-138">string</span></span> | <span data-ttu-id="052ac-139">在软件产品 (EOS) 或生命周期结束 (EOL) 终止支持</span><span class="sxs-lookup"><span data-stu-id="052ac-139">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="052ac-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="052ac-140">Related topics</span></span>

- [<span data-ttu-id="052ac-141">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="052ac-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="052ac-142">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="052ac-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="052ac-143">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="052ac-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="052ac-144">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="052ac-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="052ac-145">了解架构</span><span class="sxs-lookup"><span data-stu-id="052ac-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="052ac-146">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="052ac-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="052ac-147">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="052ac-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)