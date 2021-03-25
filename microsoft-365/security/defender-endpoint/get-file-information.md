---
title: 获取文件信息 API
description: 了解如何使用获取文件信息 API 在 Microsoft Defender for Endpoint 中通过 Sha1、Sha256 或 MD5 标识符获取文件。
keywords: api， 图形 api， 受支持的 api， 获取， 文件， 信息， sha1， sha256， md5
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 181d808b465bfbf26eeff48a564e231b00a9a77f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166322"
---
# <a name="get-file-information-api"></a><span data-ttu-id="96bda-104">获取文件信息 API</span><span class="sxs-lookup"><span data-stu-id="96bda-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="96bda-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="96bda-105">**Applies to:**</span></span>
- [<span data-ttu-id="96bda-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="96bda-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="96bda-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96bda-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="96bda-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="96bda-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="96bda-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="96bda-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="96bda-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="96bda-110">API description</span></span>
<span data-ttu-id="96bda-111">按标识符 [Sha1](files.md) 或 Sha256 检索文件</span><span class="sxs-lookup"><span data-stu-id="96bda-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="96bda-112">限制</span><span class="sxs-lookup"><span data-stu-id="96bda-112">Limitations</span></span>
1. <span data-ttu-id="96bda-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="96bda-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="96bda-114">权限</span><span class="sxs-lookup"><span data-stu-id="96bda-114">Permissions</span></span>
<span data-ttu-id="96bda-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="96bda-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="96bda-116">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="96bda-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="96bda-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="96bda-117">Permission type</span></span> |   <span data-ttu-id="96bda-118">权限</span><span class="sxs-lookup"><span data-stu-id="96bda-118">Permission</span></span>  |   <span data-ttu-id="96bda-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="96bda-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="96bda-120">Application</span><span class="sxs-lookup"><span data-stu-id="96bda-120">Application</span></span> |   <span data-ttu-id="96bda-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="96bda-121">File.Read.All</span></span> | <span data-ttu-id="96bda-122">"读取所有文件配置文件"</span><span class="sxs-lookup"><span data-stu-id="96bda-122">'Read all file profiles'</span></span>
<span data-ttu-id="96bda-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="96bda-123">Delegated (work or school account)</span></span> | <span data-ttu-id="96bda-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="96bda-124">File.Read.All</span></span> |    <span data-ttu-id="96bda-125">"读取所有文件配置文件"</span><span class="sxs-lookup"><span data-stu-id="96bda-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="96bda-126">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="96bda-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="96bda-127">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="96bda-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="96bda-128">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="96bda-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="96bda-129">请求标头</span><span class="sxs-lookup"><span data-stu-id="96bda-129">Request headers</span></span>

<span data-ttu-id="96bda-130">名称</span><span class="sxs-lookup"><span data-stu-id="96bda-130">Name</span></span> | <span data-ttu-id="96bda-131">类型</span><span class="sxs-lookup"><span data-stu-id="96bda-131">Type</span></span> | <span data-ttu-id="96bda-132">说明</span><span class="sxs-lookup"><span data-stu-id="96bda-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="96bda-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="96bda-133">Authorization</span></span> | <span data-ttu-id="96bda-134">String</span><span class="sxs-lookup"><span data-stu-id="96bda-134">String</span></span> | <span data-ttu-id="96bda-135">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="96bda-135">Bearer {token}.</span></span> <span data-ttu-id="96bda-136">**必需**。</span><span class="sxs-lookup"><span data-stu-id="96bda-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="96bda-137">请求正文</span><span class="sxs-lookup"><span data-stu-id="96bda-137">Request body</span></span>
<span data-ttu-id="96bda-138">Empty</span><span class="sxs-lookup"><span data-stu-id="96bda-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="96bda-139">响应</span><span class="sxs-lookup"><span data-stu-id="96bda-139">Response</span></span>
<span data-ttu-id="96bda-140">如果成功且文件存在 - 200 正常，正文中为 [file](files.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="96bda-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="96bda-141">如果文件不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="96bda-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="96bda-142">示例</span><span class="sxs-lookup"><span data-stu-id="96bda-142">Example</span></span>

<span data-ttu-id="96bda-143">**请求**</span><span class="sxs-lookup"><span data-stu-id="96bda-143">**Request**</span></span>

<span data-ttu-id="96bda-144">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="96bda-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="96bda-145">**响应**</span><span class="sxs-lookup"><span data-stu-id="96bda-145">**Response**</span></span>

<span data-ttu-id="96bda-146">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="96bda-146">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files/$entity",
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
