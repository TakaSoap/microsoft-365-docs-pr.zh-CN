---
title: 按 ID API 获取计算机
description: 了解如何使用按 ID 获取计算机 API 在 Microsoft Defender for Endpoint 中按计算机的设备 ID 或计算机名称检索计算机。
keywords: api， 图形 api， 受支持的 api， 获取， 设备， 实体， id
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
ms.openlocfilehash: 29423230d0d8d4baaa1acca9a3661dc3436f303d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200086"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="151b8-104">按 ID API 获取计算机</span><span class="sxs-lookup"><span data-stu-id="151b8-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="151b8-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="151b8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="151b8-106">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="151b8-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="151b8-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="151b8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="151b8-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="151b8-108">API description</span></span>
<span data-ttu-id="151b8-109">按特定 [计算机的设备](machine.md) ID 或计算机名称检索它。</span><span class="sxs-lookup"><span data-stu-id="151b8-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="151b8-110">限制</span><span class="sxs-lookup"><span data-stu-id="151b8-110">Limitations</span></span>
1. <span data-ttu-id="151b8-111">你可以根据配置的保留策略获取最后一次看到的设备。</span><span class="sxs-lookup"><span data-stu-id="151b8-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="151b8-112">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="151b8-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="151b8-113">权限</span><span class="sxs-lookup"><span data-stu-id="151b8-113">Permissions</span></span>
<span data-ttu-id="151b8-114">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="151b8-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="151b8-115">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="151b8-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="151b8-116">权限类型</span><span class="sxs-lookup"><span data-stu-id="151b8-116">Permission type</span></span> |   <span data-ttu-id="151b8-117">权限</span><span class="sxs-lookup"><span data-stu-id="151b8-117">Permission</span></span>  |   <span data-ttu-id="151b8-118">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="151b8-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="151b8-119">应用程序</span><span class="sxs-lookup"><span data-stu-id="151b8-119">Application</span></span> |   <span data-ttu-id="151b8-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="151b8-120">Machine.Read.All</span></span> |  <span data-ttu-id="151b8-121">"读取所有计算机配置文件"</span><span class="sxs-lookup"><span data-stu-id="151b8-121">'Read all machine profiles'</span></span>
<span data-ttu-id="151b8-122">应用程序</span><span class="sxs-lookup"><span data-stu-id="151b8-122">Application</span></span> |   <span data-ttu-id="151b8-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="151b8-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="151b8-124">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="151b8-124">'Read and write all machine information'</span></span>
<span data-ttu-id="151b8-125">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="151b8-125">Delegated (work or school account)</span></span> | <span data-ttu-id="151b8-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="151b8-126">Machine.Read</span></span> | <span data-ttu-id="151b8-127">"读取计算机信息"</span><span class="sxs-lookup"><span data-stu-id="151b8-127">'Read machine information'</span></span>
<span data-ttu-id="151b8-128">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="151b8-128">Delegated (work or school account)</span></span> | <span data-ttu-id="151b8-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="151b8-129">Machine.ReadWrite</span></span> | <span data-ttu-id="151b8-130">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="151b8-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="151b8-131">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="151b8-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="151b8-132">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="151b8-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="151b8-133">用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="151b8-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="151b8-134">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="151b8-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="151b8-135">请求标头</span><span class="sxs-lookup"><span data-stu-id="151b8-135">Request headers</span></span>

<span data-ttu-id="151b8-136">名称</span><span class="sxs-lookup"><span data-stu-id="151b8-136">Name</span></span> | <span data-ttu-id="151b8-137">类型</span><span class="sxs-lookup"><span data-stu-id="151b8-137">Type</span></span> | <span data-ttu-id="151b8-138">说明</span><span class="sxs-lookup"><span data-stu-id="151b8-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="151b8-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="151b8-139">Authorization</span></span> | <span data-ttu-id="151b8-140">String</span><span class="sxs-lookup"><span data-stu-id="151b8-140">String</span></span> | <span data-ttu-id="151b8-141">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="151b8-141">Bearer {token}.</span></span> <span data-ttu-id="151b8-142">**必需**。</span><span class="sxs-lookup"><span data-stu-id="151b8-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="151b8-143">请求正文</span><span class="sxs-lookup"><span data-stu-id="151b8-143">Request body</span></span>
<span data-ttu-id="151b8-144">Empty</span><span class="sxs-lookup"><span data-stu-id="151b8-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="151b8-145">响应</span><span class="sxs-lookup"><span data-stu-id="151b8-145">Response</span></span>
<span data-ttu-id="151b8-146">如果成功且设备存在 - 200 正常，正文中为 [计算机](machine.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="151b8-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="151b8-147">如果未找到具有指定 ID 的机器 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="151b8-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="151b8-148">示例</span><span class="sxs-lookup"><span data-stu-id="151b8-148">Example</span></span>

<span data-ttu-id="151b8-149">**请求**</span><span class="sxs-lookup"><span data-stu-id="151b8-149">**Request**</span></span>

<span data-ttu-id="151b8-150">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="151b8-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="151b8-151">**响应**</span><span class="sxs-lookup"><span data-stu-id="151b8-151">**Response**</span></span>

<span data-ttu-id="151b8-152">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="151b8-152">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2018-08-02T14:55:03.7791856Z",
    "osPlatform": "Windows10",
    "version": "1709",
    "osProcessor": "x64",
    "lastIpAddress": "172.17.230.209",
    "lastExternalIpAddress": "167.220.196.71",
    "osBuild": 18209,
    "healthStatus": "Active",
    "rbacGroupId": 140,
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Medium",
    "isAadJoined": true,
    "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
    "machineTags": [ "test tag 1", "test tag 2" ]
}

```
