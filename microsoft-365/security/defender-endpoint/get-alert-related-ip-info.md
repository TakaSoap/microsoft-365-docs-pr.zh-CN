---
title: 获取通知相关 IP 信息
description: 使用 Microsoft Defender for Endpoint 检索与特定警报相关的所有 IP。
keywords: api， 图形 api， 受支持的 api， 获取警报信息， 警报信息， 相关 ip
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
ms.openlocfilehash: 970f82038bd7feb4f0c568ed13b285f75bf1ab19
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166439"
---
# <a name="get-alert-related-ips-information-api"></a><span data-ttu-id="43814-104">获取与警报相关的 IP 信息 API</span><span class="sxs-lookup"><span data-stu-id="43814-104">Get alert related IPs information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="43814-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="43814-105">**Applies to:**</span></span>
- [<span data-ttu-id="43814-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="43814-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="43814-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43814-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="43814-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="43814-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="43814-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="43814-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="43814-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="43814-110">API description</span></span>
<span data-ttu-id="43814-111">检索与特定警报相关的所有 IP。</span><span class="sxs-lookup"><span data-stu-id="43814-111">Retrieves all IPs related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="43814-112">限制</span><span class="sxs-lookup"><span data-stu-id="43814-112">Limitations</span></span>
1. <span data-ttu-id="43814-113">你可以根据配置的保留期查询上次更新的警报。</span><span class="sxs-lookup"><span data-stu-id="43814-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="43814-114">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="43814-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="43814-115">权限</span><span class="sxs-lookup"><span data-stu-id="43814-115">Permissions</span></span>
<span data-ttu-id="43814-116">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="43814-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="43814-117">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="43814-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="43814-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="43814-118">Permission type</span></span> |   <span data-ttu-id="43814-119">权限</span><span class="sxs-lookup"><span data-stu-id="43814-119">Permission</span></span>  |   <span data-ttu-id="43814-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="43814-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="43814-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="43814-121">Application</span></span> |   <span data-ttu-id="43814-122">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="43814-122">Ip.Read.All</span></span> |   <span data-ttu-id="43814-123">"读取 IP 地址配置文件"</span><span class="sxs-lookup"><span data-stu-id="43814-123">'Read IP address profiles'</span></span>
<span data-ttu-id="43814-124">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="43814-124">Delegated (work or school account)</span></span> | <span data-ttu-id="43814-125">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="43814-125">Ip.Read.All</span></span> |  <span data-ttu-id="43814-126">"读取 IP 地址配置文件"</span><span class="sxs-lookup"><span data-stu-id="43814-126">'Read IP address profiles'</span></span>

>[!Note]
> <span data-ttu-id="43814-127">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="43814-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="43814-128">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="43814-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="43814-129">用户需要具有与警报关联的设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="43814-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="43814-130">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="43814-130">HTTP request</span></span>
```
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a><span data-ttu-id="43814-131">请求标头</span><span class="sxs-lookup"><span data-stu-id="43814-131">Request headers</span></span>

<span data-ttu-id="43814-132">名称</span><span class="sxs-lookup"><span data-stu-id="43814-132">Name</span></span> | <span data-ttu-id="43814-133">类型</span><span class="sxs-lookup"><span data-stu-id="43814-133">Type</span></span> | <span data-ttu-id="43814-134">说明</span><span class="sxs-lookup"><span data-stu-id="43814-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="43814-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="43814-135">Authorization</span></span> | <span data-ttu-id="43814-136">String</span><span class="sxs-lookup"><span data-stu-id="43814-136">String</span></span> | <span data-ttu-id="43814-137">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="43814-137">Bearer {token}.</span></span> <span data-ttu-id="43814-138">**必需**。</span><span class="sxs-lookup"><span data-stu-id="43814-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="43814-139">请求正文</span><span class="sxs-lookup"><span data-stu-id="43814-139">Request body</span></span>
<span data-ttu-id="43814-140">Empty</span><span class="sxs-lookup"><span data-stu-id="43814-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="43814-141">响应</span><span class="sxs-lookup"><span data-stu-id="43814-141">Response</span></span>
<span data-ttu-id="43814-142">如果成功且警报和 IP 存在 - 200 正常。</span><span class="sxs-lookup"><span data-stu-id="43814-142">If successful and alert and an IP exist - 200 OK.</span></span> <span data-ttu-id="43814-143">如果未找到警报 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="43814-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="43814-144">示例</span><span class="sxs-lookup"><span data-stu-id="43814-144">Example</span></span>

<span data-ttu-id="43814-145">**请求**</span><span class="sxs-lookup"><span data-stu-id="43814-145">**Request**</span></span>

<span data-ttu-id="43814-146">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="43814-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

<span data-ttu-id="43814-147">**响应**</span><span class="sxs-lookup"><span data-stu-id="43814-147">**Response**</span></span>

<span data-ttu-id="43814-148">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="43814-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Ips",    
    "value": [
                {
                    "id": "104.80.104.128"
                },
                {
                    "id": "23.203.232.228   
                }
                ...
    ]
}
 
```
