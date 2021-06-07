---
title: 按 ID 获取软件
description: 按设备组检索曝光评分列表。
keywords: api， 图形 api， 受支持的 api， 获取， 软件， Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7e9e6b5e64099e7ab49fec624d83f13f18e6029c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769157"
---
# <a name="get-software-by-id"></a><span data-ttu-id="b1a20-104">按 ID 获取软件</span><span class="sxs-lookup"><span data-stu-id="b1a20-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1a20-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b1a20-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b1a20-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b1a20-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b1a20-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b1a20-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b1a20-108">按 ID 检索软件详细信息。</span><span class="sxs-lookup"><span data-stu-id="b1a20-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="b1a20-109">权限</span><span class="sxs-lookup"><span data-stu-id="b1a20-109">Permissions</span></span>
<span data-ttu-id="b1a20-110">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="b1a20-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b1a20-111">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="b1a20-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b1a20-112">权限类型</span><span class="sxs-lookup"><span data-stu-id="b1a20-112">Permission type</span></span> |   <span data-ttu-id="b1a20-113">权限</span><span class="sxs-lookup"><span data-stu-id="b1a20-113">Permission</span></span>  |   <span data-ttu-id="b1a20-114">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="b1a20-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b1a20-115">应用程序</span><span class="sxs-lookup"><span data-stu-id="b1a20-115">Application</span></span> | <span data-ttu-id="b1a20-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="b1a20-116">Software.Read.All</span></span> | <span data-ttu-id="b1a20-117">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="b1a20-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="b1a20-118">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="b1a20-118">Delegated (work or school account)</span></span> | <span data-ttu-id="b1a20-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="b1a20-119">Software.Read</span></span> | <span data-ttu-id="b1a20-120">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="b1a20-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b1a20-121">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="b1a20-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="b1a20-122">请求标头</span><span class="sxs-lookup"><span data-stu-id="b1a20-122">Request headers</span></span>

| <span data-ttu-id="b1a20-123">名称</span><span class="sxs-lookup"><span data-stu-id="b1a20-123">Name</span></span>        | <span data-ttu-id="b1a20-124">类型</span><span class="sxs-lookup"><span data-stu-id="b1a20-124">Type</span></span> | <span data-ttu-id="b1a20-125">说明</span><span class="sxs-lookup"><span data-stu-id="b1a20-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="b1a20-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="b1a20-126">Authorization</span></span> | <span data-ttu-id="b1a20-127">String</span><span class="sxs-lookup"><span data-stu-id="b1a20-127">String</span></span> | <span data-ttu-id="b1a20-128">Bearer {token}。**必需**。</span><span class="sxs-lookup"><span data-stu-id="b1a20-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b1a20-129">请求正文</span><span class="sxs-lookup"><span data-stu-id="b1a20-129">Request body</span></span>
<span data-ttu-id="b1a20-130">Empty</span><span class="sxs-lookup"><span data-stu-id="b1a20-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b1a20-131">响应</span><span class="sxs-lookup"><span data-stu-id="b1a20-131">Response</span></span>
<span data-ttu-id="b1a20-132">如果成功，此方法在正文中返回 200 OK 以及指定的软件数据。</span><span class="sxs-lookup"><span data-stu-id="b1a20-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="b1a20-133">示例</span><span class="sxs-lookup"><span data-stu-id="b1a20-133">Example</span></span>

<span data-ttu-id="b1a20-134">**请求**</span><span class="sxs-lookup"><span data-stu-id="b1a20-134">**Request**</span></span>

<span data-ttu-id="b1a20-135">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="b1a20-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="b1a20-136">**响应**</span><span class="sxs-lookup"><span data-stu-id="b1a20-136">**Response**</span></span>

<span data-ttu-id="b1a20-137">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="b1a20-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a><span data-ttu-id="b1a20-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="b1a20-138">Related topics</span></span>
- [<span data-ttu-id="b1a20-139">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="b1a20-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b1a20-140">威胁&漏洞软件清单</span><span class="sxs-lookup"><span data-stu-id="b1a20-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
