---
title: 高级搜寻架构中的 DeviceTvmSecureConfigurationAssessment 表
description: 在高级搜寻架构的 DeviceTvmSecureConfigurationAssessment 表中了解有关威胁和漏洞管理安全评估事件的信息。 这些事件提供计算机信息以及安全配置详细信息、影响和合规性信息。
keywords: 高级搜寻, 威胁搜寻, 网络威胁搜寻, 搜索, 查询, 遥测, 架构参考, kusto, 表格, 列, 数据类型, 说明, 威胁和漏洞管理, TVM, 设备管理, 安全配置, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2fee44c0d9c9ff30ca23ccef863e056cadee7de8
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910787"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="12c44-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="12c44-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="12c44-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="12c44-106">**Applies to:**</span></span>
- <span data-ttu-id="12c44-107">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="12c44-107">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="12c44-108">`DeviceTvmSecureConfigurationAssessment` 表中的每一行均包含针对来自[威胁和漏洞管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的特定安全配置的评估事件。</span><span class="sxs-lookup"><span data-stu-id="12c44-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="12c44-109">使用此参考来检查最新的评估结果，并确定设备是否符合要求。</span><span class="sxs-lookup"><span data-stu-id="12c44-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="12c44-110">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="12c44-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="12c44-111">列名称</span><span class="sxs-lookup"><span data-stu-id="12c44-111">Column name</span></span> | <span data-ttu-id="12c44-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="12c44-112">Data type</span></span> | <span data-ttu-id="12c44-113">说明</span><span class="sxs-lookup"><span data-stu-id="12c44-113">Description</span></span> |
|-------------|-----------|-------------|
| `MachineId` | <span data-ttu-id="12c44-114">string</span><span class="sxs-lookup"><span data-stu-id="12c44-114">string</span></span> | <span data-ttu-id="12c44-115">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="12c44-115">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="12c44-116">string</span><span class="sxs-lookup"><span data-stu-id="12c44-116">string</span></span> | <span data-ttu-id="12c44-117">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="12c44-117">Fully qualified domain name (FQDN) of the pool</span></span> |
| `OSPlatform` | <span data-ttu-id="12c44-118">string</span><span class="sxs-lookup"><span data-stu-id="12c44-118">string</span></span> | <span data-ttu-id="12c44-119">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="12c44-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="12c44-120">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="12c44-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="12c44-121">datetime</span><span class="sxs-lookup"><span data-stu-id="12c44-121">dateTime</span></span> | <span data-ttu-id="12c44-122">生成记录的日期和时间</span><span class="sxs-lookup"><span data-stu-id="12c44-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="12c44-123">string</span><span class="sxs-lookup"><span data-stu-id="12c44-123">string</span></span> | <span data-ttu-id="12c44-124">特定配置的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="12c44-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="12c44-125">string</span><span class="sxs-lookup"><span data-stu-id="12c44-125">string</span></span> | <span data-ttu-id="12c44-126">配置所属的类别或分组：应用程序、OS、网络、帐户、安全控件</span><span class="sxs-lookup"><span data-stu-id="12c44-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="12c44-127">string</span><span class="sxs-lookup"><span data-stu-id="12c44-127">string</span></span> | <span data-ttu-id="12c44-128">配置所属的子类别或子组。</span><span class="sxs-lookup"><span data-stu-id="12c44-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="12c44-129">在许多情况下，它用于描述特定的功能。</span><span class="sxs-lookup"><span data-stu-id="12c44-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="12c44-130">string</span><span class="sxs-lookup"><span data-stu-id="12c44-130">string</span></span> | <span data-ttu-id="12c44-131">配置对总体配置评分的影响程度 (1-10)</span><span class="sxs-lookup"><span data-stu-id="12c44-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="12c44-132">boolean</span><span class="sxs-lookup"><span data-stu-id="12c44-132">boolean</span></span> | <span data-ttu-id="12c44-133">指示是否正确配置了配置或策略</span><span class="sxs-lookup"><span data-stu-id="12c44-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="12c44-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="12c44-134">Related topics</span></span>

- [<span data-ttu-id="12c44-135">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="12c44-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="12c44-136">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="12c44-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="12c44-137">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="12c44-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="12c44-138">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="12c44-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="12c44-139">了解架构</span><span class="sxs-lookup"><span data-stu-id="12c44-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="12c44-140">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="12c44-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="12c44-141">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="12c44-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
