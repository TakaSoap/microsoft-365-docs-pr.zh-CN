---
title: 高级搜寻架构中的 DeviceTvmSecureConfigurationAssessmentKB 表
description: 在高级搜寻架构的 DeviceTvmSecureConfigurationAssessmentKB 表中了解有关由威胁和漏洞管理评估的各种安全配置的信息。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 描述， 威胁 & 漏洞管理， TVM， 设备管理， 安全配置， MITRE ATT&CK 框架， 知识库， KB， DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 1dfa710b86afdcfd8a5643555564a0f34c7b4702
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024237"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="941f2-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="941f2-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="941f2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="941f2-105">**Applies to:**</span></span>
- <span data-ttu-id="941f2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="941f2-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="941f2-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="941f2-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="941f2-108">高级搜寻架构中的 `DeviceTvmSecureConfigurationAssessmentKB` 表包含有关各种安全配置（例如设备是否已启用自动更新，可通过[威胁和漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)进行检查）的信息。</span><span class="sxs-lookup"><span data-stu-id="941f2-108">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="941f2-109">它还包括风险信息、相关的行业基准以及适用的 MITRE ATT&CK 技术和技巧。</span><span class="sxs-lookup"><span data-stu-id="941f2-109">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="941f2-110">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="941f2-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="941f2-111">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="941f2-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="941f2-112">列名称</span><span class="sxs-lookup"><span data-stu-id="941f2-112">Column name</span></span> | <span data-ttu-id="941f2-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="941f2-113">Data type</span></span> | <span data-ttu-id="941f2-114">说明</span><span class="sxs-lookup"><span data-stu-id="941f2-114">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="941f2-115">string</span><span class="sxs-lookup"><span data-stu-id="941f2-115">string</span></span> | <span data-ttu-id="941f2-116">特定配置的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="941f2-116">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="941f2-117">string</span><span class="sxs-lookup"><span data-stu-id="941f2-117">string</span></span> | <span data-ttu-id="941f2-118">配置对总体配置评分的影响程度 (1-10)</span><span class="sxs-lookup"><span data-stu-id="941f2-118">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="941f2-119">string</span><span class="sxs-lookup"><span data-stu-id="941f2-119">string</span></span> | <span data-ttu-id="941f2-120">配置的显示名称</span><span class="sxs-lookup"><span data-stu-id="941f2-120">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="941f2-121">string</span><span class="sxs-lookup"><span data-stu-id="941f2-121">string</span></span> | <span data-ttu-id="941f2-122">配置的说明</span><span class="sxs-lookup"><span data-stu-id="941f2-122">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="941f2-123">string</span><span class="sxs-lookup"><span data-stu-id="941f2-123">string</span></span> | <span data-ttu-id="941f2-124">关联风险的说明</span><span class="sxs-lookup"><span data-stu-id="941f2-124">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="941f2-125">string</span><span class="sxs-lookup"><span data-stu-id="941f2-125">string</span></span> | <span data-ttu-id="941f2-126">配置所属的类别或分组：应用程序、OS、网络、帐户、安全控件</span><span class="sxs-lookup"><span data-stu-id="941f2-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="941f2-127">string</span><span class="sxs-lookup"><span data-stu-id="941f2-127">string</span></span> |<span data-ttu-id="941f2-128">配置所属的子类别或子组。</span><span class="sxs-lookup"><span data-stu-id="941f2-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="941f2-129">在许多情况下，它用于描述特定的功能。</span><span class="sxs-lookup"><span data-stu-id="941f2-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="941f2-130">string</span><span class="sxs-lookup"><span data-stu-id="941f2-130">string</span></span> | <span data-ttu-id="941f2-131">推荐相同或类似配置的行业基准的列表</span><span class="sxs-lookup"><span data-stu-id="941f2-131">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="941f2-132">string</span><span class="sxs-lookup"><span data-stu-id="941f2-132">string</span></span> | <span data-ttu-id="941f2-133">表示用于标识或分类安全配置的各种属性的标签</span><span class="sxs-lookup"><span data-stu-id="941f2-133">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="941f2-134">string</span><span class="sxs-lookup"><span data-stu-id="941f2-134">string</span></span> | <span data-ttu-id="941f2-135">用于降低或解决任何关联风险的建议操作</span><span class="sxs-lookup"><span data-stu-id="941f2-135">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="941f2-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="941f2-136">Related topics</span></span>

- [<span data-ttu-id="941f2-137">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="941f2-137">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="941f2-138">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="941f2-138">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="941f2-139">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="941f2-139">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="941f2-140">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="941f2-140">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="941f2-141">了解架构</span><span class="sxs-lookup"><span data-stu-id="941f2-141">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="941f2-142">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="941f2-142">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="941f2-143">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="941f2-143">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)