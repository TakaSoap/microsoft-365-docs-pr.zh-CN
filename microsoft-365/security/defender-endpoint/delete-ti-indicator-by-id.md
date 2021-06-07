---
title: 删除指示器 API。
description: 了解如何使用删除指示器 API 在 Microsoft Defender for Endpoint 中按 ID 删除指示器实体。
keywords: api， 公共 api， 受支持的 api， 删除， ti 指示器， 实体， id
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: eaef6b25e2db72149a1a1128899d8a79a38a4c60
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771017"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="89994-104">删除指示器 API</span><span class="sxs-lookup"><span data-stu-id="89994-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="89994-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="89994-105">**Applies to:**</span></span>
- [<span data-ttu-id="89994-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="89994-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="89994-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89994-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="89994-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="89994-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="89994-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="89994-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="89994-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="89994-110">API description</span></span>
<span data-ttu-id="89994-111">按 ID [删除 Indicator](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="89994-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="89994-112">限制</span><span class="sxs-lookup"><span data-stu-id="89994-112">Limitations</span></span>
1. <span data-ttu-id="89994-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="89994-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="89994-114">权限</span><span class="sxs-lookup"><span data-stu-id="89994-114">Permissions</span></span>
<span data-ttu-id="89994-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="89994-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="89994-116">若要了解更多信息（包括如何选择权限），请参阅 [入门](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="89994-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="89994-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="89994-117">Permission type</span></span> |   <span data-ttu-id="89994-118">权限</span><span class="sxs-lookup"><span data-stu-id="89994-118">Permission</span></span>  |   <span data-ttu-id="89994-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="89994-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="89994-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="89994-120">Application</span></span> |   <span data-ttu-id="89994-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="89994-121">Ti.ReadWrite</span></span> |  <span data-ttu-id="89994-122">"读取和写入 TI 指示器"</span><span class="sxs-lookup"><span data-stu-id="89994-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="89994-123">应用程序</span><span class="sxs-lookup"><span data-stu-id="89994-123">Application</span></span> |   <span data-ttu-id="89994-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="89994-124">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="89994-125">"读取和写入指示器"</span><span class="sxs-lookup"><span data-stu-id="89994-125">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="89994-126">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="89994-126">HTTP request</span></span>
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="89994-127">请求标头</span><span class="sxs-lookup"><span data-stu-id="89994-127">Request headers</span></span>

<span data-ttu-id="89994-128">名称</span><span class="sxs-lookup"><span data-stu-id="89994-128">Name</span></span> | <span data-ttu-id="89994-129">类型</span><span class="sxs-lookup"><span data-stu-id="89994-129">Type</span></span> | <span data-ttu-id="89994-130">说明</span><span class="sxs-lookup"><span data-stu-id="89994-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="89994-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="89994-131">Authorization</span></span> | <span data-ttu-id="89994-132">String</span><span class="sxs-lookup"><span data-stu-id="89994-132">String</span></span> | <span data-ttu-id="89994-133">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="89994-133">Bearer {token}.</span></span> <span data-ttu-id="89994-134">**必需**。</span><span class="sxs-lookup"><span data-stu-id="89994-134">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="89994-135">请求正文</span><span class="sxs-lookup"><span data-stu-id="89994-135">Request body</span></span>
<span data-ttu-id="89994-136">Empty</span><span class="sxs-lookup"><span data-stu-id="89994-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="89994-137">响应</span><span class="sxs-lookup"><span data-stu-id="89994-137">Response</span></span>
<span data-ttu-id="89994-138">如果指示符存在并成功删除 - 204 正常，无内容。</span><span class="sxs-lookup"><span data-stu-id="89994-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>
<span data-ttu-id="89994-139">如果未找到具有指定 ID 的 Indicator - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="89994-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="89994-140">示例</span><span class="sxs-lookup"><span data-stu-id="89994-140">Example</span></span>

<span data-ttu-id="89994-141">**请求**</span><span class="sxs-lookup"><span data-stu-id="89994-141">**Request**</span></span>

<span data-ttu-id="89994-142">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="89994-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
