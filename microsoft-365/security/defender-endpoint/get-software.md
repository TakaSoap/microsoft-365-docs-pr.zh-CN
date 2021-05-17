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
ms.openlocfilehash: 6522b546dfde7447a03b3c417be93d288e261908
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934005"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="c0ff7-104">列出软件清单 API</span><span class="sxs-lookup"><span data-stu-id="c0ff7-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c0ff7-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c0ff7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c0ff7-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c0ff7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c0ff7-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c0ff7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="c0ff7-108">检索组织软件清单。</span><span class="sxs-lookup"><span data-stu-id="c0ff7-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="c0ff7-109">权限</span><span class="sxs-lookup"><span data-stu-id="c0ff7-109">Permissions</span></span>
<span data-ttu-id="c0ff7-110">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="c0ff7-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c0ff7-111">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="c0ff7-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="c0ff7-112">权限类型</span><span class="sxs-lookup"><span data-stu-id="c0ff7-112">Permission type</span></span> |   <span data-ttu-id="c0ff7-113">权限</span><span class="sxs-lookup"><span data-stu-id="c0ff7-113">Permission</span></span>  |   <span data-ttu-id="c0ff7-114">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="c0ff7-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c0ff7-115">应用程序</span><span class="sxs-lookup"><span data-stu-id="c0ff7-115">Application</span></span> |<span data-ttu-id="c0ff7-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="c0ff7-116">Software.Read.All</span></span> |    <span data-ttu-id="c0ff7-117">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="c0ff7-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="c0ff7-118">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="c0ff7-118">Delegated (work or school account)</span></span> | <span data-ttu-id="c0ff7-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="c0ff7-119">Software.Read</span></span> |    <span data-ttu-id="c0ff7-120">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="c0ff7-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="c0ff7-121">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="c0ff7-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="c0ff7-122">请求标头</span><span class="sxs-lookup"><span data-stu-id="c0ff7-122">Request headers</span></span>

<span data-ttu-id="c0ff7-123">名称</span><span class="sxs-lookup"><span data-stu-id="c0ff7-123">Name</span></span> | <span data-ttu-id="c0ff7-124">类型</span><span class="sxs-lookup"><span data-stu-id="c0ff7-124">Type</span></span> | <span data-ttu-id="c0ff7-125">说明</span><span class="sxs-lookup"><span data-stu-id="c0ff7-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="c0ff7-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="c0ff7-126">Authorization</span></span> | <span data-ttu-id="c0ff7-127">String</span><span class="sxs-lookup"><span data-stu-id="c0ff7-127">String</span></span> | <span data-ttu-id="c0ff7-128">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="c0ff7-128">Bearer {token}.</span></span> <span data-ttu-id="c0ff7-129">**必需**。</span><span class="sxs-lookup"><span data-stu-id="c0ff7-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c0ff7-130">请求正文</span><span class="sxs-lookup"><span data-stu-id="c0ff7-130">Request body</span></span>
<span data-ttu-id="c0ff7-131">Empty</span><span class="sxs-lookup"><span data-stu-id="c0ff7-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c0ff7-132">响应</span><span class="sxs-lookup"><span data-stu-id="c0ff7-132">Response</span></span>
<span data-ttu-id="c0ff7-133">如果成功，此方法在正文中返回软件清单为 200 OK。</span><span class="sxs-lookup"><span data-stu-id="c0ff7-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="c0ff7-134">示例</span><span class="sxs-lookup"><span data-stu-id="c0ff7-134">Example</span></span>

<span data-ttu-id="c0ff7-135">**请求**</span><span class="sxs-lookup"><span data-stu-id="c0ff7-135">**Request**</span></span>

<span data-ttu-id="c0ff7-136">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="c0ff7-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="c0ff7-137">**响应**</span><span class="sxs-lookup"><span data-stu-id="c0ff7-137">**Response**</span></span>

<span data-ttu-id="c0ff7-138">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="c0ff7-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="c0ff7-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="c0ff7-139">Related topics</span></span>
- [<span data-ttu-id="c0ff7-140">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="c0ff7-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="c0ff7-141">威胁&漏洞软件清单</span><span class="sxs-lookup"><span data-stu-id="c0ff7-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
