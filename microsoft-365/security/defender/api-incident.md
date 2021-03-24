---
title: Microsoft 365 Defender 事件 API 和事件资源类型
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
ms.openlocfilehash: 0a9022c0448ae0ddc16dc996ca93075abf6b2857
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054610"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="aaa8f-104">Microsoft 365 Defender 事件 API 和事件资源类型</span><span class="sxs-lookup"><span data-stu-id="aaa8f-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="aaa8f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="aaa8f-105">**Applies to:**</span></span>

- <span data-ttu-id="aaa8f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aaa8f-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aaa8f-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="aaa8f-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="aaa8f-109">[事件](incidents-overview.md)是帮助描述攻击的相关警报的集合。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="aaa8f-110">来自组织中不同实体的事件由 Microsoft 365 Defender 自动聚合。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="aaa8f-111">可以使用事件 API 以编程方式访问组织的事件和相关警报。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="aaa8f-112">配额和资源分配</span><span class="sxs-lookup"><span data-stu-id="aaa8f-112">Quotas and resource allocation</span></span>

<span data-ttu-id="aaa8f-113">每分钟最多可以请求 50 个呼叫或每小时 1500 个呼叫。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="aaa8f-114">每个方法也有其自己的配额。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-114">Each method also has its own quotas.</span></span> <span data-ttu-id="aaa8f-115">有关特定于方法的配额的信息，请参阅想要使用的方法各自的文章。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="aaa8f-116">HTTP 响应代码指示你已按发送的请求数或按分配的运行时间 `429` 达到配额。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="aaa8f-117">响应正文将包括重置达到的配额之前的时间。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="aaa8f-118">权限</span><span class="sxs-lookup"><span data-stu-id="aaa8f-118">Permissions</span></span>

<span data-ttu-id="aaa8f-119">事件 API 需要针对其每个方法的不同类型的权限。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="aaa8f-120">有关所需权限详细信息，请参阅相应方法的文章。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="aaa8f-121">方法</span><span class="sxs-lookup"><span data-stu-id="aaa8f-121">Methods</span></span>

<span data-ttu-id="aaa8f-122">方法</span><span class="sxs-lookup"><span data-stu-id="aaa8f-122">Method</span></span> | <span data-ttu-id="aaa8f-123">返回类型</span><span class="sxs-lookup"><span data-stu-id="aaa8f-123">Return Type</span></span> | <span data-ttu-id="aaa8f-124">说明</span><span class="sxs-lookup"><span data-stu-id="aaa8f-124">Description</span></span>
-|-|-
[<span data-ttu-id="aaa8f-125">列出事件</span><span class="sxs-lookup"><span data-stu-id="aaa8f-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="aaa8f-126">[事件](api-incident.md) 列表</span><span class="sxs-lookup"><span data-stu-id="aaa8f-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="aaa8f-127">获取事件列表。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-127">Get a list of incidents.</span></span>
[<span data-ttu-id="aaa8f-128">更新事件</span><span class="sxs-lookup"><span data-stu-id="aaa8f-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="aaa8f-129">事件</span><span class="sxs-lookup"><span data-stu-id="aaa8f-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="aaa8f-130">更新特定事件。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="aaa8f-131">请求正文、响应和示例</span><span class="sxs-lookup"><span data-stu-id="aaa8f-131">Request body, response, and examples</span></span>

<span data-ttu-id="aaa8f-132">请参阅各自的方法文章，了解有关如何构造请求或分析响应的更多详细信息，以及实际示例。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="aaa8f-133">通用属性</span><span class="sxs-lookup"><span data-stu-id="aaa8f-133">Common properties</span></span>

<span data-ttu-id="aaa8f-134">属性</span><span class="sxs-lookup"><span data-stu-id="aaa8f-134">Property</span></span> | <span data-ttu-id="aaa8f-135">类型</span><span class="sxs-lookup"><span data-stu-id="aaa8f-135">Type</span></span> | <span data-ttu-id="aaa8f-136">说明</span><span class="sxs-lookup"><span data-stu-id="aaa8f-136">Description</span></span>
-|-|-
<span data-ttu-id="aaa8f-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="aaa8f-137">incidentId</span></span> | <span data-ttu-id="aaa8f-138">long</span><span class="sxs-lookup"><span data-stu-id="aaa8f-138">long</span></span> | <span data-ttu-id="aaa8f-139">事件唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-139">Incident unique ID.</span></span>
<span data-ttu-id="aaa8f-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="aaa8f-140">redirectIncidentId</span></span> | <span data-ttu-id="aaa8f-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="aaa8f-141">nullable long</span></span> | <span data-ttu-id="aaa8f-142">当前事件合并到的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="aaa8f-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="aaa8f-143">incidentName</span></span> | <span data-ttu-id="aaa8f-144">string</span><span class="sxs-lookup"><span data-stu-id="aaa8f-144">string</span></span> | <span data-ttu-id="aaa8f-145">事件的名称。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-145">The name of the Incident.</span></span>
<span data-ttu-id="aaa8f-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="aaa8f-146">createdTime</span></span> | <span data-ttu-id="aaa8f-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="aaa8f-147">DateTimeOffset</span></span> | <span data-ttu-id="aaa8f-148">创建事件时 (UTC) 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="aaa8f-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="aaa8f-149">lastUpdateTime</span></span> | <span data-ttu-id="aaa8f-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="aaa8f-150">DateTimeOffset</span></span> | <span data-ttu-id="aaa8f-151">上次更新事件 (UTC) 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="aaa8f-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="aaa8f-152">assignedTo</span></span> | <span data-ttu-id="aaa8f-153">string</span><span class="sxs-lookup"><span data-stu-id="aaa8f-153">string</span></span> | <span data-ttu-id="aaa8f-154">事件的所有者。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-154">Owner of the Incident.</span></span>
<span data-ttu-id="aaa8f-155">severity</span><span class="sxs-lookup"><span data-stu-id="aaa8f-155">severity</span></span> | <span data-ttu-id="aaa8f-156">枚举</span><span class="sxs-lookup"><span data-stu-id="aaa8f-156">Enum</span></span> | <span data-ttu-id="aaa8f-157">事件的严重性。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-157">Severity of the Incident.</span></span> <span data-ttu-id="aaa8f-158">可能的值是 ```UnSpecified``` ```Informational``` ```Low``` ：、、、 ```Medium``` 和 ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="aaa8f-159">状态</span><span class="sxs-lookup"><span data-stu-id="aaa8f-159">status</span></span> | <span data-ttu-id="aaa8f-160">枚举</span><span class="sxs-lookup"><span data-stu-id="aaa8f-160">Enum</span></span> | <span data-ttu-id="aaa8f-161">指定事件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="aaa8f-162">可能的值是 ```Active``` ：、 ```Resolved``` 和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="aaa8f-163">classification</span><span class="sxs-lookup"><span data-stu-id="aaa8f-163">classification</span></span> | <span data-ttu-id="aaa8f-164">枚举</span><span class="sxs-lookup"><span data-stu-id="aaa8f-164">Enum</span></span> | <span data-ttu-id="aaa8f-165">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-165">Specification of the incident.</span></span> <span data-ttu-id="aaa8f-166">可取值为：```Unknown```、```FalsePositive```、```TruePositive```。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="aaa8f-167">确定</span><span class="sxs-lookup"><span data-stu-id="aaa8f-167">determination</span></span> | <span data-ttu-id="aaa8f-168">枚举</span><span class="sxs-lookup"><span data-stu-id="aaa8f-168">Enum</span></span> | <span data-ttu-id="aaa8f-169">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="aaa8f-170">可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="aaa8f-171">tags</span><span class="sxs-lookup"><span data-stu-id="aaa8f-171">tags</span></span> | <span data-ttu-id="aaa8f-172">字符串列表</span><span class="sxs-lookup"><span data-stu-id="aaa8f-172">string List</span></span> | <span data-ttu-id="aaa8f-173">事件标记列表。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-173">List of Incident tags.</span></span>
<span data-ttu-id="aaa8f-174">警报</span><span class="sxs-lookup"><span data-stu-id="aaa8f-174">alerts</span></span> | <span data-ttu-id="aaa8f-175">警报列表</span><span class="sxs-lookup"><span data-stu-id="aaa8f-175">Alert List</span></span> | <span data-ttu-id="aaa8f-176">相关警报列表。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-176">List of related alerts.</span></span> <span data-ttu-id="aaa8f-177">请参阅列表事件 API [文档](api-list-incidents.md) 的示例。</span><span class="sxs-lookup"><span data-stu-id="aaa8f-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="aaa8f-178">相关文章</span><span class="sxs-lookup"><span data-stu-id="aaa8f-178">Related articles</span></span>

- [<span data-ttu-id="aaa8f-179">Microsoft 365 Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="aaa8f-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="aaa8f-180">事件概述</span><span class="sxs-lookup"><span data-stu-id="aaa8f-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="aaa8f-181">列出事件 API</span><span class="sxs-lookup"><span data-stu-id="aaa8f-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="aaa8f-182">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="aaa8f-182">Update incident API</span></span>](api-update-incidents.md)
