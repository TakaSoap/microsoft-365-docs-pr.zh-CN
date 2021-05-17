---
title: 更新事件 API
description: 了解如何使用 Microsoft 365 Defender API 更新事件
keywords: 更新， api， 事件
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
ms.openlocfilehash: d6872a7a4b1b2d2c131066076af02a65b4ef6d8a
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107600"
---
# <a name="update-incidents-api"></a><span data-ttu-id="e448c-104">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="e448c-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e448c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e448c-105">**Applies to:**</span></span>

- <span data-ttu-id="e448c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e448c-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e448c-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="e448c-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e448c-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="e448c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="e448c-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="e448c-109">API description</span></span>

<span data-ttu-id="e448c-110">更新现有事件的属性。</span><span class="sxs-lookup"><span data-stu-id="e448c-110">Updates properties of existing incident.</span></span> <span data-ttu-id="e448c-111">可更新的属性包括 ```status``` ```determination``` ```classification``` ：、、、 ```assignedTo``` 和 ```tags``` 。</span><span class="sxs-lookup"><span data-stu-id="e448c-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="e448c-112">配额、资源分配和其他约束</span><span class="sxs-lookup"><span data-stu-id="e448c-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="e448c-113">在达到限制阈值之前，每分钟最多可以拨打 50 个呼叫或每小时 1500 个呼叫。</span><span class="sxs-lookup"><span data-stu-id="e448c-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="e448c-114">只有在设置为 `determination` `classification` TruePositive 时，才能设置该属性。</span><span class="sxs-lookup"><span data-stu-id="e448c-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="e448c-115">如果请求受到限制，它将返回 响应 `429` 代码。</span><span class="sxs-lookup"><span data-stu-id="e448c-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="e448c-116">响应正文将指示开始进行新呼叫的时间。</span><span class="sxs-lookup"><span data-stu-id="e448c-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="e448c-117">权限</span><span class="sxs-lookup"><span data-stu-id="e448c-117">Permissions</span></span>

<span data-ttu-id="e448c-118">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="e448c-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e448c-119">若要了解更多信息，包括如何选择权限，请参阅访问[Microsoft 365 Defender API。](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="e448c-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="e448c-120">权限类型</span><span class="sxs-lookup"><span data-stu-id="e448c-120">Permission type</span></span> | <span data-ttu-id="e448c-121">权限</span><span class="sxs-lookup"><span data-stu-id="e448c-121">Permission</span></span> | <span data-ttu-id="e448c-122">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="e448c-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="e448c-123">应用程序</span><span class="sxs-lookup"><span data-stu-id="e448c-123">Application</span></span> | <span data-ttu-id="e448c-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e448c-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="e448c-125">读取和写入所有事件</span><span class="sxs-lookup"><span data-stu-id="e448c-125">Read and write all incidents</span></span>
<span data-ttu-id="e448c-126">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="e448c-126">Delegated (work or school account)</span></span> | <span data-ttu-id="e448c-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e448c-127">Incident.ReadWrite</span></span> | <span data-ttu-id="e448c-128">读取和写入事件</span><span class="sxs-lookup"><span data-stu-id="e448c-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="e448c-129">使用用户凭据获取令牌时，用户需要具有在门户中更新事件的权限。</span><span class="sxs-lookup"><span data-stu-id="e448c-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="e448c-130">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="e448c-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="e448c-131">请求标头</span><span class="sxs-lookup"><span data-stu-id="e448c-131">Request headers</span></span>

<span data-ttu-id="e448c-132">名称</span><span class="sxs-lookup"><span data-stu-id="e448c-132">Name</span></span> | <span data-ttu-id="e448c-133">类型</span><span class="sxs-lookup"><span data-stu-id="e448c-133">Type</span></span> | <span data-ttu-id="e448c-134">说明</span><span class="sxs-lookup"><span data-stu-id="e448c-134">Description</span></span>
-|-|-
<span data-ttu-id="e448c-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="e448c-135">Authorization</span></span> | <span data-ttu-id="e448c-136">String</span><span class="sxs-lookup"><span data-stu-id="e448c-136">String</span></span> | <span data-ttu-id="e448c-137">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="e448c-137">Bearer {token}.</span></span> <span data-ttu-id="e448c-138">**必需**。</span><span class="sxs-lookup"><span data-stu-id="e448c-138">**Required**.</span></span>
<span data-ttu-id="e448c-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e448c-139">Content-Type</span></span> | <span data-ttu-id="e448c-140">String</span><span class="sxs-lookup"><span data-stu-id="e448c-140">String</span></span> | <span data-ttu-id="e448c-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="e448c-141">application/json.</span></span> <span data-ttu-id="e448c-142">**必需**。</span><span class="sxs-lookup"><span data-stu-id="e448c-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e448c-143">请求正文</span><span class="sxs-lookup"><span data-stu-id="e448c-143">Request body</span></span>

<span data-ttu-id="e448c-144">在请求正文中，提供应更新的字段的值。</span><span class="sxs-lookup"><span data-stu-id="e448c-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="e448c-145">请求正文中未包含的现有属性将保留其值，除非由于相关值更改而必须重新计算它们。</span><span class="sxs-lookup"><span data-stu-id="e448c-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="e448c-146">为获得最佳性能，应省略尚未更改的现有值。</span><span class="sxs-lookup"><span data-stu-id="e448c-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="e448c-147">属性</span><span class="sxs-lookup"><span data-stu-id="e448c-147">Property</span></span> | <span data-ttu-id="e448c-148">类型</span><span class="sxs-lookup"><span data-stu-id="e448c-148">Type</span></span> | <span data-ttu-id="e448c-149">说明</span><span class="sxs-lookup"><span data-stu-id="e448c-149">Description</span></span>
-|-|-
<span data-ttu-id="e448c-150">状态</span><span class="sxs-lookup"><span data-stu-id="e448c-150">status</span></span> | <span data-ttu-id="e448c-151">枚举</span><span class="sxs-lookup"><span data-stu-id="e448c-151">Enum</span></span> | <span data-ttu-id="e448c-152">指定事件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="e448c-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="e448c-153">可能的值是 ```Active``` ：、 ```Resolved``` 和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="e448c-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="e448c-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="e448c-154">assignedTo</span></span> | <span data-ttu-id="e448c-155">string</span><span class="sxs-lookup"><span data-stu-id="e448c-155">string</span></span> | <span data-ttu-id="e448c-156">事件的所有者。</span><span class="sxs-lookup"><span data-stu-id="e448c-156">Owner of the incident.</span></span>
<span data-ttu-id="e448c-157">classification</span><span class="sxs-lookup"><span data-stu-id="e448c-157">classification</span></span> | <span data-ttu-id="e448c-158">枚举</span><span class="sxs-lookup"><span data-stu-id="e448c-158">Enum</span></span> | <span data-ttu-id="e448c-159">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="e448c-159">Specification of the incident.</span></span> <span data-ttu-id="e448c-160">可取值为：```Unknown```、```FalsePositive```、```TruePositive```。</span><span class="sxs-lookup"><span data-stu-id="e448c-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="e448c-161">确定</span><span class="sxs-lookup"><span data-stu-id="e448c-161">determination</span></span> | <span data-ttu-id="e448c-162">枚举</span><span class="sxs-lookup"><span data-stu-id="e448c-162">Enum</span></span> | <span data-ttu-id="e448c-163">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="e448c-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="e448c-164">可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。</span><span class="sxs-lookup"><span data-stu-id="e448c-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="e448c-165">tags</span><span class="sxs-lookup"><span data-stu-id="e448c-165">tags</span></span> | <span data-ttu-id="e448c-166">字符串列表</span><span class="sxs-lookup"><span data-stu-id="e448c-166">string List</span></span> | <span data-ttu-id="e448c-167">事件标记列表。</span><span class="sxs-lookup"><span data-stu-id="e448c-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="e448c-168">响应</span><span class="sxs-lookup"><span data-stu-id="e448c-168">Response</span></span>

<span data-ttu-id="e448c-169">如果成功，此方法返回 `200 OK` 。</span><span class="sxs-lookup"><span data-stu-id="e448c-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="e448c-170">响应正文将包含具有更新属性的事件实体。</span><span class="sxs-lookup"><span data-stu-id="e448c-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="e448c-171">如果未找到具有指定 ID 的事件，该方法将返回 `404 Not Found` 。</span><span class="sxs-lookup"><span data-stu-id="e448c-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="e448c-172">示例</span><span class="sxs-lookup"><span data-stu-id="e448c-172">Example</span></span>

<span data-ttu-id="e448c-173">**请求**</span><span class="sxs-lookup"><span data-stu-id="e448c-173">**Request**</span></span>

<span data-ttu-id="e448c-174">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="e448c-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="e448c-175">**响应**</span><span class="sxs-lookup"><span data-stu-id="e448c-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="e448c-176">相关文章</span><span class="sxs-lookup"><span data-stu-id="e448c-176">Related articles</span></span>

- [<span data-ttu-id="e448c-177">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="e448c-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="e448c-178">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="e448c-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="e448c-179">了解错误代码</span><span class="sxs-lookup"><span data-stu-id="e448c-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="e448c-180">事件 API</span><span class="sxs-lookup"><span data-stu-id="e448c-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="e448c-181">列出事件</span><span class="sxs-lookup"><span data-stu-id="e448c-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="e448c-182">事件概述</span><span class="sxs-lookup"><span data-stu-id="e448c-182">Incidents overview</span></span>](incidents-overview.md)
