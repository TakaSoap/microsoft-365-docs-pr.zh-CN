---
title: 获取所有漏洞
description: 检索影响组织的所有漏洞的列表
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 6def1b64430ad70dc4b4898ba2b914288826873e
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861487"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="f5381-104">列出漏洞</span><span class="sxs-lookup"><span data-stu-id="f5381-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f5381-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f5381-105">**Applies to:**</span></span>
- [<span data-ttu-id="f5381-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f5381-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f5381-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5381-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f5381-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f5381-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f5381-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f5381-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f5381-110">检索所有漏洞的列表。</span><span class="sxs-lookup"><span data-stu-id="f5381-110">Retrieves a list of all the vulnerabilities.</span></span>

## <a name="permissions"></a><span data-ttu-id="f5381-111">权限</span><span class="sxs-lookup"><span data-stu-id="f5381-111">Permissions</span></span>
<span data-ttu-id="f5381-112">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="f5381-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f5381-113">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="f5381-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="f5381-114">权限类型</span><span class="sxs-lookup"><span data-stu-id="f5381-114">Permission type</span></span> |   <span data-ttu-id="f5381-115">权限</span><span class="sxs-lookup"><span data-stu-id="f5381-115">Permission</span></span>  |   <span data-ttu-id="f5381-116">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="f5381-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f5381-117">应用程序</span><span class="sxs-lookup"><span data-stu-id="f5381-117">Application</span></span> |   <span data-ttu-id="f5381-118">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="f5381-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="f5381-119">"读取威胁和漏洞管理漏洞信息"</span><span class="sxs-lookup"><span data-stu-id="f5381-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="f5381-120">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="f5381-120">Delegated (work or school account)</span></span> | <span data-ttu-id="f5381-121">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="f5381-121">Vulnerability.Read</span></span> |   <span data-ttu-id="f5381-122">"读取威胁和漏洞管理漏洞信息"</span><span class="sxs-lookup"><span data-stu-id="f5381-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="f5381-123">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="f5381-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="f5381-124">请求标头</span><span class="sxs-lookup"><span data-stu-id="f5381-124">Request headers</span></span>

<span data-ttu-id="f5381-125">名称</span><span class="sxs-lookup"><span data-stu-id="f5381-125">Name</span></span> | <span data-ttu-id="f5381-126">类型</span><span class="sxs-lookup"><span data-stu-id="f5381-126">Type</span></span> | <span data-ttu-id="f5381-127">说明</span><span class="sxs-lookup"><span data-stu-id="f5381-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="f5381-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="f5381-128">Authorization</span></span> | <span data-ttu-id="f5381-129">String</span><span class="sxs-lookup"><span data-stu-id="f5381-129">String</span></span> | <span data-ttu-id="f5381-130">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="f5381-130">Bearer {token}.</span></span> <span data-ttu-id="f5381-131">**必需**。</span><span class="sxs-lookup"><span data-stu-id="f5381-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f5381-132">请求正文</span><span class="sxs-lookup"><span data-stu-id="f5381-132">Request body</span></span>
<span data-ttu-id="f5381-133">Empty</span><span class="sxs-lookup"><span data-stu-id="f5381-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f5381-134">响应</span><span class="sxs-lookup"><span data-stu-id="f5381-134">Response</span></span>
<span data-ttu-id="f5381-135">如果成功，此方法返回 200 OK，并返回正文中的漏洞列表。</span><span class="sxs-lookup"><span data-stu-id="f5381-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="f5381-136">示例</span><span class="sxs-lookup"><span data-stu-id="f5381-136">Example</span></span>

<span data-ttu-id="f5381-137">**请求**</span><span class="sxs-lookup"><span data-stu-id="f5381-137">**Request**</span></span>

<span data-ttu-id="f5381-138">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="f5381-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="f5381-139">**响应**</span><span class="sxs-lookup"><span data-stu-id="f5381-139">**Response**</span></span>

<span data-ttu-id="f5381-140">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="f5381-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Vulnerabilities",
    "value": [
        {
            "id": "CVE-2019-0608",
            "name": "CVE-2019-0608",
            "description": "A spoofing vulnerability exists when Microsoft Browsers does not properly parse HTTP content. An attacker who successfully exploited this vulnerability could impersonate a user request by crafting HTTP queries. The specially crafted website could either spoof content or serve as a pivot to chain an attack with other vulnerabilities in web services.To exploit the vulnerability, the user must click a specially crafted URL. In an email attack scenario, an attacker could send an email message containing the specially crafted URL to the user in an attempt to convince the user to click it.In a web-based attack scenario, an attacker could host a specially crafted website designed to appear as a legitimate website to the user. However, the attacker would have no way to force the user to visit the specially crafted website. The attacker would have to convince the user to visit the specially crafted website, typically by way of enticement in an email or instant message, and then convince the user to interact with content on the website.The update addresses the vulnerability by correcting how Microsoft Browsers parses HTTP responses.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 4,
            "publishedOn": "2019-10-08T00:00:00Z",
            "updatedOn": "2019-12-16T16:20:00Z",
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

## <a name="see-also"></a><span data-ttu-id="f5381-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5381-141">See also</span></span>
- [<span data-ttu-id="f5381-142">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="f5381-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f5381-143">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="f5381-143">Vulnerabilities in your organization</span></span>](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
