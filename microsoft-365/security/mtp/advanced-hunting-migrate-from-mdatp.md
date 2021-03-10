---
title: 从 Microsoft Defender for Endpoint 迁移高级搜寻查询
description: 了解如何调整适用于终结点的 Microsoft Defender 查询，以便可以在 Microsoft 365 Defender 中使用它们
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， microsoft 威胁防护， microsoft 365， mtp， m365， microsoft defender atp， mdatp， 搜索， 查询， 遥测， 自定义检测， 架构， kusto， microsoft 365， 映射
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
ms.openlocfilehash: 4d29f4f3df3d65ad72a19f059763523d7f7cba31
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50596990"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="bda7e-104">从 Microsoft Defender for Endpoint 迁移高级搜寻查询</span><span class="sxs-lookup"><span data-stu-id="bda7e-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bda7e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bda7e-105">**Applies to:**</span></span>
- <span data-ttu-id="bda7e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bda7e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bda7e-107">从 Microsoft Defender for Endpoint 移动高级搜寻工作流，以使用更广泛的一组数据主动搜寻威胁。</span><span class="sxs-lookup"><span data-stu-id="bda7e-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="bda7e-108">在 Microsoft 365 Defender 中，你可以访问其他 Microsoft 365 安全解决方案的数据，包括：</span><span class="sxs-lookup"><span data-stu-id="bda7e-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="bda7e-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bda7e-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="bda7e-110">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="bda7e-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="bda7e-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bda7e-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="bda7e-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="bda7e-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="bda7e-113">大多数 Microsoft Defender for Endpoint 客户可以使用 [Microsoft 365 Defender，而无需其他许可证](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="bda7e-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="bda7e-114">若要开始从 Defender for Endpoint 转换高级搜寻工作流，[请打开 Microsoft 365 Defender。](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="bda7e-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="bda7e-115">你可以转换，而不会影响现有的 Defender for Endpoint 工作流。</span><span class="sxs-lookup"><span data-stu-id="bda7e-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="bda7e-116">保存的查询保持不变，并且自定义检测规则将继续运行并生成警报。</span><span class="sxs-lookup"><span data-stu-id="bda7e-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="bda7e-117">但是，它们将在 Microsoft 365 Defender 中可见。</span><span class="sxs-lookup"><span data-stu-id="bda7e-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="bda7e-118">仅适用于 Microsoft 365 Defender 中的架构表</span><span class="sxs-lookup"><span data-stu-id="bda7e-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="bda7e-119">[Microsoft 365 Defender 高级搜寻架构](advanced-hunting-schema-tables.md)提供包含各种 Microsoft 365 安全解决方案数据的其他表。</span><span class="sxs-lookup"><span data-stu-id="bda7e-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="bda7e-120">下表仅适用于 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="bda7e-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="bda7e-121">表名</span><span class="sxs-lookup"><span data-stu-id="bda7e-121">Table name</span></span> | <span data-ttu-id="bda7e-122">说明</span><span class="sxs-lookup"><span data-stu-id="bda7e-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="bda7e-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="bda7e-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="bda7e-124">与警报关联的文件、IP 地址、URL、用户或设备</span><span class="sxs-lookup"><span data-stu-id="bda7e-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="bda7e-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="bda7e-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="bda7e-126">来自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的警报，包括严重性信息和威胁类别</span><span class="sxs-lookup"><span data-stu-id="bda7e-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="bda7e-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="bda7e-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="bda7e-128">云应用和服务中的文件相关活动</span><span class="sxs-lookup"><span data-stu-id="bda7e-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="bda7e-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="bda7e-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="bda7e-130">有关附加到电子邮件的文件的信息</span><span class="sxs-lookup"><span data-stu-id="bda7e-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="bda7e-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="bda7e-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="bda7e-132">Microsoft 365 电子邮件事件，包括电子邮件传递和阻止事件</span><span class="sxs-lookup"><span data-stu-id="bda7e-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="bda7e-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="bda7e-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="bda7e-134">在 Microsoft 365 将电子邮件传递到收件人邮箱后发生的安全事件</span><span class="sxs-lookup"><span data-stu-id="bda7e-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="bda7e-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="bda7e-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="bda7e-136">有关电子邮件 URL 的信息</span><span class="sxs-lookup"><span data-stu-id="bda7e-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="bda7e-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="bda7e-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="bda7e-138">涉及运行 Active Directory 本地域控制器的事件 (AD) 。</span><span class="sxs-lookup"><span data-stu-id="bda7e-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="bda7e-139">此表涵盖域控制器上与标识相关的一系列事件和系统事件。</span><span class="sxs-lookup"><span data-stu-id="bda7e-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="bda7e-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="bda7e-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="bda7e-141">来自各种源的帐户信息，包括 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bda7e-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="bda7e-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="bda7e-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="bda7e-143">Active Directory 和 Microsoft 在线服务上的身份验证事件</span><span class="sxs-lookup"><span data-stu-id="bda7e-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="bda7e-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="bda7e-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="bda7e-145">Active Directory 对象的查询，例如用户、组、设备和域</span><span class="sxs-lookup"><span data-stu-id="bda7e-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="bda7e-146">使用仅适用于 Microsoft 365 Defender 的架构表的查询和自定义检测只能在 Microsoft 365 Defender 中查看。</span><span class="sxs-lookup"><span data-stu-id="bda7e-146">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="bda7e-147">映射 DeviceAlertEvents 表</span><span class="sxs-lookup"><span data-stu-id="bda7e-147">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="bda7e-148">和 `AlertInfo` `AlertEvidence` 表将替换 `DeviceAlertEvents` Microsoft Defender for Endpoint 架构中的表。</span><span class="sxs-lookup"><span data-stu-id="bda7e-148">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="bda7e-149">除了有关设备警报的数据，这两个表还包括有关标识、应用和电子邮件警报的数据。</span><span class="sxs-lookup"><span data-stu-id="bda7e-149">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="bda7e-150">使用下表检查列 `DeviceAlertEvents` 如何映射到和表中的 `AlertInfo` `AlertEvidence` 列。</span><span class="sxs-lookup"><span data-stu-id="bda7e-150">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="bda7e-151">除了下表中的列之外，该表还包含许多其他列，这些列提供来自各种源的警报 `AlertEvidence` 的更全面图片。</span><span class="sxs-lookup"><span data-stu-id="bda7e-151">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="bda7e-152">查看所有 AlertEvidence 列</span><span class="sxs-lookup"><span data-stu-id="bda7e-152">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="bda7e-153">DeviceAlertEvents 列</span><span class="sxs-lookup"><span data-stu-id="bda7e-153">DeviceAlertEvents column</span></span> | <span data-ttu-id="bda7e-154">在哪里可以找到 Microsoft 365 Defender 中的相同数据</span><span class="sxs-lookup"><span data-stu-id="bda7e-154">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="bda7e-155">`AlertInfo` 和  `AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="bda7e-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="bda7e-156">`AlertInfo` 和  `AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="bda7e-156">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="bda7e-157">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="bda7e-157">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="bda7e-158">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="bda7e-158">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="bda7e-159">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="bda7e-159">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="bda7e-160">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="bda7e-160">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="bda7e-161">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="bda7e-161">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="bda7e-162">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="bda7e-162">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="bda7e-163">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="bda7e-163">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="bda7e-164">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="bda7e-164">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="bda7e-165">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="bda7e-165">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="bda7e-166">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="bda7e-166">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="bda7e-167">此列通常在 Microsoft Defender for Endpoint 中用于查找其他表中的相关记录。</span><span class="sxs-lookup"><span data-stu-id="bda7e-167">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="bda7e-168">在 Microsoft 365 Defender 中，你可以直接从表中获取 `AlertEvidence` 相关数据。</span><span class="sxs-lookup"><span data-stu-id="bda7e-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="bda7e-169">此列通常在 Microsoft Defender for Endpoint 中用于其他表中的其他事件信息。</span><span class="sxs-lookup"><span data-stu-id="bda7e-169">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="bda7e-170">在 Microsoft 365 Defender 中，你可以直接从表中获取 `AlertEvidence` 相关数据。</span><span class="sxs-lookup"><span data-stu-id="bda7e-170">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="bda7e-171">调整现有的 Microsoft Defender 终结点查询</span><span class="sxs-lookup"><span data-stu-id="bda7e-171">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="bda7e-172">Microsoft Defender for Endpoint 查询将像现在一样工作，除非它们引用 `DeviceAlertEvents` 该表。</span><span class="sxs-lookup"><span data-stu-id="bda7e-172">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="bda7e-173">若要在 Microsoft 365 Defender 中使用这些查询，请应用这些更改：</span><span class="sxs-lookup"><span data-stu-id="bda7e-173">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="bda7e-174">替换为 `DeviceAlertEvents` `AlertInfo` 。</span><span class="sxs-lookup"><span data-stu-id="bda7e-174">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="bda7e-175">将 `AlertInfo` 和表 `AlertEvidence` 联接在一起 `AlertId` 可获取等效数据。</span><span class="sxs-lookup"><span data-stu-id="bda7e-175">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="bda7e-176">原始查询</span><span class="sxs-lookup"><span data-stu-id="bda7e-176">Original query</span></span>
<span data-ttu-id="bda7e-177">以下查询在 `DeviceAlertEvents` Microsoft Defender for Endpoint 中用于获取涉及以下powershell.exe：</span><span class="sxs-lookup"><span data-stu-id="bda7e-177">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="bda7e-178">修改后的查询</span><span class="sxs-lookup"><span data-stu-id="bda7e-178">Modified query</span></span>
<span data-ttu-id="bda7e-179">以下查询已调整为在 Microsoft 365 Defender 中使用。</span><span class="sxs-lookup"><span data-stu-id="bda7e-179">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="bda7e-180">它联接并检查该表中的文件名，而不是直接从中 `DeviceAlertEvents` `AlertEvidence` 检查文件名。</span><span class="sxs-lookup"><span data-stu-id="bda7e-180">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="bda7e-181">迁移自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="bda7e-181">Migrate custom detection rules</span></span>

<span data-ttu-id="bda7e-182">在 Microsoft 365 Defender 上编辑 Microsoft Defender for Endpoint 规则时，它们继续像以前一样运行，因为生成的查询仅查看设备表。</span><span class="sxs-lookup"><span data-stu-id="bda7e-182">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="bda7e-183">例如，由仅查询设备表的自定义检测规则生成的警报将继续传递到 SIEM 并生成电子邮件通知，具体取决于你在 Microsoft Defender for Endpoint 中配置这些警报的方式。</span><span class="sxs-lookup"><span data-stu-id="bda7e-183">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bda7e-184">Defender for Endpoint 中的任何现有抑制规则也将继续适用。</span><span class="sxs-lookup"><span data-stu-id="bda7e-184">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="bda7e-185">编辑 Defender for Endpoint 规则以便查询仅在 Microsoft 365 Defender 中可用的标识和电子邮件表后，该规则将自动移动到 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="bda7e-185">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="bda7e-186">由迁移的规则生成的警报：</span><span class="sxs-lookup"><span data-stu-id="bda7e-186">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="bda7e-187">在 Microsoft Defender 安全中心 (Defender for Endpoint 门户中不再) </span><span class="sxs-lookup"><span data-stu-id="bda7e-187">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="bda7e-188">停止传递到 SIEM 或生成电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="bda7e-188">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="bda7e-189">若要处理此更改，请通过 Microsoft 365 Defender 配置通知，获取警报。</span><span class="sxs-lookup"><span data-stu-id="bda7e-189">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="bda7e-190">可以使用 Microsoft [365 Defender API](api-incident.md) 接收客户检测警报或相关事件的通知。</span><span class="sxs-lookup"><span data-stu-id="bda7e-190">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="bda7e-191">Microsoft Defender 对于终结点抑制规则不会禁止。</span><span class="sxs-lookup"><span data-stu-id="bda7e-191">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="bda7e-192">若要阻止为特定用户、设备或邮箱生成警报，请修改相应的查询以明确排除这些实体。</span><span class="sxs-lookup"><span data-stu-id="bda7e-192">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="bda7e-193">如果这样编辑规则，则系统会提示你在应用此类更改之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="bda7e-193">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="bda7e-194">Microsoft 365 Defender 门户中的自定义检测规则生成的新警报显示在提供以下信息的警报页面中：</span><span class="sxs-lookup"><span data-stu-id="bda7e-194">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="bda7e-195">警报标题和说明</span><span class="sxs-lookup"><span data-stu-id="bda7e-195">Alert title and description</span></span> 
- <span data-ttu-id="bda7e-196">影响的资产</span><span class="sxs-lookup"><span data-stu-id="bda7e-196">Impacted assets</span></span>
- <span data-ttu-id="bda7e-197">为响应警报而采取的操作</span><span class="sxs-lookup"><span data-stu-id="bda7e-197">Actions taken in response to the alert</span></span>
- <span data-ttu-id="bda7e-198">触发警报的查询结果</span><span class="sxs-lookup"><span data-stu-id="bda7e-198">Query results that triggered the alert</span></span> 
- <span data-ttu-id="bda7e-199">有关自定义检测规则的信息</span><span class="sxs-lookup"><span data-stu-id="bda7e-199">Information on the custom detection rule</span></span> 
 
![新警报页面的图像](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="bda7e-201">编写不含 DeviceAlertEvents 的查询</span><span class="sxs-lookup"><span data-stu-id="bda7e-201">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="bda7e-202">在 Microsoft 365 Defender 架构中，提供和表以适应各种来源的警报附带的 `AlertInfo` `AlertEvidence` 各种信息集。</span><span class="sxs-lookup"><span data-stu-id="bda7e-202">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="bda7e-203">若要获取用于从 Microsoft Defender for Endpoint 架构中的表获取的相同警报信息，请筛选该表，然后将每个唯一 ID 与表联接，该表提供详细的事件和 `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` 实体信息。</span><span class="sxs-lookup"><span data-stu-id="bda7e-203">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="bda7e-204">请参阅下面的示例查询：</span><span class="sxs-lookup"><span data-stu-id="bda7e-204">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="bda7e-205">此查询产生列数多于 `DeviceAlertEvents` Microsoft Defender for Endpoint 架构中的列数。</span><span class="sxs-lookup"><span data-stu-id="bda7e-205">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="bda7e-206">若要使结果可管理，请使用 `project` 仅获取感兴趣的列。</span><span class="sxs-lookup"><span data-stu-id="bda7e-206">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="bda7e-207">下面的示例列出了调查检测到 PowerShell 活动时您可能感兴趣的列：</span><span class="sxs-lookup"><span data-stu-id="bda7e-207">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="bda7e-208">如果要筛选警报中涉及的特定实体，可以通过指定要筛选的实体类型和值 `EntityType` 来这样做。</span><span class="sxs-lookup"><span data-stu-id="bda7e-208">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="bda7e-209">以下示例查找特定的 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="bda7e-209">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="bda7e-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bda7e-210">See also</span></span>
- [<span data-ttu-id="bda7e-211">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bda7e-211">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bda7e-212">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="bda7e-212">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bda7e-213">了解架构</span><span class="sxs-lookup"><span data-stu-id="bda7e-213">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bda7e-214">Microsoft Defender for Endpoint 中的高级搜寻</span><span class="sxs-lookup"><span data-stu-id="bda7e-214">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)