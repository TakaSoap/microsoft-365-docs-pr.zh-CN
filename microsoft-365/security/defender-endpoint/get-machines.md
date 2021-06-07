---
title: 列出计算机 API
description: 了解如何使用列出计算机 API 检索已与 Microsoft Defender for Endpoint 云通信的计算机集合。
keywords: api， 图形 api， 受支持的 api， 获取， 设备
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f06973bc45ecac05c15d48afe5f0e2e9e7788f78
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770741"
---
# <a name="list-machines-api"></a><span data-ttu-id="b12d7-104">列出计算机 API</span><span class="sxs-lookup"><span data-stu-id="b12d7-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b12d7-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b12d7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b12d7-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b12d7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b12d7-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b12d7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b12d7-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="b12d7-108">API description</span></span>
<span data-ttu-id="b12d7-109">检索 [已与](machine.md) Microsoft Defender for Endpoint 云通信的计算机集合。</span><span class="sxs-lookup"><span data-stu-id="b12d7-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="b12d7-110">支持 [OData V4 查询](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="b12d7-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="b12d7-111">OData 的 `$filter` 查询在 上受支持 `computerDnsName` `lastSeen` ：、、、、 `healthStatus` `osPlatform` 和 `riskScore` `rbacGroupId` 。</span><span class="sxs-lookup"><span data-stu-id="b12d7-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="b12d7-112">有关示例， [请参阅使用 Defender for Endpoint 的 OData 查询](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="b12d7-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="b12d7-113">限制</span><span class="sxs-lookup"><span data-stu-id="b12d7-113">Limitations</span></span>
1. <span data-ttu-id="b12d7-114">你可以根据配置的保留期获取最后一次看到的设备。</span><span class="sxs-lookup"><span data-stu-id="b12d7-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="b12d7-115">最大页面大小为 10，000。</span><span class="sxs-lookup"><span data-stu-id="b12d7-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="b12d7-116">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="b12d7-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="b12d7-117">权限</span><span class="sxs-lookup"><span data-stu-id="b12d7-117">Permissions</span></span>

<span data-ttu-id="b12d7-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="b12d7-118">Permission type</span></span> |   <span data-ttu-id="b12d7-119">权限</span><span class="sxs-lookup"><span data-stu-id="b12d7-119">Permission</span></span>  |   <span data-ttu-id="b12d7-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="b12d7-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b12d7-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="b12d7-121">Application</span></span> |   <span data-ttu-id="b12d7-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="b12d7-122">Machine.Read.All</span></span> |  <span data-ttu-id="b12d7-123">"读取所有计算机配置文件"</span><span class="sxs-lookup"><span data-stu-id="b12d7-123">'Read all machine profiles'</span></span>
<span data-ttu-id="b12d7-124">应用程序</span><span class="sxs-lookup"><span data-stu-id="b12d7-124">Application</span></span> |   <span data-ttu-id="b12d7-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b12d7-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="b12d7-126">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="b12d7-126">'Read and write all machine information'</span></span>
<span data-ttu-id="b12d7-127">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="b12d7-127">Delegated (work or school account)</span></span> | <span data-ttu-id="b12d7-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="b12d7-128">Machine.Read</span></span> | <span data-ttu-id="b12d7-129">"读取计算机信息"</span><span class="sxs-lookup"><span data-stu-id="b12d7-129">'Read machine information'</span></span>
<span data-ttu-id="b12d7-130">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="b12d7-130">Delegated (work or school account)</span></span> | <span data-ttu-id="b12d7-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b12d7-131">Machine.ReadWrite</span></span> | <span data-ttu-id="b12d7-132">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="b12d7-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="b12d7-133">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="b12d7-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b12d7-134">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="b12d7-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b12d7-135">响应将仅包括用户有权访问的设备，根据设备组设置 (请参阅创建和管理设备组，了解) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="b12d7-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b12d7-136">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="b12d7-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="b12d7-137">请求标头</span><span class="sxs-lookup"><span data-stu-id="b12d7-137">Request headers</span></span>

<span data-ttu-id="b12d7-138">名称</span><span class="sxs-lookup"><span data-stu-id="b12d7-138">Name</span></span> | <span data-ttu-id="b12d7-139">类型</span><span class="sxs-lookup"><span data-stu-id="b12d7-139">Type</span></span> | <span data-ttu-id="b12d7-140">说明</span><span class="sxs-lookup"><span data-stu-id="b12d7-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="b12d7-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="b12d7-141">Authorization</span></span> | <span data-ttu-id="b12d7-142">String</span><span class="sxs-lookup"><span data-stu-id="b12d7-142">String</span></span> | <span data-ttu-id="b12d7-143">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="b12d7-143">Bearer {token}.</span></span> <span data-ttu-id="b12d7-144">**必需**。</span><span class="sxs-lookup"><span data-stu-id="b12d7-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b12d7-145">请求正文</span><span class="sxs-lookup"><span data-stu-id="b12d7-145">Request body</span></span>
<span data-ttu-id="b12d7-146">Empty</span><span class="sxs-lookup"><span data-stu-id="b12d7-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b12d7-147">响应</span><span class="sxs-lookup"><span data-stu-id="b12d7-147">Response</span></span>
<span data-ttu-id="b12d7-148">如果成功且计算机存在 - 200 正常，正文中 [包含](machine.md) 计算机实体列表。</span><span class="sxs-lookup"><span data-stu-id="b12d7-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="b12d7-149">如果没有最近的计算机 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="b12d7-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="b12d7-150">示例</span><span class="sxs-lookup"><span data-stu-id="b12d7-150">Example</span></span>

<span data-ttu-id="b12d7-151">**请求**</span><span class="sxs-lookup"><span data-stu-id="b12d7-151">**Request**</span></span>

<span data-ttu-id="b12d7-152">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="b12d7-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="b12d7-153">**响应**</span><span class="sxs-lookup"><span data-stu-id="b12d7-153">**Response**</span></span>

<span data-ttu-id="b12d7-154">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="b12d7-154">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
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
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="b12d7-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="b12d7-155">Related topics</span></span>
- [<span data-ttu-id="b12d7-156">使用 Microsoft Defender for Endpoint 的 OData 查询</span><span class="sxs-lookup"><span data-stu-id="b12d7-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
