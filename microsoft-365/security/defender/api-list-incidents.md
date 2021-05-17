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
ms.openlocfilehash: 7fb0de4f8dc67331e7acca59e70d061fe7c19493
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935733"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="2fbc4-104">在 defender 中列出Microsoft 365 API</span><span class="sxs-lookup"><span data-stu-id="2fbc4-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2fbc4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2fbc4-105">**Applies to:**</span></span>

- <span data-ttu-id="2fbc4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2fbc4-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fbc4-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2fbc4-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="2fbc4-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="2fbc4-109">API description</span></span>

<span data-ttu-id="2fbc4-110">列表事件 API 允许你对事件进行排序，以创建明智的网络安全响应。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="2fbc4-111">它公开在环境保留策略中指定的时间范围内网络中标记的事件集合。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="2fbc4-112">最新事件显示在列表顶部。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="2fbc4-113">每个事件都包含一组相关警报及其相关实体。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="2fbc4-114">API 支持以下 **OData** 运算符：</span><span class="sxs-lookup"><span data-stu-id="2fbc4-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="2fbc4-115">`$filter` 在 `lastUpdateTime` 、 `createdTime` 、 和 `status` `assignedTo` 属性上</span><span class="sxs-lookup"><span data-stu-id="2fbc4-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="2fbc4-116">`$top`，最大值为 **100**</span><span class="sxs-lookup"><span data-stu-id="2fbc4-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="2fbc4-117">限制</span><span class="sxs-lookup"><span data-stu-id="2fbc4-117">Limitations</span></span>

1. <span data-ttu-id="2fbc4-118">最大页面大小为 **100 个事件**。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="2fbc4-119">最大请求速率为每分钟 **50** 个呼叫和 **每小时 1500 个呼叫**。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="2fbc4-120">权限</span><span class="sxs-lookup"><span data-stu-id="2fbc4-120">Permissions</span></span>

<span data-ttu-id="2fbc4-121">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2fbc4-122">若要了解更多信息（包括如何选择权限），请参阅[Access Microsoft 365 Defender API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="2fbc4-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="2fbc4-123">权限类型</span><span class="sxs-lookup"><span data-stu-id="2fbc4-123">Permission type</span></span> | <span data-ttu-id="2fbc4-124">权限</span><span class="sxs-lookup"><span data-stu-id="2fbc4-124">Permission</span></span> | <span data-ttu-id="2fbc4-125">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="2fbc4-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="2fbc4-126">应用程序</span><span class="sxs-lookup"><span data-stu-id="2fbc4-126">Application</span></span> | <span data-ttu-id="2fbc4-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="2fbc4-127">Incident.Read.All</span></span> | <span data-ttu-id="2fbc4-128">读取所有事件</span><span class="sxs-lookup"><span data-stu-id="2fbc4-128">Read all incidents</span></span>
<span data-ttu-id="2fbc4-129">应用程序</span><span class="sxs-lookup"><span data-stu-id="2fbc4-129">Application</span></span> | <span data-ttu-id="2fbc4-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="2fbc4-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="2fbc4-131">读取和写入所有事件</span><span class="sxs-lookup"><span data-stu-id="2fbc4-131">Read and write all incidents</span></span>
<span data-ttu-id="2fbc4-132">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="2fbc4-132">Delegated (work or school account)</span></span> | <span data-ttu-id="2fbc4-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="2fbc4-133">Incident.Read</span></span> | <span data-ttu-id="2fbc4-134">读取事件</span><span class="sxs-lookup"><span data-stu-id="2fbc4-134">Read incidents</span></span>
<span data-ttu-id="2fbc4-135">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="2fbc4-135">Delegated (work or school account)</span></span> | <span data-ttu-id="2fbc4-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="2fbc4-136">Incident.ReadWrite</span></span> | <span data-ttu-id="2fbc4-137">读取和写入事件</span><span class="sxs-lookup"><span data-stu-id="2fbc4-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="2fbc4-138">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="2fbc4-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="2fbc4-139">用户需要具有门户中事件的查看权限。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="2fbc4-140">该响应将仅包括向用户公开的事件。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="2fbc4-141">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="2fbc4-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="2fbc4-142">请求标头</span><span class="sxs-lookup"><span data-stu-id="2fbc4-142">Request headers</span></span>

<span data-ttu-id="2fbc4-143">名称</span><span class="sxs-lookup"><span data-stu-id="2fbc4-143">Name</span></span> | <span data-ttu-id="2fbc4-144">类型</span><span class="sxs-lookup"><span data-stu-id="2fbc4-144">Type</span></span> | <span data-ttu-id="2fbc4-145">说明</span><span class="sxs-lookup"><span data-stu-id="2fbc4-145">Description</span></span>
-|-|-
<span data-ttu-id="2fbc4-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="2fbc4-146">Authorization</span></span> | <span data-ttu-id="2fbc4-147">String</span><span class="sxs-lookup"><span data-stu-id="2fbc4-147">String</span></span> | <span data-ttu-id="2fbc4-148">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-148">Bearer {token}.</span></span> <span data-ttu-id="2fbc4-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="2fbc4-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="2fbc4-150">请求正文</span><span class="sxs-lookup"><span data-stu-id="2fbc4-150">Request body</span></span>

<span data-ttu-id="2fbc4-151">无。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="2fbc4-152">响应</span><span class="sxs-lookup"><span data-stu-id="2fbc4-152">Response</span></span>

<span data-ttu-id="2fbc4-153">如果成功，此方法在响应正文中返回 和 `200 OK` 事件列表。 [](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="2fbc4-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="2fbc4-154">架构映射</span><span class="sxs-lookup"><span data-stu-id="2fbc4-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="2fbc4-155">事件元数据</span><span class="sxs-lookup"><span data-stu-id="2fbc4-155">Incident metadata</span></span>

<span data-ttu-id="2fbc4-156">字段名</span><span class="sxs-lookup"><span data-stu-id="2fbc4-156">Field name</span></span> | <span data-ttu-id="2fbc4-157">说明</span><span class="sxs-lookup"><span data-stu-id="2fbc4-157">Description</span></span> | <span data-ttu-id="2fbc4-158">示例值</span><span class="sxs-lookup"><span data-stu-id="2fbc4-158">Example value</span></span>
-|-|-
<span data-ttu-id="2fbc4-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-159">incidentId</span></span> | <span data-ttu-id="2fbc4-160">表示事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="2fbc4-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="2fbc4-161">924565</span><span class="sxs-lookup"><span data-stu-id="2fbc4-161">924565</span></span>
<span data-ttu-id="2fbc4-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-162">redirectIncidentId</span></span> | <span data-ttu-id="2fbc4-163">只有在将事件与另一个事件分组在一起时填充，作为事件处理逻辑的一部分。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="2fbc4-164">924569</span><span class="sxs-lookup"><span data-stu-id="2fbc4-164">924569</span></span>
<span data-ttu-id="2fbc4-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="2fbc4-165">incidentName</span></span> | <span data-ttu-id="2fbc4-166">可用于每个事件的字符串值。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-166">String value available for every incident.</span></span> | <span data-ttu-id="2fbc4-167">勒索软件活动</span><span class="sxs-lookup"><span data-stu-id="2fbc4-167">Ransomware activity</span></span>
<span data-ttu-id="2fbc4-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="2fbc4-168">createdTime</span></span> | <span data-ttu-id="2fbc4-169">第一次创建事件的时间。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-169">Time when incident was first created.</span></span> | <span data-ttu-id="2fbc4-170">2020-09-06T14：46：57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="2fbc4-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="2fbc4-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="2fbc4-171">lastUpdateTime</span></span> | <span data-ttu-id="2fbc4-172">上次在后端更新事件的时间。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="2fbc4-173">为检索事件的时间范围设置请求参数时，可以使用此字段。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="2fbc4-174">2020-09-06T14：46：57.29Z</span><span class="sxs-lookup"><span data-stu-id="2fbc4-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="2fbc4-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="2fbc4-175">assignedTo</span></span> | <span data-ttu-id="2fbc4-176">事件的所有者;如果没有分配 *所有者* ，则为空。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="2fbc4-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fbc4-177">secop2@contoso.com</span></span>
<span data-ttu-id="2fbc4-178">classification</span><span class="sxs-lookup"><span data-stu-id="2fbc4-178">classification</span></span> | <span data-ttu-id="2fbc4-179">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-179">The specification for the incident.</span></span> <span data-ttu-id="2fbc4-180">属性值为 *：Unknown、FalsePositive、TruePositive*  </span><span class="sxs-lookup"><span data-stu-id="2fbc4-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="2fbc4-181">未知</span><span class="sxs-lookup"><span data-stu-id="2fbc4-181">Unknown</span></span>
<span data-ttu-id="2fbc4-182">确定</span><span class="sxs-lookup"><span data-stu-id="2fbc4-182">determination</span></span> | <span data-ttu-id="2fbc4-183">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="2fbc4-184">属性值包括：NotAvailable、Apt、Malware、SecurityPersonnel、SecurityTesting、UnwantedSoftware、Other       </span><span class="sxs-lookup"><span data-stu-id="2fbc4-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="2fbc4-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="2fbc4-185">NotAvailable</span></span>
<span data-ttu-id="2fbc4-186">状态</span><span class="sxs-lookup"><span data-stu-id="2fbc4-186">status</span></span> | <span data-ttu-id="2fbc4-187">将事件分类 (*活动"* 或"已解决 *) "*</span><span class="sxs-lookup"><span data-stu-id="2fbc4-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="2fbc4-188">它可以帮助您组织和管理对事件的响应。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="2fbc4-189">活动</span><span class="sxs-lookup"><span data-stu-id="2fbc4-189">Active</span></span>
<span data-ttu-id="2fbc4-190">severity</span><span class="sxs-lookup"><span data-stu-id="2fbc4-190">severity</span></span> | <span data-ttu-id="2fbc4-191">指示对资产可能的影响。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="2fbc4-192">严重性越高，影响越大。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="2fbc4-193">通常，严重性级别较高的项目需要最直接的关注。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="2fbc4-194">下列值之一 *：Informational、Low、*Medium\* 和 *High。* </span><span class="sxs-lookup"><span data-stu-id="2fbc4-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="2fbc4-195">中</span><span class="sxs-lookup"><span data-stu-id="2fbc4-195">Medium</span></span>
<span data-ttu-id="2fbc4-196">tags</span><span class="sxs-lookup"><span data-stu-id="2fbc4-196">tags</span></span> | <span data-ttu-id="2fbc4-197">与事件关联的自定义标记数组，例如，用于标记一组具有共同特征的事件。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="2fbc4-198">警报</span><span class="sxs-lookup"><span data-stu-id="2fbc4-198">alerts</span></span> | <span data-ttu-id="2fbc4-199">包含与事件相关的所有警报以及其他信息（如严重性、警报中涉及的实体以及警报来源）的数组。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="2fbc4-200">\[\] (以下警报字段的详细信息) </span><span class="sxs-lookup"><span data-stu-id="2fbc4-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="2fbc4-201">警报元数据</span><span class="sxs-lookup"><span data-stu-id="2fbc4-201">Alerts metadata</span></span>

<span data-ttu-id="2fbc4-202">字段名</span><span class="sxs-lookup"><span data-stu-id="2fbc4-202">Field name</span></span> | <span data-ttu-id="2fbc4-203">说明</span><span class="sxs-lookup"><span data-stu-id="2fbc4-203">Description</span></span> | <span data-ttu-id="2fbc4-204">示例值</span><span class="sxs-lookup"><span data-stu-id="2fbc4-204">Example value</span></span>
-|-|-
<span data-ttu-id="2fbc4-205">alertId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-205">alertId</span></span> | <span data-ttu-id="2fbc4-206">表示警报的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="2fbc4-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="2fbc4-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="2fbc4-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="2fbc4-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-208">incidentId</span></span> | <span data-ttu-id="2fbc4-209">表示与此警报关联的事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="2fbc4-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="2fbc4-210">924565</span><span class="sxs-lookup"><span data-stu-id="2fbc4-210">924565</span></span>
<span data-ttu-id="2fbc4-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="2fbc4-211">serviceSource</span></span> | <span data-ttu-id="2fbc4-212">警报源自的服务，例如 Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity 或 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="2fbc4-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="2fbc4-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="2fbc4-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="2fbc4-214">creationTime</span></span> | <span data-ttu-id="2fbc4-215">首次创建警报的时间。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-215">Time when alert was first created.</span></span> | <span data-ttu-id="2fbc4-216">2020-09-06T14：46：55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="2fbc4-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="2fbc4-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="2fbc4-217">lastUpdatedTime</span></span> | <span data-ttu-id="2fbc4-218">上次在后端更新警报的时间。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="2fbc4-219">2020-09-06T14：46：57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="2fbc4-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="2fbc4-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="2fbc4-220">resolvedTime</span></span> | <span data-ttu-id="2fbc4-221">警报解决的时间。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-221">Time when alert was resolved.</span></span> | <span data-ttu-id="2fbc4-222">2020-09-10T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="2fbc4-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="2fbc4-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="2fbc4-223">firstActivity</span></span> | <span data-ttu-id="2fbc4-224">警报首次报告在后端更新活动的时间。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="2fbc4-225">2020-09-04T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="2fbc4-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="2fbc4-226">title</span><span class="sxs-lookup"><span data-stu-id="2fbc4-226">title</span></span> | <span data-ttu-id="2fbc4-227">简要标识可用于每个警报的字符串值。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="2fbc4-228">勒索软件活动</span><span class="sxs-lookup"><span data-stu-id="2fbc4-228">Ransomware activity</span></span>
<span data-ttu-id="2fbc4-229">说明</span><span class="sxs-lookup"><span data-stu-id="2fbc4-229">description</span></span> | <span data-ttu-id="2fbc4-230">描述每个警报的字符串值。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-230">String value describing each alert.</span></span> | <span data-ttu-id="2fbc4-231">用户 Test User2 (testUser2@contoso.com) 操作 99 个文件，其多个扩展名以不常见的扩展 *名 herunterladen 结尾*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="2fbc4-232">这是异常多的文件操作，是潜在勒索软件攻击的表示。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="2fbc4-233">“类别”</span><span class="sxs-lookup"><span data-stu-id="2fbc4-233">category</span></span> | <span data-ttu-id="2fbc4-234">有关攻击在击杀链上的进度的可视和数值视图。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="2fbc4-235">与 [MITRE ATT&CK™对齐](https://attack.mitre.org/)。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="2fbc4-236">影响</span><span class="sxs-lookup"><span data-stu-id="2fbc4-236">Impact</span></span>
<span data-ttu-id="2fbc4-237">状态</span><span class="sxs-lookup"><span data-stu-id="2fbc4-237">status</span></span> | <span data-ttu-id="2fbc4-238">将警报分类 (*新建*、*活动或\*\*已解决*) 。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="2fbc4-239">它可以帮助你组织和管理对警报的响应。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="2fbc4-240">新增</span><span class="sxs-lookup"><span data-stu-id="2fbc4-240">New</span></span>
<span data-ttu-id="2fbc4-241">severity</span><span class="sxs-lookup"><span data-stu-id="2fbc4-241">severity</span></span> | <span data-ttu-id="2fbc4-242">指示对资产可能的影响。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="2fbc4-243">严重性越高，影响越大。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="2fbc4-244">通常，严重性级别较高的项目需要最直接的关注。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="2fbc4-245">下列值之一 *：Informational、Low、*Medium\* 和 *High。* </span><span class="sxs-lookup"><span data-stu-id="2fbc4-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="2fbc4-246">中</span><span class="sxs-lookup"><span data-stu-id="2fbc4-246">Medium</span></span>
<span data-ttu-id="2fbc4-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-247">investigationId</span></span> | <span data-ttu-id="2fbc4-248">此警报触发的自动调查 ID。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="2fbc4-249">1234</span><span class="sxs-lookup"><span data-stu-id="2fbc4-249">1234</span></span>
<span data-ttu-id="2fbc4-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="2fbc4-250">investigationState</span></span> | <span data-ttu-id="2fbc4-251">有关调查的当前状态的信息。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-251">Information on the investigation's current status.</span></span> <span data-ttu-id="2fbc4-252">下列值之一：Unknown、Terminated、SuccessfullyRemediated、Failed、Failed、PartiallyRemediated、Running、PendingApproval、PendingResource、PartiallyInvestigated、TerminatedByUser、TerminatedBySystem、Queued、InnerFailure、PreexistingAlert、UnsupportedOs、UnsupportedAlertType、SuppressedAlert 。                  </span><span class="sxs-lookup"><span data-stu-id="2fbc4-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="2fbc4-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="2fbc4-253">UnsupportedAlertType</span></span>
<span data-ttu-id="2fbc4-254">classification</span><span class="sxs-lookup"><span data-stu-id="2fbc4-254">classification</span></span> | <span data-ttu-id="2fbc4-255">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-255">The specification for the incident.</span></span> <span data-ttu-id="2fbc4-256">属性值包括：Unknown、FalsePositive、TruePositive 或 null   </span><span class="sxs-lookup"><span data-stu-id="2fbc4-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="2fbc4-257">未知</span><span class="sxs-lookup"><span data-stu-id="2fbc4-257">Unknown</span></span>
<span data-ttu-id="2fbc4-258">确定</span><span class="sxs-lookup"><span data-stu-id="2fbc4-258">determination</span></span> | <span data-ttu-id="2fbc4-259">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="2fbc4-260">属性值包括：NotAvailable、Apt、Malware、SecurityPersonnel、SecurityTesting、UnwantedSoftware、Other或 null      </span><span class="sxs-lookup"><span data-stu-id="2fbc4-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="2fbc4-261">Apt</span><span class="sxs-lookup"><span data-stu-id="2fbc4-261">Apt</span></span>
<span data-ttu-id="2fbc4-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="2fbc4-262">assignedTo</span></span> | <span data-ttu-id="2fbc4-263">事件的所有者;如果没有分配 *所有者* ，则为空。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="2fbc4-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fbc4-264">secop2@contoso.com</span></span>
<span data-ttu-id="2fbc4-265">actorName</span><span class="sxs-lookup"><span data-stu-id="2fbc4-265">actorName</span></span> | <span data-ttu-id="2fbc4-266">与此警报关联的活动组（如果有）。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="2fbc4-267">一个</span><span class="sxs-lookup"><span data-stu-id="2fbc4-267">BORON</span></span>
<span data-ttu-id="2fbc4-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="2fbc4-268">threatFamilyName</span></span> | <span data-ttu-id="2fbc4-269">与此警报关联的威胁系列。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="2fbc4-270">空</span><span class="sxs-lookup"><span data-stu-id="2fbc4-270">null</span></span>
<span data-ttu-id="2fbc4-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="2fbc4-271">mitreTechniques</span></span> | <span data-ttu-id="2fbc4-272">攻击技术，与 [MITRE ATT](https://attack.mitre.org/)&CK ™框架一致。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="2fbc4-273">设备</span><span class="sxs-lookup"><span data-stu-id="2fbc4-273">devices</span></span> | <span data-ttu-id="2fbc4-274">已发送与事件相关的警报的所有设备。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="2fbc4-275">\[\] (下面实体字段的详细信息) </span><span class="sxs-lookup"><span data-stu-id="2fbc4-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="2fbc4-276">设备格式</span><span class="sxs-lookup"><span data-stu-id="2fbc4-276">Device format</span></span>

<span data-ttu-id="2fbc4-277">字段名</span><span class="sxs-lookup"><span data-stu-id="2fbc4-277">Field name</span></span> | <span data-ttu-id="2fbc4-278">说明</span><span class="sxs-lookup"><span data-stu-id="2fbc4-278">Description</span></span> | <span data-ttu-id="2fbc4-279">示例值</span><span class="sxs-lookup"><span data-stu-id="2fbc4-279">Example value</span></span>
-|-|-
<span data-ttu-id="2fbc4-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-280">DeviceId</span></span> | <span data-ttu-id="2fbc4-281">在 Microsoft Defender for Endpoint 中指定的设备 ID。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-281">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="2fbc4-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="2fbc4-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="2fbc4-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-283">aadDeviceId</span></span> |  <span data-ttu-id="2fbc4-284">中指定的设备 ID [Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="2fbc4-284">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="2fbc4-285">仅适用于已加入域的设备。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="2fbc4-286">空</span><span class="sxs-lookup"><span data-stu-id="2fbc4-286">null</span></span>
<span data-ttu-id="2fbc4-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="2fbc4-287">deviceDnsName</span></span> | <span data-ttu-id="2fbc4-288">设备的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="2fbc4-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fbc4-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="2fbc4-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="2fbc4-290">osPlatform</span></span> | <span data-ttu-id="2fbc4-291">设备正在运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-291">The OS platform the device is running.</span></span>| <span data-ttu-id="2fbc4-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="2fbc4-292">WindowsServer2016</span></span>
<span data-ttu-id="2fbc4-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="2fbc4-293">osBuild</span></span> | <span data-ttu-id="2fbc4-294">设备正在运行的操作系统的生成版本。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="2fbc4-295">14393</span><span class="sxs-lookup"><span data-stu-id="2fbc4-295">14393</span></span>
<span data-ttu-id="2fbc4-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="2fbc4-296">rbacGroupName</span></span> | <span data-ttu-id="2fbc4-297">基于 [角色的访问控制 (](/azure/role-based-access-control/overview) 与) 关联的 RBAC 组。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-297">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="2fbc4-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="2fbc4-298">WDATP-Ring0</span></span>
<span data-ttu-id="2fbc4-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="2fbc4-299">firstSeen</span></span> | <span data-ttu-id="2fbc4-300">首次看到设备的时间。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-300">Time when device was first seen.</span></span> | <span data-ttu-id="2fbc4-301">2020-02-06T14：16：01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="2fbc4-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="2fbc4-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="2fbc4-302">healthStatus</span></span> | <span data-ttu-id="2fbc4-303">设备的运行状况。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-303">The health state of the device.</span></span> | <span data-ttu-id="2fbc4-304">活动</span><span class="sxs-lookup"><span data-stu-id="2fbc4-304">Active</span></span>
<span data-ttu-id="2fbc4-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="2fbc4-305">riskScore</span></span> | <span data-ttu-id="2fbc4-306">设备的风险评分。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-306">The risk score for the  device.</span></span> | <span data-ttu-id="2fbc4-307">高</span><span class="sxs-lookup"><span data-stu-id="2fbc4-307">High</span></span>
<span data-ttu-id="2fbc4-308">entities</span><span class="sxs-lookup"><span data-stu-id="2fbc4-308">entities</span></span> | <span data-ttu-id="2fbc4-309">已标识为给定警报的一部分或与给定警报相关的所有实体。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="2fbc4-310">\[\] (下面实体字段的详细信息) </span><span class="sxs-lookup"><span data-stu-id="2fbc4-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="2fbc4-311">实体格式</span><span class="sxs-lookup"><span data-stu-id="2fbc4-311">Entity Format</span></span>

<span data-ttu-id="2fbc4-312">字段名</span><span class="sxs-lookup"><span data-stu-id="2fbc4-312">Field name</span></span> | <span data-ttu-id="2fbc4-313">说明</span><span class="sxs-lookup"><span data-stu-id="2fbc4-313">Description</span></span> | <span data-ttu-id="2fbc4-314">示例值</span><span class="sxs-lookup"><span data-stu-id="2fbc4-314">Example value</span></span>
-|-|-
<span data-ttu-id="2fbc4-315">entityType</span><span class="sxs-lookup"><span data-stu-id="2fbc4-315">entityType</span></span> | <span data-ttu-id="2fbc4-316">已标识为给定警报的一部分或与给定警报相关的实体。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="2fbc4-317">属性值包括：User、Ip、Url、File、Process、MailBox、MailMessage、MailCluster、Registry         </span><span class="sxs-lookup"><span data-stu-id="2fbc4-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="2fbc4-318">用户</span><span class="sxs-lookup"><span data-stu-id="2fbc4-318">User</span></span>
<span data-ttu-id="2fbc4-319">sha1</span><span class="sxs-lookup"><span data-stu-id="2fbc4-319">sha1</span></span> | <span data-ttu-id="2fbc4-320">如果 entityType 为 File ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="2fbc4-321">与文件或进程关联的警报的文件哈希。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="2fbc4-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="2fbc4-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="2fbc4-323">sha256</span><span class="sxs-lookup"><span data-stu-id="2fbc4-323">sha256</span></span> | <span data-ttu-id="2fbc4-324">如果 entityType 为 File ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="2fbc4-325">与文件或进程关联的警报的文件哈希。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="2fbc4-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="2fbc4-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="2fbc4-327">fileName</span><span class="sxs-lookup"><span data-stu-id="2fbc4-327">fileName</span></span> | <span data-ttu-id="2fbc4-328">如果 entityType 为 File ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="2fbc4-329">与文件或进程关联的警报的文件名</span><span class="sxs-lookup"><span data-stu-id="2fbc4-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="2fbc4-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="2fbc4-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="2fbc4-331">filePath</span><span class="sxs-lookup"><span data-stu-id="2fbc4-331">filePath</span></span> | <span data-ttu-id="2fbc4-332">如果 entityType 为 File ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="2fbc4-333">与文件或进程关联的警报的文件路径</span><span class="sxs-lookup"><span data-stu-id="2fbc4-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="2fbc4-334">C： \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="2fbc4-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="2fbc4-335">processId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-335">processId</span></span> | <span data-ttu-id="2fbc4-336">如果 entityType 为 Process ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="2fbc4-337">24348</span><span class="sxs-lookup"><span data-stu-id="2fbc4-337">24348</span></span>
<span data-ttu-id="2fbc4-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="2fbc4-338">processCommandLine</span></span> | <span data-ttu-id="2fbc4-339">如果 entityType 为 Process ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="2fbc4-340">"你的文件已准备好下载 \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="2fbc4-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="2fbc4-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="2fbc4-341">processCreationTime</span></span> | <span data-ttu-id="2fbc4-342">如果 entityType 为 Process ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="2fbc4-343">2020-07-18T03：25：38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="2fbc4-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="2fbc4-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-344">parentProcessId</span></span> | <span data-ttu-id="2fbc4-345">如果 entityType 为 Process ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="2fbc4-346">16840</span><span class="sxs-lookup"><span data-stu-id="2fbc4-346">16840</span></span>
<span data-ttu-id="2fbc4-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="2fbc4-347">parentProcessCreationTime</span></span> | <span data-ttu-id="2fbc4-348">如果 entityType 为 Process ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="2fbc4-349">2020-07-18T02：12：32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="2fbc4-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="2fbc4-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="2fbc4-350">ipAddress</span></span> | <span data-ttu-id="2fbc4-351">如果 entityType 为 *Ip，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="2fbc4-352">与网络事件（如到恶意网络目标的通信）关联的警报的 IP *地址*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="2fbc4-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="2fbc4-353">62.216.203.204</span></span>
<span data-ttu-id="2fbc4-354">url</span><span class="sxs-lookup"><span data-stu-id="2fbc4-354">url</span></span> | <span data-ttu-id="2fbc4-355">如果 entityType 为 *Url，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="2fbc4-356">与网络事件（例如，到恶意网络目标的通信）*关联的警报的 URL。*</span><span class="sxs-lookup"><span data-stu-id="2fbc4-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="2fbc4-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="2fbc4-357">down.esales360.cn</span></span>
<span data-ttu-id="2fbc4-358">accountName</span><span class="sxs-lookup"><span data-stu-id="2fbc4-358">accountName</span></span> | <span data-ttu-id="2fbc4-359">如果 entityType 为 User ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="2fbc4-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="2fbc4-360">testUser2</span></span>
<span data-ttu-id="2fbc4-361">domainName</span><span class="sxs-lookup"><span data-stu-id="2fbc4-361">domainName</span></span> | <span data-ttu-id="2fbc4-362">如果 entityType 为 User ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="2fbc4-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="2fbc4-363">europe.corp.contoso</span></span>
<span data-ttu-id="2fbc4-364">userSid</span><span class="sxs-lookup"><span data-stu-id="2fbc4-364">userSid</span></span> | <span data-ttu-id="2fbc4-365">如果 entityType 为 User ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="2fbc4-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="2fbc4-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="2fbc4-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-367">aadUserId</span></span> | <span data-ttu-id="2fbc4-368">如果 entityType 为 User ， *则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="2fbc4-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="2fbc4-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="2fbc4-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2fbc4-370">userPrincipalName</span></span> | <span data-ttu-id="2fbc4-371">如果 entityType 为 *User* / *MailBox* / *MailMessage，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="2fbc4-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fbc4-372">testUser2@contoso.com</span></span>
<span data-ttu-id="2fbc4-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="2fbc4-373">mailboxDisplayName</span></span> | <span data-ttu-id="2fbc4-374">如果 entityType 为 *MailBox ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="2fbc4-375">test User2</span><span class="sxs-lookup"><span data-stu-id="2fbc4-375">test User2</span></span>
<span data-ttu-id="2fbc4-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="2fbc4-376">mailboxAddress</span></span> | <span data-ttu-id="2fbc4-377">如果 entityType 为 *User* / *MailBox* / *MailMessage，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="2fbc4-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fbc4-378">testUser2@contoso.com</span></span>
<span data-ttu-id="2fbc4-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="2fbc4-379">clusterBy</span></span> | <span data-ttu-id="2fbc4-380">如果 entityType 为  *MailCluster，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="2fbc4-381">主题;P2SenderDomain;ContentType</span><span class="sxs-lookup"><span data-stu-id="2fbc4-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="2fbc4-382">sender</span><span class="sxs-lookup"><span data-stu-id="2fbc4-382">sender</span></span> | <span data-ttu-id="2fbc4-383">如果 entityType 为 *User* / *MailBox* / *MailMessage，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="2fbc4-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="2fbc4-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="2fbc4-385">recipient</span><span class="sxs-lookup"><span data-stu-id="2fbc4-385">recipient</span></span> | <span data-ttu-id="2fbc4-386">如果 entityType 为 *MailMessage ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="2fbc4-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fbc4-387">testUser2@contoso.com</span></span>
<span data-ttu-id="2fbc4-388">subject</span><span class="sxs-lookup"><span data-stu-id="2fbc4-388">subject</span></span> | <span data-ttu-id="2fbc4-389">如果 entityType 为 *MailMessage ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="2fbc4-390">\[外部 \] 关注</span><span class="sxs-lookup"><span data-stu-id="2fbc4-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="2fbc4-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="2fbc4-391">deliveryAction</span></span> | <span data-ttu-id="2fbc4-392">如果 entityType 为 *MailMessage ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="2fbc4-393">已传递</span><span class="sxs-lookup"><span data-stu-id="2fbc4-393">Delivered</span></span>
<span data-ttu-id="2fbc4-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-394">securityGroupId</span></span> | <span data-ttu-id="2fbc4-395">如果 entityType 为  *SecurityGroup，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="2fbc4-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="2fbc4-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="2fbc4-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="2fbc4-397">securityGroupName</span></span> | <span data-ttu-id="2fbc4-398">如果 entityType 为  *SecurityGroup，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="2fbc4-399">网络配置运算符</span><span class="sxs-lookup"><span data-stu-id="2fbc4-399">Network Configuration Operators</span></span>
<span data-ttu-id="2fbc4-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="2fbc4-400">registryHive</span></span> | <span data-ttu-id="2fbc4-401">如果 entityType 为  *Registry ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="2fbc4-402">HKEY \_ 本地 \_ 计算机</span><span class="sxs-lookup"><span data-stu-id="2fbc4-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="2fbc4-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="2fbc4-403">registryKey</span></span> | <span data-ttu-id="2fbc4-404">如果 entityType 为  *Registry ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="2fbc4-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="2fbc4-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="2fbc4-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="2fbc4-406">registryValueType</span></span> | <span data-ttu-id="2fbc4-407">如果 entityType 为  *Registry ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="2fbc4-408">String</span><span class="sxs-lookup"><span data-stu-id="2fbc4-408">String</span></span>
<span data-ttu-id="2fbc4-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="2fbc4-409">registryValue</span></span> | <span data-ttu-id="2fbc4-410">如果 entityType 为  *Registry ，则可用*。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="2fbc4-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="2fbc4-411">31-00-00-00</span></span>
<span data-ttu-id="2fbc4-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="2fbc4-412">deviceId</span></span> | <span data-ttu-id="2fbc4-413">与实体相关的设备的 ID（如果有）。</span><span class="sxs-lookup"><span data-stu-id="2fbc4-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="2fbc4-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="2fbc4-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="2fbc4-415">示例</span><span class="sxs-lookup"><span data-stu-id="2fbc4-415">Example</span></span>

<span data-ttu-id="2fbc4-416">**请求**</span><span class="sxs-lookup"><span data-stu-id="2fbc4-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="2fbc4-417">**响应**</span><span class="sxs-lookup"><span data-stu-id="2fbc4-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="2fbc4-418">相关文章</span><span class="sxs-lookup"><span data-stu-id="2fbc4-418">Related articles</span></span>

- [<span data-ttu-id="2fbc4-419">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="2fbc4-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="2fbc4-420">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="2fbc4-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="2fbc4-421">了解错误代码</span><span class="sxs-lookup"><span data-stu-id="2fbc4-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="2fbc4-422">事件概述</span><span class="sxs-lookup"><span data-stu-id="2fbc4-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="2fbc4-423">事件 API</span><span class="sxs-lookup"><span data-stu-id="2fbc4-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="2fbc4-424">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="2fbc4-424">Update incident API</span></span>](api-update-incidents.md)