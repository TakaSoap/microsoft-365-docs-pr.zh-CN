---
title: 获取 KB 集合 API
description: 使用 Microsoft Defender for Endpoint 检索知识库 (KB) 和 KB 详细信息。
keywords: api， 图形 api， 受支持的 api， 获取， kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166479"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="fbac2-104">获取 KB 集合 API</span><span class="sxs-lookup"><span data-stu-id="fbac2-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fbac2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="fbac2-105">**Applies to:**</span></span>
- [<span data-ttu-id="fbac2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fbac2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fbac2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbac2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fbac2-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="fbac2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fbac2-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="fbac2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="fbac2-110">检索 KB 和 KB 详细信息的集合。</span><span class="sxs-lookup"><span data-stu-id="fbac2-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="fbac2-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="fbac2-111">Permissions</span></span>
<span data-ttu-id="fbac2-112">用户需要读取权限。</span><span class="sxs-lookup"><span data-stu-id="fbac2-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="fbac2-113">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="fbac2-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="fbac2-114">请求标头</span><span class="sxs-lookup"><span data-stu-id="fbac2-114">Request headers</span></span>

<span data-ttu-id="fbac2-115">标头</span><span class="sxs-lookup"><span data-stu-id="fbac2-115">Header</span></span> | <span data-ttu-id="fbac2-116">值</span><span class="sxs-lookup"><span data-stu-id="fbac2-116">Value</span></span> 
:---|:---
<span data-ttu-id="fbac2-117">Authorization</span><span class="sxs-lookup"><span data-stu-id="fbac2-117">Authorization</span></span> | <span data-ttu-id="fbac2-118">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="fbac2-118">Bearer {token}.</span></span> <span data-ttu-id="fbac2-119">**必需**。</span><span class="sxs-lookup"><span data-stu-id="fbac2-119">**Required**.</span></span>
<span data-ttu-id="fbac2-120">内容类型</span><span class="sxs-lookup"><span data-stu-id="fbac2-120">Content type</span></span> | <span data-ttu-id="fbac2-121">application/json</span><span class="sxs-lookup"><span data-stu-id="fbac2-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="fbac2-122">请求正文</span><span class="sxs-lookup"><span data-stu-id="fbac2-122">Request body</span></span>
<span data-ttu-id="fbac2-123">Empty</span><span class="sxs-lookup"><span data-stu-id="fbac2-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="fbac2-124">响应</span><span class="sxs-lookup"><span data-stu-id="fbac2-124">Response</span></span>
<span data-ttu-id="fbac2-125">如果成功 - 200 正常。</span><span class="sxs-lookup"><span data-stu-id="fbac2-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="fbac2-126">示例</span><span class="sxs-lookup"><span data-stu-id="fbac2-126">Example</span></span>

<span data-ttu-id="fbac2-127">**请求**</span><span class="sxs-lookup"><span data-stu-id="fbac2-127">**Request**</span></span>

<span data-ttu-id="fbac2-128">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="fbac2-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="fbac2-129">**响应**</span><span class="sxs-lookup"><span data-stu-id="fbac2-129">**Response**</span></span>

<span data-ttu-id="fbac2-130">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="fbac2-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
