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
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080732"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="9995f-104">从 Microsoft Defender for Endpoint 迁移高级搜寻查询</span><span class="sxs-lookup"><span data-stu-id="9995f-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9995f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9995f-105">**Applies to:**</span></span>
- <span data-ttu-id="9995f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9995f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9995f-107">从 Microsoft Defender for Endpoint 移动高级搜寻工作流，以使用更广泛的数据集主动搜寻威胁。</span><span class="sxs-lookup"><span data-stu-id="9995f-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="9995f-108">在 Microsoft 365 Defender 中，你可以访问来自其他 Microsoft 365 安全解决方案的数据，包括：</span><span class="sxs-lookup"><span data-stu-id="9995f-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="9995f-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9995f-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="9995f-110">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="9995f-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="9995f-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9995f-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="9995f-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="9995f-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="9995f-113">大多数适用于终结点的 Microsoft Defender 客户可以使用 [Microsoft 365 Defender，而无需其他许可证](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="9995f-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="9995f-114">若要开始从 Defender for Endpoint 转换高级搜寻工作流，[请打开 Microsoft 365 Defender。](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="9995f-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="9995f-115">你可以转换，而不会影响现有的 Defender for Endpoint 工作流。</span><span class="sxs-lookup"><span data-stu-id="9995f-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="9995f-116">保存的查询保持不变，并且自定义检测规则将继续运行并生成警报。</span><span class="sxs-lookup"><span data-stu-id="9995f-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="9995f-117">但是，它们将在 Microsoft 365 Defender 中可见。</span><span class="sxs-lookup"><span data-stu-id="9995f-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="9995f-118">仅适用于 Microsoft 365 Defender 中的架构表</span><span class="sxs-lookup"><span data-stu-id="9995f-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="9995f-119">[Microsoft 365 Defender 高级搜寻架构](advanced-hunting-schema-tables.md)提供包含各种 Microsoft 365 安全解决方案数据的其他表。</span><span class="sxs-lookup"><span data-stu-id="9995f-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="9995f-120">下表仅适用于 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="9995f-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="9995f-121">表名</span><span class="sxs-lookup"><span data-stu-id="9995f-121">Table name</span></span> | <span data-ttu-id="9995f-122">说明</span><span class="sxs-lookup"><span data-stu-id="9995f-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="9995f-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="9995f-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="9995f-124">与警报关联的文件、IP 地址、URL、用户或设备</span><span class="sxs-lookup"><span data-stu-id="9995f-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="9995f-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="9995f-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="9995f-126">来自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的警报，包括严重性信息和威胁类别</span><span class="sxs-lookup"><span data-stu-id="9995f-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="9995f-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="9995f-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="9995f-128">云应用和服务中的文件相关活动</span><span class="sxs-lookup"><span data-stu-id="9995f-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="9995f-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="9995f-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="9995f-130">有关附加到电子邮件的文件的信息</span><span class="sxs-lookup"><span data-stu-id="9995f-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="9995f-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="9995f-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="9995f-132">Microsoft 365 电子邮件事件，包括电子邮件传递和阻止事件</span><span class="sxs-lookup"><span data-stu-id="9995f-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="9995f-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="9995f-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="9995f-134">在 Microsoft 365 将电子邮件传递到收件人邮箱后发生的安全事件</span><span class="sxs-lookup"><span data-stu-id="9995f-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="9995f-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="9995f-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="9995f-136">有关电子邮件 URL 的信息</span><span class="sxs-lookup"><span data-stu-id="9995f-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="9995f-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="9995f-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="9995f-138">涉及运行 Active Directory 本地域控制器的事件 (AD) 。</span><span class="sxs-lookup"><span data-stu-id="9995f-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="9995f-139">此表涵盖域控制器上与标识相关的一系列事件和系统事件。</span><span class="sxs-lookup"><span data-stu-id="9995f-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="9995f-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="9995f-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="9995f-141">来自各种源的帐户信息，包括 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9995f-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="9995f-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="9995f-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="9995f-143">Active Directory 和 Microsoft 联机服务上的身份验证事件</span><span class="sxs-lookup"><span data-stu-id="9995f-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="9995f-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="9995f-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="9995f-145">对 Active Directory 对象（如用户、组、设备和域）的查询</span><span class="sxs-lookup"><span data-stu-id="9995f-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="9995f-146">映射 DeviceAlertEvents 表</span><span class="sxs-lookup"><span data-stu-id="9995f-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="9995f-147">和 `AlertInfo` `AlertEvidence` 表替换了 `DeviceAlertEvents` Microsoft Defender for Endpoint 架构中的表。</span><span class="sxs-lookup"><span data-stu-id="9995f-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="9995f-148">除了有关设备警报的数据，这两个表还包括有关标识、应用和电子邮件警报的数据。</span><span class="sxs-lookup"><span data-stu-id="9995f-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="9995f-149">使用下表检查列 `DeviceAlertEvents` 如何映射到和表中的 `AlertInfo` `AlertEvidence` 列。</span><span class="sxs-lookup"><span data-stu-id="9995f-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="9995f-150">除了下表中的列之外，该表还包含许多其他列，这些列提供来自各种源的警报的更全面的 `AlertEvidence` 图片。</span><span class="sxs-lookup"><span data-stu-id="9995f-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="9995f-151">查看所有 AlertEvidence 列</span><span class="sxs-lookup"><span data-stu-id="9995f-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="9995f-152">DeviceAlertEvents 列</span><span class="sxs-lookup"><span data-stu-id="9995f-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="9995f-153">在哪里可以找到 Microsoft 365 Defender 中的相同数据</span><span class="sxs-lookup"><span data-stu-id="9995f-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="9995f-154">`AlertInfo` 和  `AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="9995f-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="9995f-155">`AlertInfo` 和  `AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="9995f-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="9995f-156">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9995f-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="9995f-157">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9995f-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="9995f-158">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9995f-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="9995f-159">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9995f-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="9995f-160">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9995f-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="9995f-161">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9995f-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="9995f-162">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9995f-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="9995f-163">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9995f-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="9995f-164">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9995f-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="9995f-165">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9995f-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="9995f-166">此列通常在 Microsoft Defender for Endpoint 中用于查找其他表中的相关记录。</span><span class="sxs-lookup"><span data-stu-id="9995f-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="9995f-167">在 Microsoft 365 Defender 中，你可以直接从表中获取 `AlertEvidence` 相关数据。</span><span class="sxs-lookup"><span data-stu-id="9995f-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="9995f-168">此列通常在 Microsoft Defender for Endpoint 中用于其他表中的其他事件信息。</span><span class="sxs-lookup"><span data-stu-id="9995f-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="9995f-169">在 Microsoft 365 Defender 中，你可以直接从表中获取 `AlertEvidence` 相关数据。</span><span class="sxs-lookup"><span data-stu-id="9995f-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="9995f-170">调整现有的 Microsoft Defender 终结点查询</span><span class="sxs-lookup"><span data-stu-id="9995f-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="9995f-171">Microsoft Defender for Endpoint 查询将正常工作，除非它们引用 `DeviceAlertEvents` 该表。</span><span class="sxs-lookup"><span data-stu-id="9995f-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="9995f-172">若要在 Microsoft 365 Defender 中使用这些查询，请应用这些更改：</span><span class="sxs-lookup"><span data-stu-id="9995f-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="9995f-173">替换为 `DeviceAlertEvents` `AlertInfo` 。</span><span class="sxs-lookup"><span data-stu-id="9995f-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="9995f-174">将 `AlertInfo` 和表 `AlertEvidence` 联接在一起 `AlertId` 可获取等效数据。</span><span class="sxs-lookup"><span data-stu-id="9995f-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="9995f-175">原始查询</span><span class="sxs-lookup"><span data-stu-id="9995f-175">Original query</span></span>
<span data-ttu-id="9995f-176">以下查询在 `DeviceAlertEvents` Microsoft Defender for Endpoint 中用于获取涉及以下powershell.exe：</span><span class="sxs-lookup"><span data-stu-id="9995f-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="9995f-177">修改后的查询</span><span class="sxs-lookup"><span data-stu-id="9995f-177">Modified query</span></span>
<span data-ttu-id="9995f-178">以下查询已调整为在 Microsoft 365 Defender 中使用。</span><span class="sxs-lookup"><span data-stu-id="9995f-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="9995f-179">它联接并检查该表中的文件名，而不是直接 `DeviceAlertEvents` `AlertEvidence` 检查文件名。</span><span class="sxs-lookup"><span data-stu-id="9995f-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="9995f-180">迁移自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="9995f-180">Migrate custom detection rules</span></span>

<span data-ttu-id="9995f-181">在 Microsoft 365 Defender 上编辑 Microsoft Defender for Endpoint 规则时，它们将继续像以前一样运行，就像生成的查询仅查看设备表一样。</span><span class="sxs-lookup"><span data-stu-id="9995f-181">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> <span data-ttu-id="9995f-182">例如，由仅查询设备表的自定义检测规则生成的警报将继续传递到 SIEM 并生成电子邮件通知，具体取决于你在 Microsoft Defender for Endpoint 中配置它们的方式。</span><span class="sxs-lookup"><span data-stu-id="9995f-182">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9995f-183">Defender for Endpoint 中的任何现有抑制规则也将继续适用。</span><span class="sxs-lookup"><span data-stu-id="9995f-183">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="9995f-184">编辑 Defender for Endpoint 规则以便查询仅在 Microsoft 365 Defender 中可用的标识和电子邮件表后，该规则将自动移动到 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="9995f-184">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="9995f-185">由迁移的规则生成的警报：</span><span class="sxs-lookup"><span data-stu-id="9995f-185">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="9995f-186">在 Microsoft Defender 安全中心 (Defender for Endpoint 门户中不再) </span><span class="sxs-lookup"><span data-stu-id="9995f-186">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="9995f-187">停止传递到 SIEM 或生成电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="9995f-187">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="9995f-188">若要解决此更改，请通过 Microsoft 365 Defender 配置通知，获取警报。</span><span class="sxs-lookup"><span data-stu-id="9995f-188">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="9995f-189">可以使用 Microsoft [365 Defender API](api-incident.md) 接收客户检测警报或相关事件的通知。</span><span class="sxs-lookup"><span data-stu-id="9995f-189">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="9995f-190">Microsoft Defender 不会针对终结点抑制规则进行抑制。</span><span class="sxs-lookup"><span data-stu-id="9995f-190">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="9995f-191">若要阻止为某些用户、设备或邮箱生成警报，请修改相应的查询以明确排除这些实体。</span><span class="sxs-lookup"><span data-stu-id="9995f-191">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="9995f-192">如果通过此方式编辑规则，将在应用此类更改之前提示您进行确认。</span><span class="sxs-lookup"><span data-stu-id="9995f-192">If you do edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="9995f-193">Microsoft 365 Defender 门户中的自定义检测规则生成的新警报显示在提供以下信息的警报页面中：</span><span class="sxs-lookup"><span data-stu-id="9995f-193">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="9995f-194">警报标题和说明</span><span class="sxs-lookup"><span data-stu-id="9995f-194">Alert title and description</span></span> 
- <span data-ttu-id="9995f-195">受影响的资产</span><span class="sxs-lookup"><span data-stu-id="9995f-195">Impacted assets</span></span>
- <span data-ttu-id="9995f-196">为响应警报而采取的操作</span><span class="sxs-lookup"><span data-stu-id="9995f-196">Actions taken in response to the alert</span></span>
- <span data-ttu-id="9995f-197">触发警报的查询结果</span><span class="sxs-lookup"><span data-stu-id="9995f-197">Query results that triggered the alert</span></span> 
- <span data-ttu-id="9995f-198">有关自定义检测规则的信息</span><span class="sxs-lookup"><span data-stu-id="9995f-198">Information on the custom detection rule</span></span> 
 
![新警报页面的图像](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="9995f-200">编写不含 DeviceAlertEvents 的查询</span><span class="sxs-lookup"><span data-stu-id="9995f-200">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="9995f-201">在 Microsoft 365 Defender 架构中，提供和表以适应各种来源的警报附带的 `AlertInfo` `AlertEvidence` 一组不同信息。</span><span class="sxs-lookup"><span data-stu-id="9995f-201">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="9995f-202">若要获取用于从 Microsoft Defender for Endpoint 架构中的表获取的相同警报信息，请筛选该表，然后将每个唯一 ID 与表联接，该表提供详细的事件和 `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` 实体信息。</span><span class="sxs-lookup"><span data-stu-id="9995f-202">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="9995f-203">请参阅下面的示例查询：</span><span class="sxs-lookup"><span data-stu-id="9995f-203">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="9995f-204">此查询产生列数多于 `DeviceAlertEvents` Microsoft Defender for Endpoint 架构中的列数。</span><span class="sxs-lookup"><span data-stu-id="9995f-204">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="9995f-205">若要使结果易于管理，请使用 `project` 仅获取感兴趣的列。</span><span class="sxs-lookup"><span data-stu-id="9995f-205">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="9995f-206">下面的示例对调查检测到 PowerShell 活动时您可能感兴趣的列进行规划：</span><span class="sxs-lookup"><span data-stu-id="9995f-206">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="9995f-207">如果要筛选警报中涉及的特定实体，可以通过指定要筛选的实体类型和值 `EntityType` 来这样做。</span><span class="sxs-lookup"><span data-stu-id="9995f-207">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="9995f-208">以下示例查找特定的 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="9995f-208">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="9995f-209">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9995f-209">See also</span></span>
- [<span data-ttu-id="9995f-210">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9995f-210">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9995f-211">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="9995f-211">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9995f-212">了解架构</span><span class="sxs-lookup"><span data-stu-id="9995f-212">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9995f-213">Microsoft Defender for Endpoint 中的高级搜寻</span><span class="sxs-lookup"><span data-stu-id="9995f-213">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)