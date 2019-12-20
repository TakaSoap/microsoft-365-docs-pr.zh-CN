---
title: 高级搜寻架构中的 DeviceTvmSecureConfigurationAssessmentKB 表
description: 在高级搜寻架构的 DeviceTvmSecureConfigurationAssessmentKB 表中了解有关由威胁和漏洞管理评估的各种安全配置的信息。
keywords: 高级搜寻, 威胁搜寻, 网络威胁搜寻, 搜索, 查询, 遥测, 架构参考, kusto, 表格, 列, 数据类型, 说明, 威胁和漏洞管理, TVM, 设备管理, 安全配置, MITRE ATT&CK 框架, 知识库, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: a3ae0a95af4a51d492c577e6a2ac1f2b96bba635
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806931"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="fab20-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="fab20-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="fab20-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="fab20-105">**Applies to:**</span></span>
- <span data-ttu-id="fab20-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="fab20-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="fab20-107">高级搜寻架构中的 `DeviceTvmSecureConfigurationAssessmentKB` 表包含有关各种安全配置（例如设备是否已启用自动更新，可通过[威胁和漏洞管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)进行检查）的信息。</span><span class="sxs-lookup"><span data-stu-id="fab20-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="fab20-108">它还包括风险信息、相关的行业基准以及适用的 MITRE ATT&CK 技术和技巧。</span><span class="sxs-lookup"><span data-stu-id="fab20-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="fab20-109">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="fab20-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="fab20-110">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="fab20-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="fab20-111">列名称</span><span class="sxs-lookup"><span data-stu-id="fab20-111">Column name</span></span> | <span data-ttu-id="fab20-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="fab20-112">Data type</span></span> | <span data-ttu-id="fab20-113">说明</span><span class="sxs-lookup"><span data-stu-id="fab20-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="fab20-114">string</span><span class="sxs-lookup"><span data-stu-id="fab20-114">string</span></span> | <span data-ttu-id="fab20-115">特定配置的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="fab20-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="fab20-116">string</span><span class="sxs-lookup"><span data-stu-id="fab20-116">string</span></span> | <span data-ttu-id="fab20-117">配置对总体配置评分的影响程度 (1-10)</span><span class="sxs-lookup"><span data-stu-id="fab20-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="fab20-118">string</span><span class="sxs-lookup"><span data-stu-id="fab20-118">string</span></span> | <span data-ttu-id="fab20-119">配置的显示名称</span><span class="sxs-lookup"><span data-stu-id="fab20-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="fab20-120">string</span><span class="sxs-lookup"><span data-stu-id="fab20-120">string</span></span> | <span data-ttu-id="fab20-121">配置的说明</span><span class="sxs-lookup"><span data-stu-id="fab20-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="fab20-122">string</span><span class="sxs-lookup"><span data-stu-id="fab20-122">string</span></span> | <span data-ttu-id="fab20-123">关联风险的说明</span><span class="sxs-lookup"><span data-stu-id="fab20-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="fab20-124">string</span><span class="sxs-lookup"><span data-stu-id="fab20-124">string</span></span> | <span data-ttu-id="fab20-125">配置所属的类别或分组：应用程序、OS、网络、帐户、安全控件</span><span class="sxs-lookup"><span data-stu-id="fab20-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="fab20-126">string</span><span class="sxs-lookup"><span data-stu-id="fab20-126">string</span></span> |<span data-ttu-id="fab20-127">配置所属的子类别或子组。</span><span class="sxs-lookup"><span data-stu-id="fab20-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="fab20-128">在许多情况下，它用于描述特定的功能。</span><span class="sxs-lookup"><span data-stu-id="fab20-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="fab20-129">string</span><span class="sxs-lookup"><span data-stu-id="fab20-129">string</span></span> | <span data-ttu-id="fab20-130">推荐相同或类似配置的行业基准的列表</span><span class="sxs-lookup"><span data-stu-id="fab20-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="fab20-131">string</span><span class="sxs-lookup"><span data-stu-id="fab20-131">string</span></span> | <span data-ttu-id="fab20-132">与该配置相关的 Mitre ATT&CK 框架技术的列表</span><span class="sxs-lookup"><span data-stu-id="fab20-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="fab20-133">string</span><span class="sxs-lookup"><span data-stu-id="fab20-133">string</span></span> | <span data-ttu-id="fab20-134">与该配置相关的 Mitre ATT&CK 框架技巧的列表</span><span class="sxs-lookup"><span data-stu-id="fab20-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="fab20-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="fab20-135">Related topics</span></span>

- [<span data-ttu-id="fab20-136">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="fab20-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fab20-137">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="fab20-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fab20-138">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="fab20-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fab20-139">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="fab20-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fab20-140">了解架构</span><span class="sxs-lookup"><span data-stu-id="fab20-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fab20-141">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="fab20-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="fab20-142">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="fab20-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
