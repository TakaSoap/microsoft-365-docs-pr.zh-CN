---
title: 获取计算机安全状态集合 API
description: 使用 Microsoft Defender for Endpoint 检索设备安全状态的集合。
keywords: api， 图形 api， 受支持的 api， 获取， 设备， 安全性， 状态
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
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200361"
---
# <a name="get-machines-security-states-collection-api"></a><span data-ttu-id="cdb61-104">获取计算机安全状态集合 API</span><span class="sxs-lookup"><span data-stu-id="cdb61-104">Get Machines security states collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cdb61-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cdb61-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="cdb61-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="cdb61-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cdb61-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="cdb61-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="cdb61-108">检索设备安全状态的集合。</span><span class="sxs-lookup"><span data-stu-id="cdb61-108">Retrieves a collection of devices security states.</span></span>

## <a name="permissions"></a><span data-ttu-id="cdb61-109">Permissions</span><span class="sxs-lookup"><span data-stu-id="cdb61-109">Permissions</span></span>
<span data-ttu-id="cdb61-110">用户需要读取权限。</span><span class="sxs-lookup"><span data-stu-id="cdb61-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="cdb61-111">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="cdb61-111">HTTP request</span></span>
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a><span data-ttu-id="cdb61-112">请求标头</span><span class="sxs-lookup"><span data-stu-id="cdb61-112">Request headers</span></span>

<span data-ttu-id="cdb61-113">标头</span><span class="sxs-lookup"><span data-stu-id="cdb61-113">Header</span></span> | <span data-ttu-id="cdb61-114">值</span><span class="sxs-lookup"><span data-stu-id="cdb61-114">Value</span></span> 
:---|:---
<span data-ttu-id="cdb61-115">Authorization</span><span class="sxs-lookup"><span data-stu-id="cdb61-115">Authorization</span></span> | <span data-ttu-id="cdb61-116">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="cdb61-116">Bearer {token}.</span></span> <span data-ttu-id="cdb61-117">**必需**。</span><span class="sxs-lookup"><span data-stu-id="cdb61-117">**Required**.</span></span>
<span data-ttu-id="cdb61-118">内容类型</span><span class="sxs-lookup"><span data-stu-id="cdb61-118">Content type</span></span> | <span data-ttu-id="cdb61-119">application/json</span><span class="sxs-lookup"><span data-stu-id="cdb61-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="cdb61-120">请求正文</span><span class="sxs-lookup"><span data-stu-id="cdb61-120">Request body</span></span>
<span data-ttu-id="cdb61-121">Empty</span><span class="sxs-lookup"><span data-stu-id="cdb61-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cdb61-122">响应</span><span class="sxs-lookup"><span data-stu-id="cdb61-122">Response</span></span>
<span data-ttu-id="cdb61-123">如果成功 - 200 正常。</span><span class="sxs-lookup"><span data-stu-id="cdb61-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="cdb61-124">示例</span><span class="sxs-lookup"><span data-stu-id="cdb61-124">Example</span></span>

<span data-ttu-id="cdb61-125">**请求**</span><span class="sxs-lookup"><span data-stu-id="cdb61-125">**Request**</span></span>

<span data-ttu-id="cdb61-126">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="cdb61-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

<span data-ttu-id="cdb61-127">**响应**</span><span class="sxs-lookup"><span data-stu-id="cdb61-127">**Response**</span></span>

<span data-ttu-id="cdb61-128">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="cdb61-128">Here is an example of the response.</span></span>
<span data-ttu-id="cdb61-129">字段 *ID* 包含设备 ID，并且等于设备信息中的字段 \*ID\*\*。</span><span class="sxs-lookup"><span data-stu-id="cdb61-129">Field *id* contains device id and equal to the field *id*\* in devices info.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
