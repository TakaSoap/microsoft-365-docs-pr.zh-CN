---
title: 获取安全建议
description: 检索与给定设备 ID 相关的安全建议集合。
keywords: api， 图形 api， 受支持的 api， 获取， 列表， 文件， 信息， 每个设备的安全建议， 威胁& 漏洞管理 api， Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: bc209687d51b3e05bfcfd6028042ba5912b877f6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935301"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="10437-104">获取安全建议</span><span class="sxs-lookup"><span data-stu-id="10437-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="10437-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="10437-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="10437-106">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="10437-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="10437-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="10437-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="10437-108">检索与给定设备 ID 相关的安全建议集合。</span><span class="sxs-lookup"><span data-stu-id="10437-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="10437-109">权限</span><span class="sxs-lookup"><span data-stu-id="10437-109">Permissions</span></span>
<span data-ttu-id="10437-110">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="10437-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="10437-111">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="10437-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="10437-112">权限类型</span><span class="sxs-lookup"><span data-stu-id="10437-112">Permission type</span></span> |   <span data-ttu-id="10437-113">权限</span><span class="sxs-lookup"><span data-stu-id="10437-113">Permission</span></span>  |   <span data-ttu-id="10437-114">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="10437-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="10437-115">应用程序</span><span class="sxs-lookup"><span data-stu-id="10437-115">Application</span></span> | <span data-ttu-id="10437-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="10437-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="10437-117">"读取威胁和漏洞管理安全建议信息"</span><span class="sxs-lookup"><span data-stu-id="10437-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="10437-118">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="10437-118">Delegated (work or school account)</span></span> | <span data-ttu-id="10437-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="10437-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="10437-120">"读取威胁和漏洞管理安全建议信息"</span><span class="sxs-lookup"><span data-stu-id="10437-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="10437-121">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="10437-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="10437-122">请求标头</span><span class="sxs-lookup"><span data-stu-id="10437-122">Request headers</span></span>

<span data-ttu-id="10437-123">名称</span><span class="sxs-lookup"><span data-stu-id="10437-123">Name</span></span> | <span data-ttu-id="10437-124">类型</span><span class="sxs-lookup"><span data-stu-id="10437-124">Type</span></span> | <span data-ttu-id="10437-125">说明</span><span class="sxs-lookup"><span data-stu-id="10437-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="10437-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="10437-126">Authorization</span></span> | <span data-ttu-id="10437-127">String</span><span class="sxs-lookup"><span data-stu-id="10437-127">String</span></span> | <span data-ttu-id="10437-128">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="10437-128">Bearer {token}.</span></span> <span data-ttu-id="10437-129">**必需**。</span><span class="sxs-lookup"><span data-stu-id="10437-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="10437-130">请求正文</span><span class="sxs-lookup"><span data-stu-id="10437-130">Request body</span></span>
<span data-ttu-id="10437-131">Empty</span><span class="sxs-lookup"><span data-stu-id="10437-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="10437-132">响应</span><span class="sxs-lookup"><span data-stu-id="10437-132">Response</span></span>
<span data-ttu-id="10437-133">如果成功，此方法在正文中返回 200 OK 以及安全建议。</span><span class="sxs-lookup"><span data-stu-id="10437-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="10437-134">示例</span><span class="sxs-lookup"><span data-stu-id="10437-134">Example</span></span>

<span data-ttu-id="10437-135">**请求**</span><span class="sxs-lookup"><span data-stu-id="10437-135">**Request**</span></span>

<span data-ttu-id="10437-136">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="10437-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="10437-137">**响应**</span><span class="sxs-lookup"><span data-stu-id="10437-137">**Response**</span></span>

<span data-ttu-id="10437-138">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="10437-138">Here is an example of the response.</span></span>


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a><span data-ttu-id="10437-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="10437-139">Related topics</span></span>
- [<span data-ttu-id="10437-140">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="10437-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="10437-141">威胁&漏洞安全建议</span><span class="sxs-lookup"><span data-stu-id="10437-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
