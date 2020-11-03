---
title: 更新事件 API
description: 了解如何使用 Microsoft 365 Defender API 更新事件
keywords: 更新、api、事件
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3f77980863b0c232166d736a6b557444df98c8ac
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844832"
---
# <a name="update-incidents-api"></a><span data-ttu-id="52ded-104">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="52ded-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="52ded-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="52ded-105">**Applies to:**</span></span>
- <span data-ttu-id="52ded-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52ded-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="52ded-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="52ded-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="52ded-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="52ded-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="52ded-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="52ded-109">API description</span></span>
<span data-ttu-id="52ded-110">更新现有事件的属性。</span><span class="sxs-lookup"><span data-stu-id="52ded-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="52ded-111">可更新属性包括 ```status``` ： ```determination``` 、 ```classification``` 、 ```assignedTo``` 和 ```tags``` 。</span><span class="sxs-lookup"><span data-stu-id="52ded-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="52ded-112">限制</span><span class="sxs-lookup"><span data-stu-id="52ded-112">Limitations</span></span>
1. <span data-ttu-id="52ded-113">此 API 的速率限制为每分钟50个呼叫和每小时的1500个呼叫。</span><span class="sxs-lookup"><span data-stu-id="52ded-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="52ded-114">如果将分类设置为 TruePositive，则可以设置 " ```determination``` 仅限"。</span><span class="sxs-lookup"><span data-stu-id="52ded-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="52ded-115">权限</span><span class="sxs-lookup"><span data-stu-id="52ded-115">Permissions</span></span>
<span data-ttu-id="52ded-116">若要调用此 API，必须有以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="52ded-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="52ded-117">若要了解详细信息，包括如何选择权限，请参阅 [Access The Microsoft 365 Defender api](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="52ded-117">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="52ded-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="52ded-118">Permission type</span></span> |   <span data-ttu-id="52ded-119">权限</span><span class="sxs-lookup"><span data-stu-id="52ded-119">Permission</span></span>  |   <span data-ttu-id="52ded-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="52ded-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="52ded-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="52ded-121">Application</span></span> |   <span data-ttu-id="52ded-122">事件 ReadWrite。 All</span><span class="sxs-lookup"><span data-stu-id="52ded-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="52ded-123">' 读取和写入所有事件 '</span><span class="sxs-lookup"><span data-stu-id="52ded-123">'Read and write all incidents'</span></span>
<span data-ttu-id="52ded-124">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="52ded-124">Delegated (work or school account)</span></span> | <span data-ttu-id="52ded-125">事件读写</span><span class="sxs-lookup"><span data-stu-id="52ded-125">Incident.ReadWrite</span></span> | <span data-ttu-id="52ded-126">"读取和写入事件"</span><span class="sxs-lookup"><span data-stu-id="52ded-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="52ded-127">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="52ded-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="52ded-128">用户需要具有更新门户中的事件的权限。</span><span class="sxs-lookup"><span data-stu-id="52ded-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="52ded-129">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="52ded-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="52ded-130">请求标头</span><span class="sxs-lookup"><span data-stu-id="52ded-130">Request headers</span></span>

<span data-ttu-id="52ded-131">名称</span><span class="sxs-lookup"><span data-stu-id="52ded-131">Name</span></span> | <span data-ttu-id="52ded-132">类型</span><span class="sxs-lookup"><span data-stu-id="52ded-132">Type</span></span> | <span data-ttu-id="52ded-133">说明</span><span class="sxs-lookup"><span data-stu-id="52ded-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="52ded-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="52ded-134">Authorization</span></span> | <span data-ttu-id="52ded-135">String</span><span class="sxs-lookup"><span data-stu-id="52ded-135">String</span></span> | <span data-ttu-id="52ded-136">持有者 {令牌}。</span><span class="sxs-lookup"><span data-stu-id="52ded-136">Bearer {token}.</span></span> <span data-ttu-id="52ded-137">必需。</span><span class="sxs-lookup"><span data-stu-id="52ded-137">**Required**.</span></span>
<span data-ttu-id="52ded-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="52ded-138">Content-Type</span></span> | <span data-ttu-id="52ded-139">String</span><span class="sxs-lookup"><span data-stu-id="52ded-139">String</span></span> | <span data-ttu-id="52ded-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="52ded-140">application/json.</span></span> <span data-ttu-id="52ded-141">必需。</span><span class="sxs-lookup"><span data-stu-id="52ded-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="52ded-142">请求正文</span><span class="sxs-lookup"><span data-stu-id="52ded-142">Request body</span></span>
<span data-ttu-id="52ded-143">在请求正文中，提供应更新的相关字段的值。</span><span class="sxs-lookup"><span data-stu-id="52ded-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="52ded-144">请求正文中不包括的现有属性将保留其以前的值，或根据对其他属性值的更改重新计算。</span><span class="sxs-lookup"><span data-stu-id="52ded-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="52ded-145">为了获得最佳性能，不应包括尚未更改的现有值。</span><span class="sxs-lookup"><span data-stu-id="52ded-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="52ded-146">属性</span><span class="sxs-lookup"><span data-stu-id="52ded-146">Property</span></span> | <span data-ttu-id="52ded-147">类型</span><span class="sxs-lookup"><span data-stu-id="52ded-147">Type</span></span> | <span data-ttu-id="52ded-148">说明</span><span class="sxs-lookup"><span data-stu-id="52ded-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="52ded-149">状态</span><span class="sxs-lookup"><span data-stu-id="52ded-149">status</span></span> | <span data-ttu-id="52ded-150">枚举</span><span class="sxs-lookup"><span data-stu-id="52ded-150">Enum</span></span> | <span data-ttu-id="52ded-151">指定警报的当前状态。</span><span class="sxs-lookup"><span data-stu-id="52ded-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="52ded-152">可能的值为 ```Active``` ： ```Resolved``` 和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="52ded-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="52ded-153">assignedTo</span><span class="sxs-lookup"><span data-stu-id="52ded-153">assignedTo</span></span> | <span data-ttu-id="52ded-154">string</span><span class="sxs-lookup"><span data-stu-id="52ded-154">string</span></span> | <span data-ttu-id="52ded-155">事件的所有者。</span><span class="sxs-lookup"><span data-stu-id="52ded-155">Owner of the incident.</span></span>
<span data-ttu-id="52ded-156">classification</span><span class="sxs-lookup"><span data-stu-id="52ded-156">classification</span></span> | <span data-ttu-id="52ded-157">枚举</span><span class="sxs-lookup"><span data-stu-id="52ded-157">Enum</span></span> | <span data-ttu-id="52ded-158">通知的规范。</span><span class="sxs-lookup"><span data-stu-id="52ded-158">Specification of the alert.</span></span> <span data-ttu-id="52ded-159">可取值为：```Unknown```、```FalsePositive```、```TruePositive```。</span><span class="sxs-lookup"><span data-stu-id="52ded-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="52ded-160">可用性</span><span class="sxs-lookup"><span data-stu-id="52ded-160">determination</span></span> | <span data-ttu-id="52ded-161">枚举</span><span class="sxs-lookup"><span data-stu-id="52ded-161">Enum</span></span> | <span data-ttu-id="52ded-162">指定通知的确定。</span><span class="sxs-lookup"><span data-stu-id="52ded-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="52ded-163">可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。</span><span class="sxs-lookup"><span data-stu-id="52ded-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="52ded-164">标记</span><span class="sxs-lookup"><span data-stu-id="52ded-164">tags</span></span> | <span data-ttu-id="52ded-165">字符串列表</span><span class="sxs-lookup"><span data-stu-id="52ded-165">string List</span></span> | <span data-ttu-id="52ded-166">事件标记列表。</span><span class="sxs-lookup"><span data-stu-id="52ded-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="52ded-167">响应</span><span class="sxs-lookup"><span data-stu-id="52ded-167">Response</span></span>
<span data-ttu-id="52ded-168">如果成功，此方法将在响应正文中返回 200 OK 和 incident 实体，其中包含更新的属性。</span><span class="sxs-lookup"><span data-stu-id="52ded-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="52ded-169">如果找不到具有指定 id 的事件-找不到404。</span><span class="sxs-lookup"><span data-stu-id="52ded-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="52ded-170">示例</span><span class="sxs-lookup"><span data-stu-id="52ded-170">Example</span></span>

<span data-ttu-id="52ded-171">**请求**</span><span class="sxs-lookup"><span data-stu-id="52ded-171">**Request**</span></span>

<span data-ttu-id="52ded-172">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="52ded-172">Here is an example of the request.</span></span>

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a><span data-ttu-id="52ded-173">相关主题</span><span class="sxs-lookup"><span data-stu-id="52ded-173">Related topic</span></span>
- [<span data-ttu-id="52ded-174">事件 API</span><span class="sxs-lookup"><span data-stu-id="52ded-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="52ded-175">列出事件</span><span class="sxs-lookup"><span data-stu-id="52ded-175">List incidents</span></span>](api-list-incidents.md)
