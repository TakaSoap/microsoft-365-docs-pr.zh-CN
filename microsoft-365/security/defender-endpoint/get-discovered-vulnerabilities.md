---
title: 获取发现的漏洞
description: 检索与给定设备 ID 相关的已发现漏洞的集合。
keywords: api， 图形 api， 受支持的 api， 获取， 列表， 文件， 信息， 发现的漏洞， 威胁&漏洞管理 api， mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 08fa910c8d4c7130fdb3ed564a97cdbd2f31d233
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166325"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="f07a7-104">获取发现的漏洞</span><span class="sxs-lookup"><span data-stu-id="f07a7-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f07a7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f07a7-105">**Applies to:**</span></span>
- [<span data-ttu-id="f07a7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f07a7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f07a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f07a7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f07a7-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f07a7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f07a7-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f07a7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="f07a7-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="f07a7-110">API description</span></span>
<span data-ttu-id="f07a7-111">检索与给定设备 ID 相关的已发现漏洞的集合。</span><span class="sxs-lookup"><span data-stu-id="f07a7-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="f07a7-112">限制</span><span class="sxs-lookup"><span data-stu-id="f07a7-112">Limitations</span></span>
1. <span data-ttu-id="f07a7-113">此 API 的速率限制是每分钟 50 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="f07a7-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="f07a7-114">权限</span><span class="sxs-lookup"><span data-stu-id="f07a7-114">Permissions</span></span>

<span data-ttu-id="f07a7-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="f07a7-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f07a7-116">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f07a7-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f07a7-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="f07a7-117">Permission type</span></span> | <span data-ttu-id="f07a7-118">权限</span><span class="sxs-lookup"><span data-stu-id="f07a7-118">Permission</span></span> | <span data-ttu-id="f07a7-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="f07a7-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f07a7-120">Application</span><span class="sxs-lookup"><span data-stu-id="f07a7-120">Application</span></span> |<span data-ttu-id="f07a7-121">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="f07a7-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="f07a7-122">"读取威胁和漏洞管理漏洞信息"</span><span class="sxs-lookup"><span data-stu-id="f07a7-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="f07a7-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="f07a7-123">Delegated (work or school account)</span></span> | <span data-ttu-id="f07a7-124">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="f07a7-124">Vulnerability.Read</span></span> | <span data-ttu-id="f07a7-125">"读取威胁和漏洞管理漏洞信息"</span><span class="sxs-lookup"><span data-stu-id="f07a7-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="f07a7-126">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="f07a7-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="f07a7-127">请求标头</span><span class="sxs-lookup"><span data-stu-id="f07a7-127">Request headers</span></span>

<span data-ttu-id="f07a7-128">名称</span><span class="sxs-lookup"><span data-stu-id="f07a7-128">Name</span></span> | <span data-ttu-id="f07a7-129">类型</span><span class="sxs-lookup"><span data-stu-id="f07a7-129">Type</span></span> | <span data-ttu-id="f07a7-130">说明</span><span class="sxs-lookup"><span data-stu-id="f07a7-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="f07a7-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="f07a7-131">Authorization</span></span> | <span data-ttu-id="f07a7-132">String</span><span class="sxs-lookup"><span data-stu-id="f07a7-132">String</span></span> | <span data-ttu-id="f07a7-133">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="f07a7-133">Bearer {token}.</span></span> <span data-ttu-id="f07a7-134">**必需**。</span><span class="sxs-lookup"><span data-stu-id="f07a7-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f07a7-135">请求正文</span><span class="sxs-lookup"><span data-stu-id="f07a7-135">Request body</span></span>

<span data-ttu-id="f07a7-136">Empty</span><span class="sxs-lookup"><span data-stu-id="f07a7-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f07a7-137">响应</span><span class="sxs-lookup"><span data-stu-id="f07a7-137">Response</span></span>

<span data-ttu-id="f07a7-138">如果成功，此方法在正文中返回 200 OK 和发现的漏洞信息。</span><span class="sxs-lookup"><span data-stu-id="f07a7-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="f07a7-139">示例</span><span class="sxs-lookup"><span data-stu-id="f07a7-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="f07a7-140">请求</span><span class="sxs-lookup"><span data-stu-id="f07a7-140">Request</span></span>

<span data-ttu-id="f07a7-141">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="f07a7-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="f07a7-142">响应</span><span class="sxs-lookup"><span data-stu-id="f07a7-142">Response</span></span>

<span data-ttu-id="f07a7-143">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="f07a7-143">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
}
```

## <a name="see-also"></a><span data-ttu-id="f07a7-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f07a7-144">See also</span></span>

- [<span data-ttu-id="f07a7-145">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="f07a7-145">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f07a7-146">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="f07a7-146">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
