---
title: 按建议列出漏洞
description: 检索与安全建议关联的漏洞列表。
keywords: api， 图形 api， 受支持的 api， 获取， 漏洞列表， 安全建议， 针对漏洞的安全建议， 危险和漏洞管理， 危险和漏洞管理 api
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
ms.openlocfilehash: b41ee2886d758ab0ab70b78ee6d6d863d0d482a7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198597"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="966f0-104">按建议列出漏洞</span><span class="sxs-lookup"><span data-stu-id="966f0-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="966f0-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="966f0-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="966f0-106">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="966f0-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="966f0-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="966f0-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="966f0-108">检索与安全建议关联的漏洞列表。</span><span class="sxs-lookup"><span data-stu-id="966f0-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="966f0-109">权限</span><span class="sxs-lookup"><span data-stu-id="966f0-109">Permissions</span></span>
<span data-ttu-id="966f0-110">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="966f0-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="966f0-111">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="966f0-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="966f0-112">权限类型</span><span class="sxs-lookup"><span data-stu-id="966f0-112">Permission type</span></span> |   <span data-ttu-id="966f0-113">权限</span><span class="sxs-lookup"><span data-stu-id="966f0-113">Permission</span></span>  |   <span data-ttu-id="966f0-114">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="966f0-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="966f0-115">应用程序</span><span class="sxs-lookup"><span data-stu-id="966f0-115">Application</span></span> |   <span data-ttu-id="966f0-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="966f0-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="966f0-117">"读取威胁和漏洞管理安全建议信息"</span><span class="sxs-lookup"><span data-stu-id="966f0-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="966f0-118">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="966f0-118">Delegated (work or school account)</span></span> | <span data-ttu-id="966f0-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="966f0-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="966f0-120">"读取威胁和漏洞管理安全建议信息"</span><span class="sxs-lookup"><span data-stu-id="966f0-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="966f0-121">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="966f0-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="966f0-122">请求标头</span><span class="sxs-lookup"><span data-stu-id="966f0-122">Request headers</span></span>

<span data-ttu-id="966f0-123">名称</span><span class="sxs-lookup"><span data-stu-id="966f0-123">Name</span></span> | <span data-ttu-id="966f0-124">类型</span><span class="sxs-lookup"><span data-stu-id="966f0-124">Type</span></span> | <span data-ttu-id="966f0-125">说明</span><span class="sxs-lookup"><span data-stu-id="966f0-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="966f0-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="966f0-126">Authorization</span></span> | <span data-ttu-id="966f0-127">String</span><span class="sxs-lookup"><span data-stu-id="966f0-127">String</span></span> | <span data-ttu-id="966f0-128">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="966f0-128">Bearer {token}.</span></span> <span data-ttu-id="966f0-129">**必需**。</span><span class="sxs-lookup"><span data-stu-id="966f0-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="966f0-130">请求正文</span><span class="sxs-lookup"><span data-stu-id="966f0-130">Request body</span></span>
<span data-ttu-id="966f0-131">Empty</span><span class="sxs-lookup"><span data-stu-id="966f0-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="966f0-132">响应</span><span class="sxs-lookup"><span data-stu-id="966f0-132">Response</span></span>
<span data-ttu-id="966f0-133">如果成功，此方法将返回 200 OK，并包含与安全建议相关联的漏洞列表。</span><span class="sxs-lookup"><span data-stu-id="966f0-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="966f0-134">示例</span><span class="sxs-lookup"><span data-stu-id="966f0-134">Example</span></span>

<span data-ttu-id="966f0-135">**请求**</span><span class="sxs-lookup"><span data-stu-id="966f0-135">**Request**</span></span>

<span data-ttu-id="966f0-136">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="966f0-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="966f0-137">**响应**</span><span class="sxs-lookup"><span data-stu-id="966f0-137">**Response**</span></span>

<span data-ttu-id="966f0-138">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="966f0-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
     ]
}
```

## <a name="related-topics"></a><span data-ttu-id="966f0-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="966f0-139">Related topics</span></span>
- [<span data-ttu-id="966f0-140">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="966f0-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="966f0-141">威胁&漏洞安全建议</span><span class="sxs-lookup"><span data-stu-id="966f0-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
