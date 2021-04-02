---
title: 通过软件 ID 获取缺失的 KB
description: 按软件 ID 检索缺少的安全更新
keywords: api， 图形 api， 受支持的 api， 获取， 列表， 文件， 信息， 软件 ID， 威胁&漏洞管理 api， mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e5d84a3eadab85713779dd70848bc11d27484dcc
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499393"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="2fbfc-104">通过软件 ID 获取缺失的 KB</span><span class="sxs-lookup"><span data-stu-id="2fbfc-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2fbfc-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2fbfc-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2fbfc-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2fbfc-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2fbfc-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2fbfc-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="2fbfc-108">按软件 ID (缺少的) 更新</span><span class="sxs-lookup"><span data-stu-id="2fbfc-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="2fbfc-109">权限</span><span class="sxs-lookup"><span data-stu-id="2fbfc-109">Permissions</span></span>

<span data-ttu-id="2fbfc-110">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="2fbfc-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2fbfc-111">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="2fbfc-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="2fbfc-112">权限类型</span><span class="sxs-lookup"><span data-stu-id="2fbfc-112">Permission type</span></span> |   <span data-ttu-id="2fbfc-113">权限</span><span class="sxs-lookup"><span data-stu-id="2fbfc-113">Permission</span></span>   |   <span data-ttu-id="2fbfc-114">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="2fbfc-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2fbfc-115">应用程序</span><span class="sxs-lookup"><span data-stu-id="2fbfc-115">Application</span></span> |<span data-ttu-id="2fbfc-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="2fbfc-116">Software.Read.All</span></span> |   <span data-ttu-id="2fbfc-117">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="2fbfc-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="2fbfc-118">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="2fbfc-118">Delegated (work or school account)</span></span> | <span data-ttu-id="2fbfc-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="2fbfc-119">Software.Read</span></span> |   <span data-ttu-id="2fbfc-120">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="2fbfc-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="2fbfc-121">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="2fbfc-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="2fbfc-122">请求标头</span><span class="sxs-lookup"><span data-stu-id="2fbfc-122">Request header</span></span>

<span data-ttu-id="2fbfc-123">名称</span><span class="sxs-lookup"><span data-stu-id="2fbfc-123">Name</span></span> | <span data-ttu-id="2fbfc-124">类型</span><span class="sxs-lookup"><span data-stu-id="2fbfc-124">Type</span></span> | <span data-ttu-id="2fbfc-125">说明</span><span class="sxs-lookup"><span data-stu-id="2fbfc-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="2fbfc-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="2fbfc-126">Authorization</span></span> | <span data-ttu-id="2fbfc-127">字符串</span><span class="sxs-lookup"><span data-stu-id="2fbfc-127">String</span></span> | <span data-ttu-id="2fbfc-128">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="2fbfc-128">Bearer {token}.</span></span> <span data-ttu-id="2fbfc-129">**必需**。</span><span class="sxs-lookup"><span data-stu-id="2fbfc-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2fbfc-130">请求正文</span><span class="sxs-lookup"><span data-stu-id="2fbfc-130">Request body</span></span>

<span data-ttu-id="2fbfc-131">Empty</span><span class="sxs-lookup"><span data-stu-id="2fbfc-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2fbfc-132">响应</span><span class="sxs-lookup"><span data-stu-id="2fbfc-132">Response</span></span>

<span data-ttu-id="2fbfc-133">如果成功，此方法返回 200 OK，正文中缺少指定的软件 kb 数据。</span><span class="sxs-lookup"><span data-stu-id="2fbfc-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="2fbfc-134">示例</span><span class="sxs-lookup"><span data-stu-id="2fbfc-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="2fbfc-135">请求</span><span class="sxs-lookup"><span data-stu-id="2fbfc-135">Request</span></span>

<span data-ttu-id="2fbfc-136">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="2fbfc-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="2fbfc-137">响应</span><span class="sxs-lookup"><span data-stu-id="2fbfc-137">Response</span></span>

<span data-ttu-id="2fbfc-138">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="2fbfc-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="2fbfc-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="2fbfc-139">Related topics</span></span>

- [<span data-ttu-id="2fbfc-140">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="2fbfc-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2fbfc-141">威胁&漏洞软件清单</span><span class="sxs-lookup"><span data-stu-id="2fbfc-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
