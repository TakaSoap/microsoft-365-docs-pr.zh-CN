---
title: 列出 machineActions API
description: 了解如何使用 List MachineActions API 检索 Microsoft Defender for Endpoint 中的计算机操作集合。
keywords: api， 图形 api， 受支持的 api， machineaction 集合
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
ms.openlocfilehash: d86303d115912d1c89b5b782bae03db4ccbba6ec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200397"
---
# <a name="list-machineactions-api"></a><span data-ttu-id="6c810-104">列出 MachineActions API</span><span class="sxs-lookup"><span data-stu-id="6c810-104">List MachineActions API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6c810-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6c810-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="6c810-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6c810-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6c810-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6c810-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="6c810-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="6c810-108">API description</span></span>
<span data-ttu-id="6c810-109">检索计算机操作 [的集合](machineaction.md)。</span><span class="sxs-lookup"><span data-stu-id="6c810-109">Retrieves a collection of [Machine Actions](machineaction.md).</span></span>
<br><span data-ttu-id="6c810-110">支持 [OData V4 查询](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="6c810-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="6c810-111">OData 的 ```$filter``` 查询在以下项上受支持 ```status``` ：、、 和 ```machineId``` ```type``` ```requestor``` ```creationDateTimeUtc``` 属性。</span><span class="sxs-lookup"><span data-stu-id="6c810-111">The OData's ```$filter``` query is supported on: ```status```, ```machineId```, ```type```, ```requestor``` and ```creationDateTimeUtc``` properties.</span></span>
<br><span data-ttu-id="6c810-112">请参阅 Microsoft [Defender for Endpoint 的 OData 查询示例](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="6c810-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="6c810-113">限制</span><span class="sxs-lookup"><span data-stu-id="6c810-113">Limitations</span></span>
1. <span data-ttu-id="6c810-114">最大页面大小为 10，000。</span><span class="sxs-lookup"><span data-stu-id="6c810-114">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="6c810-115">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="6c810-115">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="6c810-116">权限</span><span class="sxs-lookup"><span data-stu-id="6c810-116">Permissions</span></span>
<span data-ttu-id="6c810-117">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="6c810-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6c810-118">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6c810-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6c810-119">权限类型</span><span class="sxs-lookup"><span data-stu-id="6c810-119">Permission type</span></span> |   <span data-ttu-id="6c810-120">权限</span><span class="sxs-lookup"><span data-stu-id="6c810-120">Permission</span></span>  |   <span data-ttu-id="6c810-121">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="6c810-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6c810-122">应用程序</span><span class="sxs-lookup"><span data-stu-id="6c810-122">Application</span></span> |   <span data-ttu-id="6c810-123">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="6c810-123">Machine.Read.All</span></span> |  <span data-ttu-id="6c810-124">"读取所有计算机配置文件"</span><span class="sxs-lookup"><span data-stu-id="6c810-124">'Read all machine profiles'</span></span>
<span data-ttu-id="6c810-125">应用程序</span><span class="sxs-lookup"><span data-stu-id="6c810-125">Application</span></span> |   <span data-ttu-id="6c810-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="6c810-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="6c810-127">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="6c810-127">'Read and write all machine information'</span></span>
<span data-ttu-id="6c810-128">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="6c810-128">Delegated (work or school account)</span></span> | <span data-ttu-id="6c810-129">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="6c810-129">Machine.Read</span></span> | <span data-ttu-id="6c810-130">"读取计算机信息"</span><span class="sxs-lookup"><span data-stu-id="6c810-130">'Read machine information'</span></span>
<span data-ttu-id="6c810-131">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="6c810-131">Delegated (work or school account)</span></span> | <span data-ttu-id="6c810-132">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6c810-132">Machine.ReadWrite</span></span> | <span data-ttu-id="6c810-133">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="6c810-133">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="6c810-134">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="6c810-134">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6c810-135">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6c810-135">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6c810-136">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="6c810-136">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

## <a name="request-headers"></a><span data-ttu-id="6c810-137">请求标头</span><span class="sxs-lookup"><span data-stu-id="6c810-137">Request headers</span></span>

<span data-ttu-id="6c810-138">名称</span><span class="sxs-lookup"><span data-stu-id="6c810-138">Name</span></span> | <span data-ttu-id="6c810-139">类型</span><span class="sxs-lookup"><span data-stu-id="6c810-139">Type</span></span> | <span data-ttu-id="6c810-140">说明</span><span class="sxs-lookup"><span data-stu-id="6c810-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="6c810-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="6c810-141">Authorization</span></span> | <span data-ttu-id="6c810-142">String</span><span class="sxs-lookup"><span data-stu-id="6c810-142">String</span></span> | <span data-ttu-id="6c810-143">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="6c810-143">Bearer {token}.</span></span> <span data-ttu-id="6c810-144">**必需**。</span><span class="sxs-lookup"><span data-stu-id="6c810-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6c810-145">请求正文</span><span class="sxs-lookup"><span data-stu-id="6c810-145">Request body</span></span>
<span data-ttu-id="6c810-146">Empty</span><span class="sxs-lookup"><span data-stu-id="6c810-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6c810-147">响应</span><span class="sxs-lookup"><span data-stu-id="6c810-147">Response</span></span>
<span data-ttu-id="6c810-148">如果成功，此方法将返回包含 [machineAction](machineaction.md) 实体集合的 200 正常响应代码。</span><span class="sxs-lookup"><span data-stu-id="6c810-148">If successful, this method returns 200, Ok response code with a collection of [machineAction](machineaction.md) entities.</span></span>


## <a name="example-1"></a><span data-ttu-id="6c810-149">示例 1</span><span class="sxs-lookup"><span data-stu-id="6c810-149">Example 1</span></span>

<span data-ttu-id="6c810-150">**请求**</span><span class="sxs-lookup"><span data-stu-id="6c810-150">**Request**</span></span>

<span data-ttu-id="6c810-151">下面是具有三个 MachineAction 的组织中请求的示例。</span><span class="sxs-lookup"><span data-stu-id="6c810-151">Here is an example of the request on an organization that has three MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

<span data-ttu-id="6c810-152">**响应**</span><span class="sxs-lookup"><span data-stu-id="6c810-152">**Response**</span></span>

<span data-ttu-id="6c810-153">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="6c810-153">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        },
        {
            "id": "44cffc15-0e3d-4cbf-96aa-bf76f9b27f5e",
            "type": "StopAndQuarantineFile",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:15:40.6052029Z",
            "lastUpdateTimeUtc": "2018-12-04T12:16:14.2899973Z",
            "relatedFileInfo": {
                "fileIdentifier": "a0c659857ccbe457fdaf5fe21d54efdcbf6f6508",
                "fileIdentifierType": "Sha1"
            }
        }
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="6c810-154">示例 2</span><span class="sxs-lookup"><span data-stu-id="6c810-154">Example 2</span></span>

<span data-ttu-id="6c810-155">**请求**</span><span class="sxs-lookup"><span data-stu-id="6c810-155">**Request**</span></span>

<span data-ttu-id="6c810-156">下面是一个请求示例，该请求按计算机 ID 筛选 MachineActions，并显示最新的两个 MachineAction。</span><span class="sxs-lookup"><span data-stu-id="6c810-156">Here is an example of a request that filters the MachineActions by machine ID and shows the latest two MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions?$filter=machineId eq 'f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f'&$top=2
```

<span data-ttu-id="6c810-157">**响应**</span><span class="sxs-lookup"><span data-stu-id="6c810-157">**Response**</span></span>

<span data-ttu-id="6c810-158">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="6c810-158">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="6c810-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="6c810-159">Related topics</span></span>
- [<span data-ttu-id="6c810-160">使用 Microsoft Defender for Endpoint 的 OData 查询</span><span class="sxs-lookup"><span data-stu-id="6c810-160">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
