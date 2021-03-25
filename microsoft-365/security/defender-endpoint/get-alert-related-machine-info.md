---
title: 获取与警报相关的计算机信息
description: 使用 Microsoft Defender for Endpoint 检索与特定警报相关的所有设备。
keywords: api， 图形 api， 受支持的 api， 获取警报信息， 警报信息， 相关设备
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
ms.openlocfilehash: 70ce6adce3e14be7ee440b96587b8f9402c0b99f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166344"
---
# <a name="get-alert-related-machine-information-api"></a><span data-ttu-id="5cb0a-104">获取警报相关的计算机信息 API</span><span class="sxs-lookup"><span data-stu-id="5cb0a-104">Get alert related machine information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5cb0a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5cb0a-105">**Applies to:**</span></span>
- [<span data-ttu-id="5cb0a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5cb0a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5cb0a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5cb0a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="5cb0a-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5cb0a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5cb0a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5cb0a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5cb0a-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="5cb0a-110">API description</span></span>
<span data-ttu-id="5cb0a-111">检索 [与](machine.md) 特定警报相关的设备。</span><span class="sxs-lookup"><span data-stu-id="5cb0a-111">Retrieves [Device](machine.md) related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="5cb0a-112">限制</span><span class="sxs-lookup"><span data-stu-id="5cb0a-112">Limitations</span></span>
1. <span data-ttu-id="5cb0a-113">你可以根据配置的保留期查询上次更新的警报。</span><span class="sxs-lookup"><span data-stu-id="5cb0a-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="5cb0a-114">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="5cb0a-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5cb0a-115">权限</span><span class="sxs-lookup"><span data-stu-id="5cb0a-115">Permissions</span></span>
<span data-ttu-id="5cb0a-116">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="5cb0a-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5cb0a-117">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5cb0a-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5cb0a-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="5cb0a-118">Permission type</span></span> |   <span data-ttu-id="5cb0a-119">权限</span><span class="sxs-lookup"><span data-stu-id="5cb0a-119">Permission</span></span>  |   <span data-ttu-id="5cb0a-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="5cb0a-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5cb0a-121">Application</span><span class="sxs-lookup"><span data-stu-id="5cb0a-121">Application</span></span> |   <span data-ttu-id="5cb0a-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="5cb0a-122">Machine.Read.All</span></span> |  <span data-ttu-id="5cb0a-123">"读取所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="5cb0a-123">'Read all machine information'</span></span>
<span data-ttu-id="5cb0a-124">Application</span><span class="sxs-lookup"><span data-stu-id="5cb0a-124">Application</span></span> |   <span data-ttu-id="5cb0a-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5cb0a-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="5cb0a-126">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="5cb0a-126">'Read and write all machine information'</span></span>
<span data-ttu-id="5cb0a-127">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="5cb0a-127">Delegated (work or school account)</span></span> | <span data-ttu-id="5cb0a-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="5cb0a-128">Machine.Read</span></span> | <span data-ttu-id="5cb0a-129">"读取计算机信息"</span><span class="sxs-lookup"><span data-stu-id="5cb0a-129">'Read machine information'</span></span>
<span data-ttu-id="5cb0a-130">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="5cb0a-130">Delegated (work or school account)</span></span> | <span data-ttu-id="5cb0a-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5cb0a-131">Machine.ReadWrite</span></span> | <span data-ttu-id="5cb0a-132">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="5cb0a-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="5cb0a-133">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="5cb0a-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5cb0a-134">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="5cb0a-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="5cb0a-135">用户需要具有与警报关联的设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="5cb0a-135">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5cb0a-136">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="5cb0a-136">HTTP request</span></span>

```http
GET /api/alerts/{id}/machine
```

## <a name="request-headers"></a><span data-ttu-id="5cb0a-137">请求标头</span><span class="sxs-lookup"><span data-stu-id="5cb0a-137">Request headers</span></span>

<span data-ttu-id="5cb0a-138">名称</span><span class="sxs-lookup"><span data-stu-id="5cb0a-138">Name</span></span> | <span data-ttu-id="5cb0a-139">类型</span><span class="sxs-lookup"><span data-stu-id="5cb0a-139">Type</span></span> | <span data-ttu-id="5cb0a-140">说明</span><span class="sxs-lookup"><span data-stu-id="5cb0a-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="5cb0a-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="5cb0a-141">Authorization</span></span> | <span data-ttu-id="5cb0a-142">String</span><span class="sxs-lookup"><span data-stu-id="5cb0a-142">String</span></span> | <span data-ttu-id="5cb0a-143">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="5cb0a-143">Bearer {token}.</span></span> <span data-ttu-id="5cb0a-144">**必需**。</span><span class="sxs-lookup"><span data-stu-id="5cb0a-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5cb0a-145">请求正文</span><span class="sxs-lookup"><span data-stu-id="5cb0a-145">Request body</span></span>
<span data-ttu-id="5cb0a-146">Empty</span><span class="sxs-lookup"><span data-stu-id="5cb0a-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5cb0a-147">响应</span><span class="sxs-lookup"><span data-stu-id="5cb0a-147">Response</span></span>
<span data-ttu-id="5cb0a-148">如果成功且警报和设备存在 - 200 正常。</span><span class="sxs-lookup"><span data-stu-id="5cb0a-148">If successful and alert and device exist - 200 OK.</span></span> <span data-ttu-id="5cb0a-149">如果未找到警报或未找到设备 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="5cb0a-149">If alert not found or device not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="5cb0a-150">示例</span><span class="sxs-lookup"><span data-stu-id="5cb0a-150">Example</span></span>

<span data-ttu-id="5cb0a-151">**请求**</span><span class="sxs-lookup"><span data-stu-id="5cb0a-151">**Request**</span></span>

<span data-ttu-id="5cb0a-152">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="5cb0a-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/machine
```

<span data-ttu-id="5cb0a-153">**响应**</span><span class="sxs-lookup"><span data-stu-id="5cb0a-153">**Response**</span></span>

<span data-ttu-id="5cb0a-154">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="5cb0a-154">Here is an example of the response.</span></span>


```json
{
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2021-01-25T07:27:36.052313Z",
    "osPlatform": "Windows10",
    "osProcessor": "x64",
    "version": "1901",
    "lastIpAddress": "10.166.113.46",
    "lastExternalIpAddress": "167.220.203.175",
    "osBuild": 19042,
    "healthStatus": "Active",
    "deviceValue": "Normal",
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Low",
    "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
    "machineTags": [
        "Tag1",
        "Tag2"
    ],
    "ipAddresses": [
        {
            "ipAddress": "10.166.113.47",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        },
        {
            "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        }
    ]
}
```
