---
title: 列出软件
description: 检索软件清单列表
keywords: api， 图形 api， 受支持的 api， 获取， 列表， 文件， 信息， 软件清单， 威胁&漏洞管理 api， mdatp tvm api
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
ms.openlocfilehash: 867fb57f61bd98b7c0afabd20b27e68d6bf45ef7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198561"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="1db47-104">列出软件清单 API</span><span class="sxs-lookup"><span data-stu-id="1db47-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1db47-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1db47-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1db47-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1db47-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1db47-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1db47-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="1db47-108">检索组织软件清单。</span><span class="sxs-lookup"><span data-stu-id="1db47-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="1db47-109">权限</span><span class="sxs-lookup"><span data-stu-id="1db47-109">Permissions</span></span>
<span data-ttu-id="1db47-110">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="1db47-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1db47-111">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="1db47-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1db47-112">权限类型</span><span class="sxs-lookup"><span data-stu-id="1db47-112">Permission type</span></span> |   <span data-ttu-id="1db47-113">权限</span><span class="sxs-lookup"><span data-stu-id="1db47-113">Permission</span></span>  |   <span data-ttu-id="1db47-114">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="1db47-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1db47-115">应用程序</span><span class="sxs-lookup"><span data-stu-id="1db47-115">Application</span></span> |<span data-ttu-id="1db47-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="1db47-116">Software.Read.All</span></span> |    <span data-ttu-id="1db47-117">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="1db47-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="1db47-118">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="1db47-118">Delegated (work or school account)</span></span> | <span data-ttu-id="1db47-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="1db47-119">Software.Read</span></span> |    <span data-ttu-id="1db47-120">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="1db47-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1db47-121">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="1db47-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="1db47-122">请求标头</span><span class="sxs-lookup"><span data-stu-id="1db47-122">Request headers</span></span>

<span data-ttu-id="1db47-123">名称</span><span class="sxs-lookup"><span data-stu-id="1db47-123">Name</span></span> | <span data-ttu-id="1db47-124">类型</span><span class="sxs-lookup"><span data-stu-id="1db47-124">Type</span></span> | <span data-ttu-id="1db47-125">说明</span><span class="sxs-lookup"><span data-stu-id="1db47-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="1db47-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="1db47-126">Authorization</span></span> | <span data-ttu-id="1db47-127">字符串</span><span class="sxs-lookup"><span data-stu-id="1db47-127">String</span></span> | <span data-ttu-id="1db47-128">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="1db47-128">Bearer {token}.</span></span> <span data-ttu-id="1db47-129">**必需**。</span><span class="sxs-lookup"><span data-stu-id="1db47-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1db47-130">请求正文</span><span class="sxs-lookup"><span data-stu-id="1db47-130">Request body</span></span>
<span data-ttu-id="1db47-131">Empty</span><span class="sxs-lookup"><span data-stu-id="1db47-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1db47-132">响应</span><span class="sxs-lookup"><span data-stu-id="1db47-132">Response</span></span>
<span data-ttu-id="1db47-133">如果成功，此方法在正文中返回软件清单为 200 OK。</span><span class="sxs-lookup"><span data-stu-id="1db47-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="1db47-134">示例</span><span class="sxs-lookup"><span data-stu-id="1db47-134">Example</span></span>

<span data-ttu-id="1db47-135">**请求**</span><span class="sxs-lookup"><span data-stu-id="1db47-135">**Request**</span></span>

<span data-ttu-id="1db47-136">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="1db47-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="1db47-137">**响应**</span><span class="sxs-lookup"><span data-stu-id="1db47-137">**Response**</span></span>

<span data-ttu-id="1db47-138">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="1db47-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="1db47-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="1db47-139">Related topics</span></span>
- [<span data-ttu-id="1db47-140">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="1db47-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1db47-141">威胁&漏洞软件清单</span><span class="sxs-lookup"><span data-stu-id="1db47-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
