---
title: 从 Microsoft Defender for Endpoint 迁移高级搜寻查询
description: 了解如何调整 Microsoft Defender for Endpoint 查询，以便你可以在 Microsoft 365 Defender 中使用它们
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、microsoft defender atp、mdatp、search、query、遥测、自定义检测、架构、kusto、microsoft 365、映射
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846852"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="0f096-104">从 Microsoft Defender for Endpoint 迁移高级搜寻查询</span><span class="sxs-lookup"><span data-stu-id="0f096-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0f096-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0f096-105">**Applies to:**</span></span>
- <span data-ttu-id="0f096-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0f096-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0f096-107">通过 Microsoft Defender for Endpoint 移动高级的求职工作流，以使用更广泛的数据集主动查找威胁。</span><span class="sxs-lookup"><span data-stu-id="0f096-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="0f096-108">在 Microsoft 365 Defender 中，你可以访问其他 Microsoft 365 安全解决方案中的数据，包括：</span><span class="sxs-lookup"><span data-stu-id="0f096-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="0f096-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0f096-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="0f096-110">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0f096-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="0f096-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0f096-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="0f096-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="0f096-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="0f096-113">大多数 Microsoft Defender for Endpoint 客户可以 [使用 Microsoft 365 Defender，而无需其他许可证](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="0f096-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="0f096-114">若要开始从 Defender for Endpoint 转换你的高级求职工作流，请 [打开 Microsoft 365 Defender](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="0f096-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="0f096-115">你可以在不影响现有 Defender 的终结点工作流的情况下进行转换。</span><span class="sxs-lookup"><span data-stu-id="0f096-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="0f096-116">保存的查询保持不变，自定义检测规则将继续运行并生成警报。</span><span class="sxs-lookup"><span data-stu-id="0f096-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="0f096-117">但是，它们将在 Microsoft 365 Defender 中可见。</span><span class="sxs-lookup"><span data-stu-id="0f096-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="0f096-118">仅限 Microsoft 365 Defender 中的架构表</span><span class="sxs-lookup"><span data-stu-id="0f096-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="0f096-119">[Microsoft 365 Defender 高级搜寻架构](advanced-hunting-schema-tables.md)提供了其他表格，其中包含来自各种 Microsoft 365 安全解决方案的数据。</span><span class="sxs-lookup"><span data-stu-id="0f096-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="0f096-120">以下表格仅适用于 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="0f096-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="0f096-121">表名</span><span class="sxs-lookup"><span data-stu-id="0f096-121">Table name</span></span> | <span data-ttu-id="0f096-122">说明</span><span class="sxs-lookup"><span data-stu-id="0f096-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="0f096-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="0f096-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="0f096-124">与警报关联的文件、IP 地址、Url、用户或设备</span><span class="sxs-lookup"><span data-stu-id="0f096-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="0f096-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="0f096-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="0f096-126">来自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft 云应用安全性和 Microsoft Defender for Identity 的警报，包括严重信息和威胁类别</span><span class="sxs-lookup"><span data-stu-id="0f096-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="0f096-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="0f096-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="0f096-128">云应用和服务中与文件相关的活动</span><span class="sxs-lookup"><span data-stu-id="0f096-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="0f096-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="0f096-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="0f096-130">有关附加到电子邮件的文件的信息</span><span class="sxs-lookup"><span data-stu-id="0f096-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="0f096-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="0f096-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="0f096-132">Microsoft 365 电子邮件事件，包括电子邮件传递和阻止事件</span><span class="sxs-lookup"><span data-stu-id="0f096-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="0f096-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="0f096-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="0f096-134">在 Microsoft 365 将电子邮件传递给收件人邮箱之后，在送达后发生的安全事件</span><span class="sxs-lookup"><span data-stu-id="0f096-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="0f096-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="0f096-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="0f096-136">有关电子邮件上的 Url 的信息</span><span class="sxs-lookup"><span data-stu-id="0f096-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="0f096-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="0f096-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="0f096-138">涉及运行 Active Directory (AD) 的本地域控制器的事件。</span><span class="sxs-lookup"><span data-stu-id="0f096-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="0f096-139">此表涵盖了域控制器上与标识相关的事件和系统事件的范围。</span><span class="sxs-lookup"><span data-stu-id="0f096-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="0f096-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="0f096-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="0f096-141">来自各种源（包括 Azure Active Directory）的帐户信息</span><span class="sxs-lookup"><span data-stu-id="0f096-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="0f096-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="0f096-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="0f096-143">Active Directory 和 Microsoft online services 上的身份验证事件</span><span class="sxs-lookup"><span data-stu-id="0f096-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="0f096-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="0f096-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="0f096-145">对 Active Directory 对象（如用户、组、设备和域）的查询</span><span class="sxs-lookup"><span data-stu-id="0f096-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="0f096-146">Map DeviceAlertEvents 表</span><span class="sxs-lookup"><span data-stu-id="0f096-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="0f096-147">`AlertInfo`和 `AlertEvidence` 表将替换 `DeviceAlertEvents` Microsoft Defender for Endpoint 架构中的表。</span><span class="sxs-lookup"><span data-stu-id="0f096-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="0f096-148">除了有关设备警报的数据之外，这两个表还包括有关标识、应用和电子邮件的警报的数据。</span><span class="sxs-lookup"><span data-stu-id="0f096-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="0f096-149">使用下表可检查列如何 `DeviceAlertEvents` 映射到和表中的 `AlertInfo` 列 `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="0f096-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="0f096-150">除了下表中的列， `AlertEvidence` 该表还包含许多其他列，这些列提供了来自各种源的更全面的警报。</span><span class="sxs-lookup"><span data-stu-id="0f096-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="0f096-151">查看所有 AlertEvidence 列</span><span class="sxs-lookup"><span data-stu-id="0f096-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="0f096-152">DeviceAlertEvents 列</span><span class="sxs-lookup"><span data-stu-id="0f096-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="0f096-153">在 Microsoft 365 Defender 中查找相同数据的位置</span><span class="sxs-lookup"><span data-stu-id="0f096-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="0f096-154">`AlertInfo` 和  `AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="0f096-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="0f096-155">`AlertInfo` 和  `AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="0f096-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="0f096-156">`AlertEvidence` 型</span><span class="sxs-lookup"><span data-stu-id="0f096-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="0f096-157">`AlertEvidence` 型</span><span class="sxs-lookup"><span data-stu-id="0f096-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="0f096-158">`AlertInfo` 型</span><span class="sxs-lookup"><span data-stu-id="0f096-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="0f096-159">`AlertInfo` 型</span><span class="sxs-lookup"><span data-stu-id="0f096-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="0f096-160">`AlertInfo` 型</span><span class="sxs-lookup"><span data-stu-id="0f096-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="0f096-161">`AlertEvidence` 型</span><span class="sxs-lookup"><span data-stu-id="0f096-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="0f096-162">`AlertEvidence` 型</span><span class="sxs-lookup"><span data-stu-id="0f096-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="0f096-163">`AlertEvidence` 型</span><span class="sxs-lookup"><span data-stu-id="0f096-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="0f096-164">`AlertEvidence` 型</span><span class="sxs-lookup"><span data-stu-id="0f096-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="0f096-165">`AlertInfo` 型</span><span class="sxs-lookup"><span data-stu-id="0f096-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="0f096-166">此列通常用于在 Microsoft Defender for Endpoint 中查找其他表中的相关记录。</span><span class="sxs-lookup"><span data-stu-id="0f096-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="0f096-167">在 Microsoft 365 Defender 中，可以直接从表中获取相关数据 `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="0f096-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="0f096-168">此列通常在 Microsoft Defender for Endpoint 中用于其他表中的其他事件信息。</span><span class="sxs-lookup"><span data-stu-id="0f096-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="0f096-169">在 Microsoft 365 Defender 中，可以直接从表中获取相关数据 `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="0f096-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="0f096-170">调整现有 Microsoft Defender for Endpoint 查询</span><span class="sxs-lookup"><span data-stu-id="0f096-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="0f096-171">Microsoft Defender for Endpoint 查询将正常工作，除非它们引用 `DeviceAlertEvents` 表。</span><span class="sxs-lookup"><span data-stu-id="0f096-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="0f096-172">若要在 Microsoft 365 Defender 中使用这些查询，请应用以下更改：</span><span class="sxs-lookup"><span data-stu-id="0f096-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="0f096-173">替换 `DeviceAlertEvents` 为 `AlertInfo` 。</span><span class="sxs-lookup"><span data-stu-id="0f096-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="0f096-174">联接 `AlertInfo` 和上的 `AlertEvidence` 表 `AlertId` 以获取等效数据。</span><span class="sxs-lookup"><span data-stu-id="0f096-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="0f096-175">原始查询</span><span class="sxs-lookup"><span data-stu-id="0f096-175">Original query</span></span>
<span data-ttu-id="0f096-176">以下查询 `DeviceAlertEvents` 在 Microsoft Defender For Endpoint 中使用，以获取涉及 _powershell.exe_ 的警报：</span><span class="sxs-lookup"><span data-stu-id="0f096-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_ :</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="0f096-177">修改的查询</span><span class="sxs-lookup"><span data-stu-id="0f096-177">Modified query</span></span>
<span data-ttu-id="0f096-178">以下查询已调整为在 Microsoft 365 Defender 中使用。</span><span class="sxs-lookup"><span data-stu-id="0f096-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="0f096-179">`DeviceAlertEvents`它将加入 `AlertEvidence` 并检查该表中的文件名，而不是直接从文件名签。</span><span class="sxs-lookup"><span data-stu-id="0f096-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="0f096-180">相关主题</span><span class="sxs-lookup"><span data-stu-id="0f096-180">Related topics</span></span>
- [<span data-ttu-id="0f096-181">启用 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0f096-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0f096-182">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="0f096-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0f096-183">了解架构</span><span class="sxs-lookup"><span data-stu-id="0f096-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0f096-184">Microsoft Defender for Endpoint 中的高级搜寻</span><span class="sxs-lookup"><span data-stu-id="0f096-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)