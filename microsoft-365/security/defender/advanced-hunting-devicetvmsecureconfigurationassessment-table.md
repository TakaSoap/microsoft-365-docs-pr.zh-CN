---
title: 高级搜寻架构中的 DeviceTvmSecureConfigurationAssessment 表
description: 了解高级搜寻架构的 DeviceTvmSecureConfigurationAssessment 表中的安全评估事件。 这些威胁& 漏洞管理事件提供设备信息以及安全配置详细信息、影响和合规性信息。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 描述， 威胁 & 漏洞管理， TVM， 设备管理， 安全配置， DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2e3e649911cb2ce63c2a49be0ebc93e35e8055d6
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024213"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="b69de-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="b69de-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b69de-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b69de-106">**Applies to:**</span></span>
- <span data-ttu-id="b69de-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b69de-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="b69de-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b69de-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="b69de-109">`DeviceTvmSecureConfigurationAssessment` 表中的每一行均包含针对来自[威胁和漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的特定安全配置的评估事件。</span><span class="sxs-lookup"><span data-stu-id="b69de-109">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="b69de-110">使用此参考来检查最新的评估结果，并确定设备是否符合要求。</span><span class="sxs-lookup"><span data-stu-id="b69de-110">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="b69de-111">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="b69de-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b69de-112">列名称</span><span class="sxs-lookup"><span data-stu-id="b69de-112">Column name</span></span> | <span data-ttu-id="b69de-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="b69de-113">Data type</span></span> | <span data-ttu-id="b69de-114">说明</span><span class="sxs-lookup"><span data-stu-id="b69de-114">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="b69de-115">string</span><span class="sxs-lookup"><span data-stu-id="b69de-115">string</span></span> | <span data-ttu-id="b69de-116">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="b69de-116">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b69de-117">string</span><span class="sxs-lookup"><span data-stu-id="b69de-117">string</span></span> | <span data-ttu-id="b69de-118">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="b69de-118">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="b69de-119">string</span><span class="sxs-lookup"><span data-stu-id="b69de-119">string</span></span> | <span data-ttu-id="b69de-120">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="b69de-120">Platform of the operating system running on the device.</span></span> <span data-ttu-id="b69de-121">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="b69de-121">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="b69de-122">datetime</span><span class="sxs-lookup"><span data-stu-id="b69de-122">datetime</span></span> | <span data-ttu-id="b69de-123">生成记录的日期和时间</span><span class="sxs-lookup"><span data-stu-id="b69de-123">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="b69de-124">string</span><span class="sxs-lookup"><span data-stu-id="b69de-124">string</span></span> | <span data-ttu-id="b69de-125">特定配置的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="b69de-125">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="b69de-126">string</span><span class="sxs-lookup"><span data-stu-id="b69de-126">string</span></span> | <span data-ttu-id="b69de-127">配置所属的类别或分组：应用程序、OS、网络、帐户、安全控件</span><span class="sxs-lookup"><span data-stu-id="b69de-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="b69de-128">string</span><span class="sxs-lookup"><span data-stu-id="b69de-128">string</span></span> | <span data-ttu-id="b69de-129">配置所属的子类别或子组。</span><span class="sxs-lookup"><span data-stu-id="b69de-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="b69de-130">在许多情况下，它用于描述特定的功能。</span><span class="sxs-lookup"><span data-stu-id="b69de-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="b69de-131">string</span><span class="sxs-lookup"><span data-stu-id="b69de-131">string</span></span> | <span data-ttu-id="b69de-132">配置对总体配置评分的影响程度 (1-10)</span><span class="sxs-lookup"><span data-stu-id="b69de-132">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="b69de-133">boolean</span><span class="sxs-lookup"><span data-stu-id="b69de-133">boolean</span></span> | <span data-ttu-id="b69de-134">指示是否正确配置了配置或策略</span><span class="sxs-lookup"><span data-stu-id="b69de-134">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="b69de-135">boolean</span><span class="sxs-lookup"><span data-stu-id="b69de-135">boolean</span></span> | <span data-ttu-id="b69de-136">指示配置或策略是否适用于设备</span><span class="sxs-lookup"><span data-stu-id="b69de-136">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="b69de-137">string</span><span class="sxs-lookup"><span data-stu-id="b69de-137">string</span></span> | <span data-ttu-id="b69de-138">有关配置或策略的其他上下文信息</span><span class="sxs-lookup"><span data-stu-id="b69de-138">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="b69de-139">boolean</span><span class="sxs-lookup"><span data-stu-id="b69de-139">boolean</span></span> | <span data-ttu-id="b69de-140">指示应用配置或策略时是否将影响用户</span><span class="sxs-lookup"><span data-stu-id="b69de-140">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b69de-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="b69de-141">Related topics</span></span>

- [<span data-ttu-id="b69de-142">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="b69de-142">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b69de-143">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="b69de-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b69de-144">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="b69de-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b69de-145">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="b69de-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b69de-146">了解架构</span><span class="sxs-lookup"><span data-stu-id="b69de-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b69de-147">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="b69de-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b69de-148">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="b69de-148">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)