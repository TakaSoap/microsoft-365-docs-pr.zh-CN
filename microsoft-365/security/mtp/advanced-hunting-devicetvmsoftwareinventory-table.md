---
title: 高级搜寻架构中的 DeviceTvmSoftwareInventory 表
description: 在高级搜寻架构的 DeviceTvmSoftwareInventory 表中了解设备中的软件清单。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， 威胁 & 漏洞管理， TVM， 设备管理， 软件， 清单， 漏洞， CVE ID， OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 445e6f767cc2269315a0b280df2f4deefa2faa08
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423971"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="94a21-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="94a21-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="94a21-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="94a21-105">**Applies to:**</span></span>
- <span data-ttu-id="94a21-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94a21-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="94a21-107">某些信息与预发布产品相关，该产品在商业发布之前可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="94a21-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="94a21-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="94a21-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="94a21-109">高级搜寻架构中的表包含&网络中设备上当前安装的软件的威胁和漏洞管理清单，包括支持 `DeviceTvmSoftwareInventory` 信息结尾。 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="94a21-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="94a21-110">例如，你可以搜寻涉及使用当前易受攻击的软件版本安装的设备的事件。</span><span class="sxs-lookup"><span data-stu-id="94a21-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="94a21-111">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="94a21-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="94a21-112">和 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 表已替换 `DeviceTvmSoftwareInventoryVulnerabilities` 该表。</span><span class="sxs-lookup"><span data-stu-id="94a21-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="94a21-113">前两个表一起包含更多列，可用于帮助通知 vulnerablity 管理活动或搜寻易受攻击的设备。</span><span class="sxs-lookup"><span data-stu-id="94a21-113">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="94a21-114">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="94a21-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="94a21-115">列名称</span><span class="sxs-lookup"><span data-stu-id="94a21-115">Column name</span></span> | <span data-ttu-id="94a21-116">数据类型</span><span class="sxs-lookup"><span data-stu-id="94a21-116">Data type</span></span> | <span data-ttu-id="94a21-117">说明</span><span class="sxs-lookup"><span data-stu-id="94a21-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="94a21-118">string</span><span class="sxs-lookup"><span data-stu-id="94a21-118">string</span></span> | <span data-ttu-id="94a21-119">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="94a21-119">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="94a21-120">string</span><span class="sxs-lookup"><span data-stu-id="94a21-120">string</span></span> | <span data-ttu-id="94a21-121">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="94a21-121">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="94a21-122">string</span><span class="sxs-lookup"><span data-stu-id="94a21-122">string</span></span> | <span data-ttu-id="94a21-123">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="94a21-123">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="94a21-124">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="94a21-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="94a21-125">string</span><span class="sxs-lookup"><span data-stu-id="94a21-125">string</span></span> | <span data-ttu-id="94a21-126">计算机上运行的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="94a21-126">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="94a21-127">string</span><span class="sxs-lookup"><span data-stu-id="94a21-127">string</span></span> | <span data-ttu-id="94a21-128">计算机上运行的操作系统的体系结构</span><span class="sxs-lookup"><span data-stu-id="94a21-128">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="94a21-129">string</span><span class="sxs-lookup"><span data-stu-id="94a21-129">string</span></span> | <span data-ttu-id="94a21-130">软件供应商的名称</span><span class="sxs-lookup"><span data-stu-id="94a21-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="94a21-131">string</span><span class="sxs-lookup"><span data-stu-id="94a21-131">string</span></span> | <span data-ttu-id="94a21-132">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="94a21-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="94a21-133">string</span><span class="sxs-lookup"><span data-stu-id="94a21-133">string</span></span> | <span data-ttu-id="94a21-134">软件产品版本号</span><span class="sxs-lookup"><span data-stu-id="94a21-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="94a21-135">string</span><span class="sxs-lookup"><span data-stu-id="94a21-135">string</span></span> | <span data-ttu-id="94a21-136">指示软件产品的生命周期阶段（相对于其指定的支持终止 (EOS) 或生命周期 (EOL) 日期）</span><span class="sxs-lookup"><span data-stu-id="94a21-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="94a21-137">string</span><span class="sxs-lookup"><span data-stu-id="94a21-137">string</span></span> | <span data-ttu-id="94a21-138">软件产品的 EOL (终止) 或生命周期 (EOL) 终止</span><span class="sxs-lookup"><span data-stu-id="94a21-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="94a21-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="94a21-139">Related topics</span></span>

- [<span data-ttu-id="94a21-140">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="94a21-140">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="94a21-141">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="94a21-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="94a21-142">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="94a21-142">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="94a21-143">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="94a21-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="94a21-144">了解架构</span><span class="sxs-lookup"><span data-stu-id="94a21-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="94a21-145">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="94a21-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="94a21-146">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="94a21-146">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
