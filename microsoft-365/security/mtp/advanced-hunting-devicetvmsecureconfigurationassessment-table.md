---
title: 高级搜寻架构中的 DeviceTvmSecureConfigurationAssessment 表
description: 了解高级搜寻架构的 DeviceTvmSecureConfigurationAssessment 表中的安全评估事件。 这些威胁 & 漏洞管理事件提供了设备信息，以及安全配置详细信息、影响和合规性信息。
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、威胁 & 漏洞管理、TVM、设备管理、安全配置、DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 356548c3115aacce8c76d7fbc552811c168750ed
ms.sourcegitcommit: e8b3855302fc34d09b6df6c737033a2f326d6eee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48770069"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="d2feb-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="d2feb-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d2feb-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d2feb-106">**Applies to:**</span></span>
- <span data-ttu-id="d2feb-107">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="d2feb-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="d2feb-108">`DeviceTvmSecureConfigurationAssessment` 表中的每一行均包含针对来自[威胁和漏洞管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的特定安全配置的评估事件。</span><span class="sxs-lookup"><span data-stu-id="d2feb-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="d2feb-109">使用此参考来检查最新的评估结果，并确定设备是否符合要求。</span><span class="sxs-lookup"><span data-stu-id="d2feb-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="d2feb-110">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="d2feb-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d2feb-111">列名称</span><span class="sxs-lookup"><span data-stu-id="d2feb-111">Column name</span></span> | <span data-ttu-id="d2feb-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="d2feb-112">Data type</span></span> | <span data-ttu-id="d2feb-113">说明</span><span class="sxs-lookup"><span data-stu-id="d2feb-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="d2feb-114">string</span><span class="sxs-lookup"><span data-stu-id="d2feb-114">string</span></span> | <span data-ttu-id="d2feb-115">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="d2feb-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d2feb-116">string</span><span class="sxs-lookup"><span data-stu-id="d2feb-116">string</span></span> | <span data-ttu-id="d2feb-117">设备 (FQDN) 的完全限定的域名称</span><span class="sxs-lookup"><span data-stu-id="d2feb-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="d2feb-118">string</span><span class="sxs-lookup"><span data-stu-id="d2feb-118">string</span></span> | <span data-ttu-id="d2feb-119">设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="d2feb-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="d2feb-120">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="d2feb-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="d2feb-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d2feb-121">datetime</span></span> | <span data-ttu-id="d2feb-122">生成记录的日期和时间</span><span class="sxs-lookup"><span data-stu-id="d2feb-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="d2feb-123">string</span><span class="sxs-lookup"><span data-stu-id="d2feb-123">string</span></span> | <span data-ttu-id="d2feb-124">特定配置的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="d2feb-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="d2feb-125">string</span><span class="sxs-lookup"><span data-stu-id="d2feb-125">string</span></span> | <span data-ttu-id="d2feb-126">配置所属的类别或分组：应用程序、OS、网络、帐户、安全控件</span><span class="sxs-lookup"><span data-stu-id="d2feb-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="d2feb-127">string</span><span class="sxs-lookup"><span data-stu-id="d2feb-127">string</span></span> | <span data-ttu-id="d2feb-128">配置所属的子类别或子组。</span><span class="sxs-lookup"><span data-stu-id="d2feb-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="d2feb-129">在许多情况下，它用于描述特定的功能。</span><span class="sxs-lookup"><span data-stu-id="d2feb-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="d2feb-130">string</span><span class="sxs-lookup"><span data-stu-id="d2feb-130">string</span></span> | <span data-ttu-id="d2feb-131">配置对总体配置评分的影响程度 (1-10)</span><span class="sxs-lookup"><span data-stu-id="d2feb-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="d2feb-132">boolean</span><span class="sxs-lookup"><span data-stu-id="d2feb-132">boolean</span></span> | <span data-ttu-id="d2feb-133">指示是否正确配置了配置或策略</span><span class="sxs-lookup"><span data-stu-id="d2feb-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="d2feb-134">boolean</span><span class="sxs-lookup"><span data-stu-id="d2feb-134">boolean</span></span> | <span data-ttu-id="d2feb-135">指示配置或策略是否适用于设备</span><span class="sxs-lookup"><span data-stu-id="d2feb-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="d2feb-136">string</span><span class="sxs-lookup"><span data-stu-id="d2feb-136">string</span></span> | <span data-ttu-id="d2feb-137">有关配置或策略的其他上下文信息</span><span class="sxs-lookup"><span data-stu-id="d2feb-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="d2feb-138">boolean</span><span class="sxs-lookup"><span data-stu-id="d2feb-138">boolean</span></span> | <span data-ttu-id="d2feb-139">指示在应用配置或策略时是否会对用户产生影响</span><span class="sxs-lookup"><span data-stu-id="d2feb-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d2feb-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="d2feb-140">Related topics</span></span>

- [<span data-ttu-id="d2feb-141">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="d2feb-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d2feb-142">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="d2feb-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d2feb-143">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="d2feb-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d2feb-144">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="d2feb-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d2feb-145">了解架构</span><span class="sxs-lookup"><span data-stu-id="d2feb-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d2feb-146">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="d2feb-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d2feb-147">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="d2feb-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
