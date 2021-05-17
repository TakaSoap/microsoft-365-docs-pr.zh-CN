---
title: 列表调查 API
description: 使用此 API 创建与获取调查集合相关的调用
keywords: api， 图形 api， 受支持的 api， 调查集合
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
ms.openlocfilehash: 9ad1216a05846b48bff4186c7e6f39e9da3623b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166459"
---
# <a name="list-investigations-api"></a><span data-ttu-id="3ed67-104">列表调查 API</span><span class="sxs-lookup"><span data-stu-id="3ed67-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ed67-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3ed67-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ed67-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3ed67-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3ed67-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ed67-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3ed67-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3ed67-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ed67-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="3ed67-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3ed67-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="3ed67-110">API description</span></span>
<span data-ttu-id="3ed67-111">检索调查 [的集合](investigation.md)。</span><span class="sxs-lookup"><span data-stu-id="3ed67-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="3ed67-112">支持 [OData V4 查询](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="3ed67-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="3ed67-113">OData 的 ```$filter``` 查询在： 、 ```startTime``` 和 ```state``` ```machineId``` 属性上 ```triggeringAlertId``` 受支持。</span><span class="sxs-lookup"><span data-stu-id="3ed67-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="3ed67-114">请参阅 Microsoft [Defender for Endpoint 的 OData 查询示例](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="3ed67-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="3ed67-115">限制</span><span class="sxs-lookup"><span data-stu-id="3ed67-115">Limitations</span></span>
1. <span data-ttu-id="3ed67-116">最大页面大小为 10，000。</span><span class="sxs-lookup"><span data-stu-id="3ed67-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="3ed67-117">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="3ed67-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="3ed67-118">权限</span><span class="sxs-lookup"><span data-stu-id="3ed67-118">Permissions</span></span>
<span data-ttu-id="3ed67-119">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="3ed67-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3ed67-120">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3ed67-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3ed67-121">权限类型</span><span class="sxs-lookup"><span data-stu-id="3ed67-121">Permission type</span></span> |   <span data-ttu-id="3ed67-122">权限</span><span class="sxs-lookup"><span data-stu-id="3ed67-122">Permission</span></span>  |   <span data-ttu-id="3ed67-123">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="3ed67-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3ed67-124">应用程序</span><span class="sxs-lookup"><span data-stu-id="3ed67-124">Application</span></span> |   <span data-ttu-id="3ed67-125">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="3ed67-125">Alert.Read.All</span></span> |    <span data-ttu-id="3ed67-126">"读取所有警报"</span><span class="sxs-lookup"><span data-stu-id="3ed67-126">'Read all alerts'</span></span>
<span data-ttu-id="3ed67-127">应用程序</span><span class="sxs-lookup"><span data-stu-id="3ed67-127">Application</span></span> |   <span data-ttu-id="3ed67-128">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="3ed67-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="3ed67-129">"读取和写入所有警报"</span><span class="sxs-lookup"><span data-stu-id="3ed67-129">'Read and write all alerts'</span></span>
<span data-ttu-id="3ed67-130">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="3ed67-130">Delegated (work or school account)</span></span> | <span data-ttu-id="3ed67-131">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="3ed67-131">Alert.Read</span></span> | <span data-ttu-id="3ed67-132">"读取警报"</span><span class="sxs-lookup"><span data-stu-id="3ed67-132">'Read alerts'</span></span>
<span data-ttu-id="3ed67-133">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="3ed67-133">Delegated (work or school account)</span></span> | <span data-ttu-id="3ed67-134">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3ed67-134">Alert.ReadWrite</span></span> | <span data-ttu-id="3ed67-135">"读取和写入警报"</span><span class="sxs-lookup"><span data-stu-id="3ed67-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="3ed67-136">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="3ed67-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3ed67-137">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="3ed67-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3ed67-138">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="3ed67-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="3ed67-139">请求标头</span><span class="sxs-lookup"><span data-stu-id="3ed67-139">Request headers</span></span>

<span data-ttu-id="3ed67-140">名称</span><span class="sxs-lookup"><span data-stu-id="3ed67-140">Name</span></span> | <span data-ttu-id="3ed67-141">类型</span><span class="sxs-lookup"><span data-stu-id="3ed67-141">Type</span></span> | <span data-ttu-id="3ed67-142">说明</span><span class="sxs-lookup"><span data-stu-id="3ed67-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="3ed67-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="3ed67-143">Authorization</span></span> | <span data-ttu-id="3ed67-144">String</span><span class="sxs-lookup"><span data-stu-id="3ed67-144">String</span></span> | <span data-ttu-id="3ed67-145">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="3ed67-145">Bearer {token}.</span></span> <span data-ttu-id="3ed67-146">**必需**。</span><span class="sxs-lookup"><span data-stu-id="3ed67-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3ed67-147">请求正文</span><span class="sxs-lookup"><span data-stu-id="3ed67-147">Request body</span></span>
<span data-ttu-id="3ed67-148">Empty</span><span class="sxs-lookup"><span data-stu-id="3ed67-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3ed67-149">响应</span><span class="sxs-lookup"><span data-stu-id="3ed67-149">Response</span></span>
<span data-ttu-id="3ed67-150">如果成功，此方法将返回包含调查实体集合的 200 正常 [响应](investigation.md) 代码。</span><span class="sxs-lookup"><span data-stu-id="3ed67-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="3ed67-151">示例</span><span class="sxs-lookup"><span data-stu-id="3ed67-151">Example</span></span>

<span data-ttu-id="3ed67-152">**请求**</span><span class="sxs-lookup"><span data-stu-id="3ed67-152">**Request**</span></span>

<span data-ttu-id="3ed67-153">下面是请求获取所有调查的示例：</span><span class="sxs-lookup"><span data-stu-id="3ed67-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="3ed67-154">**响应**</span><span class="sxs-lookup"><span data-stu-id="3ed67-154">**Response**</span></span>

<span data-ttu-id="3ed67-155">下面是一个响应示例：</span><span class="sxs-lookup"><span data-stu-id="3ed67-155">Here is an example of the response:</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
