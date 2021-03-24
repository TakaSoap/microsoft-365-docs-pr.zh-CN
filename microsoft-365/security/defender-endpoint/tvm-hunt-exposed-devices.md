---
title: 搜寻公开的设备
description: 了解如何使用威胁和漏洞管理来帮助安全管理员、IT 管理员和 SecOps 进行协作。
keywords: mdatp-tvm 方案， mdatp， tvm， tvm scenarios， reduce threat & vulnerability exposure， reduce threat and vulnerability， improve security configuration， increase Microsoft Secure Score for Devices， increase threat & vulnerability Microsoft Secure Score for Devices， Microsoft Secure Score for Devices， exposure score， security controls
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9af7464d9cae06dc53abb019aa0b189d6e72e749
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054613"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="48492-104">搜寻公开的设备 - 威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="48492-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="48492-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="48492-105">**Applies to:**</span></span>

- [<span data-ttu-id="48492-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="48492-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="48492-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="48492-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="48492-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48492-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="48492-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="48492-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="48492-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="48492-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="48492-111">使用高级搜寻查找具有漏洞的设备</span><span class="sxs-lookup"><span data-stu-id="48492-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="48492-112">高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。</span><span class="sxs-lookup"><span data-stu-id="48492-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="48492-113">你可以主动检查网络中事件，以查找威胁指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="48492-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="48492-114">通过灵活的数据访问，可以不受限制地搜寻已知威胁和潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="48492-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="48492-115">详细了解高级搜寻</span><span class="sxs-lookup"><span data-stu-id="48492-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="48492-116">架构表</span><span class="sxs-lookup"><span data-stu-id="48492-116">Schema tables</span></span>

- <span data-ttu-id="48492-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - 设备上安装的软件清单，包括其版本信息和停止支持状态</span><span class="sxs-lookup"><span data-stu-id="48492-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status</span></span>

- <span data-ttu-id="48492-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - 设备上发现的软件漏洞以及可解决每个漏洞的可用安全更新列表</span><span class="sxs-lookup"><span data-stu-id="48492-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability</span></span>

- <span data-ttu-id="48492-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - 公开披露漏洞的知识库，包括攻击代码是否公开可用</span><span class="sxs-lookup"><span data-stu-id="48492-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span>

- <span data-ttu-id="48492-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - 威胁和漏洞管理评估事件，指示设备上各种安全配置的状态</span><span class="sxs-lookup"><span data-stu-id="48492-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices</span></span>

- <span data-ttu-id="48492-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - 威胁和漏洞管理用于评估&各种安全配置的知识库;包括到各种标准和基准的映射</span><span class="sxs-lookup"><span data-stu-id="48492-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="48492-122">检查高严重性警报中涉及的设备</span><span class="sxs-lookup"><span data-stu-id="48492-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="48492-123">从 Microsoft Defender **安全** 中心的左侧导航窗格中转到高级搜寻。</span><span class="sxs-lookup"><span data-stu-id="48492-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="48492-124">向下滚动到 TVM 高级搜寻架构，以熟悉列名称。</span><span class="sxs-lookup"><span data-stu-id="48492-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="48492-125">输入以下查询：</span><span class="sxs-lookup"><span data-stu-id="48492-125">Enter the following queries:</span></span>

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a><span data-ttu-id="48492-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="48492-126">Related topics</span></span>

- [<span data-ttu-id="48492-127">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="48492-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="48492-128">安全性建议</span><span class="sxs-lookup"><span data-stu-id="48492-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="48492-129">API</span><span class="sxs-lookup"><span data-stu-id="48492-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="48492-130">配置威胁和漏洞管理角色的数据访问</span><span class="sxs-lookup"><span data-stu-id="48492-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="48492-131">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="48492-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="48492-132">所有高级搜寻表</span><span class="sxs-lookup"><span data-stu-id="48492-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
