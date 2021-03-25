---
title: 获取与警报相关的域信息
description: 使用 Microsoft Defender for Endpoint 检索与特定警报相关的所有域。
keywords: api， 图形 api， 受支持的 api， 获取警报信息， 警报信息， 相关域
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
ms.openlocfilehash: 0cb09b23df8243d970069d087976ddc79394b67d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200409"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="354d0-104">获取与警报相关的域信息 API</span><span class="sxs-lookup"><span data-stu-id="354d0-104">Get alert related domain information API</span></span>

<span data-ttu-id="354d0-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="354d0-105">**Applies to:**</span></span> 
- [<span data-ttu-id="354d0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="354d0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="354d0-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="354d0-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="354d0-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="354d0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="354d0-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="354d0-109">API description</span></span>
<span data-ttu-id="354d0-110">检索与特定警报相关的所有域。</span><span class="sxs-lookup"><span data-stu-id="354d0-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="354d0-111">限制</span><span class="sxs-lookup"><span data-stu-id="354d0-111">Limitations</span></span>
1. <span data-ttu-id="354d0-112">你可以根据配置的保留期查询上次更新的警报。</span><span class="sxs-lookup"><span data-stu-id="354d0-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="354d0-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="354d0-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="354d0-114">权限</span><span class="sxs-lookup"><span data-stu-id="354d0-114">Permissions</span></span>
<span data-ttu-id="354d0-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="354d0-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="354d0-116">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="354d0-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="354d0-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="354d0-117">Permission type</span></span> | <span data-ttu-id="354d0-118">权限</span><span class="sxs-lookup"><span data-stu-id="354d0-118">Permission</span></span> | <span data-ttu-id="354d0-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="354d0-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="354d0-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="354d0-120">Application</span></span> | <span data-ttu-id="354d0-121">URL。Read.All</span><span class="sxs-lookup"><span data-stu-id="354d0-121">URL.Read.All</span></span> | <span data-ttu-id="354d0-122">"读取 URL"</span><span class="sxs-lookup"><span data-stu-id="354d0-122">'Read URLs'</span></span>
<span data-ttu-id="354d0-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="354d0-123">Delegated (work or school account)</span></span> | <span data-ttu-id="354d0-124">URL。Read.All</span><span class="sxs-lookup"><span data-stu-id="354d0-124">URL.Read.All</span></span> | <span data-ttu-id="354d0-125">"读取 URL"</span><span class="sxs-lookup"><span data-stu-id="354d0-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="354d0-126">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="354d0-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="354d0-127">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="354d0-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="354d0-128">用户需要具有与警报关联的设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="354d0-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="354d0-129">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="354d0-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="354d0-130">请求标头</span><span class="sxs-lookup"><span data-stu-id="354d0-130">Request headers</span></span>

<span data-ttu-id="354d0-131">名称</span><span class="sxs-lookup"><span data-stu-id="354d0-131">Name</span></span> | <span data-ttu-id="354d0-132">类型</span><span class="sxs-lookup"><span data-stu-id="354d0-132">Type</span></span> | <span data-ttu-id="354d0-133">说明</span><span class="sxs-lookup"><span data-stu-id="354d0-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="354d0-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="354d0-134">Authorization</span></span> | <span data-ttu-id="354d0-135">字符串</span><span class="sxs-lookup"><span data-stu-id="354d0-135">String</span></span> | <span data-ttu-id="354d0-136">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="354d0-136">Bearer {token}.</span></span> <span data-ttu-id="354d0-137">**必需**。</span><span class="sxs-lookup"><span data-stu-id="354d0-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="354d0-138">请求正文</span><span class="sxs-lookup"><span data-stu-id="354d0-138">Request body</span></span>
<span data-ttu-id="354d0-139">Empty</span><span class="sxs-lookup"><span data-stu-id="354d0-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="354d0-140">响应</span><span class="sxs-lookup"><span data-stu-id="354d0-140">Response</span></span>
<span data-ttu-id="354d0-141">如果成功且警报和域存在 - 200 正常。</span><span class="sxs-lookup"><span data-stu-id="354d0-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="354d0-142">如果未找到警报 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="354d0-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="354d0-143">示例</span><span class="sxs-lookup"><span data-stu-id="354d0-143">Example</span></span>

<span data-ttu-id="354d0-144">**请求**</span><span class="sxs-lookup"><span data-stu-id="354d0-144">**Request**</span></span>

<span data-ttu-id="354d0-145">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="354d0-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="354d0-146">**响应**</span><span class="sxs-lookup"><span data-stu-id="354d0-146">**Response**</span></span>

<span data-ttu-id="354d0-147">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="354d0-147">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
