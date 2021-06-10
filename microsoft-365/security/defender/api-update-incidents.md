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
ms.openlocfilehash: b50fe4672dd4cd721464c7414297efcc4a4921b7
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861499"
---
# <a name="update-incidents-api"></a><span data-ttu-id="25d22-104">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="25d22-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="25d22-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="25d22-105">**Applies to:**</span></span>

- [<span data-ttu-id="25d22-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25d22-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="25d22-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="25d22-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="25d22-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="25d22-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="25d22-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="25d22-109">API description</span></span>

<span data-ttu-id="25d22-110">更新现有事件的属性。</span><span class="sxs-lookup"><span data-stu-id="25d22-110">Updates properties of existing incident.</span></span> <span data-ttu-id="25d22-111">可更新的属性包括 ```status``` ```determination``` ```classification``` ：、、、、 ```assignedTo``` ```tags``` 和 ```comments``` 。</span><span class="sxs-lookup"><span data-stu-id="25d22-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="25d22-112">配额、资源分配和其他约束</span><span class="sxs-lookup"><span data-stu-id="25d22-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="25d22-113">在达到限制阈值之前，每分钟最多可以拨打 50 个呼叫或每小时 1500 个呼叫。</span><span class="sxs-lookup"><span data-stu-id="25d22-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="25d22-114">只有在设置为 `determination` `classification` TruePositive 时，才能设置该属性。</span><span class="sxs-lookup"><span data-stu-id="25d22-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="25d22-115">如果请求受到限制，它将返回 响应 `429` 代码。</span><span class="sxs-lookup"><span data-stu-id="25d22-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="25d22-116">响应正文将指示开始进行新呼叫的时间。</span><span class="sxs-lookup"><span data-stu-id="25d22-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="25d22-117">权限</span><span class="sxs-lookup"><span data-stu-id="25d22-117">Permissions</span></span>

<span data-ttu-id="25d22-118">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="25d22-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="25d22-119">若要了解更多信息，包括如何选择权限，请参阅访问[Microsoft 365 Defender API。](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="25d22-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="25d22-120">权限类型</span><span class="sxs-lookup"><span data-stu-id="25d22-120">Permission type</span></span> | <span data-ttu-id="25d22-121">权限</span><span class="sxs-lookup"><span data-stu-id="25d22-121">Permission</span></span> | <span data-ttu-id="25d22-122">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="25d22-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="25d22-123">应用程序</span><span class="sxs-lookup"><span data-stu-id="25d22-123">Application</span></span> | <span data-ttu-id="25d22-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="25d22-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="25d22-125">读取和写入所有事件</span><span class="sxs-lookup"><span data-stu-id="25d22-125">Read and write all incidents</span></span>
<span data-ttu-id="25d22-126">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="25d22-126">Delegated (work or school account)</span></span> | <span data-ttu-id="25d22-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="25d22-127">Incident.ReadWrite</span></span> | <span data-ttu-id="25d22-128">读取和写入事件</span><span class="sxs-lookup"><span data-stu-id="25d22-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="25d22-129">使用用户凭据获取令牌时，用户需要具有在门户中更新事件的权限。</span><span class="sxs-lookup"><span data-stu-id="25d22-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="25d22-130">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="25d22-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="25d22-131">请求标头</span><span class="sxs-lookup"><span data-stu-id="25d22-131">Request headers</span></span>

<span data-ttu-id="25d22-132">名称</span><span class="sxs-lookup"><span data-stu-id="25d22-132">Name</span></span> | <span data-ttu-id="25d22-133">类型</span><span class="sxs-lookup"><span data-stu-id="25d22-133">Type</span></span> | <span data-ttu-id="25d22-134">说明</span><span class="sxs-lookup"><span data-stu-id="25d22-134">Description</span></span>
-|-|-
<span data-ttu-id="25d22-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="25d22-135">Authorization</span></span> | <span data-ttu-id="25d22-136">String</span><span class="sxs-lookup"><span data-stu-id="25d22-136">String</span></span> | <span data-ttu-id="25d22-137">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="25d22-137">Bearer {token}.</span></span> <span data-ttu-id="25d22-138">**必需**。</span><span class="sxs-lookup"><span data-stu-id="25d22-138">**Required**.</span></span>
<span data-ttu-id="25d22-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="25d22-139">Content-Type</span></span> | <span data-ttu-id="25d22-140">String</span><span class="sxs-lookup"><span data-stu-id="25d22-140">String</span></span> | <span data-ttu-id="25d22-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="25d22-141">application/json.</span></span> <span data-ttu-id="25d22-142">**必需**。</span><span class="sxs-lookup"><span data-stu-id="25d22-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="25d22-143">请求正文</span><span class="sxs-lookup"><span data-stu-id="25d22-143">Request body</span></span>

<span data-ttu-id="25d22-144">在请求正文中，提供应更新的字段的值。</span><span class="sxs-lookup"><span data-stu-id="25d22-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="25d22-145">请求正文中未包含的现有属性将保留其值，除非由于相关值更改而必须重新计算它们。</span><span class="sxs-lookup"><span data-stu-id="25d22-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="25d22-146">为获得最佳性能，应省略尚未更改的现有值。</span><span class="sxs-lookup"><span data-stu-id="25d22-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="25d22-147">属性</span><span class="sxs-lookup"><span data-stu-id="25d22-147">Property</span></span> | <span data-ttu-id="25d22-148">类型</span><span class="sxs-lookup"><span data-stu-id="25d22-148">Type</span></span> | <span data-ttu-id="25d22-149">说明</span><span class="sxs-lookup"><span data-stu-id="25d22-149">Description</span></span>
-|-|-
<span data-ttu-id="25d22-150">状态</span><span class="sxs-lookup"><span data-stu-id="25d22-150">status</span></span> | <span data-ttu-id="25d22-151">枚举</span><span class="sxs-lookup"><span data-stu-id="25d22-151">Enum</span></span> | <span data-ttu-id="25d22-152">指定事件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="25d22-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="25d22-153">可能的值是 ```Active``` ：、 ```Resolved``` 和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="25d22-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="25d22-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="25d22-154">assignedTo</span></span> | <span data-ttu-id="25d22-155">string</span><span class="sxs-lookup"><span data-stu-id="25d22-155">string</span></span> | <span data-ttu-id="25d22-156">事件的所有者。</span><span class="sxs-lookup"><span data-stu-id="25d22-156">Owner of the incident.</span></span>
<span data-ttu-id="25d22-157">classification</span><span class="sxs-lookup"><span data-stu-id="25d22-157">classification</span></span> | <span data-ttu-id="25d22-158">枚举</span><span class="sxs-lookup"><span data-stu-id="25d22-158">Enum</span></span> | <span data-ttu-id="25d22-159">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="25d22-159">Specification of the incident.</span></span> <span data-ttu-id="25d22-160">可取值为：```Unknown```、```FalsePositive```、```TruePositive```。</span><span class="sxs-lookup"><span data-stu-id="25d22-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="25d22-161">确定</span><span class="sxs-lookup"><span data-stu-id="25d22-161">determination</span></span> | <span data-ttu-id="25d22-162">枚举</span><span class="sxs-lookup"><span data-stu-id="25d22-162">Enum</span></span> | <span data-ttu-id="25d22-163">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="25d22-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="25d22-164">可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。</span><span class="sxs-lookup"><span data-stu-id="25d22-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="25d22-165">tags</span><span class="sxs-lookup"><span data-stu-id="25d22-165">tags</span></span> | <span data-ttu-id="25d22-166">字符串列表</span><span class="sxs-lookup"><span data-stu-id="25d22-166">string List</span></span> | <span data-ttu-id="25d22-167">事件标记列表。</span><span class="sxs-lookup"><span data-stu-id="25d22-167">List of Incident tags.</span></span>
<span data-ttu-id="25d22-168">comment</span><span class="sxs-lookup"><span data-stu-id="25d22-168">comment</span></span> | <span data-ttu-id="25d22-169">string</span><span class="sxs-lookup"><span data-stu-id="25d22-169">string</span></span> | <span data-ttu-id="25d22-170">要添加到事件的注释。</span><span class="sxs-lookup"><span data-stu-id="25d22-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="25d22-171">响应</span><span class="sxs-lookup"><span data-stu-id="25d22-171">Response</span></span>

<span data-ttu-id="25d22-172">如果成功，此方法返回 `200 OK` 。</span><span class="sxs-lookup"><span data-stu-id="25d22-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="25d22-173">响应正文将包含具有更新属性的事件实体。</span><span class="sxs-lookup"><span data-stu-id="25d22-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="25d22-174">如果未找到具有指定 ID 的事件，该方法将返回 `404 Not Found` 。</span><span class="sxs-lookup"><span data-stu-id="25d22-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="25d22-175">示例</span><span class="sxs-lookup"><span data-stu-id="25d22-175">Example</span></span>

<span data-ttu-id="25d22-176">**请求**</span><span class="sxs-lookup"><span data-stu-id="25d22-176">**Request**</span></span>

<span data-ttu-id="25d22-177">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="25d22-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="25d22-178">**响应**</span><span class="sxs-lookup"><span data-stu-id="25d22-178">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a><span data-ttu-id="25d22-179">相关文章</span><span class="sxs-lookup"><span data-stu-id="25d22-179">Related articles</span></span>

- [<span data-ttu-id="25d22-180">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="25d22-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="25d22-181">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="25d22-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="25d22-182">了解错误代码</span><span class="sxs-lookup"><span data-stu-id="25d22-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="25d22-183">事件 API</span><span class="sxs-lookup"><span data-stu-id="25d22-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="25d22-184">列出事件</span><span class="sxs-lookup"><span data-stu-id="25d22-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="25d22-185">事件概述</span><span class="sxs-lookup"><span data-stu-id="25d22-185">Incidents overview</span></span>](incidents-overview.md)
