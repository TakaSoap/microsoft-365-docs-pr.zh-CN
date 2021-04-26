---
title: Microsoft 365 Defender 高级搜寻架构中的命名更改
description: 跟踪并查看高级搜寻架构中的命名更改表和列
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 数据， 命名更改， 重命名
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
ms.openlocfilehash: eb6dfa628488239e3953d19d5e78b338e76f50a2
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023781"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="59fe8-104">高级搜寻架构 - 命名更改</span><span class="sxs-lookup"><span data-stu-id="59fe8-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="59fe8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="59fe8-105">**Applies to:**</span></span>
- <span data-ttu-id="59fe8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59fe8-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="59fe8-107">高级 [搜寻架构](advanced-hunting-schema-tables.md) 会定期更新，以添加新表和列。</span><span class="sxs-lookup"><span data-stu-id="59fe8-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="59fe8-108">在某些情况下，重命名或替换现有列名称以改进用户体验。</span><span class="sxs-lookup"><span data-stu-id="59fe8-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="59fe8-109">请参阅本文，查看可能会影响查询的命名更改。</span><span class="sxs-lookup"><span data-stu-id="59fe8-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="59fe8-110">命名更改将自动应用于保存在安全中心的查询，包括自定义检测规则使用的查询。</span><span class="sxs-lookup"><span data-stu-id="59fe8-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="59fe8-111">无需手动更新这些查询。</span><span class="sxs-lookup"><span data-stu-id="59fe8-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="59fe8-112">但是，您需要更新以下查询：</span><span class="sxs-lookup"><span data-stu-id="59fe8-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="59fe8-113">使用 API 运行的查询</span><span class="sxs-lookup"><span data-stu-id="59fe8-113">Queries that are run using the API</span></span>
- <span data-ttu-id="59fe8-114">保存在安全中心外部的查询</span><span class="sxs-lookup"><span data-stu-id="59fe8-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="59fe8-115">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="59fe8-115">December 2020</span></span>

| <span data-ttu-id="59fe8-116">表名</span><span class="sxs-lookup"><span data-stu-id="59fe8-116">Table name</span></span> | <span data-ttu-id="59fe8-117">原始列名称</span><span class="sxs-lookup"><span data-stu-id="59fe8-117">Original column name</span></span> | <span data-ttu-id="59fe8-118">新列名称</span><span class="sxs-lookup"><span data-stu-id="59fe8-118">New column name</span></span> | <span data-ttu-id="59fe8-119">更改原因</span><span class="sxs-lookup"><span data-stu-id="59fe8-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="59fe8-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="59fe8-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="59fe8-121">客户反馈</span><span class="sxs-lookup"><span data-stu-id="59fe8-121">Customer feedback</span></span> |
| [<span data-ttu-id="59fe8-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="59fe8-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="59fe8-123">客户反馈</span><span class="sxs-lookup"><span data-stu-id="59fe8-123">Customer feedback</span></span> |
| [<span data-ttu-id="59fe8-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="59fe8-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="59fe8-125">客户反馈</span><span class="sxs-lookup"><span data-stu-id="59fe8-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="59fe8-126">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="59fe8-126">January 2021</span></span>

| <span data-ttu-id="59fe8-127">列名称</span><span class="sxs-lookup"><span data-stu-id="59fe8-127">Column name</span></span> | <span data-ttu-id="59fe8-128">原始值名称</span><span class="sxs-lookup"><span data-stu-id="59fe8-128">Original value name</span></span> | <span data-ttu-id="59fe8-129">新值名称</span><span class="sxs-lookup"><span data-stu-id="59fe8-129">New value name</span></span> | <span data-ttu-id="59fe8-130">更改原因</span><span class="sxs-lookup"><span data-stu-id="59fe8-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="59fe8-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="59fe8-131">MCAS</span></span> |    <span data-ttu-id="59fe8-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="59fe8-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="59fe8-133">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="59fe8-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="59fe8-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="59fe8-135">EDR</span><span class="sxs-lookup"><span data-stu-id="59fe8-135">EDR</span></span>| <span data-ttu-id="59fe8-136">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="59fe8-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="59fe8-137">WindowsDefenderAv</span></span> | <span data-ttu-id="59fe8-138">防病毒</span><span class="sxs-lookup"><span data-stu-id="59fe8-138">Antivirus</span></span> | <span data-ttu-id="59fe8-139">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="59fe8-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="59fe8-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="59fe8-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="59fe8-141">SmartScreen</span></span> | <span data-ttu-id="59fe8-142">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="59fe8-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="59fe8-143">CustomerTI</span></span> |  <span data-ttu-id="59fe8-144">自定义 TI</span><span class="sxs-lookup"><span data-stu-id="59fe8-144">Custom TI</span></span> | <span data-ttu-id="59fe8-145">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="59fe8-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="59fe8-146">OfficeATP</span></span> | <span data-ttu-id="59fe8-147">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="59fe8-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="59fe8-148">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="59fe8-149">MTP</span><span class="sxs-lookup"><span data-stu-id="59fe8-149">MTP</span></span>   | <span data-ttu-id="59fe8-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59fe8-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="59fe8-151">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="59fe8-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="59fe8-152">AzureATP</span></span> |    <span data-ttu-id="59fe8-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="59fe8-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="59fe8-154">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="59fe8-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="59fe8-155">CustomDetection</span></span>   | <span data-ttu-id="59fe8-156">自定义检测</span><span class="sxs-lookup"><span data-stu-id="59fe8-156">Custom detection</span></span> | <span data-ttu-id="59fe8-157">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="59fe8-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="59fe8-158">AutomatedInvestigation</span></span> |<span data-ttu-id="59fe8-159">自动调查</span><span class="sxs-lookup"><span data-stu-id="59fe8-159">Automated investigation</span></span> | <span data-ttu-id="59fe8-160">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="59fe8-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="59fe8-161">ThreatExperts</span></span> | <span data-ttu-id="59fe8-162">Microsoft 威胁专家</span><span class="sxs-lookup"><span data-stu-id="59fe8-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="59fe8-163">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="59fe8-164">第三方 TI</span><span class="sxs-lookup"><span data-stu-id="59fe8-164">3rd party TI</span></span> | <span data-ttu-id="59fe8-165">第三方传感器</span><span class="sxs-lookup"><span data-stu-id="59fe8-165">3rd Party sensors</span></span> | <span data-ttu-id="59fe8-166">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="59fe8-167">每个租户</span><span class="sxs-lookup"><span data-stu-id="59fe8-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="59fe8-168">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="59fe8-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="59fe8-169">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="59fe8-170">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="59fe8-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="59fe8-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59fe8-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="59fe8-172">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="59fe8-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="59fe8-173">Office 365 ATP</span></span>  |<span data-ttu-id="59fe8-174">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="59fe8-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="59fe8-175">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="59fe8-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="59fe8-176">Azure ATP</span></span>    |<span data-ttu-id="59fe8-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="59fe8-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="59fe8-178">重新品牌</span><span class="sxs-lookup"><span data-stu-id="59fe8-178">Rebranding</span></span> |

<span data-ttu-id="59fe8-179">`DetectionSource` 在 [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。</span><span class="sxs-lookup"><span data-stu-id="59fe8-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="59fe8-180">`ServiceSource` 在 [AlertEvidence 和](advanced-hunting-alertevidence-table.md) [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。</span><span class="sxs-lookup"><span data-stu-id="59fe8-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="59fe8-181">2021 年 2 月</span><span class="sxs-lookup"><span data-stu-id="59fe8-181">February 2021</span></span>

1. <span data-ttu-id="59fe8-182">在 [EmailAttachmentInfo 和](advanced-hunting-emailattachmentinfo-table.md) [EmailEvents](advanced-hunting-emailevents-table.md) 表中，和 列 `MalwareFilterVerdict` `PhishFilterVerdict` 已替换为 `ThreatTypes` 列。</span><span class="sxs-lookup"><span data-stu-id="59fe8-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="59fe8-183">和 `MalwareDetectionMethod` `PhishDetectionMethod` 列也替换为 `DetectionMethods` 列。</span><span class="sxs-lookup"><span data-stu-id="59fe8-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="59fe8-184">通过简化，可以在新列下提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="59fe8-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="59fe8-185">映射如下所示。</span><span class="sxs-lookup"><span data-stu-id="59fe8-185">The mapping is provided below.</span></span>

| <span data-ttu-id="59fe8-186">表名</span><span class="sxs-lookup"><span data-stu-id="59fe8-186">Table name</span></span> | <span data-ttu-id="59fe8-187">原始列名称</span><span class="sxs-lookup"><span data-stu-id="59fe8-187">Original column name</span></span> | <span data-ttu-id="59fe8-188">新列名称</span><span class="sxs-lookup"><span data-stu-id="59fe8-188">New column name</span></span> | <span data-ttu-id="59fe8-189">更改原因</span><span class="sxs-lookup"><span data-stu-id="59fe8-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="59fe8-190">包括更多检测方法</span><span class="sxs-lookup"><span data-stu-id="59fe8-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="59fe8-191">包括更多威胁类型</span><span class="sxs-lookup"><span data-stu-id="59fe8-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="59fe8-192">包括更多检测方法</span><span class="sxs-lookup"><span data-stu-id="59fe8-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="59fe8-193">包括更多威胁类型</span><span class="sxs-lookup"><span data-stu-id="59fe8-193">Include more threat types</span></span> |


2. <span data-ttu-id="59fe8-194">在 `EmailAttachmentInfo` 和 `EmailEvents` 表中， `ThreatNames` 添加了 列以提供有关电子邮件威胁详细信息。</span><span class="sxs-lookup"><span data-stu-id="59fe8-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="59fe8-195">此列包含"垃圾邮件"或"钓鱼邮件"等值。</span><span class="sxs-lookup"><span data-stu-id="59fe8-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="59fe8-196">在 [DeviceInfo 表中](advanced-hunting-deviceinfo-table.md) ， `DeviceObjectId` 列已根据客户反馈 `AadDeviceId` 替换为该列。</span><span class="sxs-lookup"><span data-stu-id="59fe8-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="59fe8-197">在 [DeviceEvents](advanced-hunting-deviceevents-table.md) 表中，修改了几个 ActionType 名称，以更好地反映操作的说明。</span><span class="sxs-lookup"><span data-stu-id="59fe8-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="59fe8-198">可在下方找到更改的详细信息。</span><span class="sxs-lookup"><span data-stu-id="59fe8-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="59fe8-199">表名</span><span class="sxs-lookup"><span data-stu-id="59fe8-199">Table name</span></span> | <span data-ttu-id="59fe8-200">原始 ActionType 名称</span><span class="sxs-lookup"><span data-stu-id="59fe8-200">Original ActionType name</span></span> | <span data-ttu-id="59fe8-201">新的 ActionType 名称</span><span class="sxs-lookup"><span data-stu-id="59fe8-201">New ActionType name</span></span> | <span data-ttu-id="59fe8-202">更改原因</span><span class="sxs-lookup"><span data-stu-id="59fe8-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="59fe8-203">客户反馈</span><span class="sxs-lookup"><span data-stu-id="59fe8-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="59fe8-204">客户反馈</span><span class="sxs-lookup"><span data-stu-id="59fe8-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="59fe8-205">客户反馈</span><span class="sxs-lookup"><span data-stu-id="59fe8-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="59fe8-206">客户反馈</span><span class="sxs-lookup"><span data-stu-id="59fe8-206">Customer feedback</span></span> |

## <a name="march-2021"></a><span data-ttu-id="59fe8-207">2021 年 3 月</span><span class="sxs-lookup"><span data-stu-id="59fe8-207">March 2021</span></span>

<span data-ttu-id="59fe8-208">`DeviceTvmSoftwareInventoryVulnerabilities`该表已被弃用。</span><span class="sxs-lookup"><span data-stu-id="59fe8-208">The `DeviceTvmSoftwareInventoryVulnerabilities` table has been deprecated.</span></span> <span data-ttu-id="59fe8-209">将 替换为 `DeviceTvmSoftwareInventory` 和 `DeviceTvmSoftwareVulnerabilities` 表。</span><span class="sxs-lookup"><span data-stu-id="59fe8-209">Replacing it are the `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables.</span></span>



## <a name="related-topics"></a><span data-ttu-id="59fe8-210">相关主题</span><span class="sxs-lookup"><span data-stu-id="59fe8-210">Related topics</span></span>
- [<span data-ttu-id="59fe8-211">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="59fe8-211">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="59fe8-212">了解架构</span><span class="sxs-lookup"><span data-stu-id="59fe8-212">Understand the schema</span></span>](advanced-hunting-schema-tables.md)