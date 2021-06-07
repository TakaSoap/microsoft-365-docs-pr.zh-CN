---
title: 列出所有建议
description: 检索影响组织的所有安全建议的列表。
keywords: api， 图形 api， 受支持的 api， 获取， 安全建议， Microsoft Defender for Endpoint tvm api， 危险和漏洞管理， 危险和漏洞管理 api
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
ms.openlocfilehash: 0a58287a9bd48a4d19144a40674e1d3ad3bd256a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768920"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="b7c44-104">列出所有建议</span><span class="sxs-lookup"><span data-stu-id="b7c44-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7c44-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b7c44-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7c44-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b7c44-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b7c44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7c44-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="b7c44-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b7c44-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b7c44-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b7c44-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b7c44-110">检索影响组织的所有安全建议的列表。</span><span class="sxs-lookup"><span data-stu-id="b7c44-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="b7c44-111">权限</span><span class="sxs-lookup"><span data-stu-id="b7c44-111">Permissions</span></span>
<span data-ttu-id="b7c44-112">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="b7c44-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b7c44-113">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="b7c44-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b7c44-114">权限类型</span><span class="sxs-lookup"><span data-stu-id="b7c44-114">Permission type</span></span> |   <span data-ttu-id="b7c44-115">权限</span><span class="sxs-lookup"><span data-stu-id="b7c44-115">Permission</span></span>  |   <span data-ttu-id="b7c44-116">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="b7c44-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b7c44-117">应用程序</span><span class="sxs-lookup"><span data-stu-id="b7c44-117">Application</span></span> |   <span data-ttu-id="b7c44-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="b7c44-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="b7c44-119">"读取威胁和漏洞管理安全建议信息"</span><span class="sxs-lookup"><span data-stu-id="b7c44-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="b7c44-120">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="b7c44-120">Delegated (work or school account)</span></span> | <span data-ttu-id="b7c44-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="b7c44-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="b7c44-122">"读取威胁和漏洞管理安全建议信息"</span><span class="sxs-lookup"><span data-stu-id="b7c44-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b7c44-123">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="b7c44-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="b7c44-124">请求标头</span><span class="sxs-lookup"><span data-stu-id="b7c44-124">Request headers</span></span>

<span data-ttu-id="b7c44-125">名称</span><span class="sxs-lookup"><span data-stu-id="b7c44-125">Name</span></span> | <span data-ttu-id="b7c44-126">类型</span><span class="sxs-lookup"><span data-stu-id="b7c44-126">Type</span></span> | <span data-ttu-id="b7c44-127">说明</span><span class="sxs-lookup"><span data-stu-id="b7c44-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="b7c44-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="b7c44-128">Authorization</span></span> | <span data-ttu-id="b7c44-129">String</span><span class="sxs-lookup"><span data-stu-id="b7c44-129">String</span></span> | <span data-ttu-id="b7c44-130">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="b7c44-130">Bearer {token}.</span></span> <span data-ttu-id="b7c44-131">**必需**。</span><span class="sxs-lookup"><span data-stu-id="b7c44-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b7c44-132">请求正文</span><span class="sxs-lookup"><span data-stu-id="b7c44-132">Request body</span></span>
<span data-ttu-id="b7c44-133">Empty</span><span class="sxs-lookup"><span data-stu-id="b7c44-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b7c44-134">响应</span><span class="sxs-lookup"><span data-stu-id="b7c44-134">Response</span></span>
<span data-ttu-id="b7c44-135">如果成功，此方法在正文中返回 200 OK 以及安全建议列表。</span><span class="sxs-lookup"><span data-stu-id="b7c44-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="b7c44-136">示例</span><span class="sxs-lookup"><span data-stu-id="b7c44-136">Example</span></span>

<span data-ttu-id="b7c44-137">**请求**</span><span class="sxs-lookup"><span data-stu-id="b7c44-137">**Request**</span></span>

<span data-ttu-id="b7c44-138">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="b7c44-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="b7c44-139">**响应**</span><span class="sxs-lookup"><span data-stu-id="b7c44-139">**Response**</span></span>

<span data-ttu-id="b7c44-140">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="b7c44-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a><span data-ttu-id="b7c44-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7c44-141">See also</span></span>
- [<span data-ttu-id="b7c44-142">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="b7c44-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b7c44-143">威胁&漏洞安全建议</span><span class="sxs-lookup"><span data-stu-id="b7c44-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

