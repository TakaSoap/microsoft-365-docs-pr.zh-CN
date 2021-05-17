---
title: 列表指示器 API
description: 了解如何使用列表指示器 API 检索 Microsoft Defender for Endpoint 中所有活动指示器的集合。
keywords: api， 公共 api， 受支持的 api， 指示器集合
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 868fd141cda3b3d92464a2d9247780e0e74d6de8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198549"
---
# <a name="list-indicators-api"></a><span data-ttu-id="9750f-104">列表指示器 API</span><span class="sxs-lookup"><span data-stu-id="9750f-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9750f-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9750f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="9750f-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="9750f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9750f-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="9750f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9750f-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="9750f-108">API description</span></span>
<span data-ttu-id="9750f-109">检索所有活动指示器 [的集合](ti-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="9750f-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="9750f-110">支持 [OData V4 查询](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="9750f-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="9750f-111">OData 的 ```$filter``` 查询在：、 ```indicatorValue``` ```indicatorType``` ```creationTimeDateTimeUtc``` 和 ```createdBy``` ```action``` 属性上 ```severity``` 受支持。</span><span class="sxs-lookup"><span data-stu-id="9750f-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="9750f-112">请参阅 Microsoft [Defender for Endpoint 的 OData 查询示例](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="9750f-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="9750f-113">限制</span><span class="sxs-lookup"><span data-stu-id="9750f-113">Limitations</span></span>
1. <span data-ttu-id="9750f-114">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="9750f-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="9750f-115">权限</span><span class="sxs-lookup"><span data-stu-id="9750f-115">Permissions</span></span>
<span data-ttu-id="9750f-116">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="9750f-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9750f-117">若要了解更多信息（包括如何选择权限），请参阅 [入门](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9750f-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="9750f-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="9750f-118">Permission type</span></span> |   <span data-ttu-id="9750f-119">权限</span><span class="sxs-lookup"><span data-stu-id="9750f-119">Permission</span></span>  |   <span data-ttu-id="9750f-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="9750f-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9750f-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="9750f-121">Application</span></span> |   <span data-ttu-id="9750f-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9750f-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="9750f-123">"读取和写入指示器"</span><span class="sxs-lookup"><span data-stu-id="9750f-123">'Read and write Indicators'</span></span>
<span data-ttu-id="9750f-124">应用程序</span><span class="sxs-lookup"><span data-stu-id="9750f-124">Application</span></span> |   <span data-ttu-id="9750f-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9750f-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="9750f-126">"读取和写入所有指示器"</span><span class="sxs-lookup"><span data-stu-id="9750f-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="9750f-127">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="9750f-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="9750f-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9750f-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="9750f-129">"读取和写入指示器"</span><span class="sxs-lookup"><span data-stu-id="9750f-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="9750f-130">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="9750f-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="9750f-131">请求标头</span><span class="sxs-lookup"><span data-stu-id="9750f-131">Request headers</span></span>

<span data-ttu-id="9750f-132">名称</span><span class="sxs-lookup"><span data-stu-id="9750f-132">Name</span></span> | <span data-ttu-id="9750f-133">类型</span><span class="sxs-lookup"><span data-stu-id="9750f-133">Type</span></span> | <span data-ttu-id="9750f-134">说明</span><span class="sxs-lookup"><span data-stu-id="9750f-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="9750f-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="9750f-135">Authorization</span></span> | <span data-ttu-id="9750f-136">String</span><span class="sxs-lookup"><span data-stu-id="9750f-136">String</span></span> | <span data-ttu-id="9750f-137">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="9750f-137">Bearer {token}.</span></span> <span data-ttu-id="9750f-138">**必需**。</span><span class="sxs-lookup"><span data-stu-id="9750f-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9750f-139">请求正文</span><span class="sxs-lookup"><span data-stu-id="9750f-139">Request body</span></span>
<span data-ttu-id="9750f-140">Empty</span><span class="sxs-lookup"><span data-stu-id="9750f-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9750f-141">响应</span><span class="sxs-lookup"><span data-stu-id="9750f-141">Response</span></span>
<span data-ttu-id="9750f-142">如果成功，此方法返回 200， Ok 响应代码和 [指示器](ti-indicator.md) 实体集合。</span><span class="sxs-lookup"><span data-stu-id="9750f-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="9750f-143">如果应用程序具有"Ti.ReadWrite.All"权限，它将公开给所有指示器。</span><span class="sxs-lookup"><span data-stu-id="9750f-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="9750f-144">否则，它将只对它创建的指示器公开。</span><span class="sxs-lookup"><span data-stu-id="9750f-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="9750f-145">示例 1：</span><span class="sxs-lookup"><span data-stu-id="9750f-145">Example 1:</span></span>

<span data-ttu-id="9750f-146">**请求**</span><span class="sxs-lookup"><span data-stu-id="9750f-146">**Request**</span></span>

<span data-ttu-id="9750f-147">下面是获取所有指示器的请求示例</span><span class="sxs-lookup"><span data-stu-id="9750f-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="9750f-148">**响应**</span><span class="sxs-lookup"><span data-stu-id="9750f-148">**Response**</span></span>

<span data-ttu-id="9750f-149">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="9750f-149">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="9750f-150">示例 2：</span><span class="sxs-lookup"><span data-stu-id="9750f-150">Example 2:</span></span>

<span data-ttu-id="9750f-151">**请求**</span><span class="sxs-lookup"><span data-stu-id="9750f-151">**Request**</span></span>

<span data-ttu-id="9750f-152">下面是使用"AlertAndBlock"操作获取所有指示器的请求示例</span><span class="sxs-lookup"><span data-stu-id="9750f-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="9750f-153">**响应**</span><span class="sxs-lookup"><span data-stu-id="9750f-153">**Response**</span></span>

<span data-ttu-id="9750f-154">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="9750f-154">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
