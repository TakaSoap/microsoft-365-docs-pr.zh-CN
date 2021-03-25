---
title: 获取警报 API
description: 了解 Microsoft Defender for Endpoint 中警报资源类型的方法和属性。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4997d7118b139d993ed94ed917137ca107940e46
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199617"
---
# <a name="alert-resource-type"></a><span data-ttu-id="0de77-104">警报资源类型</span><span class="sxs-lookup"><span data-stu-id="0de77-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0de77-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0de77-105">**Applies to:**</span></span>
- [<span data-ttu-id="0de77-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0de77-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="0de77-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="0de77-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0de77-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="0de77-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="0de77-109">方法</span><span class="sxs-lookup"><span data-stu-id="0de77-109">Methods</span></span>

<span data-ttu-id="0de77-110">方法</span><span class="sxs-lookup"><span data-stu-id="0de77-110">Method</span></span> |<span data-ttu-id="0de77-111">返回类型</span><span class="sxs-lookup"><span data-stu-id="0de77-111">Return Type</span></span> |<span data-ttu-id="0de77-112">说明</span><span class="sxs-lookup"><span data-stu-id="0de77-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="0de77-113">获取警报</span><span class="sxs-lookup"><span data-stu-id="0de77-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="0de77-114">Alert</span><span class="sxs-lookup"><span data-stu-id="0de77-114">Alert</span></span>](alerts.md) | <span data-ttu-id="0de77-115">获取单个 [alert](alerts.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="0de77-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="0de77-116">列出警报</span><span class="sxs-lookup"><span data-stu-id="0de77-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="0de77-117">[警报](alerts.md) 集合</span><span class="sxs-lookup"><span data-stu-id="0de77-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="0de77-118">列出 [警报](alerts.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="0de77-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="0de77-119">更新警报</span><span class="sxs-lookup"><span data-stu-id="0de77-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="0de77-120">Alert</span><span class="sxs-lookup"><span data-stu-id="0de77-120">Alert</span></span>](alerts.md) | <span data-ttu-id="0de77-121">更新特定 [警报](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="0de77-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="0de77-122">批更新通知</span><span class="sxs-lookup"><span data-stu-id="0de77-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="0de77-123">更新一批 [警报](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="0de77-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="0de77-124">创建警报</span><span class="sxs-lookup"><span data-stu-id="0de77-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="0de77-125">Alert</span><span class="sxs-lookup"><span data-stu-id="0de77-125">Alert</span></span>](alerts.md)|<span data-ttu-id="0de77-126">根据从高级搜寻 获取的事件数据 [创建警报](run-advanced-query-api.md)。</span><span class="sxs-lookup"><span data-stu-id="0de77-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="0de77-127">列出相关域</span><span class="sxs-lookup"><span data-stu-id="0de77-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="0de77-128">域集合</span><span class="sxs-lookup"><span data-stu-id="0de77-128">Domain collection</span></span>| <span data-ttu-id="0de77-129">列出与警报关联的 URL。</span><span class="sxs-lookup"><span data-stu-id="0de77-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="0de77-130">列出相关文件</span><span class="sxs-lookup"><span data-stu-id="0de77-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="0de77-131">[文件](files.md) 集合</span><span class="sxs-lookup"><span data-stu-id="0de77-131">[File](files.md) collection</span></span> |  <span data-ttu-id="0de77-132">列出 [与](files.md) 警报关联的文件 [实体](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="0de77-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="0de77-133">列出相关 IP</span><span class="sxs-lookup"><span data-stu-id="0de77-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="0de77-134">IP 集合</span><span class="sxs-lookup"><span data-stu-id="0de77-134">IP collection</span></span> | <span data-ttu-id="0de77-135">列出与警报关联的 IP。</span><span class="sxs-lookup"><span data-stu-id="0de77-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="0de77-136">获取相关计算机</span><span class="sxs-lookup"><span data-stu-id="0de77-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="0de77-137">计算机</span><span class="sxs-lookup"><span data-stu-id="0de77-137">Machine</span></span>](machine.md) | <span data-ttu-id="0de77-138">[与](machine.md)警报关联的[计算机](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="0de77-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="0de77-139">获取相关用户</span><span class="sxs-lookup"><span data-stu-id="0de77-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="0de77-140">用户</span><span class="sxs-lookup"><span data-stu-id="0de77-140">User</span></span>](user.md) | <span data-ttu-id="0de77-141">[与](user.md)警报关联的[用户](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="0de77-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>


## <a name="properties"></a><span data-ttu-id="0de77-142">属性</span><span class="sxs-lookup"><span data-stu-id="0de77-142">Properties</span></span>

<span data-ttu-id="0de77-143">属性</span><span class="sxs-lookup"><span data-stu-id="0de77-143">Property</span></span> |    <span data-ttu-id="0de77-144">类型</span><span class="sxs-lookup"><span data-stu-id="0de77-144">Type</span></span>    |    <span data-ttu-id="0de77-145">说明</span><span class="sxs-lookup"><span data-stu-id="0de77-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="0de77-146">id</span><span class="sxs-lookup"><span data-stu-id="0de77-146">id</span></span> | <span data-ttu-id="0de77-147">字符串</span><span class="sxs-lookup"><span data-stu-id="0de77-147">String</span></span> | <span data-ttu-id="0de77-148">警报 ID。</span><span class="sxs-lookup"><span data-stu-id="0de77-148">Alert ID.</span></span>
<span data-ttu-id="0de77-149">title</span><span class="sxs-lookup"><span data-stu-id="0de77-149">title</span></span> | <span data-ttu-id="0de77-150">String</span><span class="sxs-lookup"><span data-stu-id="0de77-150">String</span></span> | <span data-ttu-id="0de77-151">警报标题。</span><span class="sxs-lookup"><span data-stu-id="0de77-151">Alert title.</span></span>
<span data-ttu-id="0de77-152">说明</span><span class="sxs-lookup"><span data-stu-id="0de77-152">description</span></span> | <span data-ttu-id="0de77-153">String</span><span class="sxs-lookup"><span data-stu-id="0de77-153">String</span></span> | <span data-ttu-id="0de77-154">警报说明。</span><span class="sxs-lookup"><span data-stu-id="0de77-154">Alert description.</span></span>
<span data-ttu-id="0de77-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="0de77-155">alertCreationTime</span></span> | <span data-ttu-id="0de77-156">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0de77-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="0de77-157">创建警报时 (UTC) 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0de77-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="0de77-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="0de77-158">lastEventTime</span></span> | <span data-ttu-id="0de77-159">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0de77-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="0de77-160">在同一设备上触发警报的事件的最后一次发生次数。</span><span class="sxs-lookup"><span data-stu-id="0de77-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="0de77-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="0de77-161">firstEventTime</span></span> | <span data-ttu-id="0de77-162">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0de77-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="0de77-163">在该设备上触发警报的事件的第一次发生。</span><span class="sxs-lookup"><span data-stu-id="0de77-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="0de77-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="0de77-164">lastUpdateTime</span></span> | <span data-ttu-id="0de77-165">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0de77-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="0de77-166">上次更新警报 (UTC) 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0de77-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="0de77-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="0de77-167">resolvedTime</span></span> | <span data-ttu-id="0de77-168">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0de77-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="0de77-169">警报状态更改为"已解决"的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0de77-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="0de77-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="0de77-170">incidentId</span></span> | <span data-ttu-id="0de77-171">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="0de77-171">Nullable Long</span></span> | <span data-ttu-id="0de77-172">[警报](view-incidents-queue.md)的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="0de77-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="0de77-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="0de77-173">investigationId</span></span> | <span data-ttu-id="0de77-174">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="0de77-174">Nullable Long</span></span> | <span data-ttu-id="0de77-175">与 [警报](automated-investigations.md) 相关的调查 ID。</span><span class="sxs-lookup"><span data-stu-id="0de77-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="0de77-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="0de77-176">investigationState</span></span> | <span data-ttu-id="0de77-177">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="0de77-177">Nullable Enum</span></span> | <span data-ttu-id="0de77-178">调查 的当前 [状态](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="0de77-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="0de77-179">可能的值包括："Unknown"、"Terminated"、 "SuccessfullyRemediated"、"Benign"、"Failed"、"PartiallyRemediated"、"Running"、"PendingApproval"、"PendingResource"、"PartiallyInvestigated"、"TerminatedByUser"、"TerminatedBySystem"、"Queued"、"InnerFailure"、"PreexistingAlert"、"UnsupportedOs"、"UnsupportedAlertType"和"SuppressedAlert"。</span><span class="sxs-lookup"><span data-stu-id="0de77-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="0de77-180">assignedTo</span><span class="sxs-lookup"><span data-stu-id="0de77-180">assignedTo</span></span> | <span data-ttu-id="0de77-181">String</span><span class="sxs-lookup"><span data-stu-id="0de77-181">String</span></span> | <span data-ttu-id="0de77-182">警报的所有者。</span><span class="sxs-lookup"><span data-stu-id="0de77-182">Owner of the alert.</span></span>
<span data-ttu-id="0de77-183">severity</span><span class="sxs-lookup"><span data-stu-id="0de77-183">severity</span></span> | <span data-ttu-id="0de77-184">枚举</span><span class="sxs-lookup"><span data-stu-id="0de77-184">Enum</span></span> | <span data-ttu-id="0de77-185">警报的严重性。</span><span class="sxs-lookup"><span data-stu-id="0de77-185">Severity of the alert.</span></span> <span data-ttu-id="0de77-186">可能的值包括："UnSpecified"、"Informational"、"Low"、"Medium"和"High"。</span><span class="sxs-lookup"><span data-stu-id="0de77-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="0de77-187">状态</span><span class="sxs-lookup"><span data-stu-id="0de77-187">status</span></span> | <span data-ttu-id="0de77-188">枚举</span><span class="sxs-lookup"><span data-stu-id="0de77-188">Enum</span></span> | <span data-ttu-id="0de77-189">指定警报的当前状态。</span><span class="sxs-lookup"><span data-stu-id="0de77-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="0de77-190">可能的值是："Unknown"、"New"、"InProgress"和"Resolved"。</span><span class="sxs-lookup"><span data-stu-id="0de77-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="0de77-191">classification</span><span class="sxs-lookup"><span data-stu-id="0de77-191">classification</span></span> | <span data-ttu-id="0de77-192">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="0de77-192">Nullable Enum</span></span> | <span data-ttu-id="0de77-193">警报的规范。</span><span class="sxs-lookup"><span data-stu-id="0de77-193">Specification of the alert.</span></span> <span data-ttu-id="0de77-194">可能的值是："Unknown"、"FalsePositive"、"TruePositive"。</span><span class="sxs-lookup"><span data-stu-id="0de77-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="0de77-195">确定</span><span class="sxs-lookup"><span data-stu-id="0de77-195">determination</span></span> | <span data-ttu-id="0de77-196">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="0de77-196">Nullable Enum</span></span> | <span data-ttu-id="0de77-197">指定警报的确定。</span><span class="sxs-lookup"><span data-stu-id="0de77-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="0de77-198">可能的值包括："NotAvailable"、"Apt"、"Malware"、SecurityPersonnel、"SecurityTesting"、"UnwantedSoftware"和"Other"。</span><span class="sxs-lookup"><span data-stu-id="0de77-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="0de77-199">“类别”</span><span class="sxs-lookup"><span data-stu-id="0de77-199">category</span></span>| <span data-ttu-id="0de77-200">字符串</span><span class="sxs-lookup"><span data-stu-id="0de77-200">String</span></span> | <span data-ttu-id="0de77-201">警报的类别。</span><span class="sxs-lookup"><span data-stu-id="0de77-201">Category of the alert.</span></span>
<span data-ttu-id="0de77-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="0de77-202">detectionSource</span></span> | <span data-ttu-id="0de77-203">字符串</span><span class="sxs-lookup"><span data-stu-id="0de77-203">String</span></span> | <span data-ttu-id="0de77-204">检测源。</span><span class="sxs-lookup"><span data-stu-id="0de77-204">Detection source.</span></span>
<span data-ttu-id="0de77-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="0de77-205">threatFamilyName</span></span> | <span data-ttu-id="0de77-206">字符串</span><span class="sxs-lookup"><span data-stu-id="0de77-206">String</span></span> | <span data-ttu-id="0de77-207">威胁系列。</span><span class="sxs-lookup"><span data-stu-id="0de77-207">Threat family.</span></span>
<span data-ttu-id="0de77-208">threatName</span><span class="sxs-lookup"><span data-stu-id="0de77-208">threatName</span></span> | <span data-ttu-id="0de77-209">字符串</span><span class="sxs-lookup"><span data-stu-id="0de77-209">String</span></span> | <span data-ttu-id="0de77-210">威胁名称。</span><span class="sxs-lookup"><span data-stu-id="0de77-210">Threat name.</span></span>
<span data-ttu-id="0de77-211">machineId</span><span class="sxs-lookup"><span data-stu-id="0de77-211">machineId</span></span> | <span data-ttu-id="0de77-212">字符串</span><span class="sxs-lookup"><span data-stu-id="0de77-212">String</span></span> | <span data-ttu-id="0de77-213">与 [警报关联的](machine.md) 计算机实体的 ID。</span><span class="sxs-lookup"><span data-stu-id="0de77-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="0de77-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="0de77-214">computerDnsName</span></span> | <span data-ttu-id="0de77-215">字符串</span><span class="sxs-lookup"><span data-stu-id="0de77-215">String</span></span> | <span data-ttu-id="0de77-216">[计算机](machine.md) 完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="0de77-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="0de77-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="0de77-217">aadTenantId</span></span> | <span data-ttu-id="0de77-218">字符串</span><span class="sxs-lookup"><span data-stu-id="0de77-218">String</span></span> | <span data-ttu-id="0de77-219">Azure Active Directory ID。</span><span class="sxs-lookup"><span data-stu-id="0de77-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="0de77-220">一个</span><span class="sxs-lookup"><span data-stu-id="0de77-220">detectorId</span></span> | <span data-ttu-id="0de77-221">字符串</span><span class="sxs-lookup"><span data-stu-id="0de77-221">String</span></span> | <span data-ttu-id="0de77-222">触发警报的检测器的 ID。</span><span class="sxs-lookup"><span data-stu-id="0de77-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="0de77-223">comments</span><span class="sxs-lookup"><span data-stu-id="0de77-223">comments</span></span> | <span data-ttu-id="0de77-224">警报注释列表</span><span class="sxs-lookup"><span data-stu-id="0de77-224">List of Alert comments</span></span> | <span data-ttu-id="0de77-225">Alert Comment 对象包含：注释字符串、createdBy 字符串和 createTime 日期时间。</span><span class="sxs-lookup"><span data-stu-id="0de77-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="0de77-226">证据</span><span class="sxs-lookup"><span data-stu-id="0de77-226">Evidence</span></span> | <span data-ttu-id="0de77-227">警报证据列表</span><span class="sxs-lookup"><span data-stu-id="0de77-227">List of Alert evidence</span></span> | <span data-ttu-id="0de77-228">与警报相关的证据。</span><span class="sxs-lookup"><span data-stu-id="0de77-228">Evidence related to the alert.</span></span> <span data-ttu-id="0de77-229">请参阅下面的示例。</span><span class="sxs-lookup"><span data-stu-id="0de77-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="0de77-230">获取单个警报的响应示例：</span><span class="sxs-lookup"><span data-stu-id="0de77-230">Response example for getting single alert:</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
