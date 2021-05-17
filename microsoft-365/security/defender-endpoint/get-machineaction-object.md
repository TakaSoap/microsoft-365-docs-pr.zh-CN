---
title: 获取 MachineAction 对象 API
description: 了解如何使用 Get MachineAction API 按特定计算机操作在 Microsoft Defender for Endpoint 中的 ID 检索它。
keywords: api， 图形 api， 受支持的 api， machineaction 对象
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
ms.openlocfilehash: 180179d5b1362ad4952618148b11007aa9efe91c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200061"
---
# <a name="get-machineaction-api"></a><span data-ttu-id="e3e78-104">获取 machineAction API</span><span class="sxs-lookup"><span data-stu-id="e3e78-104">Get machineAction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e3e78-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e3e78-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="e3e78-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e3e78-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e3e78-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e3e78-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e3e78-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="e3e78-108">API description</span></span>
<span data-ttu-id="e3e78-109">按其 ID [检索](machineaction.md) 特定计算机操作。</span><span class="sxs-lookup"><span data-stu-id="e3e78-109">Retrieves specific [Machine Action](machineaction.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="e3e78-110">限制</span><span class="sxs-lookup"><span data-stu-id="e3e78-110">Limitations</span></span>
1. <span data-ttu-id="e3e78-111">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="e3e78-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="e3e78-112">权限</span><span class="sxs-lookup"><span data-stu-id="e3e78-112">Permissions</span></span>
<span data-ttu-id="e3e78-113">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="e3e78-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e3e78-114">若要了解更多信息（包括如何选择权限），请参阅对 [终结点 API 使用 Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e3e78-114">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e3e78-115">权限类型</span><span class="sxs-lookup"><span data-stu-id="e3e78-115">Permission type</span></span> |   <span data-ttu-id="e3e78-116">权限</span><span class="sxs-lookup"><span data-stu-id="e3e78-116">Permission</span></span>  |   <span data-ttu-id="e3e78-117">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="e3e78-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e3e78-118">应用程序</span><span class="sxs-lookup"><span data-stu-id="e3e78-118">Application</span></span> |   <span data-ttu-id="e3e78-119">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="e3e78-119">Machine.Read.All</span></span> |  <span data-ttu-id="e3e78-120">"读取所有计算机配置文件"</span><span class="sxs-lookup"><span data-stu-id="e3e78-120">'Read all machine profiles'</span></span>
<span data-ttu-id="e3e78-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="e3e78-121">Application</span></span> |   <span data-ttu-id="e3e78-122">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e3e78-122">Machine.ReadWrite.All</span></span> | <span data-ttu-id="e3e78-123">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="e3e78-123">'Read and write all machine information'</span></span>
<span data-ttu-id="e3e78-124">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="e3e78-124">Delegated (work or school account)</span></span> | <span data-ttu-id="e3e78-125">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="e3e78-125">Machine.Read</span></span> | <span data-ttu-id="e3e78-126">"读取计算机信息"</span><span class="sxs-lookup"><span data-stu-id="e3e78-126">'Read machine information'</span></span>
<span data-ttu-id="e3e78-127">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="e3e78-127">Delegated (work or school account)</span></span> | <span data-ttu-id="e3e78-128">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e3e78-128">Machine.ReadWrite</span></span> | <span data-ttu-id="e3e78-129">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="e3e78-129">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="e3e78-130">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="e3e78-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e3e78-131">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="e3e78-131">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e3e78-132">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="e3e78-132">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a><span data-ttu-id="e3e78-133">请求标头</span><span class="sxs-lookup"><span data-stu-id="e3e78-133">Request headers</span></span>

<span data-ttu-id="e3e78-134">名称</span><span class="sxs-lookup"><span data-stu-id="e3e78-134">Name</span></span> | <span data-ttu-id="e3e78-135">类型</span><span class="sxs-lookup"><span data-stu-id="e3e78-135">Type</span></span> | <span data-ttu-id="e3e78-136">说明</span><span class="sxs-lookup"><span data-stu-id="e3e78-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="e3e78-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="e3e78-137">Authorization</span></span> | <span data-ttu-id="e3e78-138">String</span><span class="sxs-lookup"><span data-stu-id="e3e78-138">String</span></span> | <span data-ttu-id="e3e78-139">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="e3e78-139">Bearer {token}.</span></span> <span data-ttu-id="e3e78-140">**必需**。</span><span class="sxs-lookup"><span data-stu-id="e3e78-140">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e3e78-141">请求正文</span><span class="sxs-lookup"><span data-stu-id="e3e78-141">Request body</span></span>
<span data-ttu-id="e3e78-142">Empty</span><span class="sxs-lookup"><span data-stu-id="e3e78-142">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e3e78-143">响应</span><span class="sxs-lookup"><span data-stu-id="e3e78-143">Response</span></span>
<span data-ttu-id="e3e78-144">如果成功，此方法使用 Machine Action 实体返回 200 Ok [响应](machineaction.md) 代码。</span><span class="sxs-lookup"><span data-stu-id="e3e78-144">If successful, this method returns 200, Ok response code with a [Machine Action](machineaction.md) entity.</span></span> <span data-ttu-id="e3e78-145">如果未找到具有指定 ID 的机器操作实体 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="e3e78-145">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="e3e78-146">示例</span><span class="sxs-lookup"><span data-stu-id="e3e78-146">Example</span></span>

<span data-ttu-id="e3e78-147">**请求**</span><span class="sxs-lookup"><span data-stu-id="e3e78-147">**Request**</span></span>

<span data-ttu-id="e3e78-148">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="e3e78-148">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

<span data-ttu-id="e3e78-149">**响应**</span><span class="sxs-lookup"><span data-stu-id="e3e78-149">**Response**</span></span>

<span data-ttu-id="e3e78-150">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="e3e78-150">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```
