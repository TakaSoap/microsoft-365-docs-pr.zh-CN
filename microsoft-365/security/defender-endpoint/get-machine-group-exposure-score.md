---
title: 按设备组列出曝光分数
description: 按设备组检索曝光评分列表。
keywords: api， 图形 api， 受支持的 api， 获取， 曝光分数， 设备组， 设备组曝光分数
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 71daccdbcb223ac48d80721bf0a296d9c1a7c98c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770093"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="777e8-104">按设备组列出曝光分数</span><span class="sxs-lookup"><span data-stu-id="777e8-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="777e8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="777e8-105">**Applies to:**</span></span>
- [<span data-ttu-id="777e8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="777e8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="777e8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="777e8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="777e8-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="777e8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="777e8-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="777e8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="777e8-110">检索与给定域地址相关的警报集合。</span><span class="sxs-lookup"><span data-stu-id="777e8-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="777e8-111">权限</span><span class="sxs-lookup"><span data-stu-id="777e8-111">Permissions</span></span>

<span data-ttu-id="777e8-112">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="777e8-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="777e8-113">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="777e8-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="777e8-114">权限类型</span><span class="sxs-lookup"><span data-stu-id="777e8-114">Permission type</span></span> |   <span data-ttu-id="777e8-115">权限</span><span class="sxs-lookup"><span data-stu-id="777e8-115">Permission</span></span>  |   <span data-ttu-id="777e8-116">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="777e8-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="777e8-117">应用程序</span><span class="sxs-lookup"><span data-stu-id="777e8-117">Application</span></span> | <span data-ttu-id="777e8-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="777e8-118">Score.Read.All</span></span> | <span data-ttu-id="777e8-119">"读取威胁和漏洞管理分数"</span><span class="sxs-lookup"><span data-stu-id="777e8-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="777e8-120">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="777e8-120">Delegated (work or school account)</span></span> | <span data-ttu-id="777e8-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="777e8-121">Score.Read</span></span> | <span data-ttu-id="777e8-122">"读取威胁和漏洞管理分数"</span><span class="sxs-lookup"><span data-stu-id="777e8-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="777e8-123">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="777e8-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="777e8-124">请求标头</span><span class="sxs-lookup"><span data-stu-id="777e8-124">Request headers</span></span>

| <span data-ttu-id="777e8-125">名称</span><span class="sxs-lookup"><span data-stu-id="777e8-125">Name</span></span>        | <span data-ttu-id="777e8-126">类型</span><span class="sxs-lookup"><span data-stu-id="777e8-126">Type</span></span> | <span data-ttu-id="777e8-127">说明</span><span class="sxs-lookup"><span data-stu-id="777e8-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="777e8-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="777e8-128">Authorization</span></span> | <span data-ttu-id="777e8-129">String</span><span class="sxs-lookup"><span data-stu-id="777e8-129">String</span></span> | <span data-ttu-id="777e8-130">Bearer {token}。**必需**。</span><span class="sxs-lookup"><span data-stu-id="777e8-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="777e8-131">请求正文</span><span class="sxs-lookup"><span data-stu-id="777e8-131">Request body</span></span>

<span data-ttu-id="777e8-132">Empty</span><span class="sxs-lookup"><span data-stu-id="777e8-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="777e8-133">响应</span><span class="sxs-lookup"><span data-stu-id="777e8-133">Response</span></span>

<span data-ttu-id="777e8-134">如果成功，此方法返回 200 OK，响应正文中每个设备组数据的曝光评分列表。</span><span class="sxs-lookup"><span data-stu-id="777e8-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="777e8-135">示例</span><span class="sxs-lookup"><span data-stu-id="777e8-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="777e8-136">请求</span><span class="sxs-lookup"><span data-stu-id="777e8-136">Request</span></span>

<span data-ttu-id="777e8-137">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="777e8-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="777e8-138">响应</span><span class="sxs-lookup"><span data-stu-id="777e8-138">Response</span></span>

<span data-ttu-id="777e8-139">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="777e8-139">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="777e8-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="777e8-140">Related topics</span></span>

- [<span data-ttu-id="777e8-141">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="777e8-141">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="777e8-142">威胁&漏洞暴露分数</span><span class="sxs-lookup"><span data-stu-id="777e8-142">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
