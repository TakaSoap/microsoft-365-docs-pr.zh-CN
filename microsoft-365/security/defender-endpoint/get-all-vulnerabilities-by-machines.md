---
title: 通过计算机和软件获取所有漏洞
description: 检索计算机和软件影响组织的所有漏洞的列表
keywords: api， 图形 api， 受支持的 api， 获取， 漏洞信息， Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 229c1f9e77a0cb85744155e82934b48dd63052b2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933405"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a><span data-ttu-id="1263d-104">按计算机和软件列出漏洞</span><span class="sxs-lookup"><span data-stu-id="1263d-104">List vulnerabilities by machine and software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1263d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1263d-105">**Applies to:**</span></span>
- [<span data-ttu-id="1263d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1263d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1263d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1263d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1263d-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1263d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1263d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1263d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="1263d-110">检索每台计算机和软件影响组织的所有[漏洞](machine.md)[的列表](software.md)。</span><span class="sxs-lookup"><span data-stu-id="1263d-110">Retrieves a list of all the vulnerabilities affecting the organization per [machine](machine.md) and [software](software.md).</span></span>
- <span data-ttu-id="1263d-111">如果漏洞具有修复 KB，它将出现在响应中。</span><span class="sxs-lookup"><span data-stu-id="1263d-111">If the vulnerability has a fixing KB, it will appear in the response.</span></span>
- <span data-ttu-id="1263d-112">支持 [OData V4 查询](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="1263d-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
- <span data-ttu-id="1263d-113">OData ```$filter``` 在所有属性上均受支持。</span><span class="sxs-lookup"><span data-stu-id="1263d-113">The OData ```$filter``` is supported on all properties.</span></span>

>[!Tip]
><span data-ttu-id="1263d-114">这是适用于集成Power BI [API。](api-power-bi.md)</span><span class="sxs-lookup"><span data-stu-id="1263d-114">This is great API for [Power BI integration](api-power-bi.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="1263d-115">权限</span><span class="sxs-lookup"><span data-stu-id="1263d-115">Permissions</span></span>
<span data-ttu-id="1263d-116">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="1263d-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1263d-117">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="1263d-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1263d-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="1263d-118">Permission type</span></span> |   <span data-ttu-id="1263d-119">权限</span><span class="sxs-lookup"><span data-stu-id="1263d-119">Permission</span></span>  |   <span data-ttu-id="1263d-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="1263d-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1263d-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="1263d-121">Application</span></span> |   <span data-ttu-id="1263d-122">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="1263d-122">Vulnerability.Read.All</span></span> |    <span data-ttu-id="1263d-123">"读取威胁和漏洞管理漏洞信息"</span><span class="sxs-lookup"><span data-stu-id="1263d-123">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="1263d-124">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="1263d-124">Delegated (work or school account)</span></span> | <span data-ttu-id="1263d-125">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="1263d-125">Vulnerability.Read</span></span> |   <span data-ttu-id="1263d-126">"读取威胁和漏洞管理漏洞信息"</span><span class="sxs-lookup"><span data-stu-id="1263d-126">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1263d-127">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="1263d-127">HTTP request</span></span>
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="1263d-128">请求标头</span><span class="sxs-lookup"><span data-stu-id="1263d-128">Request headers</span></span>

<span data-ttu-id="1263d-129">名称</span><span class="sxs-lookup"><span data-stu-id="1263d-129">Name</span></span> | <span data-ttu-id="1263d-130">类型</span><span class="sxs-lookup"><span data-stu-id="1263d-130">Type</span></span> | <span data-ttu-id="1263d-131">说明</span><span class="sxs-lookup"><span data-stu-id="1263d-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="1263d-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="1263d-132">Authorization</span></span> | <span data-ttu-id="1263d-133">String</span><span class="sxs-lookup"><span data-stu-id="1263d-133">String</span></span> | <span data-ttu-id="1263d-134">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="1263d-134">Bearer {token}.</span></span> <span data-ttu-id="1263d-135">**必需**。</span><span class="sxs-lookup"><span data-stu-id="1263d-135">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1263d-136">请求正文</span><span class="sxs-lookup"><span data-stu-id="1263d-136">Request body</span></span>
<span data-ttu-id="1263d-137">Empty</span><span class="sxs-lookup"><span data-stu-id="1263d-137">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1263d-138">响应</span><span class="sxs-lookup"><span data-stu-id="1263d-138">Response</span></span>
<span data-ttu-id="1263d-139">如果成功，此方法返回 200 OK，并返回正文中的漏洞列表。</span><span class="sxs-lookup"><span data-stu-id="1263d-139">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="1263d-140">示例</span><span class="sxs-lookup"><span data-stu-id="1263d-140">Example</span></span>

<span data-ttu-id="1263d-141">**请求**</span><span class="sxs-lookup"><span data-stu-id="1263d-141">**Request**</span></span>

<span data-ttu-id="1263d-142">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="1263d-142">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

<span data-ttu-id="1263d-143">**响应**</span><span class="sxs-lookup"><span data-stu-id="1263d-143">**Response**</span></span>

<span data-ttu-id="1263d-144">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="1263d-144">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="1263d-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1263d-145">See also</span></span>

- [<span data-ttu-id="1263d-146">基于风险危险和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="1263d-146">Risk-based threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1263d-147">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="1263d-147">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
