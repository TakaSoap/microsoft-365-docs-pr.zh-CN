---
title: 获取计算机登录用户 API
description: 了解如何使用获取计算机登录用户 API 在 Microsoft Defender for Endpoint 中检索设备上已登录用户的集合。
keywords: api， 图形 api， 受支持的 api， 获取， 设备， 登录， 用户
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
ms.openlocfilehash: 590bd1dee14e54359dd699e86795664819c23d05
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200087"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="eda4f-104">获取计算机登录用户 API</span><span class="sxs-lookup"><span data-stu-id="eda4f-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="eda4f-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="eda4f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="eda4f-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="eda4f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eda4f-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="eda4f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="eda4f-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="eda4f-108">API description</span></span>
<span data-ttu-id="eda4f-109">检索特定设备上已登录用户的集合。</span><span class="sxs-lookup"><span data-stu-id="eda4f-109">Retrieves a collection of logged on users on a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="eda4f-110">限制</span><span class="sxs-lookup"><span data-stu-id="eda4f-110">Limitations</span></span>
1. <span data-ttu-id="eda4f-111">你可以根据配置的保留期查询上次更新的警报。</span><span class="sxs-lookup"><span data-stu-id="eda4f-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="eda4f-112">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="eda4f-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="eda4f-113">权限</span><span class="sxs-lookup"><span data-stu-id="eda4f-113">Permissions</span></span>
<span data-ttu-id="eda4f-114">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="eda4f-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="eda4f-115">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="eda4f-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="eda4f-116">权限类型</span><span class="sxs-lookup"><span data-stu-id="eda4f-116">Permission type</span></span> |   <span data-ttu-id="eda4f-117">权限</span><span class="sxs-lookup"><span data-stu-id="eda4f-117">Permission</span></span>  |   <span data-ttu-id="eda4f-118">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="eda4f-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="eda4f-119">Application</span><span class="sxs-lookup"><span data-stu-id="eda4f-119">Application</span></span> |   <span data-ttu-id="eda4f-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="eda4f-120">User.Read.All</span></span> | <span data-ttu-id="eda4f-121">"读取用户配置文件"</span><span class="sxs-lookup"><span data-stu-id="eda4f-121">'Read user profiles'</span></span>
<span data-ttu-id="eda4f-122">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="eda4f-122">Delegated (work or school account)</span></span> | <span data-ttu-id="eda4f-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="eda4f-123">User.Read.All</span></span> | <span data-ttu-id="eda4f-124">"读取用户配置文件"</span><span class="sxs-lookup"><span data-stu-id="eda4f-124">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="eda4f-125">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="eda4f-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="eda4f-126">用户至少需要具有以下角色权限："查看数据"。</span><span class="sxs-lookup"><span data-stu-id="eda4f-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="eda4f-127">有关详细信息，请参阅创建 [和管理角色](user-roles.md) ) </span><span class="sxs-lookup"><span data-stu-id="eda4f-127">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="eda4f-128">响应将仅在设备对用户可见时包含用户，基于设备组设置。</span><span class="sxs-lookup"><span data-stu-id="eda4f-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="eda4f-129">有关详细信息，请参阅创建 [和管理设备组](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="eda4f-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="eda4f-130">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="eda4f-130">HTTP request</span></span>
```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="eda4f-131">请求标头</span><span class="sxs-lookup"><span data-stu-id="eda4f-131">Request headers</span></span>

<span data-ttu-id="eda4f-132">名称</span><span class="sxs-lookup"><span data-stu-id="eda4f-132">Name</span></span> | <span data-ttu-id="eda4f-133">类型</span><span class="sxs-lookup"><span data-stu-id="eda4f-133">Type</span></span> | <span data-ttu-id="eda4f-134">说明</span><span class="sxs-lookup"><span data-stu-id="eda4f-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="eda4f-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="eda4f-135">Authorization</span></span> | <span data-ttu-id="eda4f-136">String</span><span class="sxs-lookup"><span data-stu-id="eda4f-136">String</span></span> | <span data-ttu-id="eda4f-137">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="eda4f-137">Bearer {token}.</span></span> <span data-ttu-id="eda4f-138">**必需**。</span><span class="sxs-lookup"><span data-stu-id="eda4f-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="eda4f-139">请求正文</span><span class="sxs-lookup"><span data-stu-id="eda4f-139">Request body</span></span>
<span data-ttu-id="eda4f-140">Empty</span><span class="sxs-lookup"><span data-stu-id="eda4f-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="eda4f-141">响应</span><span class="sxs-lookup"><span data-stu-id="eda4f-141">Response</span></span>
<span data-ttu-id="eda4f-142">如果成功且设备存在 - 200 正常[](user.md)，正文中具有用户实体列表。</span><span class="sxs-lookup"><span data-stu-id="eda4f-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="eda4f-143">如果未找到设备 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="eda4f-143">If device was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="eda4f-144">示例</span><span class="sxs-lookup"><span data-stu-id="eda4f-144">Example</span></span>

<span data-ttu-id="eda4f-145">**请求**</span><span class="sxs-lookup"><span data-stu-id="eda4f-145">**Request**</span></span>

<span data-ttu-id="eda4f-146">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="eda4f-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

<span data-ttu-id="eda4f-147">**响应**</span><span class="sxs-lookup"><span data-stu-id="eda4f-147">**Response**</span></span>

<span data-ttu-id="eda4f-148">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="eda4f-148">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
