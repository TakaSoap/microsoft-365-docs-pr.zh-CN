---
title: 获取曝光分数
description: 检索组织曝光分数。
keywords: api， 图形 api， 受支持的 api， 获取， 曝光分数， 组织曝光分数
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c6b3f965c7abb1cb9208f0bfa157c1fd8aa3f891
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500712"
---
# <a name="get-exposure-score"></a><span data-ttu-id="f5bc3-104">获取曝光分数</span><span class="sxs-lookup"><span data-stu-id="f5bc3-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f5bc3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f5bc3-105">**Applies to:**</span></span>
- [<span data-ttu-id="f5bc3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f5bc3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f5bc3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5bc3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f5bc3-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f5bc3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f5bc3-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f5bc3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f5bc3-110">检索组织曝光分数。</span><span class="sxs-lookup"><span data-stu-id="f5bc3-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="f5bc3-111">权限</span><span class="sxs-lookup"><span data-stu-id="f5bc3-111">Permissions</span></span>

<span data-ttu-id="f5bc3-112">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="f5bc3-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f5bc3-113">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f5bc3-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f5bc3-114">权限类型</span><span class="sxs-lookup"><span data-stu-id="f5bc3-114">Permission type</span></span> | <span data-ttu-id="f5bc3-115">权限</span><span class="sxs-lookup"><span data-stu-id="f5bc3-115">Permission</span></span> | <span data-ttu-id="f5bc3-116">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="f5bc3-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f5bc3-117">应用程序</span><span class="sxs-lookup"><span data-stu-id="f5bc3-117">Application</span></span> | <span data-ttu-id="f5bc3-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="f5bc3-118">Score.Read.All</span></span> | <span data-ttu-id="f5bc3-119">"读取威胁和漏洞管理分数"</span><span class="sxs-lookup"><span data-stu-id="f5bc3-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="f5bc3-120">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="f5bc3-120">Delegated (work or school account)</span></span> | <span data-ttu-id="f5bc3-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="f5bc3-121">Score.Read</span></span> | <span data-ttu-id="f5bc3-122">"读取威胁和漏洞管理分数"</span><span class="sxs-lookup"><span data-stu-id="f5bc3-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="f5bc3-123">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="f5bc3-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="f5bc3-124">请求标头</span><span class="sxs-lookup"><span data-stu-id="f5bc3-124">Request headers</span></span>

<span data-ttu-id="f5bc3-125">名称</span><span class="sxs-lookup"><span data-stu-id="f5bc3-125">Name</span></span> | <span data-ttu-id="f5bc3-126">类型</span><span class="sxs-lookup"><span data-stu-id="f5bc3-126">Type</span></span> | <span data-ttu-id="f5bc3-127">说明</span><span class="sxs-lookup"><span data-stu-id="f5bc3-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="f5bc3-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="f5bc3-128">Authorization</span></span> | <span data-ttu-id="f5bc3-129">字符串</span><span class="sxs-lookup"><span data-stu-id="f5bc3-129">String</span></span> | <span data-ttu-id="f5bc3-130">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="f5bc3-130">Bearer {token}.</span></span> <span data-ttu-id="f5bc3-131">**必需**。</span><span class="sxs-lookup"><span data-stu-id="f5bc3-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f5bc3-132">请求正文</span><span class="sxs-lookup"><span data-stu-id="f5bc3-132">Request body</span></span>

<span data-ttu-id="f5bc3-133">Empty</span><span class="sxs-lookup"><span data-stu-id="f5bc3-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f5bc3-134">响应</span><span class="sxs-lookup"><span data-stu-id="f5bc3-134">Response</span></span>

<span data-ttu-id="f5bc3-135">如果成功，此方法返回 200 OK，响应正文中显示曝光数据。</span><span class="sxs-lookup"><span data-stu-id="f5bc3-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="f5bc3-136">示例</span><span class="sxs-lookup"><span data-stu-id="f5bc3-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="f5bc3-137">请求</span><span class="sxs-lookup"><span data-stu-id="f5bc3-137">Request</span></span>

<span data-ttu-id="f5bc3-138">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="f5bc3-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="f5bc3-139">响应</span><span class="sxs-lookup"><span data-stu-id="f5bc3-139">Response</span></span>

<span data-ttu-id="f5bc3-140">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="f5bc3-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="f5bc3-141">为简洁起见，可能会截断此处显示的响应列表。</span><span class="sxs-lookup"><span data-stu-id="f5bc3-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="f5bc3-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5bc3-142">See also</span></span>

- [<span data-ttu-id="f5bc3-143">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="f5bc3-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f5bc3-144">威胁&漏洞暴露分数</span><span class="sxs-lookup"><span data-stu-id="f5bc3-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
