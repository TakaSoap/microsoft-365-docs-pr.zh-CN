---
title: 搜索暴露的设备
description: 了解如何危险和漏洞管理安全管理员、IT 管理员和 SecOps 协作。
keywords: 适用于 Endpoint-tvm 方案的 Microsoft Defender， 适用于终结点的 Microsoft Defender， tvm， tvm 方案， 减少威胁 & 漏洞暴露， 减少威胁和漏洞， 改进安全配置， 提高 Microsoft 设备安全分数， 增加威胁 & 漏洞 Microsoft 设备安全分数， Microsoft 设备安全分数， 曝光分数， 安全控制
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9a8ebcc89c3009cd93fbb42f2a74bbb9ffcc31b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934089"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="0585e-104">搜寻公开的设备 - 危险和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="0585e-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0585e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0585e-105">**Applies to:**</span></span>

- [<span data-ttu-id="0585e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0585e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="0585e-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="0585e-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="0585e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0585e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0585e-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="0585e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0585e-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="0585e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="0585e-111">使用高级搜寻查找具有漏洞的设备</span><span class="sxs-lookup"><span data-stu-id="0585e-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="0585e-112">高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。</span><span class="sxs-lookup"><span data-stu-id="0585e-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="0585e-113">你可以主动检查网络中事件，以查找威胁指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="0585e-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="0585e-114">通过灵活的数据访问，可以不受限制地搜寻已知威胁和潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="0585e-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="0585e-115">详细了解高级搜寻</span><span class="sxs-lookup"><span data-stu-id="0585e-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="0585e-116">架构表</span><span class="sxs-lookup"><span data-stu-id="0585e-116">Schema tables</span></span>

- <span data-ttu-id="0585e-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - 设备上安装的软件清单，包括其版本信息和停止支持状态。</span><span class="sxs-lookup"><span data-stu-id="0585e-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status.</span></span>

- <span data-ttu-id="0585e-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - 设备上发现的软件漏洞以及可解决每个漏洞的可用安全更新列表。</span><span class="sxs-lookup"><span data-stu-id="0585e-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability.</span></span>

- <span data-ttu-id="0585e-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - 公开披露漏洞的知识库，包括攻击代码是否公开可用。</span><span class="sxs-lookup"><span data-stu-id="0585e-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available.</span></span>

- <span data-ttu-id="0585e-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - 威胁漏洞管理评估事件，指示设备上各种安全配置的状态。</span><span class="sxs-lookup"><span data-stu-id="0585e-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices.</span></span>

- <span data-ttu-id="0585e-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - 威胁和漏洞管理用于评估&各种安全配置的知识库;包括到各种标准和基准的映射</span><span class="sxs-lookup"><span data-stu-id="0585e-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="0585e-122">检查高严重性警报中涉及的设备</span><span class="sxs-lookup"><span data-stu-id="0585e-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="0585e-123">从 **左侧** 导航窗格中转到高级搜寻Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="0585e-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="0585e-124">向下滚动到 TVM 高级搜寻架构，以熟悉列名称。</span><span class="sxs-lookup"><span data-stu-id="0585e-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="0585e-125">输入以下查询：</span><span class="sxs-lookup"><span data-stu-id="0585e-125">Enter the following queries:</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="0585e-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="0585e-126">Related topics</span></span>

- [<span data-ttu-id="0585e-127">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="0585e-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="0585e-128">安全性建议</span><span class="sxs-lookup"><span data-stu-id="0585e-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="0585e-129">API</span><span class="sxs-lookup"><span data-stu-id="0585e-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="0585e-130">为角色配置危险和漏洞管理访问</span><span class="sxs-lookup"><span data-stu-id="0585e-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="0585e-131">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="0585e-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="0585e-132">所有高级搜寻表</span><span class="sxs-lookup"><span data-stu-id="0585e-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
