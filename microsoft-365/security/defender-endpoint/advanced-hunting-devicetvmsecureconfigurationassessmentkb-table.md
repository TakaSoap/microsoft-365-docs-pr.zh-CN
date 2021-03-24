---
title: 高级搜寻架构中的 DeviceTvmSecureConfigurationAssessmentKB 表
description: 了解高级搜寻架构的 DeviceTvmSecureConfigurationAssessmentKB 表中的威胁&漏洞管理评估的各种安全配置。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， 威胁 & 漏洞管理， TVM， 设备管理， 安全配置， MITRE ATT&CK 框架， 知识库， KB， DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056144"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="6f323-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="6f323-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6f323-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6f323-105">**Applies to:**</span></span>
- [<span data-ttu-id="6f323-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6f323-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="6f323-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="6f323-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6f323-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6f323-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6f323-109">高级搜寻架构中的 `DeviceTvmSecureConfigurationAssessmentKB` 表包含有关各种安全配置（例如设备是否已启用自动更新，可通过[威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)进行检查）的信息。</span><span class="sxs-lookup"><span data-stu-id="6f323-109">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="6f323-110">它还包括风险信息、相关的行业基准以及适用的 MITRE ATT&CK 技术和技巧。</span><span class="sxs-lookup"><span data-stu-id="6f323-110">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="6f323-111">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="6f323-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6f323-112">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。</span><span class="sxs-lookup"><span data-stu-id="6f323-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="6f323-113">列名称</span><span class="sxs-lookup"><span data-stu-id="6f323-113">Column name</span></span> | <span data-ttu-id="6f323-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="6f323-114">Data type</span></span> | <span data-ttu-id="6f323-115">说明</span><span class="sxs-lookup"><span data-stu-id="6f323-115">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="6f323-116">string</span><span class="sxs-lookup"><span data-stu-id="6f323-116">string</span></span> | <span data-ttu-id="6f323-117">特定配置的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="6f323-117">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="6f323-118">string</span><span class="sxs-lookup"><span data-stu-id="6f323-118">string</span></span> | <span data-ttu-id="6f323-119">配置对总体配置评分的影响程度 (1-10)</span><span class="sxs-lookup"><span data-stu-id="6f323-119">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="6f323-120">string</span><span class="sxs-lookup"><span data-stu-id="6f323-120">string</span></span> | <span data-ttu-id="6f323-121">配置的显示名称</span><span class="sxs-lookup"><span data-stu-id="6f323-121">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="6f323-122">string</span><span class="sxs-lookup"><span data-stu-id="6f323-122">string</span></span> | <span data-ttu-id="6f323-123">配置的说明</span><span class="sxs-lookup"><span data-stu-id="6f323-123">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="6f323-124">string</span><span class="sxs-lookup"><span data-stu-id="6f323-124">string</span></span> | <span data-ttu-id="6f323-125">关联风险的说明</span><span class="sxs-lookup"><span data-stu-id="6f323-125">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="6f323-126">string</span><span class="sxs-lookup"><span data-stu-id="6f323-126">string</span></span> | <span data-ttu-id="6f323-127">配置所属的类别或分组：应用程序、OS、网络、帐户、安全控件</span><span class="sxs-lookup"><span data-stu-id="6f323-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="6f323-128">string</span><span class="sxs-lookup"><span data-stu-id="6f323-128">string</span></span> |<span data-ttu-id="6f323-129">配置所属的子类别或子组。</span><span class="sxs-lookup"><span data-stu-id="6f323-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="6f323-130">在许多情况下，它用于描述特定的功能。</span><span class="sxs-lookup"><span data-stu-id="6f323-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="6f323-131">string</span><span class="sxs-lookup"><span data-stu-id="6f323-131">string</span></span> | <span data-ttu-id="6f323-132">推荐相同或类似配置的行业基准的列表</span><span class="sxs-lookup"><span data-stu-id="6f323-132">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="6f323-133">string</span><span class="sxs-lookup"><span data-stu-id="6f323-133">string</span></span> | <span data-ttu-id="6f323-134">与该配置相关的 Mitre ATT&CK 框架技术的列表</span><span class="sxs-lookup"><span data-stu-id="6f323-134">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="6f323-135">string</span><span class="sxs-lookup"><span data-stu-id="6f323-135">string</span></span> | <span data-ttu-id="6f323-136">与该配置相关的 Mitre ATT&CK 框架技巧的列表</span><span class="sxs-lookup"><span data-stu-id="6f323-136">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6f323-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="6f323-137">Related topics</span></span>

- [<span data-ttu-id="6f323-138">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="6f323-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6f323-139">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="6f323-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6f323-140">了解架构</span><span class="sxs-lookup"><span data-stu-id="6f323-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="6f323-141">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="6f323-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
