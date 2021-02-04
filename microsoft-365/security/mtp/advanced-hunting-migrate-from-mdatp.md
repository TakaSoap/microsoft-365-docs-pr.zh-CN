---
title: 从 Microsoft Defender for Endpoint 迁移高级搜寻查询
description: 了解如何调整适用于终结点查询的 Microsoft Defender，以便可以在 Microsoft 365 Defender 中使用它们
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， microsoft defender atp， mdatp， 搜索， 查询， 遥测， 自定义检测， 架构， kusto， microsoft 365， 映射
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094803"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="2e0d2-104">从 Microsoft Defender for Endpoint 迁移高级搜寻查询</span><span class="sxs-lookup"><span data-stu-id="2e0d2-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2e0d2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2e0d2-105">**Applies to:**</span></span>
- <span data-ttu-id="2e0d2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e0d2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2e0d2-107">从 Microsoft Defender for Endpoint 移动高级搜寻工作流，以使用更广泛的数据集主动搜寻威胁。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="2e0d2-108">在 Microsoft 365 Defender 中，你可以访问来自其他 Microsoft 365 安全解决方案的数据，包括：</span><span class="sxs-lookup"><span data-stu-id="2e0d2-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="2e0d2-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2e0d2-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="2e0d2-110">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="2e0d2-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="2e0d2-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2e0d2-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2e0d2-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2e0d2-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="2e0d2-113">大多数适用于终结点的 Microsoft Defender 客户可以使用 [Microsoft 365 Defender，而无需其他许可证](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="2e0d2-114">若要开始从 Defender for Endpoint 转换高级搜寻工作流，[请打开 Microsoft 365 Defender。](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="2e0d2-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="2e0d2-115">你可以转换，而不会影响现有的 Defender for Endpoint 工作流。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="2e0d2-116">保存的查询保持不变，并且自定义检测规则将继续运行并生成警报。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="2e0d2-117">但是，它们将在 Microsoft 365 Defender 中可见。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="2e0d2-118">仅适用于 Microsoft 365 Defender 中的架构表</span><span class="sxs-lookup"><span data-stu-id="2e0d2-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="2e0d2-119">[Microsoft 365 Defender 高级搜寻架构](advanced-hunting-schema-tables.md)提供包含各种 Microsoft 365 安全解决方案数据的其他表。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="2e0d2-120">下表仅适用于 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="2e0d2-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="2e0d2-121">表名</span><span class="sxs-lookup"><span data-stu-id="2e0d2-121">Table name</span></span> | <span data-ttu-id="2e0d2-122">说明</span><span class="sxs-lookup"><span data-stu-id="2e0d2-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="2e0d2-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="2e0d2-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="2e0d2-124">与警报关联的文件、IP 地址、URL、用户或设备</span><span class="sxs-lookup"><span data-stu-id="2e0d2-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="2e0d2-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="2e0d2-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="2e0d2-126">来自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的警报，包括严重性信息和威胁类别</span><span class="sxs-lookup"><span data-stu-id="2e0d2-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="2e0d2-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="2e0d2-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="2e0d2-128">云应用和服务中的文件相关活动</span><span class="sxs-lookup"><span data-stu-id="2e0d2-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="2e0d2-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="2e0d2-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="2e0d2-130">有关附加到电子邮件的文件的信息</span><span class="sxs-lookup"><span data-stu-id="2e0d2-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="2e0d2-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="2e0d2-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="2e0d2-132">Microsoft 365 电子邮件事件，包括电子邮件传递和阻止事件</span><span class="sxs-lookup"><span data-stu-id="2e0d2-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="2e0d2-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="2e0d2-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="2e0d2-134">在 Microsoft 365 将电子邮件传递到收件人邮箱后发生的安全事件</span><span class="sxs-lookup"><span data-stu-id="2e0d2-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="2e0d2-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="2e0d2-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="2e0d2-136">有关电子邮件 URL 的信息</span><span class="sxs-lookup"><span data-stu-id="2e0d2-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="2e0d2-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="2e0d2-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="2e0d2-138">涉及运行 Active Directory 本地域控制器的事件 (AD) 。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="2e0d2-139">此表涵盖域控制器上与标识相关的一系列事件和系统事件。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="2e0d2-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="2e0d2-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="2e0d2-141">来自各种源的帐户信息，包括 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2e0d2-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="2e0d2-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="2e0d2-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="2e0d2-143">Active Directory 和 Microsoft 联机服务上的身份验证事件</span><span class="sxs-lookup"><span data-stu-id="2e0d2-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="2e0d2-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="2e0d2-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="2e0d2-145">对 Active Directory 对象（如用户、组、设备和域）的查询</span><span class="sxs-lookup"><span data-stu-id="2e0d2-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="2e0d2-146">映射 DeviceAlertEvents 表</span><span class="sxs-lookup"><span data-stu-id="2e0d2-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="2e0d2-147">和 `AlertInfo` `AlertEvidence` 表替换了 `DeviceAlertEvents` Microsoft Defender for Endpoint 架构中的表。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="2e0d2-148">除了有关设备警报的数据，这两个表还包括有关标识、应用和电子邮件警报的数据。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="2e0d2-149">使用下表检查列 `DeviceAlertEvents` 如何映射到和表中的 `AlertInfo` `AlertEvidence` 列。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="2e0d2-150">除了下表中的列之外，该表还包含许多其他列，这些列提供来自各种源的警报的更全面的 `AlertEvidence` 图片。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="2e0d2-151">查看所有 AlertEvidence 列</span><span class="sxs-lookup"><span data-stu-id="2e0d2-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="2e0d2-152">DeviceAlertEvents 列</span><span class="sxs-lookup"><span data-stu-id="2e0d2-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="2e0d2-153">在哪里可以找到 Microsoft 365 Defender 中的相同数据</span><span class="sxs-lookup"><span data-stu-id="2e0d2-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="2e0d2-154">`AlertInfo` 和  `AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="2e0d2-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="2e0d2-155">`AlertInfo` 和  `AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="2e0d2-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="2e0d2-156">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="2e0d2-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="2e0d2-157">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="2e0d2-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="2e0d2-158">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="2e0d2-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="2e0d2-159">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="2e0d2-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="2e0d2-160">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="2e0d2-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="2e0d2-161">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="2e0d2-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="2e0d2-162">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="2e0d2-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="2e0d2-163">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="2e0d2-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="2e0d2-164">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="2e0d2-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="2e0d2-165">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="2e0d2-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="2e0d2-166">此列通常在 Microsoft Defender for Endpoint 中用于查找其他表中的相关记录。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="2e0d2-167">在 Microsoft 365 Defender 中，你可以直接从表中获取 `AlertEvidence` 相关数据。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="2e0d2-168">此列通常在 Microsoft Defender for Endpoint 中用于其他表中的其他事件信息。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="2e0d2-169">在 Microsoft 365 Defender 中，你可以直接从表中获取 `AlertEvidence` 相关数据。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="2e0d2-170">调整现有的 Microsoft Defender 终结点查询</span><span class="sxs-lookup"><span data-stu-id="2e0d2-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="2e0d2-171">Microsoft Defender for Endpoint 查询将正常工作，除非它们引用 `DeviceAlertEvents` 该表。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="2e0d2-172">若要在 Microsoft 365 Defender 中使用这些查询，请应用这些更改：</span><span class="sxs-lookup"><span data-stu-id="2e0d2-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="2e0d2-173">替换为 `DeviceAlertEvents` `AlertInfo` 。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="2e0d2-174">将 `AlertInfo` 和表 `AlertEvidence` 联接在一起 `AlertId` 可获取等效数据。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="2e0d2-175">原始查询</span><span class="sxs-lookup"><span data-stu-id="2e0d2-175">Original query</span></span>
<span data-ttu-id="2e0d2-176">以下查询在 `DeviceAlertEvents` Microsoft Defender for Endpoint 中用于获取涉及以下powershell.exe：</span><span class="sxs-lookup"><span data-stu-id="2e0d2-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="2e0d2-177">修改后的查询</span><span class="sxs-lookup"><span data-stu-id="2e0d2-177">Modified query</span></span>
<span data-ttu-id="2e0d2-178">以下查询已调整为在 Microsoft 365 Defender 中使用。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="2e0d2-179">它联接并检查该表中的文件名，而不是直接 `DeviceAlertEvents` `AlertEvidence` 检查文件名。</span><span class="sxs-lookup"><span data-stu-id="2e0d2-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a><span data-ttu-id="2e0d2-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e0d2-180">See also</span></span>
- [<span data-ttu-id="2e0d2-181">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e0d2-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2e0d2-182">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="2e0d2-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2e0d2-183">了解架构</span><span class="sxs-lookup"><span data-stu-id="2e0d2-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2e0d2-184">Microsoft Defender for Endpoint 中的高级搜寻</span><span class="sxs-lookup"><span data-stu-id="2e0d2-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)