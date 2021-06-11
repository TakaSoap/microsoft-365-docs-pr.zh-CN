---
title: Microsoft 365Defender 事件 API 和事件资源类型
description: 了解 Microsoft 365 Defender 中的事件资源类型的方法和属性
keywords: 事件， 事件， api
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
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888429"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="d1906-104">Microsoft 365Defender 事件 API 和事件资源类型</span><span class="sxs-lookup"><span data-stu-id="d1906-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d1906-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d1906-105">**Applies to:**</span></span>

- [<span data-ttu-id="d1906-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1906-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="d1906-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="d1906-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d1906-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="d1906-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d1906-109">[事件](incidents-overview.md)是帮助描述攻击的相关警报的集合。</span><span class="sxs-lookup"><span data-stu-id="d1906-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="d1906-110">来自组织中不同实体的事件由 Defender 自动Microsoft 365聚合。</span><span class="sxs-lookup"><span data-stu-id="d1906-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="d1906-111">可以使用事件 API 以编程方式访问组织的事件和相关警报。</span><span class="sxs-lookup"><span data-stu-id="d1906-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="d1906-112">配额和资源分配</span><span class="sxs-lookup"><span data-stu-id="d1906-112">Quotas and resource allocation</span></span>

<span data-ttu-id="d1906-113">每分钟最多可以请求 50 个呼叫或每小时 1500 个呼叫。</span><span class="sxs-lookup"><span data-stu-id="d1906-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="d1906-114">每个方法也有其自己的配额。</span><span class="sxs-lookup"><span data-stu-id="d1906-114">Each method also has its own quotas.</span></span> <span data-ttu-id="d1906-115">有关特定于方法的配额的信息，请参阅想要使用的方法各自的文章。</span><span class="sxs-lookup"><span data-stu-id="d1906-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="d1906-116">HTTP 响应代码指示你已按发送的请求数或按分配的运行时间 `429` 达到配额。</span><span class="sxs-lookup"><span data-stu-id="d1906-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="d1906-117">响应正文将包括重置达到的配额之前的时间。</span><span class="sxs-lookup"><span data-stu-id="d1906-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="d1906-118">权限</span><span class="sxs-lookup"><span data-stu-id="d1906-118">Permissions</span></span>

<span data-ttu-id="d1906-119">事件 API 需要针对其每个方法的不同类型的权限。</span><span class="sxs-lookup"><span data-stu-id="d1906-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="d1906-120">有关所需权限详细信息，请参阅相应方法的文章。</span><span class="sxs-lookup"><span data-stu-id="d1906-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="d1906-121">方法</span><span class="sxs-lookup"><span data-stu-id="d1906-121">Methods</span></span>

<span data-ttu-id="d1906-122">方法</span><span class="sxs-lookup"><span data-stu-id="d1906-122">Method</span></span> | <span data-ttu-id="d1906-123">返回类型</span><span class="sxs-lookup"><span data-stu-id="d1906-123">Return Type</span></span> | <span data-ttu-id="d1906-124">说明</span><span class="sxs-lookup"><span data-stu-id="d1906-124">Description</span></span>
-|-|-
[<span data-ttu-id="d1906-125">列出事件</span><span class="sxs-lookup"><span data-stu-id="d1906-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="d1906-126">[事件](api-incident.md) 列表</span><span class="sxs-lookup"><span data-stu-id="d1906-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="d1906-127">获取事件列表。</span><span class="sxs-lookup"><span data-stu-id="d1906-127">Get a list of incidents.</span></span>
[<span data-ttu-id="d1906-128">更新事件</span><span class="sxs-lookup"><span data-stu-id="d1906-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="d1906-129">事件</span><span class="sxs-lookup"><span data-stu-id="d1906-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="d1906-130">更新特定事件。</span><span class="sxs-lookup"><span data-stu-id="d1906-130">Update a specific incident.</span></span>
[<span data-ttu-id="d1906-131">获取事件</span><span class="sxs-lookup"><span data-stu-id="d1906-131">Get incident</span></span>](api-get-incident.md) | [<span data-ttu-id="d1906-132">事件</span><span class="sxs-lookup"><span data-stu-id="d1906-132">Incident</span></span>](api-incident.md) | <span data-ttu-id="d1906-133">获取单个事件。</span><span class="sxs-lookup"><span data-stu-id="d1906-133">Get a single incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="d1906-134">请求正文、响应和示例</span><span class="sxs-lookup"><span data-stu-id="d1906-134">Request body, response, and examples</span></span>

<span data-ttu-id="d1906-135">请参阅各自的方法文章，了解有关如何构造请求或分析响应的更多详细信息，以及实际示例。</span><span class="sxs-lookup"><span data-stu-id="d1906-135">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="d1906-136">通用属性</span><span class="sxs-lookup"><span data-stu-id="d1906-136">Common properties</span></span>

<span data-ttu-id="d1906-137">属性</span><span class="sxs-lookup"><span data-stu-id="d1906-137">Property</span></span> | <span data-ttu-id="d1906-138">类型</span><span class="sxs-lookup"><span data-stu-id="d1906-138">Type</span></span> | <span data-ttu-id="d1906-139">说明</span><span class="sxs-lookup"><span data-stu-id="d1906-139">Description</span></span>
-|-|-
<span data-ttu-id="d1906-140">incidentId</span><span class="sxs-lookup"><span data-stu-id="d1906-140">incidentId</span></span> | <span data-ttu-id="d1906-141">long</span><span class="sxs-lookup"><span data-stu-id="d1906-141">long</span></span> | <span data-ttu-id="d1906-142">事件唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="d1906-142">Incident unique ID.</span></span>
<span data-ttu-id="d1906-143">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="d1906-143">redirectIncidentId</span></span> | <span data-ttu-id="d1906-144">nullable long</span><span class="sxs-lookup"><span data-stu-id="d1906-144">nullable long</span></span> | <span data-ttu-id="d1906-145">当前事件合并到的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="d1906-145">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="d1906-146">incidentName</span><span class="sxs-lookup"><span data-stu-id="d1906-146">incidentName</span></span> | <span data-ttu-id="d1906-147">string</span><span class="sxs-lookup"><span data-stu-id="d1906-147">string</span></span> | <span data-ttu-id="d1906-148">事件的名称。</span><span class="sxs-lookup"><span data-stu-id="d1906-148">The name of the Incident.</span></span>
<span data-ttu-id="d1906-149">createdTime</span><span class="sxs-lookup"><span data-stu-id="d1906-149">createdTime</span></span> | <span data-ttu-id="d1906-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d1906-150">DateTimeOffset</span></span> | <span data-ttu-id="d1906-151">创建事件时 (UTC) 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="d1906-151">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="d1906-152">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="d1906-152">lastUpdateTime</span></span> | <span data-ttu-id="d1906-153">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d1906-153">DateTimeOffset</span></span> | <span data-ttu-id="d1906-154">上次更新事件 (UTC) 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="d1906-154">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="d1906-155">assignedTo</span><span class="sxs-lookup"><span data-stu-id="d1906-155">assignedTo</span></span> | <span data-ttu-id="d1906-156">string</span><span class="sxs-lookup"><span data-stu-id="d1906-156">string</span></span> | <span data-ttu-id="d1906-157">事件的所有者。</span><span class="sxs-lookup"><span data-stu-id="d1906-157">Owner of the Incident.</span></span>
<span data-ttu-id="d1906-158">severity</span><span class="sxs-lookup"><span data-stu-id="d1906-158">severity</span></span> | <span data-ttu-id="d1906-159">枚举</span><span class="sxs-lookup"><span data-stu-id="d1906-159">Enum</span></span> | <span data-ttu-id="d1906-160">事件的严重性。</span><span class="sxs-lookup"><span data-stu-id="d1906-160">Severity of the Incident.</span></span> <span data-ttu-id="d1906-161">可能的值是 ```UnSpecified``` ```Informational``` ```Low``` ：、、、 ```Medium``` 和 ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="d1906-161">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="d1906-162">状态</span><span class="sxs-lookup"><span data-stu-id="d1906-162">status</span></span> | <span data-ttu-id="d1906-163">枚举</span><span class="sxs-lookup"><span data-stu-id="d1906-163">Enum</span></span> | <span data-ttu-id="d1906-164">指定事件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="d1906-164">Specifies the current status of the incident.</span></span> <span data-ttu-id="d1906-165">可能的值是 ```Active``` ：、 ```Resolved``` 和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="d1906-165">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="d1906-166">classification</span><span class="sxs-lookup"><span data-stu-id="d1906-166">classification</span></span> | <span data-ttu-id="d1906-167">枚举</span><span class="sxs-lookup"><span data-stu-id="d1906-167">Enum</span></span> | <span data-ttu-id="d1906-168">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="d1906-168">Specification of the incident.</span></span> <span data-ttu-id="d1906-169">可取值为：```Unknown```、```FalsePositive```、```TruePositive```。</span><span class="sxs-lookup"><span data-stu-id="d1906-169">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="d1906-170">确定</span><span class="sxs-lookup"><span data-stu-id="d1906-170">determination</span></span> | <span data-ttu-id="d1906-171">枚举</span><span class="sxs-lookup"><span data-stu-id="d1906-171">Enum</span></span> | <span data-ttu-id="d1906-172">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="d1906-172">Specifies the determination of the incident.</span></span> <span data-ttu-id="d1906-173">可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。</span><span class="sxs-lookup"><span data-stu-id="d1906-173">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="d1906-174">标记</span><span class="sxs-lookup"><span data-stu-id="d1906-174">tags</span></span> | <span data-ttu-id="d1906-175">字符串列表</span><span class="sxs-lookup"><span data-stu-id="d1906-175">string List</span></span> | <span data-ttu-id="d1906-176">事件标记列表。</span><span class="sxs-lookup"><span data-stu-id="d1906-176">List of Incident tags.</span></span>
<span data-ttu-id="d1906-177">comments</span><span class="sxs-lookup"><span data-stu-id="d1906-177">comments</span></span> | <span data-ttu-id="d1906-178">事件注释列表</span><span class="sxs-lookup"><span data-stu-id="d1906-178">List of incident comments</span></span> | <span data-ttu-id="d1906-179">事件注释对象包含：注释字符串、createdBy 字符串和 createTime 日期时间。</span><span class="sxs-lookup"><span data-stu-id="d1906-179">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="d1906-180">警报</span><span class="sxs-lookup"><span data-stu-id="d1906-180">alerts</span></span> | <span data-ttu-id="d1906-181">警报列表</span><span class="sxs-lookup"><span data-stu-id="d1906-181">Alert List</span></span> | <span data-ttu-id="d1906-182">相关警报列表。</span><span class="sxs-lookup"><span data-stu-id="d1906-182">List of related alerts.</span></span> <span data-ttu-id="d1906-183">请参阅列表事件 API [文档](api-list-incidents.md) 的示例。</span><span class="sxs-lookup"><span data-stu-id="d1906-183">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d1906-184">相关文章</span><span class="sxs-lookup"><span data-stu-id="d1906-184">Related articles</span></span>

- [<span data-ttu-id="d1906-185">Microsoft 365Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="d1906-185">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="d1906-186">事件概述</span><span class="sxs-lookup"><span data-stu-id="d1906-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d1906-187">列出事件 API</span><span class="sxs-lookup"><span data-stu-id="d1906-187">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="d1906-188">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="d1906-188">Update incident API</span></span>](api-update-incidents.md)
