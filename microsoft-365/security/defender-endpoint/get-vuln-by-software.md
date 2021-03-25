---
title: 按软件列出漏洞
description: 检索已安装软件中的漏洞列表。
keywords: api， 图形 api， 受支持的 api， 获取， 漏洞列表， mdatp tvm api
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
ms.openlocfilehash: 8f05c1a67c845e7f88cbcb3ee88cf7a664d5a4bf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166488"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="a428f-104">按软件列出漏洞</span><span class="sxs-lookup"><span data-stu-id="a428f-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a428f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a428f-105">**Applies to:**</span></span>
- [<span data-ttu-id="a428f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a428f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a428f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a428f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a428f-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="a428f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a428f-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a428f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a428f-110">检索已安装软件中的漏洞列表。</span><span class="sxs-lookup"><span data-stu-id="a428f-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="a428f-111">权限</span><span class="sxs-lookup"><span data-stu-id="a428f-111">Permissions</span></span>
<span data-ttu-id="a428f-112">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="a428f-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a428f-113">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a428f-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="a428f-114">权限类型</span><span class="sxs-lookup"><span data-stu-id="a428f-114">Permission type</span></span> |   <span data-ttu-id="a428f-115">权限</span><span class="sxs-lookup"><span data-stu-id="a428f-115">Permission</span></span>  |   <span data-ttu-id="a428f-116">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="a428f-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a428f-117">Application</span><span class="sxs-lookup"><span data-stu-id="a428f-117">Application</span></span> | <span data-ttu-id="a428f-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="a428f-118">Software.Read.All</span></span> | <span data-ttu-id="a428f-119">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="a428f-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="a428f-120">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="a428f-120">Delegated (work or school account)</span></span> | <span data-ttu-id="a428f-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="a428f-121">Software.Read</span></span> | <span data-ttu-id="a428f-122">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="a428f-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="a428f-123">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="a428f-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="a428f-124">请求标头</span><span class="sxs-lookup"><span data-stu-id="a428f-124">Request headers</span></span>

| <span data-ttu-id="a428f-125">名称</span><span class="sxs-lookup"><span data-stu-id="a428f-125">Name</span></span>        | <span data-ttu-id="a428f-126">类型</span><span class="sxs-lookup"><span data-stu-id="a428f-126">Type</span></span> | <span data-ttu-id="a428f-127">说明</span><span class="sxs-lookup"><span data-stu-id="a428f-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="a428f-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="a428f-128">Authorization</span></span> | <span data-ttu-id="a428f-129">String</span><span class="sxs-lookup"><span data-stu-id="a428f-129">String</span></span> | <span data-ttu-id="a428f-130">Bearer {token}。**必需**。</span><span class="sxs-lookup"><span data-stu-id="a428f-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a428f-131">请求正文</span><span class="sxs-lookup"><span data-stu-id="a428f-131">Request body</span></span>
<span data-ttu-id="a428f-132">Empty</span><span class="sxs-lookup"><span data-stu-id="a428f-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a428f-133">响应</span><span class="sxs-lookup"><span data-stu-id="a428f-133">Response</span></span>
<span data-ttu-id="a428f-134">如果成功，此方法返回 200 OK，并列出指定软件公开的漏洞。</span><span class="sxs-lookup"><span data-stu-id="a428f-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="a428f-135">示例</span><span class="sxs-lookup"><span data-stu-id="a428f-135">Example</span></span>

<span data-ttu-id="a428f-136">**请求**</span><span class="sxs-lookup"><span data-stu-id="a428f-136">**Request**</span></span>

<span data-ttu-id="a428f-137">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="a428f-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="a428f-138">**响应**</span><span class="sxs-lookup"><span data-stu-id="a428f-138">**Response**</span></span>

<span data-ttu-id="a428f-139">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="a428f-139">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
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

