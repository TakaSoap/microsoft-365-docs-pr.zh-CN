---
title: 高级搜寻架构中的 DeviceTvmSecureConfigurationAssessment 表
description: 了解高级&的 DeviceTvmSecureConfigurationAssessment 表中的威胁和漏洞管理安全评估事件。 这些事件提供设备信息以及安全配置详细信息、影响和合规性信息。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， 威胁 & 漏洞管理， TVM， 设备管理， 安全配置， DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056145"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="487d6-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="487d6-105">DeviceTvmSecureConfigurationAssessment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="487d6-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="487d6-106">**Applies to:**</span></span>
- [<span data-ttu-id="487d6-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="487d6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="487d6-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="487d6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="487d6-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="487d6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="487d6-110">`DeviceTvmSecureConfigurationAssessment` 表中的每一行均包含针对来自[威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)的特定安全配置的评估事件。</span><span class="sxs-lookup"><span data-stu-id="487d6-110">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="487d6-111">使用此参考来检查最新的评估结果，并确定设备是否符合要求。</span><span class="sxs-lookup"><span data-stu-id="487d6-111">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="487d6-112">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。</span><span class="sxs-lookup"><span data-stu-id="487d6-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="487d6-113">列名称</span><span class="sxs-lookup"><span data-stu-id="487d6-113">Column name</span></span> | <span data-ttu-id="487d6-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="487d6-114">Data type</span></span> | <span data-ttu-id="487d6-115">说明</span><span class="sxs-lookup"><span data-stu-id="487d6-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="487d6-116">string</span><span class="sxs-lookup"><span data-stu-id="487d6-116">string</span></span> | <span data-ttu-id="487d6-117">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="487d6-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="487d6-118">string</span><span class="sxs-lookup"><span data-stu-id="487d6-118">string</span></span> | <span data-ttu-id="487d6-119">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="487d6-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="487d6-120">string</span><span class="sxs-lookup"><span data-stu-id="487d6-120">string</span></span> | <span data-ttu-id="487d6-121">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="487d6-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="487d6-122">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="487d6-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="487d6-123">datetime</span><span class="sxs-lookup"><span data-stu-id="487d6-123">datetime</span></span> |<span data-ttu-id="487d6-124">生成记录的日期和时间</span><span class="sxs-lookup"><span data-stu-id="487d6-124">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="487d6-125">string</span><span class="sxs-lookup"><span data-stu-id="487d6-125">string</span></span> | <span data-ttu-id="487d6-126">特定配置的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="487d6-126">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="487d6-127">string</span><span class="sxs-lookup"><span data-stu-id="487d6-127">string</span></span> | <span data-ttu-id="487d6-128">配置所属的类别或分组：应用程序、OS、网络、帐户、安全控件</span><span class="sxs-lookup"><span data-stu-id="487d6-128">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="487d6-129">string</span><span class="sxs-lookup"><span data-stu-id="487d6-129">string</span></span> |<span data-ttu-id="487d6-130">配置所属的子类别或子组。</span><span class="sxs-lookup"><span data-stu-id="487d6-130">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="487d6-131">在许多情况下，它用于描述特定的功能。</span><span class="sxs-lookup"><span data-stu-id="487d6-131">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="487d6-132">string</span><span class="sxs-lookup"><span data-stu-id="487d6-132">string</span></span> | <span data-ttu-id="487d6-133">配置对总体配置评分的影响程度 (1-10)</span><span class="sxs-lookup"><span data-stu-id="487d6-133">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="487d6-134">boolean</span><span class="sxs-lookup"><span data-stu-id="487d6-134">boolean</span></span> | <span data-ttu-id="487d6-135">指示是否正确配置了配置或策略</span><span class="sxs-lookup"><span data-stu-id="487d6-135">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="487d6-136">boolean</span><span class="sxs-lookup"><span data-stu-id="487d6-136">boolean</span></span> | <span data-ttu-id="487d6-137">指示配置或策略是否适用于设备</span><span class="sxs-lookup"><span data-stu-id="487d6-137">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="487d6-138">string</span><span class="sxs-lookup"><span data-stu-id="487d6-138">string</span></span> | <span data-ttu-id="487d6-139">有关配置或策略的其他上下文信息</span><span class="sxs-lookup"><span data-stu-id="487d6-139">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="487d6-140">boolean</span><span class="sxs-lookup"><span data-stu-id="487d6-140">boolean</span></span> | <span data-ttu-id="487d6-141">指示应用配置或策略时是否将影响用户</span><span class="sxs-lookup"><span data-stu-id="487d6-141">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="487d6-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="487d6-142">Related topics</span></span>

- [<span data-ttu-id="487d6-143">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="487d6-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="487d6-144">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="487d6-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="487d6-145">了解架构</span><span class="sxs-lookup"><span data-stu-id="487d6-145">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="487d6-146">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="487d6-146">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)