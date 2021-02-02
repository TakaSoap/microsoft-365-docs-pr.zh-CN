---
title: Microsoft 365 Defender 高级搜寻架构中的命名更改
description: 跟踪和查看高级搜寻架构中的命名更改表和列
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 数据， 命名更改， 重命名， Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066865"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="7b2df-104">高级搜寻架构 - 命名更改</span><span class="sxs-lookup"><span data-stu-id="7b2df-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7b2df-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7b2df-105">**Applies to:**</span></span>
- <span data-ttu-id="7b2df-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b2df-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="7b2df-107">高级 [搜寻架构](advanced-hunting-schema-tables.md) 会定期更新以添加新的表和列。</span><span class="sxs-lookup"><span data-stu-id="7b2df-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="7b2df-108">在某些情况下，将重命名或替换现有列名称，以改进用户体验。</span><span class="sxs-lookup"><span data-stu-id="7b2df-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="7b2df-109">请参阅本文，查看可能会影响查询的命名更改。</span><span class="sxs-lookup"><span data-stu-id="7b2df-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="7b2df-110">命名更改将自动应用于保存在安全中心的查询，包括自定义检测规则使用的查询。</span><span class="sxs-lookup"><span data-stu-id="7b2df-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="7b2df-111">无需手动更新这些查询。</span><span class="sxs-lookup"><span data-stu-id="7b2df-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="7b2df-112">但是，您需要更新以下查询：</span><span class="sxs-lookup"><span data-stu-id="7b2df-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="7b2df-113">使用 API 运行的查询</span><span class="sxs-lookup"><span data-stu-id="7b2df-113">Queries that are run using the API</span></span>
- <span data-ttu-id="7b2df-114">保存在安全中心外部的其他地方的查询</span><span class="sxs-lookup"><span data-stu-id="7b2df-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="7b2df-115">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="7b2df-115">December 2020</span></span>

| <span data-ttu-id="7b2df-116">表名</span><span class="sxs-lookup"><span data-stu-id="7b2df-116">Table name</span></span> | <span data-ttu-id="7b2df-117">原始列名称</span><span class="sxs-lookup"><span data-stu-id="7b2df-117">Original column name</span></span> | <span data-ttu-id="7b2df-118">新列名称</span><span class="sxs-lookup"><span data-stu-id="7b2df-118">New column name</span></span> | <span data-ttu-id="7b2df-119">更改原因</span><span class="sxs-lookup"><span data-stu-id="7b2df-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="7b2df-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="7b2df-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="7b2df-121">客户反馈</span><span class="sxs-lookup"><span data-stu-id="7b2df-121">Customer feedback</span></span> |
| [<span data-ttu-id="7b2df-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="7b2df-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="7b2df-123">客户反馈</span><span class="sxs-lookup"><span data-stu-id="7b2df-123">Customer feedback</span></span> |
| [<span data-ttu-id="7b2df-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="7b2df-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="7b2df-125">客户反馈</span><span class="sxs-lookup"><span data-stu-id="7b2df-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="7b2df-126">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="7b2df-126">January 2021</span></span>

| <span data-ttu-id="7b2df-127">列名称</span><span class="sxs-lookup"><span data-stu-id="7b2df-127">Column name</span></span> | <span data-ttu-id="7b2df-128">原始值名称</span><span class="sxs-lookup"><span data-stu-id="7b2df-128">Original value name</span></span> | <span data-ttu-id="7b2df-129">新值名称</span><span class="sxs-lookup"><span data-stu-id="7b2df-129">New value name</span></span> | <span data-ttu-id="7b2df-130">更改原因</span><span class="sxs-lookup"><span data-stu-id="7b2df-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="7b2df-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="7b2df-131">MCAS</span></span> |    <span data-ttu-id="7b2df-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7b2df-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="7b2df-133">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b2df-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="7b2df-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="7b2df-135">EDR</span><span class="sxs-lookup"><span data-stu-id="7b2df-135">EDR</span></span>| <span data-ttu-id="7b2df-136">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b2df-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="7b2df-137">WindowsDefenderAv</span></span> | <span data-ttu-id="7b2df-138">防病毒</span><span class="sxs-lookup"><span data-stu-id="7b2df-138">Antivirus</span></span> | <span data-ttu-id="7b2df-139">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b2df-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="7b2df-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="7b2df-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="7b2df-141">SmartScreen</span></span> | <span data-ttu-id="7b2df-142">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b2df-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="7b2df-143">CustomerTI</span></span> |  <span data-ttu-id="7b2df-144">自定义 TI</span><span class="sxs-lookup"><span data-stu-id="7b2df-144">Custom TI</span></span> | <span data-ttu-id="7b2df-145">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b2df-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="7b2df-146">OfficeATP</span></span> | <span data-ttu-id="7b2df-147">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7b2df-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="7b2df-148">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b2df-149">MTP</span><span class="sxs-lookup"><span data-stu-id="7b2df-149">MTP</span></span>   | <span data-ttu-id="7b2df-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b2df-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="7b2df-151">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b2df-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="7b2df-152">AzureATP</span></span> |    <span data-ttu-id="7b2df-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="7b2df-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="7b2df-154">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b2df-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="7b2df-155">CustomDetection</span></span>   | <span data-ttu-id="7b2df-156">自定义检测</span><span class="sxs-lookup"><span data-stu-id="7b2df-156">Custom detection</span></span> | <span data-ttu-id="7b2df-157">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b2df-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="7b2df-158">AutomatedInvestigation</span></span> |<span data-ttu-id="7b2df-159">自动调查</span><span class="sxs-lookup"><span data-stu-id="7b2df-159">Automated investigation</span></span> | <span data-ttu-id="7b2df-160">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b2df-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="7b2df-161">ThreatExperts</span></span> | <span data-ttu-id="7b2df-162">Microsoft 威胁专家</span><span class="sxs-lookup"><span data-stu-id="7b2df-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="7b2df-163">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b2df-164">第三方 TI</span><span class="sxs-lookup"><span data-stu-id="7b2df-164">3rd party TI</span></span> | <span data-ttu-id="7b2df-165">第三方传感器</span><span class="sxs-lookup"><span data-stu-id="7b2df-165">3rd Party sensors</span></span> | <span data-ttu-id="7b2df-166">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="7b2df-167">每个租户</span><span class="sxs-lookup"><span data-stu-id="7b2df-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="7b2df-168">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7b2df-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="7b2df-169">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="7b2df-170">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="7b2df-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="7b2df-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b2df-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="7b2df-172">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="7b2df-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="7b2df-173">Office 365 ATP</span></span>  |<span data-ttu-id="7b2df-174">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7b2df-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="7b2df-175">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="7b2df-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="7b2df-176">Azure ATP</span></span>    |<span data-ttu-id="7b2df-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="7b2df-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="7b2df-178">重新品牌</span><span class="sxs-lookup"><span data-stu-id="7b2df-178">Rebranding</span></span> |

<span data-ttu-id="7b2df-179">`DetectionSource` 在 [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。</span><span class="sxs-lookup"><span data-stu-id="7b2df-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="7b2df-180">`ServiceSource` 在 [AlertEvidence 和](advanced-hunting-alertevidence-table.md) [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。</span><span class="sxs-lookup"><span data-stu-id="7b2df-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="7b2df-181">相关主题</span><span class="sxs-lookup"><span data-stu-id="7b2df-181">Related topics</span></span>
- [<span data-ttu-id="7b2df-182">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="7b2df-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7b2df-183">了解架构</span><span class="sxs-lookup"><span data-stu-id="7b2df-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)