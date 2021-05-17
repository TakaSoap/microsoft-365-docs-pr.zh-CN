---
title: 按软件获取建议
description: 检索与特定软件相关的安全建议。
keywords: api， 图形 api， 受支持的 api， 获取， 安全建议， 软件安全建议， 危险和漏洞管理， 危险和漏洞管理 api
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
ms.openlocfilehash: 82479b0248ceee95321d269e3f48a4eeea3ad193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199497"
---
# <a name="get-recommendation-by-software"></a><span data-ttu-id="0112e-104">按软件获取建议</span><span class="sxs-lookup"><span data-stu-id="0112e-104">Get recommendation by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0112e-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0112e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="0112e-106">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="0112e-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0112e-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="0112e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="0112e-108">检索与特定软件相关的安全建议。</span><span class="sxs-lookup"><span data-stu-id="0112e-108">Retrieves a security recommendation related to a specific software.</span></span>

## <a name="permissions"></a><span data-ttu-id="0112e-109">权限</span><span class="sxs-lookup"><span data-stu-id="0112e-109">Permissions</span></span>
<span data-ttu-id="0112e-110">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="0112e-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0112e-111">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="0112e-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="0112e-112">权限类型</span><span class="sxs-lookup"><span data-stu-id="0112e-112">Permission type</span></span> |   <span data-ttu-id="0112e-113">权限</span><span class="sxs-lookup"><span data-stu-id="0112e-113">Permission</span></span>  |   <span data-ttu-id="0112e-114">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="0112e-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0112e-115">应用程序</span><span class="sxs-lookup"><span data-stu-id="0112e-115">Application</span></span> |   <span data-ttu-id="0112e-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="0112e-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="0112e-117">"读取威胁和漏洞管理安全建议信息"</span><span class="sxs-lookup"><span data-stu-id="0112e-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="0112e-118">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="0112e-118">Delegated (work or school account)</span></span> | <span data-ttu-id="0112e-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="0112e-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="0112e-120">"读取威胁和漏洞管理安全建议信息"</span><span class="sxs-lookup"><span data-stu-id="0112e-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="0112e-121">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="0112e-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a><span data-ttu-id="0112e-122">请求标头</span><span class="sxs-lookup"><span data-stu-id="0112e-122">Request headers</span></span>

<span data-ttu-id="0112e-123">名称</span><span class="sxs-lookup"><span data-stu-id="0112e-123">Name</span></span> | <span data-ttu-id="0112e-124">类型</span><span class="sxs-lookup"><span data-stu-id="0112e-124">Type</span></span> | <span data-ttu-id="0112e-125">说明</span><span class="sxs-lookup"><span data-stu-id="0112e-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="0112e-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="0112e-126">Authorization</span></span> | <span data-ttu-id="0112e-127">String</span><span class="sxs-lookup"><span data-stu-id="0112e-127">String</span></span> | <span data-ttu-id="0112e-128">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="0112e-128">Bearer {token}.</span></span> <span data-ttu-id="0112e-129">**必需**。</span><span class="sxs-lookup"><span data-stu-id="0112e-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0112e-130">请求正文</span><span class="sxs-lookup"><span data-stu-id="0112e-130">Request body</span></span>
<span data-ttu-id="0112e-131">Empty</span><span class="sxs-lookup"><span data-stu-id="0112e-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0112e-132">响应</span><span class="sxs-lookup"><span data-stu-id="0112e-132">Response</span></span>
<span data-ttu-id="0112e-133">如果成功，此方法返回 200 OK，并返回与正文中的安全建议关联的软件。</span><span class="sxs-lookup"><span data-stu-id="0112e-133">If successful, this method returns 200 OK with the software associated with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="0112e-134">示例</span><span class="sxs-lookup"><span data-stu-id="0112e-134">Example</span></span>

<span data-ttu-id="0112e-135">**请求**</span><span class="sxs-lookup"><span data-stu-id="0112e-135">**Request**</span></span>

<span data-ttu-id="0112e-136">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="0112e-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

<span data-ttu-id="0112e-137">**响应**</span><span class="sxs-lookup"><span data-stu-id="0112e-137">**Response**</span></span>

<span data-ttu-id="0112e-138">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="0112e-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a><span data-ttu-id="0112e-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="0112e-139">Related topics</span></span>
- [<span data-ttu-id="0112e-140">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="0112e-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="0112e-141">威胁&漏洞安全建议</span><span class="sxs-lookup"><span data-stu-id="0112e-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
