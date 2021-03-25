---
title: 列出软件版本分发
description: 检索组织的软件版本分布列表
keywords: api， 图形 api， 受支持的 api， 获取， 软件版本分发， mdatp tvm api
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
ms.openlocfilehash: 88f446ddd87768817099c1a206bab17aa8be5b7b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198573"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="7c704-104">列出软件版本分发</span><span class="sxs-lookup"><span data-stu-id="7c704-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7c704-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7c704-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="7c704-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="7c704-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7c704-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="7c704-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="7c704-108">检索组织的软件版本分布列表。</span><span class="sxs-lookup"><span data-stu-id="7c704-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="7c704-109">权限</span><span class="sxs-lookup"><span data-stu-id="7c704-109">Permissions</span></span>
<span data-ttu-id="7c704-110">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="7c704-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7c704-111">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="7c704-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="7c704-112">权限类型</span><span class="sxs-lookup"><span data-stu-id="7c704-112">Permission type</span></span> |   <span data-ttu-id="7c704-113">权限</span><span class="sxs-lookup"><span data-stu-id="7c704-113">Permission</span></span>  |   <span data-ttu-id="7c704-114">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="7c704-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7c704-115">应用程序</span><span class="sxs-lookup"><span data-stu-id="7c704-115">Application</span></span> | <span data-ttu-id="7c704-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="7c704-116">Software.Read.All</span></span> | <span data-ttu-id="7c704-117">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="7c704-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="7c704-118">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="7c704-118">Delegated (work or school account)</span></span> | <span data-ttu-id="7c704-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="7c704-119">Software.Read</span></span> | <span data-ttu-id="7c704-120">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="7c704-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="7c704-121">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="7c704-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="7c704-122">请求标头</span><span class="sxs-lookup"><span data-stu-id="7c704-122">Request headers</span></span>

| <span data-ttu-id="7c704-123">名称</span><span class="sxs-lookup"><span data-stu-id="7c704-123">Name</span></span>        | <span data-ttu-id="7c704-124">类型</span><span class="sxs-lookup"><span data-stu-id="7c704-124">Type</span></span> | <span data-ttu-id="7c704-125">说明</span><span class="sxs-lookup"><span data-stu-id="7c704-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="7c704-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="7c704-126">Authorization</span></span> | <span data-ttu-id="7c704-127">字符串</span><span class="sxs-lookup"><span data-stu-id="7c704-127">String</span></span> | <span data-ttu-id="7c704-128">Bearer {token}。**必需**。</span><span class="sxs-lookup"><span data-stu-id="7c704-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="7c704-129">请求正文</span><span class="sxs-lookup"><span data-stu-id="7c704-129">Request body</span></span>
<span data-ttu-id="7c704-130">Empty</span><span class="sxs-lookup"><span data-stu-id="7c704-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7c704-131">响应</span><span class="sxs-lookup"><span data-stu-id="7c704-131">Response</span></span>
<span data-ttu-id="7c704-132">如果成功，此方法返回 200 OK，并返回正文中的软件分发数据列表。</span><span class="sxs-lookup"><span data-stu-id="7c704-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="7c704-133">示例</span><span class="sxs-lookup"><span data-stu-id="7c704-133">Example</span></span>

<span data-ttu-id="7c704-134">**请求**</span><span class="sxs-lookup"><span data-stu-id="7c704-134">**Request**</span></span>

<span data-ttu-id="7c704-135">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="7c704-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="7c704-136">**响应**</span><span class="sxs-lookup"><span data-stu-id="7c704-136">**Response**</span></span>

<span data-ttu-id="7c704-137">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="7c704-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="7c704-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="7c704-138">Related topics</span></span>
- [<span data-ttu-id="7c704-139">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="7c704-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="7c704-140">威胁&漏洞软件清单</span><span class="sxs-lookup"><span data-stu-id="7c704-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
