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
ms.openlocfilehash: cd06286083297d0930270868b99a14f8ddb2f4b2
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461663"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="ad9b7-104">高级搜寻架构 - 命名更改</span><span class="sxs-lookup"><span data-stu-id="ad9b7-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ad9b7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ad9b7-105">**Applies to:**</span></span>
- <span data-ttu-id="ad9b7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad9b7-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="ad9b7-107">高级 [搜寻架构](advanced-hunting-schema-tables.md) 会定期更新以添加新表和列。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="ad9b7-108">在某些情况下，重命名或替换现有列名称以改进用户体验。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="ad9b7-109">请参阅本文，查看可能会影响查询的命名更改。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="ad9b7-110">命名更改将自动应用于保存在安全中心的查询，包括自定义检测规则使用的查询。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="ad9b7-111">无需手动更新这些查询。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="ad9b7-112">但是，您需要更新以下查询：</span><span class="sxs-lookup"><span data-stu-id="ad9b7-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="ad9b7-113">使用 API 运行的查询</span><span class="sxs-lookup"><span data-stu-id="ad9b7-113">Queries that are run using the API</span></span>
- <span data-ttu-id="ad9b7-114">保存在安全中心外部的其他地方的查询</span><span class="sxs-lookup"><span data-stu-id="ad9b7-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="ad9b7-115">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="ad9b7-115">December 2020</span></span>

| <span data-ttu-id="ad9b7-116">表名</span><span class="sxs-lookup"><span data-stu-id="ad9b7-116">Table name</span></span> | <span data-ttu-id="ad9b7-117">原始列名称</span><span class="sxs-lookup"><span data-stu-id="ad9b7-117">Original column name</span></span> | <span data-ttu-id="ad9b7-118">新列名称</span><span class="sxs-lookup"><span data-stu-id="ad9b7-118">New column name</span></span> | <span data-ttu-id="ad9b7-119">更改原因</span><span class="sxs-lookup"><span data-stu-id="ad9b7-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="ad9b7-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ad9b7-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="ad9b7-121">客户反馈</span><span class="sxs-lookup"><span data-stu-id="ad9b7-121">Customer feedback</span></span> |
| [<span data-ttu-id="ad9b7-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ad9b7-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="ad9b7-123">客户反馈</span><span class="sxs-lookup"><span data-stu-id="ad9b7-123">Customer feedback</span></span> |
| [<span data-ttu-id="ad9b7-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ad9b7-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="ad9b7-125">客户反馈</span><span class="sxs-lookup"><span data-stu-id="ad9b7-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="ad9b7-126">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="ad9b7-126">January 2021</span></span>

| <span data-ttu-id="ad9b7-127">列名称</span><span class="sxs-lookup"><span data-stu-id="ad9b7-127">Column name</span></span> | <span data-ttu-id="ad9b7-128">原始值名称</span><span class="sxs-lookup"><span data-stu-id="ad9b7-128">Original value name</span></span> | <span data-ttu-id="ad9b7-129">新值名称</span><span class="sxs-lookup"><span data-stu-id="ad9b7-129">New value name</span></span> | <span data-ttu-id="ad9b7-130">更改原因</span><span class="sxs-lookup"><span data-stu-id="ad9b7-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="ad9b7-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="ad9b7-131">MCAS</span></span> |    <span data-ttu-id="ad9b7-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ad9b7-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="ad9b7-133">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ad9b7-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="ad9b7-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="ad9b7-135">EDR</span><span class="sxs-lookup"><span data-stu-id="ad9b7-135">EDR</span></span>| <span data-ttu-id="ad9b7-136">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ad9b7-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="ad9b7-137">WindowsDefenderAv</span></span> | <span data-ttu-id="ad9b7-138">防病毒</span><span class="sxs-lookup"><span data-stu-id="ad9b7-138">Antivirus</span></span> | <span data-ttu-id="ad9b7-139">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ad9b7-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="ad9b7-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="ad9b7-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="ad9b7-141">SmartScreen</span></span> | <span data-ttu-id="ad9b7-142">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ad9b7-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="ad9b7-143">CustomerTI</span></span> |  <span data-ttu-id="ad9b7-144">自定义 TI</span><span class="sxs-lookup"><span data-stu-id="ad9b7-144">Custom TI</span></span> | <span data-ttu-id="ad9b7-145">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ad9b7-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="ad9b7-146">OfficeATP</span></span> | <span data-ttu-id="ad9b7-147">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ad9b7-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="ad9b7-148">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ad9b7-149">MTP</span><span class="sxs-lookup"><span data-stu-id="ad9b7-149">MTP</span></span>   | <span data-ttu-id="ad9b7-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad9b7-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="ad9b7-151">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ad9b7-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="ad9b7-152">AzureATP</span></span> |    <span data-ttu-id="ad9b7-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="ad9b7-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="ad9b7-154">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ad9b7-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="ad9b7-155">CustomDetection</span></span>   | <span data-ttu-id="ad9b7-156">自定义检测</span><span class="sxs-lookup"><span data-stu-id="ad9b7-156">Custom detection</span></span> | <span data-ttu-id="ad9b7-157">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ad9b7-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="ad9b7-158">AutomatedInvestigation</span></span> |<span data-ttu-id="ad9b7-159">自动调查</span><span class="sxs-lookup"><span data-stu-id="ad9b7-159">Automated investigation</span></span> | <span data-ttu-id="ad9b7-160">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ad9b7-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="ad9b7-161">ThreatExperts</span></span> | <span data-ttu-id="ad9b7-162">Microsoft 威胁专家</span><span class="sxs-lookup"><span data-stu-id="ad9b7-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="ad9b7-163">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ad9b7-164">第三方 TI</span><span class="sxs-lookup"><span data-stu-id="ad9b7-164">3rd party TI</span></span> | <span data-ttu-id="ad9b7-165">第三方传感器</span><span class="sxs-lookup"><span data-stu-id="ad9b7-165">3rd Party sensors</span></span> | <span data-ttu-id="ad9b7-166">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="ad9b7-167">每个租户</span><span class="sxs-lookup"><span data-stu-id="ad9b7-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="ad9b7-168">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ad9b7-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="ad9b7-169">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="ad9b7-170">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="ad9b7-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="ad9b7-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad9b7-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="ad9b7-172">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="ad9b7-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ad9b7-173">Office 365 ATP</span></span>  |<span data-ttu-id="ad9b7-174">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ad9b7-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="ad9b7-175">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="ad9b7-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="ad9b7-176">Azure ATP</span></span>    |<span data-ttu-id="ad9b7-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="ad9b7-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="ad9b7-178">重新品牌</span><span class="sxs-lookup"><span data-stu-id="ad9b7-178">Rebranding</span></span> |

<span data-ttu-id="ad9b7-179">`DetectionSource` 在 [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="ad9b7-180">`ServiceSource` 在 [AlertEvidence 和](advanced-hunting-alertevidence-table.md) [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="ad9b7-181">2021 年 2 月</span><span class="sxs-lookup"><span data-stu-id="ad9b7-181">February 2021</span></span>

1. <span data-ttu-id="ad9b7-182">在 [EmailAttachmentInfo 和](advanced-hunting-emailattachmentinfo-table.md) [EmailEvents](advanced-hunting-emailevents-table.md) 表中，我们弃用 and 列， `MalwareFilterVerdict` `PhishFilterVerdict` 并替换为 `ThreatTypes` 列。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, we deprecated the `MalwareFilterVerdict`and `PhishFilterVerdict` columns and replaced them with the `ThreatTypes` column.</span></span> <span data-ttu-id="ad9b7-183">我们还弃用 and 列 `MalwareDetectionMethod` `PhishDetectionMethod` ，并替换为 `DetectionMethods` 列。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-183">We also deprecated the `MalwareDetectionMethod` and `PhishDetectionMethod` columns and replaced them with the `DetectionMethods` column.</span></span> <span data-ttu-id="ad9b7-184">这种简化使我们能够在新列下提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="ad9b7-185">映射如下所示。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-185">The mapping is provided below.</span></span>

| <span data-ttu-id="ad9b7-186">表名</span><span class="sxs-lookup"><span data-stu-id="ad9b7-186">Table name</span></span> | <span data-ttu-id="ad9b7-187">原始列名称</span><span class="sxs-lookup"><span data-stu-id="ad9b7-187">Original column name</span></span> | <span data-ttu-id="ad9b7-188">新列名称</span><span class="sxs-lookup"><span data-stu-id="ad9b7-188">New column name</span></span> | <span data-ttu-id="ad9b7-189">更改原因</span><span class="sxs-lookup"><span data-stu-id="ad9b7-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="ad9b7-190">包括更多检测方法</span><span class="sxs-lookup"><span data-stu-id="ad9b7-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="ad9b7-191">包括更多威胁类型</span><span class="sxs-lookup"><span data-stu-id="ad9b7-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="ad9b7-192">包括更多检测方法</span><span class="sxs-lookup"><span data-stu-id="ad9b7-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="ad9b7-193">包括更多威胁类型</span><span class="sxs-lookup"><span data-stu-id="ad9b7-193">Include more threat types</span></span> |


2. <span data-ttu-id="ad9b7-194">在 `EmailAttachmentInfo` and `EmailEvents` 表中，我们添加了列 `ThreatNames` ，以提供有关电子邮件威胁详细信息。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, we added the column `ThreatNames` to give more information about the email threat.</span></span> <span data-ttu-id="ad9b7-195">此列包含垃圾邮件或网络钓鱼等值。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="ad9b7-196">在 [DeviceInfo 表中](advanced-hunting-deviceinfo-table.md) ，我们根据客户反馈 `DeviceObjectId` 替换 `AadDeviceId` 了列。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, we replaced the `DeviceObjectId` column with `AadDeviceId` based on customer feedback.</span></span>

4. <span data-ttu-id="ad9b7-197">在 [DeviceEvents](advanced-hunting-deviceevents-table.md) 表中，我们更新了多个 ActionType 名称，以更好地反映操作的说明。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, we updated several ActionType names to better reflect the description of the action.</span></span> <span data-ttu-id="ad9b7-198">可在下方找到详细信息。</span><span class="sxs-lookup"><span data-stu-id="ad9b7-198">Details can be found below.</span></span>

| <span data-ttu-id="ad9b7-199">表名</span><span class="sxs-lookup"><span data-stu-id="ad9b7-199">Table name</span></span> | <span data-ttu-id="ad9b7-200">原始 ActionType 名称</span><span class="sxs-lookup"><span data-stu-id="ad9b7-200">Original ActionType name</span></span> | <span data-ttu-id="ad9b7-201">新 ActionType 名称</span><span class="sxs-lookup"><span data-stu-id="ad9b7-201">New ActionType name</span></span> | <span data-ttu-id="ad9b7-202">更改原因</span><span class="sxs-lookup"><span data-stu-id="ad9b7-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="ad9b7-203">客户反馈</span><span class="sxs-lookup"><span data-stu-id="ad9b7-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="ad9b7-204">客户反馈</span><span class="sxs-lookup"><span data-stu-id="ad9b7-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="ad9b7-205">客户反馈</span><span class="sxs-lookup"><span data-stu-id="ad9b7-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="ad9b7-206">客户反馈</span><span class="sxs-lookup"><span data-stu-id="ad9b7-206">Customer feedback</span></span> |
| `DeviceEvents` | `AntivirusDetection` | `EdrBlock` | <span data-ttu-id="ad9b7-207">客户反馈</span><span class="sxs-lookup"><span data-stu-id="ad9b7-207">Customer feedback</span></span> |





## <a name="related-topics"></a><span data-ttu-id="ad9b7-208">相关主题</span><span class="sxs-lookup"><span data-stu-id="ad9b7-208">Related topics</span></span>
- [<span data-ttu-id="ad9b7-209">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="ad9b7-209">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ad9b7-210">了解架构</span><span class="sxs-lookup"><span data-stu-id="ad9b7-210">Understand the schema</span></span>](advanced-hunting-schema-tables.md)