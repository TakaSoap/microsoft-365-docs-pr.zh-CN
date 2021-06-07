---
title: 列出软件
description: 检索软件清单列表
keywords: api， 图形 api， 受支持的 api， 获取， 列表， 文件， 信息， 软件清单， 威胁& 漏洞管理 api， Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: f7e71c58396fd4b3ed40ba88aab5c2757ae41a41
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771077"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="b2f60-104">列出软件清单 API</span><span class="sxs-lookup"><span data-stu-id="b2f60-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b2f60-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b2f60-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b2f60-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b2f60-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b2f60-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b2f60-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b2f60-108">检索组织软件清单。</span><span class="sxs-lookup"><span data-stu-id="b2f60-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="b2f60-109">权限</span><span class="sxs-lookup"><span data-stu-id="b2f60-109">Permissions</span></span>
<span data-ttu-id="b2f60-110">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="b2f60-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b2f60-111">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2f60-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b2f60-112">权限类型</span><span class="sxs-lookup"><span data-stu-id="b2f60-112">Permission type</span></span> |   <span data-ttu-id="b2f60-113">权限</span><span class="sxs-lookup"><span data-stu-id="b2f60-113">Permission</span></span>  |   <span data-ttu-id="b2f60-114">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="b2f60-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b2f60-115">应用程序</span><span class="sxs-lookup"><span data-stu-id="b2f60-115">Application</span></span> |<span data-ttu-id="b2f60-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="b2f60-116">Software.Read.All</span></span> |    <span data-ttu-id="b2f60-117">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="b2f60-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="b2f60-118">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="b2f60-118">Delegated (work or school account)</span></span> | <span data-ttu-id="b2f60-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="b2f60-119">Software.Read</span></span> |    <span data-ttu-id="b2f60-120">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="b2f60-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b2f60-121">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="b2f60-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="b2f60-122">请求标头</span><span class="sxs-lookup"><span data-stu-id="b2f60-122">Request headers</span></span>

<span data-ttu-id="b2f60-123">名称</span><span class="sxs-lookup"><span data-stu-id="b2f60-123">Name</span></span> | <span data-ttu-id="b2f60-124">类型</span><span class="sxs-lookup"><span data-stu-id="b2f60-124">Type</span></span> | <span data-ttu-id="b2f60-125">说明</span><span class="sxs-lookup"><span data-stu-id="b2f60-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="b2f60-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="b2f60-126">Authorization</span></span> | <span data-ttu-id="b2f60-127">String</span><span class="sxs-lookup"><span data-stu-id="b2f60-127">String</span></span> | <span data-ttu-id="b2f60-128">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="b2f60-128">Bearer {token}.</span></span> <span data-ttu-id="b2f60-129">**必需**。</span><span class="sxs-lookup"><span data-stu-id="b2f60-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b2f60-130">请求正文</span><span class="sxs-lookup"><span data-stu-id="b2f60-130">Request body</span></span>
<span data-ttu-id="b2f60-131">Empty</span><span class="sxs-lookup"><span data-stu-id="b2f60-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b2f60-132">响应</span><span class="sxs-lookup"><span data-stu-id="b2f60-132">Response</span></span>
<span data-ttu-id="b2f60-133">如果成功，此方法在正文中返回软件清单为 200 OK。</span><span class="sxs-lookup"><span data-stu-id="b2f60-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="b2f60-134">示例</span><span class="sxs-lookup"><span data-stu-id="b2f60-134">Example</span></span>

<span data-ttu-id="b2f60-135">**请求**</span><span class="sxs-lookup"><span data-stu-id="b2f60-135">**Request**</span></span>

<span data-ttu-id="b2f60-136">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="b2f60-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="b2f60-137">**响应**</span><span class="sxs-lookup"><span data-stu-id="b2f60-137">**Response**</span></span>

<span data-ttu-id="b2f60-138">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="b2f60-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="b2f60-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="b2f60-139">Related topics</span></span>
- [<span data-ttu-id="b2f60-140">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="b2f60-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b2f60-141">威胁&漏洞软件清单</span><span class="sxs-lookup"><span data-stu-id="b2f60-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
