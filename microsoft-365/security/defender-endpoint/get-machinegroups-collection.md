---
title: 获取 RBAC 计算机组集合 API
description: 了解如何使用获取 KB 集合 API 在 Microsoft Defender for Endpoint 中检索 RBAC 设备组的集合。
keywords: api， 图形 api， 受支持的 api， 获取， RBAC， 组
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/07/2018
ms.openlocfilehash: 18566025d79f02281c1d2c1509dd98f1e57879c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932771"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="7b73f-104">获取 KB 集合 API</span><span class="sxs-lookup"><span data-stu-id="7b73f-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7b73f-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7b73f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="7b73f-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="7b73f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7b73f-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="7b73f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="7b73f-108">检索 RBAC 设备组的集合。</span><span class="sxs-lookup"><span data-stu-id="7b73f-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="7b73f-109">权限</span><span class="sxs-lookup"><span data-stu-id="7b73f-109">Permissions</span></span>
<span data-ttu-id="7b73f-110">用户需要读取权限。</span><span class="sxs-lookup"><span data-stu-id="7b73f-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="7b73f-111">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="7b73f-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="7b73f-112">请求标头</span><span class="sxs-lookup"><span data-stu-id="7b73f-112">Request headers</span></span>

<span data-ttu-id="7b73f-113">标头</span><span class="sxs-lookup"><span data-stu-id="7b73f-113">Header</span></span> | <span data-ttu-id="7b73f-114">值</span><span class="sxs-lookup"><span data-stu-id="7b73f-114">Value</span></span> 
:---|:---
<span data-ttu-id="7b73f-115">Authorization</span><span class="sxs-lookup"><span data-stu-id="7b73f-115">Authorization</span></span> | <span data-ttu-id="7b73f-116">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="7b73f-116">Bearer {token}.</span></span> <span data-ttu-id="7b73f-117">**必需**。</span><span class="sxs-lookup"><span data-stu-id="7b73f-117">**Required**.</span></span>
<span data-ttu-id="7b73f-118">内容类型</span><span class="sxs-lookup"><span data-stu-id="7b73f-118">Content type</span></span> | <span data-ttu-id="7b73f-119">application/json</span><span class="sxs-lookup"><span data-stu-id="7b73f-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="7b73f-120">请求正文</span><span class="sxs-lookup"><span data-stu-id="7b73f-120">Request body</span></span>
<span data-ttu-id="7b73f-121">Empty</span><span class="sxs-lookup"><span data-stu-id="7b73f-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7b73f-122">响应</span><span class="sxs-lookup"><span data-stu-id="7b73f-122">Response</span></span>
<span data-ttu-id="7b73f-123">如果成功 - 200 正常。</span><span class="sxs-lookup"><span data-stu-id="7b73f-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="7b73f-124">示例</span><span class="sxs-lookup"><span data-stu-id="7b73f-124">Example</span></span>

<span data-ttu-id="7b73f-125">**请求**</span><span class="sxs-lookup"><span data-stu-id="7b73f-125">**Request**</span></span>

<span data-ttu-id="7b73f-126">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="7b73f-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="7b73f-127">**响应**</span><span class="sxs-lookup"><span data-stu-id="7b73f-127">**Response**</span></span>

<span data-ttu-id="7b73f-128">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="7b73f-128">Here is an example of the response.</span></span>
<span data-ttu-id="7b73f-129">字段 ID 包含设备组 **ID，** 并且等于设备信息中的字段 **rbacGroupId。**</span><span class="sxs-lookup"><span data-stu-id="7b73f-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="7b73f-130">只有 **对于尚未** 分配到任何组的所有设备的一个组，取消分组的字段才为 true。</span><span class="sxs-lookup"><span data-stu-id="7b73f-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="7b73f-131">像往常一样，此组的名称为"UnassignedGroup"。</span><span class="sxs-lookup"><span data-stu-id="7b73f-131">This group as usual has name "UnassignedGroup".</span></span>

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
