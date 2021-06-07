---
title: 按 Id 获取建议
description: 按 ID 检索安全建议。
keywords: api， 图形 api， 受支持的 api， 获取， 安全建议， 按 ID 的安全建议， 危险和漏洞管理， 危险和漏洞管理 api
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
ms.openlocfilehash: 4ec4758453f43cb211143918ed5fe8fe83e91c3f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771797"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="1c584-104">按 ID 获取建议</span><span class="sxs-lookup"><span data-stu-id="1c584-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c584-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1c584-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1c584-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1c584-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1c584-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1c584-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1c584-108">按 ID 检索安全建议。</span><span class="sxs-lookup"><span data-stu-id="1c584-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="1c584-109">权限</span><span class="sxs-lookup"><span data-stu-id="1c584-109">Permissions</span></span>
<span data-ttu-id="1c584-110">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="1c584-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1c584-111">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="1c584-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1c584-112">权限类型</span><span class="sxs-lookup"><span data-stu-id="1c584-112">Permission type</span></span> |   <span data-ttu-id="1c584-113">权限</span><span class="sxs-lookup"><span data-stu-id="1c584-113">Permission</span></span>  |   <span data-ttu-id="1c584-114">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="1c584-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1c584-115">应用程序</span><span class="sxs-lookup"><span data-stu-id="1c584-115">Application</span></span> |   <span data-ttu-id="1c584-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="1c584-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="1c584-117">"读取威胁和漏洞管理安全建议信息"</span><span class="sxs-lookup"><span data-stu-id="1c584-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="1c584-118">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="1c584-118">Delegated (work or school account)</span></span> | <span data-ttu-id="1c584-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="1c584-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="1c584-120">"读取威胁和漏洞管理安全建议信息"</span><span class="sxs-lookup"><span data-stu-id="1c584-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1c584-121">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="1c584-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="1c584-122">请求标头</span><span class="sxs-lookup"><span data-stu-id="1c584-122">Request headers</span></span>

<span data-ttu-id="1c584-123">名称</span><span class="sxs-lookup"><span data-stu-id="1c584-123">Name</span></span> | <span data-ttu-id="1c584-124">类型</span><span class="sxs-lookup"><span data-stu-id="1c584-124">Type</span></span> | <span data-ttu-id="1c584-125">说明</span><span class="sxs-lookup"><span data-stu-id="1c584-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="1c584-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="1c584-126">Authorization</span></span> | <span data-ttu-id="1c584-127">String</span><span class="sxs-lookup"><span data-stu-id="1c584-127">String</span></span> | <span data-ttu-id="1c584-128">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="1c584-128">Bearer {token}.</span></span> <span data-ttu-id="1c584-129">**必需**。</span><span class="sxs-lookup"><span data-stu-id="1c584-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1c584-130">请求正文</span><span class="sxs-lookup"><span data-stu-id="1c584-130">Request body</span></span>
<span data-ttu-id="1c584-131">Empty</span><span class="sxs-lookup"><span data-stu-id="1c584-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1c584-132">响应</span><span class="sxs-lookup"><span data-stu-id="1c584-132">Response</span></span>
<span data-ttu-id="1c584-133">如果成功，此方法在正文中返回 200 OK 以及安全建议。</span><span class="sxs-lookup"><span data-stu-id="1c584-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="1c584-134">示例</span><span class="sxs-lookup"><span data-stu-id="1c584-134">Example</span></span>

<span data-ttu-id="1c584-135">**请求**</span><span class="sxs-lookup"><span data-stu-id="1c584-135">**Request**</span></span>

<span data-ttu-id="1c584-136">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="1c584-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="1c584-137">**响应**</span><span class="sxs-lookup"><span data-stu-id="1c584-137">**Response**</span></span>

<span data-ttu-id="1c584-138">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="1c584-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a><span data-ttu-id="1c584-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="1c584-139">Related topics</span></span>
- [<span data-ttu-id="1c584-140">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="1c584-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1c584-141">威胁&漏洞安全建议</span><span class="sxs-lookup"><span data-stu-id="1c584-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
