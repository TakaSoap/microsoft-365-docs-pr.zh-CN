---
title: 获取用户信息 API
description: 了解如何使用获取用户信息 API 在 Microsoft Defender for Endpoint 中按密钥或用户名检索用户实体。
keywords: api， 图形 api， 受支持的 api， 获取， 用户， 用户信息
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
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198537"
---
# <a name="get-user-information-api"></a><span data-ttu-id="4134e-104">获取用户信息 API</span><span class="sxs-lookup"><span data-stu-id="4134e-104">Get user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4134e-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4134e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4134e-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4134e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4134e-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4134e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> <span data-ttu-id="4134e-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="4134e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4134e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4134e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
<span data-ttu-id="4134e-110">按键检索 User 实体 (用户名) 。</span><span class="sxs-lookup"><span data-stu-id="4134e-110">Retrieve a User entity by key (user name).</span></span>

## <a name="permissions"></a><span data-ttu-id="4134e-111">权限</span><span class="sxs-lookup"><span data-stu-id="4134e-111">Permissions</span></span>
<span data-ttu-id="4134e-112">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="4134e-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4134e-113">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4134e-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4134e-114">权限类型</span><span class="sxs-lookup"><span data-stu-id="4134e-114">Permission type</span></span> |   <span data-ttu-id="4134e-115">权限</span><span class="sxs-lookup"><span data-stu-id="4134e-115">Permission</span></span>  |   <span data-ttu-id="4134e-116">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="4134e-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4134e-117">Application</span><span class="sxs-lookup"><span data-stu-id="4134e-117">Application</span></span> |   <span data-ttu-id="4134e-118">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="4134e-118">User.Read.All</span></span> | <span data-ttu-id="4134e-119">"读取所有用户配置文件"</span><span class="sxs-lookup"><span data-stu-id="4134e-119">'Read all user profiles'</span></span>

## <a name="http-request"></a><span data-ttu-id="4134e-120">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="4134e-120">HTTP request</span></span>
```
GET /api/users/{id}/
```

## <a name="request-headers"></a><span data-ttu-id="4134e-121">请求标头</span><span class="sxs-lookup"><span data-stu-id="4134e-121">Request headers</span></span>

<span data-ttu-id="4134e-122">名称</span><span class="sxs-lookup"><span data-stu-id="4134e-122">Name</span></span> | <span data-ttu-id="4134e-123">类型</span><span class="sxs-lookup"><span data-stu-id="4134e-123">Type</span></span> | <span data-ttu-id="4134e-124">说明</span><span class="sxs-lookup"><span data-stu-id="4134e-124">Description</span></span>
:---|:---|:---
<span data-ttu-id="4134e-125">Authorization</span><span class="sxs-lookup"><span data-stu-id="4134e-125">Authorization</span></span> | <span data-ttu-id="4134e-126">String</span><span class="sxs-lookup"><span data-stu-id="4134e-126">String</span></span> | <span data-ttu-id="4134e-127">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="4134e-127">Bearer {token}.</span></span> <span data-ttu-id="4134e-128">**必需**。</span><span class="sxs-lookup"><span data-stu-id="4134e-128">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4134e-129">请求正文</span><span class="sxs-lookup"><span data-stu-id="4134e-129">Request body</span></span>
<span data-ttu-id="4134e-130">Empty</span><span class="sxs-lookup"><span data-stu-id="4134e-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4134e-131">响应</span><span class="sxs-lookup"><span data-stu-id="4134e-131">Response</span></span>
<span data-ttu-id="4134e-132">如果成功且用户存在 - 正文中的 [user](user.md) 实体为 200 正常。</span><span class="sxs-lookup"><span data-stu-id="4134e-132">If successful and user exists - 200 OK with [user](user.md) entity in the body.</span></span> <span data-ttu-id="4134e-133">如果用户不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="4134e-133">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="4134e-134">示例</span><span class="sxs-lookup"><span data-stu-id="4134e-134">Example</span></span>

<span data-ttu-id="4134e-135">**请求**</span><span class="sxs-lookup"><span data-stu-id="4134e-135">**Request**</span></span>

<span data-ttu-id="4134e-136">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="4134e-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

<span data-ttu-id="4134e-137">**响应**</span><span class="sxs-lookup"><span data-stu-id="4134e-137">**Response**</span></span>

<span data-ttu-id="4134e-138">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="4134e-138">Here is an example of the response.</span></span>


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```
