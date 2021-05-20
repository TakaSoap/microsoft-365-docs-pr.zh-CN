---
title: 在 defender 中列出Microsoft 365 API
description: 了解如何在 defender 中列出Microsoft 365 API
keywords: 列表， 事件， 事件， api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572149"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="9b732-104">在 defender 中列出Microsoft 365 API</span><span class="sxs-lookup"><span data-stu-id="9b732-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9b732-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9b732-105">**Applies to:**</span></span>

- <span data-ttu-id="9b732-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b732-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b732-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="9b732-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9b732-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="9b732-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="9b732-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="9b732-109">API description</span></span>

<span data-ttu-id="9b732-110">列表事件 API 允许你对事件进行排序，以创建明智的网络安全响应。</span><span class="sxs-lookup"><span data-stu-id="9b732-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="9b732-111">它公开在环境保留策略中指定的时间范围内网络中标记的事件集合。</span><span class="sxs-lookup"><span data-stu-id="9b732-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="9b732-112">最新事件显示在列表顶部。</span><span class="sxs-lookup"><span data-stu-id="9b732-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="9b732-113">每个事件都包含一组相关警报及其相关实体。</span><span class="sxs-lookup"><span data-stu-id="9b732-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="9b732-114">API 支持以下 **OData** 运算符：</span><span class="sxs-lookup"><span data-stu-id="9b732-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="9b732-115">`$filter` 在 `lastUpdateTime` 、 `createdTime` 、 和 `status` `assignedTo` 属性上</span><span class="sxs-lookup"><span data-stu-id="9b732-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="9b732-116">`$top`，最大值为 **100**</span><span class="sxs-lookup"><span data-stu-id="9b732-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="9b732-117">限制</span><span class="sxs-lookup"><span data-stu-id="9b732-117">Limitations</span></span>

1. <span data-ttu-id="9b732-118">最大页面大小为 **100 个事件**。</span><span class="sxs-lookup"><span data-stu-id="9b732-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="9b732-119">最大请求速率为每分钟 **50** 个呼叫和 **每小时 1500 个呼叫**。</span><span class="sxs-lookup"><span data-stu-id="9b732-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="9b732-120">权限</span><span class="sxs-lookup"><span data-stu-id="9b732-120">Permissions</span></span>

<span data-ttu-id="9b732-121">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="9b732-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9b732-122">若要了解更多信息（包括如何选择权限），请参阅[Access Microsoft 365 Defender API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="9b732-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="9b732-123">权限类型</span><span class="sxs-lookup"><span data-stu-id="9b732-123">Permission type</span></span> | <span data-ttu-id="9b732-124">权限</span><span class="sxs-lookup"><span data-stu-id="9b732-124">Permission</span></span> | <span data-ttu-id="9b732-125">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="9b732-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="9b732-126">应用程序</span><span class="sxs-lookup"><span data-stu-id="9b732-126">Application</span></span> | <span data-ttu-id="9b732-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="9b732-127">Incident.Read.All</span></span> | <span data-ttu-id="9b732-128">读取所有事件</span><span class="sxs-lookup"><span data-stu-id="9b732-128">Read all incidents</span></span>
<span data-ttu-id="9b732-129">应用程序</span><span class="sxs-lookup"><span data-stu-id="9b732-129">Application</span></span> | <span data-ttu-id="9b732-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9b732-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="9b732-131">读取和写入所有事件</span><span class="sxs-lookup"><span data-stu-id="9b732-131">Read and write all incidents</span></span>
<span data-ttu-id="9b732-132">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="9b732-132">Delegated (work or school account)</span></span> | <span data-ttu-id="9b732-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="9b732-133">Incident.Read</span></span> | <span data-ttu-id="9b732-134">读取事件</span><span class="sxs-lookup"><span data-stu-id="9b732-134">Read incidents</span></span>
<span data-ttu-id="9b732-135">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="9b732-135">Delegated (work or school account)</span></span> | <span data-ttu-id="9b732-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9b732-136">Incident.ReadWrite</span></span> | <span data-ttu-id="9b732-137">读取和写入事件</span><span class="sxs-lookup"><span data-stu-id="9b732-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="9b732-138">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="9b732-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="9b732-139">用户需要具有门户中事件的查看权限。</span><span class="sxs-lookup"><span data-stu-id="9b732-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="9b732-140">该响应将仅包括向用户公开的事件。</span><span class="sxs-lookup"><span data-stu-id="9b732-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="9b732-141">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="9b732-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="9b732-142">请求标头</span><span class="sxs-lookup"><span data-stu-id="9b732-142">Request headers</span></span>

<span data-ttu-id="9b732-143">名称</span><span class="sxs-lookup"><span data-stu-id="9b732-143">Name</span></span> | <span data-ttu-id="9b732-144">类型</span><span class="sxs-lookup"><span data-stu-id="9b732-144">Type</span></span> | <span data-ttu-id="9b732-145">说明</span><span class="sxs-lookup"><span data-stu-id="9b732-145">Description</span></span>
-|-|-
<span data-ttu-id="9b732-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="9b732-146">Authorization</span></span> | <span data-ttu-id="9b732-147">String</span><span class="sxs-lookup"><span data-stu-id="9b732-147">String</span></span> | <span data-ttu-id="9b732-148">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="9b732-148">Bearer {token}.</span></span> <span data-ttu-id="9b732-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="9b732-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="9b732-150">请求正文</span><span class="sxs-lookup"><span data-stu-id="9b732-150">Request body</span></span>

<span data-ttu-id="9b732-151">无。</span><span class="sxs-lookup"><span data-stu-id="9b732-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="9b732-152">响应</span><span class="sxs-lookup"><span data-stu-id="9b732-152">Response</span></span>

<span data-ttu-id="9b732-153">如果成功，此方法在响应正文中返回 和 `200 OK` 事件列表。 [](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="9b732-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="9b732-154">架构映射</span><span class="sxs-lookup"><span data-stu-id="9b732-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="9b732-155">事件元数据</span><span class="sxs-lookup"><span data-stu-id="9b732-155">Incident metadata</span></span>

<span data-ttu-id="9b732-156">字段名</span><span class="sxs-lookup"><span data-stu-id="9b732-156">Field name</span></span> | <span data-ttu-id="9b732-157">说明</span><span class="sxs-lookup"><span data-stu-id="9b732-157">Description</span></span> | <span data-ttu-id="9b732-158">示例值</span><span class="sxs-lookup"><span data-stu-id="9b732-158">Example value</span></span>
-|-|-
<span data-ttu-id="9b732-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="9b732-159">incidentId</span></span> | <span data-ttu-id="9b732-160">表示事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="9b732-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="9b732-161">924565</span><span class="sxs-lookup"><span data-stu-id="9b732-161">924565</span></span>
<span data-ttu-id="9b732-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="9b732-162">redirectIncidentId</span></span> | <span data-ttu-id="9b732-163">只有在将事件与另一个事件分组在一起时填充，作为事件处理逻辑的一部分。</span><span class="sxs-lookup"><span data-stu-id="9b732-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="9b732-164">924569</span><span class="sxs-lookup"><span data-stu-id="9b732-164">924569</span></span>
<span data-ttu-id="9b732-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="9b732-165">incidentName</span></span> | <span data-ttu-id="9b732-166">可用于每个事件的字符串值。</span><span class="sxs-lookup"><span data-stu-id="9b732-166">String value available for every incident.</span></span> | <span data-ttu-id="9b732-167">勒索软件活动</span><span class="sxs-lookup"><span data-stu-id="9b732-167">Ransomware activity</span></span>
<span data-ttu-id="9b732-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="9b732-168">createdTime</span></span> | <span data-ttu-id="9b732-169">第一次创建事件的时间。</span><span class="sxs-lookup"><span data-stu-id="9b732-169">Time when incident was first created.</span></span> | <span data-ttu-id="9b732-170">2020-09-06T14：46：57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="9b732-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="9b732-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="9b732-171">lastUpdateTime</span></span> | <span data-ttu-id="9b732-172">上次在后端更新事件的时间。</span><span class="sxs-lookup"><span data-stu-id="9b732-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="9b732-173">为检索事件的时间范围设置请求参数时，可以使用此字段。</span><span class="sxs-lookup"><span data-stu-id="9b732-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="9b732-174">2020-09-06T14：46：57.29Z</span><span class="sxs-lookup"><span data-stu-id="9b732-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="9b732-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="9b732-175">assignedTo</span></span> | <span data-ttu-id="9b732-176">事件的所有者;如果没有分配 *所有者* ，则为空。</span><span class="sxs-lookup"><span data-stu-id="9b732-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="9b732-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b732-177">secop2@contoso.com</span></span>
<span data-ttu-id="9b732-178">classification</span><span class="sxs-lookup"><span data-stu-id="9b732-178">classification</span></span> | <span data-ttu-id="9b732-179">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="9b732-179">The specification for the incident.</span></span> <span data-ttu-id="9b732-180">属性值为 *：Unknown、FalsePositive、TruePositive*  </span><span class="sxs-lookup"><span data-stu-id="9b732-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="9b732-181">未知</span><span class="sxs-lookup"><span data-stu-id="9b732-181">Unknown</span></span>
<span data-ttu-id="9b732-182">确定</span><span class="sxs-lookup"><span data-stu-id="9b732-182">determination</span></span> | <span data-ttu-id="9b732-183">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="9b732-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="9b732-184">属性值包括：NotAvailable、Apt、Malware、SecurityPersonnel、SecurityTesting、UnwantedSoftware、Other       </span><span class="sxs-lookup"><span data-stu-id="9b732-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="9b732-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="9b732-185">NotAvailable</span></span>
<span data-ttu-id="9b732-186">状态</span><span class="sxs-lookup"><span data-stu-id="9b732-186">status</span></span> | <span data-ttu-id="9b732-187">将事件分类 (*活动"* 或"已解决 *) "*</span><span class="sxs-lookup"><span data-stu-id="9b732-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="9b732-188">它可以帮助您组织和管理对事件的响应。</span><span class="sxs-lookup"><span data-stu-id="9b732-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="9b732-189">活动</span><span class="sxs-lookup"><span data-stu-id="9b732-189">Active</span></span>
<span data-ttu-id="9b732-190">severity</span><span class="sxs-lookup"><span data-stu-id="9b732-190">severity</span></span> | <span data-ttu-id="9b732-191">指示对资产可能的影响。</span><span class="sxs-lookup"><span data-stu-id="9b732-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="9b732-192">严重性越高，影响越大。</span><span class="sxs-lookup"><span data-stu-id="9b732-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="9b732-193">通常，严重性级别较高的项目需要最直接的关注。</span><span class="sxs-lookup"><span data-stu-id="9b732-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="9b732-194">下列值之一 *：Informational、Low、*Medium\* 和 *High。* </span><span class="sxs-lookup"><span data-stu-id="9b732-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="9b732-195">中</span><span class="sxs-lookup"><span data-stu-id="9b732-195">Medium</span></span>
<span data-ttu-id="9b732-196">tags</span><span class="sxs-lookup"><span data-stu-id="9b732-196">tags</span></span> | <span data-ttu-id="9b732-197">与事件关联的自定义标记数组，例如，用于标记一组具有共同特征的事件。</span><span class="sxs-lookup"><span data-stu-id="9b732-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="9b732-198">comments</span><span class="sxs-lookup"><span data-stu-id="9b732-198">comments</span></span> | <span data-ttu-id="9b732-199">由 secops 在管理事件时创建的注释数组，例如有关分类选择的其他信息。</span><span class="sxs-lookup"><span data-stu-id="9b732-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="9b732-200">警报</span><span class="sxs-lookup"><span data-stu-id="9b732-200">alerts</span></span> | <span data-ttu-id="9b732-201">包含与事件相关的所有警报以及其他信息（如严重性、警报中涉及的实体以及警报来源）的数组。</span><span class="sxs-lookup"><span data-stu-id="9b732-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="9b732-202">\[\] (以下警报字段的详细信息) </span><span class="sxs-lookup"><span data-stu-id="9b732-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="9b732-203">警报元数据</span><span class="sxs-lookup"><span data-stu-id="9b732-203">Alerts metadata</span></span>

<span data-ttu-id="9b732-204">字段名</span><span class="sxs-lookup"><span data-stu-id="9b732-204">Field name</span></span> | <span data-ttu-id="9b732-205">说明</span><span class="sxs-lookup"><span data-stu-id="9b732-205">Description</span></span> | <span data-ttu-id="9b732-206">示例值</span><span class="sxs-lookup"><span data-stu-id="9b732-206">Example value</span></span>
-|-|-
<span data-ttu-id="9b732-207">alertId</span><span class="sxs-lookup"><span data-stu-id="9b732-207">alertId</span></span> | <span data-ttu-id="9b732-208">表示警报的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="9b732-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="9b732-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="9b732-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="9b732-210">incidentId</span><span class="sxs-lookup"><span data-stu-id="9b732-210">incidentId</span></span> | <span data-ttu-id="9b732-211">表示与此警报关联的事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="9b732-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="9b732-212">924565</span><span class="sxs-lookup"><span data-stu-id="9b732-212">924565</span></span>
<span data-ttu-id="9b732-213">serviceSource</span><span class="sxs-lookup"><span data-stu-id="9b732-213">serviceSource</span></span> | <span data-ttu-id="9b732-214">警报源自的服务，例如 Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity 或 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="9b732-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="9b732-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="9b732-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="9b732-216">creationTime</span><span class="sxs-lookup"><span data-stu-id="9b732-216">creationTime</span></span> | <span data-ttu-id="9b732-217">首次创建警报的时间。</span><span class="sxs-lookup"><span data-stu-id="9b732-217">Time when alert was first created.</span></span> | <span data-ttu-id="9b732-218">2020-09-06T14：46：55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="9b732-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="9b732-219">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="9b732-219">lastUpdatedTime</span></span> | <span data-ttu-id="9b732-220">上次在后端更新警报的时间。</span><span class="sxs-lookup"><span data-stu-id="9b732-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="9b732-221">2020-09-06T14：46：57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="9b732-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="9b732-222">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="9b732-222">resolvedTime</span></span> | <span data-ttu-id="9b732-223">警报解决的时间。</span><span class="sxs-lookup"><span data-stu-id="9b732-223">Time when alert was resolved.</span></span> | <span data-ttu-id="9b732-224">2020-09-10T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="9b732-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="9b732-225">firstActivity</span><span class="sxs-lookup"><span data-stu-id="9b732-225">firstActivity</span></span> | <span data-ttu-id="9b732-226">警报首次报告在后端更新活动的时间。</span><span class="sxs-lookup"><span data-stu-id="9b732-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="9b732-227">2020-09-04T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="9b732-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="9b732-228">title</span><span class="sxs-lookup"><span data-stu-id="9b732-228">title</span></span> | <span data-ttu-id="9b732-229">简要标识可用于每个警报的字符串值。</span><span class="sxs-lookup"><span data-stu-id="9b732-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="9b732-230">勒索软件活动</span><span class="sxs-lookup"><span data-stu-id="9b732-230">Ransomware activity</span></span>
<span data-ttu-id="9b732-231">说明</span><span class="sxs-lookup"><span data-stu-id="9b732-231">description</span></span> | <span data-ttu-id="9b732-232">描述每个警报的字符串值。</span><span class="sxs-lookup"><span data-stu-id="9b732-232">String value describing each alert.</span></span> | <span data-ttu-id="9b732-233">用户 Test User2 (testUser2@contoso.com) 操作 99 个文件，其多个扩展名以不常见的扩展 *名 herunterladen 结尾*。</span><span class="sxs-lookup"><span data-stu-id="9b732-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="9b732-234">这是异常多的文件操作，是潜在勒索软件攻击的表示。</span><span class="sxs-lookup"><span data-stu-id="9b732-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="9b732-235">“类别”</span><span class="sxs-lookup"><span data-stu-id="9b732-235">category</span></span> | <span data-ttu-id="9b732-236">有关攻击在击杀链上的进度的可视和数值视图。</span><span class="sxs-lookup"><span data-stu-id="9b732-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="9b732-237">与 [MITRE ATT&CK™对齐](https://attack.mitre.org/)。</span><span class="sxs-lookup"><span data-stu-id="9b732-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="9b732-238">影响</span><span class="sxs-lookup"><span data-stu-id="9b732-238">Impact</span></span>
<span data-ttu-id="9b732-239">状态</span><span class="sxs-lookup"><span data-stu-id="9b732-239">status</span></span> | <span data-ttu-id="9b732-240">将警报分类 (*新建*、*活动或\*\*已解决*) 。</span><span class="sxs-lookup"><span data-stu-id="9b732-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="9b732-241">它可以帮助你组织和管理对警报的响应。</span><span class="sxs-lookup"><span data-stu-id="9b732-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="9b732-242">新增</span><span class="sxs-lookup"><span data-stu-id="9b732-242">New</span></span>
<span data-ttu-id="9b732-243">severity</span><span class="sxs-lookup"><span data-stu-id="9b732-243">severity</span></span> | <span data-ttu-id="9b732-244">指示对资产可能的影响。</span><span class="sxs-lookup"><span data-stu-id="9b732-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="9b732-245">严重性越高，影响越大。</span><span class="sxs-lookup"><span data-stu-id="9b732-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="9b732-246">通常，严重性级别较高的项目需要最直接的关注。</span><span class="sxs-lookup"><span data-stu-id="9b732-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="9b732-247">下列值之一 *：Informational、Low、*Medium\* 和 *High。* </span><span class="sxs-lookup"><span data-stu-id="9b732-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="9b732-248">中</span><span class="sxs-lookup"><span data-stu-id="9b732-248">Medium</span></span>
<span data-ttu-id="9b732-249">investigationId</span><span class="sxs-lookup"><span data-stu-id="9b732-249">investigationId</span></span> | <span data-ttu-id="9b732-250">此警报触发的自动调查 ID。</span><span class="sxs-lookup"><span data-stu-id="9b732-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="9b732-251">1234</span><span class="sxs-lookup"><span data-stu-id="9b732-251">1234</span></span>
<span data-ttu-id="9b732-252">investigationState</span><span class="sxs-lookup"><span data-stu-id="9b732-252">investigationState</span></span> | <span data-ttu-id="9b732-253">有关调查的当前状态的信息。</span><span class="sxs-lookup"><span data-stu-id="9b732-253">Information on the investigation's current status.</span></span> <span data-ttu-id="9b732-254">下列值之一：Unknown、Terminated、SuccessfullyRemediated、Failed、Failed、PartiallyRemediated、Running、PendingApproval、PendingResource、PartiallyInvestigated、TerminatedByUser、TerminatedBySystem、Queued、InnerFailure、PreexistingAlert、UnsupportedOs、UnsupportedAlertType、SuppressedAlert 。                  </span><span class="sxs-lookup"><span data-stu-id="9b732-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="9b732-255">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="9b732-255">UnsupportedAlertType</span></span>
<span data-ttu-id="9b732-256">classification</span><span class="sxs-lookup"><span data-stu-id="9b732-256">classification</span></span> | <span data-ttu-id="9b732-257">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="9b732-257">The specification for the incident.</span></span> <span data-ttu-id="9b732-258">属性值包括：Unknown、FalsePositive、TruePositive 或 null   </span><span class="sxs-lookup"><span data-stu-id="9b732-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="9b732-259">未知</span><span class="sxs-lookup"><span data-stu-id="9b732-259">Unknown</span></span>
<span data-ttu-id="9b732-260">确定</span><span class="sxs-lookup"><span data-stu-id="9b732-260">determination</span></span> | <span data-ttu-id="9b732-261">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="9b732-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="9b732-262">属性值包括：NotAvailable、Apt、Malware、SecurityPersonnel、SecurityTesting、UnwantedSoftware、Other或 null      </span><span class="sxs-lookup"><span data-stu-id="9b732-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="9b732-263">Apt</span><span class="sxs-lookup"><span data-stu-id="9b732-263">Apt</span></span>
<span data-ttu-id="9b732-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="9b732-264">assignedTo</span></span> | <span data-ttu-id="9b732-265">事件的所有者;如果没有分配 *所有者* ，则为空。</span><span class="sxs-lookup"><span data-stu-id="9b732-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="9b732-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b732-266">secop2@contoso.com</span></span>
<span data-ttu-id="9b732-267">actorName</span><span class="sxs-lookup"><span data-stu-id="9b732-267">actorName</span></span> | <span data-ttu-id="9b732-268">与此警报关联的活动组（如果有）。</span><span class="sxs-lookup"><span data-stu-id="9b732-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="9b732-269">一个</span><span class="sxs-lookup"><span data-stu-id="9b732-269">BORON</span></span>
<span data-ttu-id="9b732-270">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="9b732-270">threatFamilyName</span></span> | <span data-ttu-id="9b732-271">与此警报关联的威胁系列。</span><span class="sxs-lookup"><span data-stu-id="9b732-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="9b732-272">空</span><span class="sxs-lookup"><span data-stu-id="9b732-272">null</span></span>
<span data-ttu-id="9b732-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="9b732-273">mitreTechniques</span></span> | <span data-ttu-id="9b732-274">攻击技术，与 [MITRE ATT](https://attack.mitre.org/)&CK ™框架一致。</span><span class="sxs-lookup"><span data-stu-id="9b732-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="9b732-275">设备</span><span class="sxs-lookup"><span data-stu-id="9b732-275">devices</span></span> | <span data-ttu-id="9b732-276">已发送与事件相关的警报的所有设备。</span><span class="sxs-lookup"><span data-stu-id="9b732-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="9b732-277">\[\] (下面实体字段的详细信息) </span><span class="sxs-lookup"><span data-stu-id="9b732-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="9b732-278">设备格式</span><span class="sxs-lookup"><span data-stu-id="9b732-278">Device format</span></span>

<span data-ttu-id="9b732-279">字段名</span><span class="sxs-lookup"><span data-stu-id="9b732-279">Field name</span></span> | <span data-ttu-id="9b732-280">说明</span><span class="sxs-lookup"><span data-stu-id="9b732-280">Description</span></span> | <span data-ttu-id="9b732-281">示例值</span><span class="sxs-lookup"><span data-stu-id="9b732-281">Example value</span></span>
-|-|-
<span data-ttu-id="9b732-282">DeviceId</span><span class="sxs-lookup"><span data-stu-id="9b732-282">DeviceId</span></span> | <span data-ttu-id="9b732-283">在 Microsoft Defender for Endpoint 中指定的设备 ID。</span><span class="sxs-lookup"><span data-stu-id="9b732-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="9b732-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="9b732-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="9b732-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="9b732-285">aadDeviceId</span></span> |  <span data-ttu-id="9b732-286">中指定的设备 ID [Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="9b732-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="9b732-287">仅适用于已加入域的设备。</span><span class="sxs-lookup"><span data-stu-id="9b732-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="9b732-288">空</span><span class="sxs-lookup"><span data-stu-id="9b732-288">null</span></span>
<span data-ttu-id="9b732-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="9b732-289">deviceDnsName</span></span> | <span data-ttu-id="9b732-290">设备的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="9b732-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="9b732-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b732-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="9b732-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="9b732-292">osPlatform</span></span> | <span data-ttu-id="9b732-293">设备正在运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="9b732-293">The OS platform the device is running.</span></span>| <span data-ttu-id="9b732-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="9b732-294">WindowsServer2016</span></span>
<span data-ttu-id="9b732-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="9b732-295">osBuild</span></span> | <span data-ttu-id="9b732-296">设备正在运行的操作系统的生成版本。</span><span class="sxs-lookup"><span data-stu-id="9b732-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="9b732-297">14393</span><span class="sxs-lookup"><span data-stu-id="9b732-297">14393</span></span>
<span data-ttu-id="9b732-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="9b732-298">rbacGroupName</span></span> | <span data-ttu-id="9b732-299">基于 [角色的访问控制 (](/azure/role-based-access-control/overview) 与) 关联的 RBAC 组。</span><span class="sxs-lookup"><span data-stu-id="9b732-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="9b732-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="9b732-300">WDATP-Ring0</span></span>
<span data-ttu-id="9b732-301">firstSeen</span><span class="sxs-lookup"><span data-stu-id="9b732-301">firstSeen</span></span> | <span data-ttu-id="9b732-302">首次看到设备的时间。</span><span class="sxs-lookup"><span data-stu-id="9b732-302">Time when device was first seen.</span></span> | <span data-ttu-id="9b732-303">2020-02-06T14：16：01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="9b732-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="9b732-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="9b732-304">healthStatus</span></span> | <span data-ttu-id="9b732-305">设备的运行状况。</span><span class="sxs-lookup"><span data-stu-id="9b732-305">The health state of the device.</span></span> | <span data-ttu-id="9b732-306">活动</span><span class="sxs-lookup"><span data-stu-id="9b732-306">Active</span></span>
<span data-ttu-id="9b732-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="9b732-307">riskScore</span></span> | <span data-ttu-id="9b732-308">设备的风险评分。</span><span class="sxs-lookup"><span data-stu-id="9b732-308">The risk score for the  device.</span></span> | <span data-ttu-id="9b732-309">高</span><span class="sxs-lookup"><span data-stu-id="9b732-309">High</span></span>
<span data-ttu-id="9b732-310">entities</span><span class="sxs-lookup"><span data-stu-id="9b732-310">entities</span></span> | <span data-ttu-id="9b732-311">已标识为给定警报的一部分或与给定警报相关的所有实体。</span><span class="sxs-lookup"><span data-stu-id="9b732-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="9b732-312">\[\] (下面实体字段的详细信息) </span><span class="sxs-lookup"><span data-stu-id="9b732-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="9b732-313">实体格式</span><span class="sxs-lookup"><span data-stu-id="9b732-313">Entity Format</span></span>

<span data-ttu-id="9b732-314">字段名</span><span class="sxs-lookup"><span data-stu-id="9b732-314">Field name</span></span> | <span data-ttu-id="9b732-315">说明</span><span class="sxs-lookup"><span data-stu-id="9b732-315">Description</span></span> | <span data-ttu-id="9b732-316">示例值</span><span class="sxs-lookup"><span data-stu-id="9b732-316">Example value</span></span>
-|-|-
<span data-ttu-id="9b732-317">entityType</span><span class="sxs-lookup"><span data-stu-id="9b732-317">entityType</span></span> | <span data-ttu-id="9b732-318">已标识为给定警报的一部分或与给定警报相关的实体。</span><span class="sxs-lookup"><span data-stu-id="9b732-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="9b732-319">属性值包括：User、Ip、Url、File、Process、MailBox、MailMessage、MailCluster、Registry         </span><span class="sxs-lookup"><span data-stu-id="9b732-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="9b732-320">用户</span><span class="sxs-lookup"><span data-stu-id="9b732-320">User</span></span>
<span data-ttu-id="9b732-321">sha1</span><span class="sxs-lookup"><span data-stu-id="9b732-321">sha1</span></span> | <span data-ttu-id="9b732-322">如果 entityType 为 File ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="9b732-323">与文件或进程关联的警报的文件哈希。</span><span class="sxs-lookup"><span data-stu-id="9b732-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="9b732-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="9b732-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="9b732-325">sha256</span><span class="sxs-lookup"><span data-stu-id="9b732-325">sha256</span></span> | <span data-ttu-id="9b732-326">如果 entityType 为 File ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="9b732-327">与文件或进程关联的警报的文件哈希。</span><span class="sxs-lookup"><span data-stu-id="9b732-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="9b732-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="9b732-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="9b732-329">fileName</span><span class="sxs-lookup"><span data-stu-id="9b732-329">fileName</span></span> | <span data-ttu-id="9b732-330">如果 entityType 为 File ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="9b732-331">与文件或进程关联的警报的文件名</span><span class="sxs-lookup"><span data-stu-id="9b732-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="9b732-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="9b732-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="9b732-333">filePath</span><span class="sxs-lookup"><span data-stu-id="9b732-333">filePath</span></span> | <span data-ttu-id="9b732-334">如果 entityType 为 File ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="9b732-335">与文件或进程关联的警报的文件路径</span><span class="sxs-lookup"><span data-stu-id="9b732-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="9b732-336">C： \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="9b732-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="9b732-337">processId</span><span class="sxs-lookup"><span data-stu-id="9b732-337">processId</span></span> | <span data-ttu-id="9b732-338">如果 entityType 为 Process ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="9b732-339">24348</span><span class="sxs-lookup"><span data-stu-id="9b732-339">24348</span></span>
<span data-ttu-id="9b732-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="9b732-340">processCommandLine</span></span> | <span data-ttu-id="9b732-341">如果 entityType 为 Process ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="9b732-342">"你的文件已准备好下载 \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="9b732-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="9b732-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="9b732-343">processCreationTime</span></span> | <span data-ttu-id="9b732-344">如果 entityType 为 Process ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="9b732-345">2020-07-18T03：25：38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="9b732-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="9b732-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="9b732-346">parentProcessId</span></span> | <span data-ttu-id="9b732-347">如果 entityType 为 Process ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="9b732-348">16840</span><span class="sxs-lookup"><span data-stu-id="9b732-348">16840</span></span>
<span data-ttu-id="9b732-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="9b732-349">parentProcessCreationTime</span></span> | <span data-ttu-id="9b732-350">如果 entityType 为 Process ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="9b732-351">2020-07-18T02：12：32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="9b732-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="9b732-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="9b732-352">ipAddress</span></span> | <span data-ttu-id="9b732-353">如果 entityType 为 *Ip，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="9b732-354">与网络事件（如到恶意网络目标的通信）关联的警报的 IP *地址*。</span><span class="sxs-lookup"><span data-stu-id="9b732-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="9b732-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="9b732-355">62.216.203.204</span></span>
<span data-ttu-id="9b732-356">url</span><span class="sxs-lookup"><span data-stu-id="9b732-356">url</span></span> | <span data-ttu-id="9b732-357">如果 entityType 为 *Url，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="9b732-358">与网络事件（例如，到恶意网络目标的通信）*关联的警报的 URL。*</span><span class="sxs-lookup"><span data-stu-id="9b732-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="9b732-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="9b732-359">down.esales360.cn</span></span>
<span data-ttu-id="9b732-360">accountName</span><span class="sxs-lookup"><span data-stu-id="9b732-360">accountName</span></span> | <span data-ttu-id="9b732-361">如果 entityType 为 User ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="9b732-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="9b732-362">testUser2</span></span>
<span data-ttu-id="9b732-363">domainName</span><span class="sxs-lookup"><span data-stu-id="9b732-363">domainName</span></span> | <span data-ttu-id="9b732-364">如果 entityType 为 User ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="9b732-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="9b732-365">europe.corp.contoso</span></span>
<span data-ttu-id="9b732-366">userSid</span><span class="sxs-lookup"><span data-stu-id="9b732-366">userSid</span></span> | <span data-ttu-id="9b732-367">如果 entityType 为 User ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="9b732-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="9b732-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="9b732-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="9b732-369">aadUserId</span></span> | <span data-ttu-id="9b732-370">如果 entityType 为 User ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="9b732-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="9b732-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="9b732-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="9b732-372">userPrincipalName</span></span> | <span data-ttu-id="9b732-373">如果 entityType 为 *User* / *MailBox* / *MailMessage，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="9b732-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b732-374">testUser2@contoso.com</span></span>
<span data-ttu-id="9b732-375">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="9b732-375">mailboxDisplayName</span></span> | <span data-ttu-id="9b732-376">如果 entityType 为 *MailBox ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="9b732-377">test User2</span><span class="sxs-lookup"><span data-stu-id="9b732-377">test User2</span></span>
<span data-ttu-id="9b732-378">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="9b732-378">mailboxAddress</span></span> | <span data-ttu-id="9b732-379">如果 entityType 为 *User* / *MailBox* / *MailMessage，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="9b732-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b732-380">testUser2@contoso.com</span></span>
<span data-ttu-id="9b732-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="9b732-381">clusterBy</span></span> | <span data-ttu-id="9b732-382">如果 entityType 为  *MailCluster，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="9b732-383">主题;P2SenderDomain;ContentType</span><span class="sxs-lookup"><span data-stu-id="9b732-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="9b732-384">sender</span><span class="sxs-lookup"><span data-stu-id="9b732-384">sender</span></span> | <span data-ttu-id="9b732-385">如果 entityType 为 *User* / *MailBox* / *MailMessage，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="9b732-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="9b732-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="9b732-387">recipient</span><span class="sxs-lookup"><span data-stu-id="9b732-387">recipient</span></span> | <span data-ttu-id="9b732-388">如果 entityType 为 *MailMessage ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="9b732-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b732-389">testUser2@contoso.com</span></span>
<span data-ttu-id="9b732-390">subject</span><span class="sxs-lookup"><span data-stu-id="9b732-390">subject</span></span> | <span data-ttu-id="9b732-391">如果 entityType 为 *MailMessage ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="9b732-392">\[外部 \] 关注</span><span class="sxs-lookup"><span data-stu-id="9b732-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="9b732-393">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="9b732-393">deliveryAction</span></span> | <span data-ttu-id="9b732-394">如果 entityType 为 *MailMessage ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="9b732-395">已传递</span><span class="sxs-lookup"><span data-stu-id="9b732-395">Delivered</span></span>
<span data-ttu-id="9b732-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="9b732-396">securityGroupId</span></span> | <span data-ttu-id="9b732-397">如果 entityType 为  *SecurityGroup，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="9b732-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="9b732-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="9b732-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="9b732-399">securityGroupName</span></span> | <span data-ttu-id="9b732-400">如果 entityType 为  *SecurityGroup，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="9b732-401">网络配置运算符</span><span class="sxs-lookup"><span data-stu-id="9b732-401">Network Configuration Operators</span></span>
<span data-ttu-id="9b732-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="9b732-402">registryHive</span></span> | <span data-ttu-id="9b732-403">如果 entityType 为  *Registry ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="9b732-404">HKEY \_ 本地 \_ 计算机</span><span class="sxs-lookup"><span data-stu-id="9b732-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="9b732-405">registryKey</span><span class="sxs-lookup"><span data-stu-id="9b732-405">registryKey</span></span> | <span data-ttu-id="9b732-406">如果 entityType 为  *Registry ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="9b732-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="9b732-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="9b732-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="9b732-408">registryValueType</span></span> | <span data-ttu-id="9b732-409">如果 entityType 为  *Registry ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="9b732-410">String</span><span class="sxs-lookup"><span data-stu-id="9b732-410">String</span></span>
<span data-ttu-id="9b732-411">registryValue</span><span class="sxs-lookup"><span data-stu-id="9b732-411">registryValue</span></span> | <span data-ttu-id="9b732-412">如果 entityType 为  *Registry ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="9b732-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="9b732-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="9b732-413">31-00-00-00</span></span>
<span data-ttu-id="9b732-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="9b732-414">deviceId</span></span> | <span data-ttu-id="9b732-415">与实体相关的设备的 ID（如果有）。</span><span class="sxs-lookup"><span data-stu-id="9b732-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="9b732-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="9b732-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="9b732-417">示例</span><span class="sxs-lookup"><span data-stu-id="9b732-417">Example</span></span>

<span data-ttu-id="9b732-418">**请求**</span><span class="sxs-lookup"><span data-stu-id="9b732-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="9b732-419">**响应**</span><span class="sxs-lookup"><span data-stu-id="9b732-419">**Response**</span></span>

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="9b732-420">相关文章</span><span class="sxs-lookup"><span data-stu-id="9b732-420">Related articles</span></span>

- [<span data-ttu-id="9b732-421">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="9b732-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="9b732-422">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="9b732-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="9b732-423">了解错误代码</span><span class="sxs-lookup"><span data-stu-id="9b732-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="9b732-424">事件概述</span><span class="sxs-lookup"><span data-stu-id="9b732-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="9b732-425">事件 API</span><span class="sxs-lookup"><span data-stu-id="9b732-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="9b732-426">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="9b732-426">Update incident API</span></span>](api-update-incidents.md)
