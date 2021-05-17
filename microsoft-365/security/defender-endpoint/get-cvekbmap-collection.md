---
title: 获取 CVE-KB 地图 API
description: 了解如何使用获取 CVE-KB 映射 API 在 Microsoft Defender for Endpoint 中检索 CVE 到 KB 的映射和 CVE 详细信息。
keywords: api， 图形 api， 受支持的 api， get， cve， kb
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
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166328"
---
# <a name="get-cve-kb-map-api"></a><span data-ttu-id="b44a5-104">获取 CVE-KB 地图 API</span><span class="sxs-lookup"><span data-stu-id="b44a5-104">Get CVE-KB map API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b44a5-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b44a5-105">**Applies to:**</span></span>
- [<span data-ttu-id="b44a5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b44a5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b44a5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b44a5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b44a5-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b44a5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b44a5-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b44a5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b44a5-110">检索 CVE 到 KB 和 CVE 详细信息的地图。</span><span class="sxs-lookup"><span data-stu-id="b44a5-110">Retrieves a map of CVE's to KB's and CVE details.</span></span>

## <a name="permissions"></a><span data-ttu-id="b44a5-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="b44a5-111">Permissions</span></span>
<span data-ttu-id="b44a5-112">用户需要读取权限。</span><span class="sxs-lookup"><span data-stu-id="b44a5-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="b44a5-113">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="b44a5-113">HTTP request</span></span>
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a><span data-ttu-id="b44a5-114">请求标头</span><span class="sxs-lookup"><span data-stu-id="b44a5-114">Request headers</span></span>

<span data-ttu-id="b44a5-115">标头</span><span class="sxs-lookup"><span data-stu-id="b44a5-115">Header</span></span> | <span data-ttu-id="b44a5-116">值</span><span class="sxs-lookup"><span data-stu-id="b44a5-116">Value</span></span> 
:---|:---
<span data-ttu-id="b44a5-117">Authorization</span><span class="sxs-lookup"><span data-stu-id="b44a5-117">Authorization</span></span> | <span data-ttu-id="b44a5-118">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="b44a5-118">Bearer {token}.</span></span> <span data-ttu-id="b44a5-119">**必需**。</span><span class="sxs-lookup"><span data-stu-id="b44a5-119">**Required**.</span></span>
<span data-ttu-id="b44a5-120">内容类型</span><span class="sxs-lookup"><span data-stu-id="b44a5-120">Content type</span></span> | <span data-ttu-id="b44a5-121">application/json</span><span class="sxs-lookup"><span data-stu-id="b44a5-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="b44a5-122">请求正文</span><span class="sxs-lookup"><span data-stu-id="b44a5-122">Request body</span></span>
<span data-ttu-id="b44a5-123">Empty</span><span class="sxs-lookup"><span data-stu-id="b44a5-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b44a5-124">响应</span><span class="sxs-lookup"><span data-stu-id="b44a5-124">Response</span></span>
<span data-ttu-id="b44a5-125">如果成功且存在映射 - 200 正常。</span><span class="sxs-lookup"><span data-stu-id="b44a5-125">If successful and map exists - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="b44a5-126">示例</span><span class="sxs-lookup"><span data-stu-id="b44a5-126">Example</span></span>

<span data-ttu-id="b44a5-127">**请求**</span><span class="sxs-lookup"><span data-stu-id="b44a5-127">**Request**</span></span>

<span data-ttu-id="b44a5-128">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="b44a5-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

<span data-ttu-id="b44a5-129">**响应**</span><span class="sxs-lookup"><span data-stu-id="b44a5-129">**Response**</span></span>

<span data-ttu-id="b44a5-130">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="b44a5-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
